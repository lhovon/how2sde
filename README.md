# How to softwar enginar

## Introduction

Welcome to the wonderful world of software engineering, the modern world's wizardry guild, where incantations and arcane knowledge form the day-to-day, mythical forefathers have legends written about them and the holy grail of AGI has been 10 years away for the past 100 years. This document will be an evolving list of resources/suggested learning topics that I deem important for becoming a software engineer, as well as complementary topics to be more well rounded. 

Software engineering is an enormous field with a wide range of niches and sub-fields, each with their relevant lore, coding practices, preferred languages, useful algorithms, math, etc. and it is not feasible for me to cover all of it, primarily due to lack of knowledge, hence this document will be more focused on learning the necessary to become a typical "backend" engineer, one of the most common types of engineer in entreprise and elligible to get that sweet big tech gig, or work for a variety of large institutions as well as a lot of startups and SMEs. Other types of software engineers might be "systems" engineers who work at a lower ["level of abstraction"](https://en.wikipedia.org/wiki/Abstraction_(computer_science)) (i.e. "closer to the metal") - they often do more "hardcore" work using more math, fancy data structures and algos, think deeply about performance - and frontend engineers who do web development, think about UX, accessibility and work closely with designers. Note that software engineering is a completetly separate function from entreprise IT which handles things like managing the company's internal network infrastructure, employee credentials, devices and system administration and are very concerned about security.

Backend engineers write server code that powers the backend of applications and deal with flows of data to and from clients. A backend engineer can call themselves "full-stack" should they also learn enough front-end to implement their features end-to-end. Backend engineers mostly write "services" (server programs) defining useful APIs (set of functions you can invoke on the services - the program's interface) to serve data to their clients. These services often work together with other services (often in a microservice architecture - as opposed to monolithic) implementing separation of concern, as well as interacting with data stores. Backend engineers generally write code in [type-safe](https://en.wikipedia.org/wiki/Type_safety), [compiled](https://en.wikipedia.org/wiki/Compiler) languages like Java (and other JVM based languages like Kotlin, Scala), C++, Rust, Go, etc. with a target platform (the runtime environment) of a [UNIX-based](https://en.wikipedia.org/wiki/Unix) server (technically if you're using a JVM language, the target platform is the JVM but what I mean is your code is going to run on a UNIX server). Engineers also write automated tests to ensure the code does what it is supposed to, and to catch potential regressions when that code evolves. They use version control systems and repositories to collaborate with other programmers and manage the evolution and storage of code.

The software that backend engineers develop has a goal of providing "business value", which refers to the reason why the softare is being written in the first place. To this end, the day to day life of an engineer consists of reading (documentation, other people's code, communications with clients and other developers, internal company documents), thinking (about the business domain, client's needs and how to technically provide them, tradeoffs, etc.), attending meetings (with clients, project managers, other devs) and writing (high and low-level design documents explaining and justifying what will be built, code (finally), code documentation). Devs today generally work following a subset of "Agile" methodology and do things such as subdividing work in tasks done in sprints of 2-3 weeks, having a daily standup meeting (scrum) where progress and blockers are mentioned, and dong retrospectives after each sprint where things that went well and others that should be improved are mentioned.

Backend engineers design their systems to be resilient to internal errors (called faults or exceptions - i.e. crashes), malformed input (either malicious or not), fluctuating demand (e.g. reddit hug of death), network issues and attackers (with proper authentication, access control mechanisms, safe data storage). Services can be thought to implement a contract with their clients, with the 2 main components being availability (is your service accessible and working) and latency (how fast can you respond to clients). Architectures will vary depending on the specific contract requirements (called SLAs - service level agreement) to ensure the services are able to meet expected demand. For example, big tech public facing services often strive to provide ["four nines's" of availability](https://en.wikipedia.org/wiki/High_availability), and the systems are designed with tons of redundancy, auto scaling capabilities, load balancing, caching, etc. to meet this goal. 

This brings us to the final aspect of backend development: infrastructure and operations. Backend engineers are often responsible for the deployment, operational monitoring and maintenance of their services. In some companies this function is split into separate teams and positions, often called "DevOps" and "SRE - Site Reliability Engineers". In the old days, this would probably be the responsibility of sysadmins. In the modern world of cloud providers, we have "infrastructure as code" where the system architecture is itself defined in code and is thus versionable and replicable, automated deployment pipelines that take care of building, packaging and copying your software to the appropriate places - as well as running your automated tests (unit and integration tests), cloud managed services (i.e. ["Serverless"](https://en.wikipedia.org/wiki/Serverless_computing), which is of course not actually server-less) that provide some of the above mentioned aspects in a configurable way.

To get a job in big tech, you will need to know how to passibly use 1 or 2 programming languages, know the basics of UNIX and be comfortable at a terminal (not evaluated at interview), have some general knowledge about networking, infrastrucure, system architecture (rarely evaluated at interview), know how to learn quickly (languages, new software - comes with experience - not evaluated but needed to keep the job lol) and be able to solve [leet code](https://leetcode.com/problemset/) easy and mediums (hards are rarely actually used, in fact the meme is that the solution to all interview questions is to use a hashmap). Leet code is often lamented as the software grind, with dev hopefuls spending tens of hours practicing (and neglecting everything else, such as proper hygiene), while at the same time being the least relevant skill to perform the actual job. It is unfortunately a fact of the industry, although some smaller companies omit them entirely, replace them with take-home assignments or more job-relevant tasks, however I think that for someone wanting to break into the field, it could kill two birds with one stone and serve as the basis to learn about data structures and algorithms (skipping the job-irrelevant stuff you learn in a degree) while also working towards getting a job.

A list of topics with overview and relevant resources follows. Don't worry if you don't understand all the terms, it's meant to have you be exposed to the lingo and imbibe with all the lore, you'll be able to come back and udnerstand more things as you progress. I'll also put some wiki links, I recommend to quickly read the first couple of paragraphs for extra context. The topics should generally be accessible in any order. The best way to learn this stuff is to use it. Some resources will contain exercises, others are interactive, and others can have project suggestions. I highly recommend to work on a few personnal projects to explore various technologies, since they will invariably lead to learning new things and I'll try to suggest a few. I also recommend going over all the topics before starting any subsection to get an overview.



## Industry sources of information

- [Hacker News](https://news.ycombinator.com/) a reddit-style message board, hosted by the legendary ycombinator startup accelerator. It is software startup focused due to its origins, but is a general geek forum with a diversity of specialist posters on a variety of technical topics from software, physics, math, biology, finance and more. Use it to keep up with what's happening in the industry, as anything big in the software world will end up on its front page. I'll post a few links to hackernews discussions on something and want you to click through to the actual content in question, with optionally reading the associated discussion for debates and extra context.
- [levels.fyi](https://www.levels.fyi/) - the most accurate source of dev salaries by company, position, location.
- [blind](https://www.teamblind.com/) - overpaid devs complaining, can be a good source of leaked info on company internal pay bands, etc. requires a company email to signup.




## General concepts that will apply everywhere: 

### Abstractions, APIs and implementations. 

Everything you interact with in software is an abstraction offering an API. An abstraction needs a concrete implementation - the code that actually defines the functionality. 
For example, reading and writing files involves using the file API offered by the OS and implemented by the file system which is an abstraction over storage devices. When writing object-oriented code, you can define abstract classes and interfaces which define the set of methods offered by all implementations of these interfaces and classes.


### Clients and Servers

Similarly to abstractions and APIs, almost everything in software can be viewed through the lens of a server and a client. The terms are commonly used to refer to web servers and clients but they are more of a conceptual view of anything returning (serving) data (of any kind) to something that has requested it (client). E.g. a program calling using the file API to open a file is a client and the file-system is the server. Client-server is often used in opposition to peer-to-peer systems, but really each peer is simply able to act as both a server and a client depending on the situation. 




# Topics

# UNIX - OS internals and the Shell

## Overview

An OS virtualizes and provides abstractions of the computer's physical resources, most notably the CPU, the memory and the storage, but also network interfaces and peripherals. OSes are conceptually split in 2 layers: the kernel - which is the core of the OS and interacts directly with the physical resources, and "user-space" which is a set of higher level abstractions that non-kernel programs (userspace programs) interact with. The layer between the two is called the system call (syscall) interface - the kernel's API are the system calls. 

We're mostly concerned with UNIX-based operating systems, which more or less follow the [POSIX API](https://en.wikipedia.org/wiki/POSIX), a standardized set of APIs for operating systems. The term UNIX is historical and used loosely to refer to all [Unix-like](https://en.wikipedia.org/wiki/Unix-like) systems, including [Linux](https://en.wikipedia.org/wiki/Linux), which is an open-source kernel invented by legendary programmer and [flamer](https://news.ycombinator.com/item?id=39191899) Linus Torvalds. Most UNIX-like OSes use the linux kernel (e.g. Ubuntu, Fedora, Redhat) so you can use the terms interchangeably.

When you log into your OS with your mouse and keyboard, you are actually running a window-manager graphical user interace (GUI) program that is calling a ton of system calls to allow you and the other programs you launch to do their jobs. Another classic way of interacting with an OS is through a [shell](https://en.wikipedia.org/wiki/Shell_(computing)), which is a command-line interface (also called a [REPL](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop), a terminal). The shell is itself a program: an interpretor for a scripting language, which allows a user to enter commands, launch other programs and write scripts to automate the shell. The shell interpretor is the one calling the kernel API behind the scenes, it merely offers an abstraction to the user. The common shell for unix systems is [bash](https://en.wikipedia.org/wiki/Bash_(Unix_shell)) and the others are mostly compatible, mostly becasue using a shell well involves calling other standard programs like find, grep, curl.

Most UNIX-like OSes are written in C, making it the de-facto OS programming language. It is also infamous for being 'unsafe' and allowing a lot of 'footguns' leading to crashes and a huge amounts of security vulnerabilities. Nowadays, evangelical Rust users (the rust-aceans) push their language as a memory-safe alternative, because the Rust language has facilities that avoid a large class of bugs present in memory unsafe languages. [Memory safety](https://en.wikipedia.org/wiki/Memory_safety) refers to having to manually manage (allocate/deallocate) memory, which is notoriously hard to do at a large scale and handling pointers to memory locations directly (the `char*`). Pointers can be complicated to reason about especially because you often have pointers to pointers (e.g. `char**`) and have mostly been hidden (abstracted away) in more modern programming languages. But it's intersting to know that higher-level languages like Java and Python are often themselves written in C behind the scenes (see [CPython](https://github.com/python/cpython) or [this post](https://stackoverflow.com/questions/1220914/in-which-language-are-the-java-compiler-and-jvm-written)).


Additional:
- Try to understand what GNU is and how it relates to Linux, UNIX, etc.
- Readup on the UNIX philosophy: https://en.wikipedia.org/wiki/Unix_philosophy
- (Lore) the original hacker definition: http://www.catb.org/~esr/faqs/hacker-howto.html
- (Lore) The cathedral and the bazaar: http://www.catb.org/~esr/writings/cathedral-bazaar/cathedral-bazaar/


## Get a Linux system

No getting around it, the best way to learn is to practice. 

On windows we now have [WSL](https://learn.microsoft.com/en-us/windows/wsl/install) which is straight up linux running on windows, install it (by default comes with Ubuntu which is just fine), open a cmd, powershell or terminal (W11) and type `wsl` as you will be in a bash shell. Get the [VSCode extension for WSL](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-wsl) to be able to code as if on a graphical linux system. 


An alternative is to get a linux VM (or dual boot). Get [VMware player](https://customerconnect.vmware.com/en/downloads/details?downloadGroup=WKST-PLAYER-1751&productId=1377&rPId=117008) or [Virtualbox](https://www.virtualbox.org/wiki/Downloads) then download an [Ubuntu](https://ubuntu.com/download/desktop) and boot the VM using the ISO file (virtual disk image).


On mac, which is closer to unix than windows, you can use the built-in terminal, but I don't know how to get a C environment running (maybe gcc is available out of the box?), else use VirtualBox.



## Shell 101

First, you'll need to learn how to use a terminal. Do (at least) the [Command Line tutorial](https://linuxjourney.com/lesson/the-shell) followed by the [Text-Fu tutorial](https://linuxjourney.com/lesson/stdout-standard-out-redirect), [Advanced Text-Fu](https://linuxjourney.com/lesson/regular-expressions-regex), [Processes] (https://linuxjourney.com/lesson/monitor-processes-ps-command), [Permissions](https://linuxjourney.com/lesson/file-permissions) - for this one you just need to know how to make a script you wrote executable (`chmod 755`). 

After this you should know how to move around, create, read, edit, delete files, know what stdin/stdout/stderr are, how to pipe together different programs (let me know if not covered), what `.`, `..`, `/`, `~`, `|`, `grep` are and more. Realize that `echo`, `ls`, `cp`, `grep`, `vim`, `cat`, etc. (though not `cd`) are [all programs](https://stackoverflow.com/questions/11528267/how-do-i-read-the-source-code-of-shell-commands) (generally written in C, but could be anything) that you are invoking from bash (they should be in `/usr/bin`). They are part of the POSIX standard and you can see their source code online here: https://github.com/coreutils/coreutils/tree/master/src. You should also know what what the man pages are and how to get help about commands from the temrinal directly.


Additional:
- Readup on the standard directory structure: https://www.theochem.ru.nl/~pwormer/Knowino/knowino.org/wiki/Unix_directory_structure.html
- Fun fact: the equivalent of deleting system32 for linux is `sudo rm -rf /`.


## Operating Systems 101 - OSTEP Textbook
The [Operating Systems: Three Easy Pieces](https://pages.cs.wisc.edu/~remzi/OSTEP/) textbook is a great free online-accessible resource to learn about OS fundamentals with some coding examples that I encourage you to follow along.

Required reading:
- [Processes](https://pages.cs.wisc.edu/~remzi/OSTEP/cpu-intro.pdf)
- [Virtual Memory](https://pages.cs.wisc.edu/~remzi/OSTEP/vm-intro.pdf)
- [The file system](https://pages.cs.wisc.edu/~remzi/OSTEP/file-implementation.pdf)
- [Concurrency](https://pages.cs.wisc.edu/~remzi/OSTEP/threads-intro.pdf)

The rest is highly recommended but obviously it's a whole textbook so it would take a long time, I have not read it fully.

To do the coding examples, e.g. [https://pages.cs.wisc.edu/~remzi/OSTEP/cpu-api.pdf](https://pages.cs.wisc.edu/~remzi/OSTEP/cpu-api.pdf) see the [Setup a C dev environment](#setup-a-c-dev-environment) section. C is syntactically very similar to Java, Javascript and a lot of other languages (because it is their ancestor).


In parallel, you can follow the [Process monitoring tutorial](https://linuxjourney.com/lesson/tracking-processes-top) to peek inside what's happening in the OS. I think the book shows off some of these tools in the examples as well.


Additional:
- The Unix API is more than just system calls or Posix (2018): https://news.ycombinator.com/item?id=32032588
- Stack vs Heap: https://stackoverflow.com/questions/79923/what-and-where-are-the-stack-and-heap
- Data vs Code: https://wiki.c2.com/?DataAndCodeAreTheSameThing

### Setup a C dev environment
Ubuntu already comes with `gcc` so no need to install, you can skip ahead to writing code.
To be able to code in C in WSL, you'll have to install `gcc` (the GNU C Compiler - one of many C compilers), this is done by running the following commands in bash:

```bash
# Refreshes the packages
sudo apt update
# Installs gcc
# apt is a package manager for Ubuntu which allows you to install software packages and their dependencies
sudo apt install gcc
```

You can now write C code in a file and compile the program using `gcc`. 
The first program is traditionally one that prints "Hello World" and exits.

Create a new file called `helloworld.c`, put the following code inside:
```c
#include <stdio.h>
int main() {
    printf("Hello World");
}
```
Compile it with gcc and run it:
```bash
# This will produce a file called a.out by default
gcc helloworld.c
# Run a.out - the dot and slash are important as they tell the shell to run a.out present in the current directory
./a.out
```


## Shell 102

Learn to use `ssh` - the secure shell - to remotely connect to systems. In practice you will often do this. For example, you connect to the production server from you laptop, or you connect to a crazy datacenter cluster from your laptop to run a computationally intensive job. ssh will drop you into an interactive shell.

To practice this, I suggest playing [these capture the flag games](https://overthewire.org/wargames/). This will have a dual purpose to practice your shell-fu as well as learn about security topics, should you want to specialize into that after. The world of security is extremely cool and you can do security a both an extremely low level (reverse engineering binaries, finding and exploiting security vulnerabilities in code) where you'll learn to read ans speak hex fluently, or at a very high institutional policy level, and anything in between.

Additional:
- Another shell tutorial and intro to computer forensics: https://primer.picoctf.org/



# Coding


## Languages to learn

I would recommend learning Java and Python. They are consistently at the top of the [most used and requested programming languages](https://spectrum.ieee.org/the-top-programming-languages-2023) and are not going anywhere. They provide a good diversity of languages as Java is statically typed, compiled, object-oriented language while Python is interpreted and dynamically typed (and also object-oriented). Java is widely used in entreprise and big tech as it is highly portable (because it targets the JVM which is supported on many target systems) and everybody kinda knows it. Python is widely used for scripting tasks, web development backend, data science and ML and is known to be more user firendly though the dynamic typing makes it harder to work on large codebases.

Nowadays, you have other JVM-languages which target the JVM, and can use it's wide ecosystem but are more ergonomic or implement different programming styles - see Scala and Kotlin. 

You can probably get away with learning just Python nowadays, but most jobs will want a Java equivalent (it could be C# which is microsoft's version of Java - targets the .NET runtime (JVM))

JVM vs JDK vs JRE: https://stackoverflow.com/questions/11547458/what-is-the-difference-between-jvm-jdk-jre-openjdk

What is the JVM?
What is an interpreter?

Languages are interpreted or compiled (simplification - look into JIT compilation). Langugages need to be implemented (you could say there are abstractions as well I guess!!)- for an interpreted langugage the implementation is an interpreter, for a compiled langugage it is a compiler. These implementations can be written in other languages, or the langugages themselves (weird but true).  


Concurrency - running things in parrallel 
- python multiprocessing
- threads API java




Recursion?


LANGUAGES   
- Compiled vs Interpreted
- Static vs dynamic typing
- type systems why its useful
- variable scope - private, package private
- packages, imports, build systems, dependency management
- libraries
- frameworks - maybe Spring? Django


WRITING CODE    
 - text editors and IDEs with syntax highlighting 
 - code style
 - linters and formatters


## System Design and Architecture

This is hard to get experience in as most personal projects don't need anywhere near the kind of complexity that is used in big entreprise. 

Understand system architecture of common apps
--> bytedance channel

data stores - file system, databases (relational or "NoSQL")

containers and vms - docker, kubernetes

Additional:
- The tail at scale: https://www.barroso.org/publications/TheTailAtScale.pdf


### Internet

https://linuxjourney.com/lesson/what-is-dns



- Setup this repo, run the thing and implement something/fix a bug.

- built a scraper and store stuff in a database then generate reports

- learn file and network APIs

- what is an API

- learn OS fundamentals: virtualization of CPU, memory and storage

- learn git 


coding basics:
- variables
- control flow
- exception handling


UNIX Command line

SQL basics

Scaling basics

Type system

Data structures/Algorthims 
- lists
- maps
- graphs
- stack, queue

coding projects
- CRUD app with backend API
- 
