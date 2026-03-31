# An Introduction to Multi Agent Systems
**Michael Wooldridge**

---

# Chapter 1: Introduction

## Five important and continuing trends in the history of computing:

### 1. Ubiquity
The decreasing cost of computing allows processing power to be embedded in many new devices and places, so computing power and a form of intelligence will become available everywhere.

### 2. Interconnection and distribution
The computers are networked into large distributed systems and distributed and concurrent systems are essentially the norm in commercial and industrial computing.

The growth of ubiquitous and interconnected computing creates major challenges for software developers. What techniques might be needed to deal with systems composed of 10¹⁰ processors? Current development methods are inadequate for extremely large systems, leading to the idea of global computing with potentially billions of processors.

The trend toward interconnection and distribution is mainstream of computer science:  
- Developing tools and mechanisms that allow us to build distributed systems with greater ease and reliability.  
- Interact with another computer system that represent interests of another:  
  - Ability to cooperate  
  - Ability to reach agreements  

### 3. Intelligence
The capability of automating and delegating more complex tasks to computers.

### 4. Delegation
In many cases, such as fly-by-wire aircraft, computers are trusted to control critical operations instead of humans, so we give control to computer systems.

Increasing delegation and intelligence require computer systems that can act on behalf of humans. This in turn implies two capabilities:  
- The ability of systems to operate independently, without our direct intervention.  
- These systems must represent users’ best interests when interacting with other people or systems.

### 5. Human-orientation
Computing has gradually shifted from machine-oriented programming to human-oriented concepts and metaphors. Interfaces and programming languages evolved from machine code and switches to graphical interfaces and high-level abstractions like objects, making computers easier for humans to use and understand.

---

Together, these trends have led to the emergence of a new field in computer science: **Multiple Agent Systems**.

## Micro/Macro distinction (distinction between this items):

- **Agent (computer system) Design**  
  How to build Agents that are capable of independent and autonomous action on behalf of its user in order to carry out the tasks that we delegate to them (Satisfy its design objectives).

- **Society Design (intelligence in individuals)**  
  How to build agents that are capable of interacting (ability to communicate, cooperate, coordinate, negotiate with each other agents) typically by exchanging messages through some computer network infrastructure, in order to carry out the tasks that we delegate to them, particularly when the other agents cannot be assumed to share the same interests/goals.

The two problems are not orthogonal - for example, in order to build a society of agents that work together effectively, it may help if we give members of the society models of the other agents in it.

---

## Researchers in multiagent systems may be predominantly concerned with engineering systems:

- How can cooperation emerge in societies of self-interested agents (computational, information processing entities)?  
- What sorts of common languages can agents use to communicate their beliefs and aspirations (strong desire), both to people and to other agents?  
- How can self-interested agents recognize when their beliefs, goals, or actions conflict, and how can they reach agreements with one another on matters of self-interest, without resorting to conflict?  
- How can autonomous agents coordinate their activities so as to cooperatively achieve goals?

---

## Some motivation for what the agents community does (long-term future visions – ideas):

1. **A space probe approaching Saturn experiences a system failure and loses contact with Earth.**  
   Instead of being lost, it diagnoses the problem, isolates the fault, and re-orients itself to reconnect with its ground crew (act autonomously)  
   - The probe needs to recognize that a fault has occurred  
   - Figure out what needs to be done  
   - How to do it  
   - Do the actions it has chosen  
   - Monitor what happens in order to ensure that all goes well  

2. **NASA's Deep Space 1 (DS1)**  
   Launched from Cape Canaveral on 24 October 1998, DS1 was the first space probe to have an autonomous, agent-based control system and was capable of making many important decisions itself.  
   - More robust, particularly against sudden unexpected problems.  
   - Very desirable side effect of reducing overall mission costs.  

3. **A key air-traffic control system at the main airport suddenly fails**  
   Fortunately, autonomous air-traffic control systems in nearby airports recognize the failure of their peer, and cooperate to track and deal with all affected flights. The potentially disastrous situation passes without incident.  
   - The ability of systems to take the initiative when circumstances dictate.  
   - The ability of agents to cooperate to solve problems that are beyond the capabilities of any individual agents.  

4. **The Distributed Vehicle Monitoring Testbed (DVMT) project**  
   Simulates a network of vehicle monitoring agents, where each agent is a problem solver that analyses sensed data in order to identify, locate, and track vehicles moving through space. Each agent is typically associated with a sensor, which has only a partial view of the entire space. The agents must therefore cooperate in order to track the progress of vehicles through the entire sensed space.  

5. **Air-traffic control systems (safety critical systems)**  
   Have been a standard application of agent research since the work of Cammarata and colleagues in the early 1980s (Cammarata et al., 1983), a multiagent air-traffic control application is the OASIS system implemented for use at Sydney airport in Australia (Ljunberg and Lucas, 1992).  

6. **Specifying your requirements to your personal digital assistant (PDA)**  
   It converses with a number of different Web sites, which sell services such as flights, hotel rooms, and hire cars. After hard negotiation on your behalf with a range of sites, your PDA presents you with a package holiday.  
   - How do you state your preferences to your agent?  
   - How can your agent compare different deals from different vendors?  
   - What algorithms can your agent use to negotiate with other agents (so as to ensure you are not 'ripped off')?  

