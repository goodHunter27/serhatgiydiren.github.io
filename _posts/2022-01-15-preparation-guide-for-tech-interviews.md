---
title: Preparation Guide for Tech Interviews - Ace Your Google & Facebook (Meta) Interviews
published: false
---

# Resume Preparation

* [Create Your Resume for Google: Tips and Advice](https://youtu.be/BYUy1yvjHxE){:target="_blank"}

# General Interview Tips

**Explain** - We want to understand how you think, so explain your thought process and decision making throughout the interview. Remember we're not only evaluating your technical ability, but also how you solve problems. Explicitly state and check assumptions with your interviewer to ensure they are reasonable. 

**Clarify** - Many questions will be deliberately open-ended to provide insight into what categories and information you value within the technological puzzle. We're looking to see how you engage with the problem and your primary method for solving it. Be sure to talk through your thought process and feel free to ask specific questions if you need clarification. 

**Improve** - Think about ways to improve the solution you present. It's worthwhile to think out loud about your initial thoughts to a question. In many cases, your first answer may need some refining and further explanation. If necessary, start with the brute force solution and improve on it - just let the interviewer know that's what you're doing and why. 

**Practice** - You won't have access to an IDE or compiler during the interview so practice writing code on paper or a whiteboard. Be sure to test your code and ensure it's easily readable without bugs. Don't stress about small syntactical errors like which substring to use for a given method (e.g. start, end or start, length) — just pick one and let your interviewer know. 

* [How We Hire at Google](https://youtu.be/zhUgaKb0s5A){:target="_blank"}
* [Interview tips from Google Software Engineers](https://youtu.be/XOtrOSatBoY){:target="_blank"}


# Leadership Interviews

Beyond the technical preparation, you'll also be asked questions on leading teams and projects. People management interviews dive into how you would support and grow your teams, covering: 

**Leadership** - Be prepared to show examples of how you've resolved complex situations. How did you ensure you dealt with team challenges in a balanced way? You may also be asked some more hypothetical questions, so be prepared to talk through how you would influence, solve problems and drive improvements. How would you take ownership and stay creative while moving quickly? 

**Working with people & teams** - Think about how you develop and retain team members. How would you address a skills gap or personality conflict? How would you ensure your team is diverse and inclusive? How could you spot burn out? How would you organize day to day work activities? How would you convince a team to adopt a new technology?  

**Googleyness** - We also want to make sure this is a place you'll thrive, so we'll be looking for signs around your comfort with ambiguity, your bias to action and your collaborative nature. Be prepared to talk about how you would support a team to help them navigate tough challenges and changes. Think about how to effectively lead in a non-hierarchical team environment and what your personal leadership style is.  

**Applying the right framework** - What's your personal Project Management philosophy? How do you apply your framework to projects you manage? Be prepared to explain and justify your methodology. Be able to discuss and compare different project management methodologies and their relative merits (e.g. tradeoffs between flexibility and process in an agile environment). Why did you use a particular approach?  

**Navigating complexity and ambiguity** - How do you deal with ambiguous situations and problems? How do you handle projects without defined end dates? How would you prioritize multiple projects of varying complexity? How do you balance process versus execution? What are signals that too much or too little process is in place? Can you give examples of projects where you demonstrated leadership even if you weren't a formal manager?  

**Delivering results** - Give examples of projects where you were the end-to-end owner. How do you evaluate the success or failure of a project? What are some strategies for handling competing visions on how to execute a project? Be prepared to discuss how to use data effectively to move critical decisions forward and how to measure impact.  


* [Prepare for your Google Interview: Leadership](https://youtu.be/2Cr3-et4xkI){:target="_blank"}


# Coding & Algorithm Interviews

**Coding** - You should know at least one programming language really well, preferably C++, Java, Python, Go, or C. You will be expected to know APIs, Object Oriented Design and Programming, how to test your code, as well as come up with corner cases and edge cases for code. Note that we focus on conceptual understanding rather than memorization.  

**Algorithms** - Approach the problem with both bottom-up and top-down algorithms. You will be expected to know the complexity of an algorithm and how you can improve / change it. Algorithms that are used to solve Google problems include sorting (plus searching and binary search), divide-and-conquer, dynamic programming / memoization, greediness, recursion or algorithms linked to a specific data structure. Know Big-O notations (e.g. run time) and be ready to discuss complex algorithms like Dijkstra and A*. We recommend discussing or outlining the algorithm you have in mind before writing code.  

**Sorting** - Be familiar with common sorting functions and on what kind of input data they're efficient or ineffcient. Think about efficiency means in terms of runtime and space used. For example, in exceptional cases insertion-sort or radix-sort are much better than the generic QuickSort / MergeSort / HeapSort answers.  

**Data structures** - You should study up on as many data structures as possible. Data structures most frequently used are arrays, linked lists, stacks, queues, hash-sets, hash-maps, hash-tables, dictionary, trees and binary trees, heaps and graphs. You should know the data structure inside out, and what algorithms tend to go along with each data structure.  

**Mathematics** - Some interviewers ask basic discrete math questions. This is more prevalent at Google than at other companies because counting problems, probability problems and other Discrete Math 101 situations surround us. Spend some time before the interview refreshing your memory on (or teaching yourself) the essentials of elementary probability theory and combinatorics. You should be familiar with n-choose-k problems and their ilk.  

**Graphs** - Consider if a problem can be applied with graph algorithms like distance, search, connectivity, cycle-detection, etc. There are three basic ways to represent a graph in memory (objects and pointers, matrix, and adjacency list) — familiarize yourself with each representation and its pros and cons. You should know the basic graph traversal algorithms, breadth-first search and depth-first search. Know their computational complexity, their tradeoffs and how to implement them in real code.  

**Recursion** - Many coding problems involve thinking recursively and potentially coding a recursive solution. Use recursion to find more elegant solutions to problems that can be solved iteratively.  

* [Prepare for Your Google Interview: Coding](https://youtu.be/6ZZX9iIgFoo){:target="_blank"}
* [How to: Work at Google — Example Coding/Engineering Interview](https://youtu.be/XKu_SEDAykw){:target="_blank"}

# System Design Interviews

## What is a system design question and why is it important?  

System design questions are used to assess a candidate's ability to combine knowledge, theory, experience and judgement toward solving a real-world engineering problem. Sample topics include feature sets, interfaces, class hierarchies, constraints, simplicity, robustness and tradeoffs. The interview will assess your deep understanding of how the internet works and familiarity with the various pieces (routers, domain name servers, load balancers, firewalls, etc.).  

## Interview Tips and Expectations:  

1.  The system design question will ask you to take an abstract question in a formerly unseen problem and present a high level framework to solve the presented problem. In doing so, follow these steps:
     *   Gather key requirements 
     *   Identify key design elements 
     *   Identify tradeoffs of different decisions 
     *   Dive deep into a specific sub-problem AND/OR demonstrate what process to use to arrive at a solution 

2.  Identify the major components of an overall system design and deeply describe at least two of them. Suggest which technologies and systems should be used to solve a relatively common problem (i.e. relational database, document-based database, etc.), and if relevant, share a story about a time you have solved a problem using these technologies.  

3.  When defining a system, include as many non-functional requirements as possible. For example: performance, latency, legal, privacy, maintainability, capacity, security, geographic, and cross-DC consideration.  

4.  Develop a framework you can use to answer most questions.  

5.  Approach the problem with an open mind: Be mindful that your familiarity (if any) with the problem may make you take shortcuts (even verbal ones when explaining your approach); the interviewer may not share the same context as you. If there is a more succinct approach, feel free to explain to the interviewer the route you’re taking and the context behind why.  

6.  Problem Solve: The interviewers are looking for problem solving and approach as much as they are assessing your solution. So, ask clarifying questions about the problem, express ideas verbally, and think out loud. Constantly challenge your own design. Be prepared to justify every decision you make. Practice going through problems with a friend.  

7.  Listen: Design questions are typically open-ended and the problem may be ambiguous. If the interviewer gives a hint or asks a question while you are solving the problem, listen intently and do not ignore. They are most likely trying to guide you or looking for a particular awareness.  

## Role-related design questions  

Due to the wide variety of projects we offer at Google, it is important our design questions are relevant to both your background and the role you will be exploring. Be sure to discuss with your recruiter the role you're pursuing and which system design question is best suited to assess your skills. Depending on your area of expertise, one of the following types of design questions will be asked:

### Distributed System Design 

System design is a general category which means "big enough systems that you have to operate on a high level of abstraction to get the basic architecture down." A distributed system question is related to problems of coordination between autonomous systems while system design can include problems constrained to a single execution. Distributed systems questions focus on cross-task coordination, communication, synchronization, and failure modes. System design questions are more weighted toward managing the complexity of large bodies of software. You can find some of the Google research around distributed systems here.

**Example Distributed System Design:** Design a distributed unique ID service.

### Low Level System Design

### Machine Learning Design 

### Mobile Application System Design 

### Front End UI Web Design 

* [Prepare for Your Google Interview: Systems Design](https://youtu.be/Gg318hR5JY0){:target="_blank"}
