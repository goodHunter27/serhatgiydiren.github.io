---
title: Google Hashcode 2022 Practice Problem (One Pizza) Solution & Scores
published: true
---

### High Scores
* A : 2
* B : 5
* C : 5
* D : 1805
* E : 2079

```cpp
#include <bits/stdc++.h>

using namespace std;
using namespace chrono;

#ifdef LOCAL
#include "debug.h"
#else
#define D(...) 404
#endif

#define EPS 1e-9

class timer:high_resolution_clock
{
 const time_point start_time;
 
 public:
  timer(): start_time(now()) {}
  rep elapsed_time() const { return duration_cast<milliseconds>(now()-start_time).count();} 
};

mt19937_64 rng(steady_clock::now().time_since_epoch().count());
uniform_int_distribution distr(1,123456789);

int c;
int count_ing=0;
unordered_map < string , int > ing;
vector < bool > sel;
vector < bool > keep;
unordered_set < int > out;
int score=0;
int restart=1;
int score_best=0;
unordered_set < int > out_best;

struct customer
{
  unordered_set < int > good;
  unordered_set < int > bad;
};

struct ingredient
{
  string name;
  unordered_set < int > pos;
  unordered_set < int > neg;
};

vector < ingredient > ings;

vector < customer > custs;

bool is_happy(const customer &e)
{
  for(auto f:e.good) if (out.find(f)==out.end()) return false;
  for(auto f:e.bad) if (out.find(f)!=out.end()) return false;
  return true;
}

void calc_score()
{
  score=0;
  for(auto e:custs) score+=is_happy(e);
}

bool is_accepted(const int &diff, const double &temperature)
{
 if (diff>=0) return true;
 if (exp(double(diff)/temperature)-0.999999>EPS) return true;
 return false;
}

void type_0(const double &temperature)
{
  int idx=rng()%count_ing;
  if (sel[idx])
  {
    if (!keep[idx])
    {
      int diff=0;
      for(auto e:ings[idx].pos) if (is_happy(custs[e])) diff--;
      out.erase(idx);
      for(auto e:ings[idx].neg) if (is_happy(custs[e])) diff++;
      if (is_accepted(diff,temperature))
      {
        score+=diff;
        sel[idx]=false;
      }
      else
      {
        out.insert(idx);
      }
    }
  }
}

void type_1(const double &temperature)
{
  int idx=rng()%count_ing;
  if (!sel[idx])
  {
    int diff=0;
    for(auto e:ings[idx].neg) if (is_happy(custs[e])) diff--;
    out.insert(idx);
    for(auto e:ings[idx].pos) if (is_happy(custs[e])) diff++;
    if (is_accepted(diff,temperature))
    {
      score+=diff;
      sel[idx]=true;
    }
    else
    {
      out.erase(idx);
    }
  }
}

void optimize()
{
  while(restart--)
  {
    double temperature=1000000;
    while(temperature>EPS)
    {
      auto score_begin=score;
      int typ=rand()%2;
      if (typ==0) type_0(temperature);
      else if (typ==1) type_1(temperature);
      temperature-=0.001;
      if (score>score_best)
      {
        score_best=score;
        out_best=out;
      }
      if (score>score_begin)
      {
        D(typ,temperature, score, score_best);
      }
    }
  }
}

void load_output()
{
}

void add_item(const string &ingredient_name, const int &cust_id, bool is_pos=true)
{
  if (ing.find(ingredient_name)==ing.end())
  {
    ing[ingredient_name]=count_ing++;
    ingredient temp;
    temp.name=ingredient_name;
    ings.push_back(temp);
  }
  if (is_pos) ings[ing[ingredient_name]].pos.insert(cust_id);
  else ings[ing[ingredient_name]].neg.insert(cust_id);
}

void read_input()
{
  int a,b;
  string item;
  cin >> c;
  custs.resize(c);
  for(int i=0;i<c;i++)
  {
    cin >> a;
    for(int j=0;j<a;j++)
    {
      cin >> item;
      add_item(item,i);
      custs[i].good.insert(ing[item]);
    }

    cin >> b;
    for(int j=0;j<b;j++)
    {
      cin >> item;
      add_item(item,i,false);
      custs[i].bad.insert(ing[item]);
    }
  }
  //for(auto e:ings) D(e.name,e.pos,e.neg);
}

void prep()
{
  for(int i=0;i<count_ing;i++) out.insert(i);
  sel.resize(count_ing, true);
  keep.resize(count_ing, false);
  for(int i=0;i<count_ing;i++)
  {
    bool ok=true;
    for(auto f:custs)
    {
      if (!ok) break;
      if (f.bad.find(i)!=f.bad.end()) { ok=false; break; }
    }
    if (ok) keep[i]=true;
  }
}

void print_output()
{
  cout << out_best.size();
  for(auto e:out_best) cout << " " << ings[e].name;
}

void init_score()
{
  //D(out);
  calc_score();
  D("init score = ", score);
}

void final_check()
{
  //D(out);
  D("success_ratio : ",score_best,c,100.0*score_best/c);
}

void solve()
{
  read_input();
  prep();
  load_output();
  init_score();
  optimize();
  final_check();
  print_output();
}

void fast_io()
{
  ios::sync_with_stdio(false);
  srand(time(NULL));
  cin.tie(0);
  cout.tie(0);
  cout << fixed << setprecision(15);
  cerr << fixed << setprecision(15);
}

int main()
{
  solve();
}
```