7. **European Commission public tenders**  
   Every year, the European Commission puts out thousands of contracts to public tender. The bureaucracy associated with managing this process has an enormous cost. The ability to automate the tendering and negotiation process would save enormous sums of money (taxpayers' money!). So the ability to automate the process of software agents reaching mutually acceptable agreements on matters of common interest is not just an abstract concern - it may affect our lives (the amount of tax we pay) in a significant way.

---

## The different ways that people think about the 'multiagent systems project':

### 1. Agents as a paradigm for software engineering
It is now widely recognized that interaction is probably the most important single characteristic of complex software. Software architectures that contain many dynamically interacting components, each with their own thread of control and engaging in complex, coordinated protocols, are typically orders of magnitude more complex to engineer correctly and efficiently. It turns out that many (if not most) real-world applications have precisely these characteristics. As a consequence, a major research topic in computer science over at least the past two decades has been the development of tools and techniques to model, understand, and implement systems in which interaction is the norm. Indeed, many researchers now believe computation itself will be understood chiefly as a process of interaction. Just as we can understand many systems as being composed of essentially passive objects, which have a state and upon which we can perform operations, so we can understand many others as being made up of interacting, semi-autonomous agents. This recognition has led to the growth of interest in agents as a new paradigm for software engineering.

### 2. Agents as a tool for understanding human societies
In Isaac Asimov's popular Foundation science fiction trilogy, a character called Hari Seldon has invented a discipline of 'psychohistory' which is a combination of psychology, history, and economics, which allows Seldon to predict the behaviour of human societies hundreds of years into the future. In particular, psychohistory enables Seldon to predict the imminent collapse of society. Psychohistory is an interesting plot device, but it is firmly in the realms of science fiction. There are far too many variables and unknown quantities in human societies to do anything except predict very broad trends a short term into the future, and even then the process is notoriously prone to embarrassing errors. This situation is not likely to change in the foreseeable future. However, multiagent systems do provide an interesting and novel new tool for simulating societies, which may help shed some light on various kinds of social processes.  

- A nice example of this work is the EOS project (Doran and Palmer, 1995). The aim of the EOS project was to use the tools of multiagent systems research to gain an insight into how and why social complexity emerged in a Palaeolithic culture in southern France at the time of the last ice age. The goal of the project was not to directly simulate these ancient societies, but to try to understand some of the factors involved in the emergence of social complexity in such societies.

---

## Objections of MASs:

### Distributed/concurrent systems and MASs?
- The concurrent systems community have for several decades been investigating the properties of systems that contain multiple interacting components, and have been developing theories, programming languages, and tools for explaining, modelling, and developing such systems.  
- By definition, MAS is subclass of concurrent systems  
- Use the wisdom of experienced persons in Distributed/concurrent systems when implementing MASs to be aware of issues like:  
  - Mutual exclusion over shared resources: only one process can use a resource at a time  
  - Deadlock: a situation where processes are unable to proceed because each is waiting for another to release a resource creating a standstill  
  - Live-lock: multiple processes repeatedly change their states in response to each other  

- Differences:  
  - Agents in MASs should synchronize and coordinate their activity at runtime and they are not hardwired at design time like concurrent systems.  
  - The economic encounters occur between computing elements in MAS, which are self-interested entities (individual or group that act primarily to maximize their own advantages) and the agents are primarily concerned with their own welfare. In classical distributed/concurrent systems, computing elements are implicitly assumed to share a common goal (making the overall system function correctly).  

- MAS concerns:  
  - Reach agreement through negotiation on matters of common interest  
  - Dynamically coordinate their activities with agents whose goals and motives are unknown  

### AI and MASs
- It has become increasingly common practice to define the endeavor of AI itself as one of constructing an intelligent agent (concerned with the components of intelligence - the ability to learn, plan, understand images, and so on).  
- Agent field concerned with entities that integrate these components in order to provide machine that is capable of making independent decisions.  
- When we build an agent to carry out a task in some environment, most of we do is computer science and software engineering and we will very likely draw upon AI techniques of some sort.  
- One important thing is Social aspects of agency, is ability to communicate, cooperate, and reach agreement with peers (not ability to learn, plan and solve problems – intelligent behavior)  

### Economics/Game theory
- Mathematical theory that studies interaction among self-interested agents (economic entities in the real world)  
- Predominant theoretical tool in use for the analysis of multi-agent systems (such as negotiation)  
- The solution concepts like Nash equilibrium developed without view to computation. They are descriptive concepts, telling us the properties of appropriate, optimal solution without telling us how to compute a solution. The problem of computing solution is computationally very hard (NP-complete)  
- MASs allow us to bring the tools of computer science (computational complexity theory) to bear on them.  
- Important tool in MAS  
- Questioning assumptions of game theory to reach conclusion  
- Is rational agent valid or useful for understanding human or artificial agent society?  

### Social science
- Primarily concerned with understanding the behavior of human societies  
- Computational MAS provide experimental tools to model and understand human societies  
- You can see how a particular function works in human societies and try to build the MAS in the same way  
- Social science represents a rich repository of concepts for understanding and building MASs
