# How to softwar enginar

## Introduction

Welcome to the wonderful world of software engineering, the modern world's wizardry guild, where incantations and arcane knowledge form the day-to-day, mythical forefathers have legends written about them and the holy grail of AGI has been 10 years away for the past 100 years. This document will be an evolving list of resources/suggested learning topics that I deem important for becoming a software engineer, as well as complementary topics to be more well rounded. 

Software engineering is an enormous field with a wide range of niches and sub-fields, each with their relevant lore, coding practices, preferred languages, useful algorithms, math, etc. and it is not feasible for me to cover all of it, primarily due to lack of knowledge, hence this document will be more focused on learning the necessary to become a typical "backend" engineer, one of the most common types of engineer in entreprise and elligible to get that sweet big tech gig, or work for a variety of large institutions as well as a lot of startups and SMEs. Other types of software engineers might be "systems" developers who work at a lower ["level of abstraction"](https://en.wikipedia.org/wiki/Abstraction_(computer_science)) (i.e. "closer to the metal") - they often do more "hardcore" work using more math, fancy data structures and algos, think deeply about performance - frontend engineers who do web development, think about UX, accessibility and work closely with designers and mobile engineers who build applications for mobile devices, writing "native" Android or iOS applications, or cross platform applications using technologies like React Native. Note that software engineering is a completetly separate function from entreprise IT which handles things like managing the company's internal network infrastructure, employee credentials, devices and system administration and are very concerned about security.

Backend engineers write server code that powers the backend of applications and deal with flows of data to and from clients. A backend engineer can call themselves "full-stack" should they also learn enough front-end to implement their features end-to-end. Backend engineers mostly write "services" (server programs) defining useful APIs (set of functions you can invoke on the services - the program's interface) to serve data to their clients. These services often work together with other services (often in a microservice architecture - as opposed to monolithic) implementing separation of concern, as well as interacting with data stores. Backend engineers generally write code in [type-safe](https://en.wikipedia.org/wiki/Type_safety), [compiled](https://en.wikipedia.org/wiki/Compiler) languages like Java (and other JVM based languages like Kotlin, Scala), C++, Rust, Go, etc. with a target platform (the runtime environment) of a [UNIX-based](https://en.wikipedia.org/wiki/Unix) server (technically if you're using a JVM language, the target platform is the JVM but what I mean is your code is going to run on a UNIX server). Engineers also write automated tests to ensure the code does what it is supposed to, and to catch potential regressions when that code evolves. They use version control systems and repositories to collaborate with other programmers and manage the evolution and storage of code.

The software that backend engineers develop has a goal of providing "business value", which refers to the reason why the softare is being written in the first place. To this end, the day to day life of an engineer consists of reading (documentation, other people's code, communications with clients and other developers, internal company documents), thinking (about the business domain, client's needs and how to technically provide them, tradeoffs, etc.), attending meetings (with clients, project managers, other devs) and writing (high and low-level design documents explaining and justifying what will be built, code (finally), code documentation). Devs today generally work following a subset of "Agile" methodology and do things such as subdividing work in tasks done in sprints of 2-3 weeks, having a daily standup meeting (scrum) where progress and blockers are mentioned, and doing retrospectives at the end of the sprint where things that went well are noted and action-items are taken to improve things that could have gone better. 

Backend engineers design their systems to be resilient to internal errors (called faults or exceptions - i.e. crashes), malformed input (either malicious or not), fluctuating demand (e.g. reddit hug of death), network issues and attackers (with proper authentication, access control mechanisms, safe data storage). Services can be thought to implement a contract with their clients, with the two main components being availability (is your service accessible and working) and latency (how fast can it respond to clients). Architectures will vary depending on the specific contract requirements (called SLAs - service level agreement) to ensure services are able to meet the expected demand. For example, big tech public facing services often strive to provide ["four nines's" of availability](https://en.wikipedia.org/wiki/High_availability), and the systems are designed with tons of redundancy, auto scaling capabilities, load balancing, caching, etc. to meet this goal. 

This brings us to the final aspect of backend development: infrastructure and operations. Backend engineers are often responsible for the deployment, operational monitoring and maintenance of their services. In some companies this function is split into separate teams and positions, often called "DevOps" and "SRE - Site Reliability Engineers". In the old days, this would probably be the responsibility of sysadmins. In the modern world of cloud providers, we have "infrastructure as code" where the system architecture is itself defined in code and is thus versionable and replicable, automated deployment pipelines that take care of building, packaging and copying your software to the appropriate places - as well as running your automated tests (unit and integration tests), cloud managed services (i.e. ["Serverless"](https://en.wikipedia.org/wiki/Serverless_computing), which is of course not actually server-less) that provide some of the above mentioned aspects in a configurable way.

To get a job in big tech, you will need to know how to passibly use 1 or 2 programming languages, know the basics of UNIX and be comfortable at a terminal (sometimes evaluated at interview), have some general knowledge about networking, infrastrucure, system architecture (rarely evaluated at interview), know how to learn quickly (languages, new software - comes with experience - not evaluated but needed to keep the job lol) and be able to solve [leet code](https://leetcode.com/problemset/) easy and mediums (hards are rarely used, in fact the meme is that the solution to all interview questions is to use a hashmap). Leet code is often lamented as the software grind, with dev hopefuls spending tens of hours practicing (and neglecting everything else, such as proper hygiene), while at the same time being the least relevant skill to perform the actual job. It is unfortunately a fact of the industry, although some smaller companies omit them entirely, replace them with take-home assignments or more job-relevant tasks. However I think that for someone wanting to break into the field, it could kill two birds with one stone and serve as the basis to learn about data structures and algorithms (skipping the job-irrelevant stuff you learn in a degree) while also working towards getting a job.

A list of topics with overview and relevant resources follows. Don't worry if you don't understand all the terms, it's meant to have you be exposed to the lingo and imbibe with all the lore, you'll be able to come back and udnerstand more things as you progress. I'll also put some wiki links, I recommend to quickly read the first couple of paragraphs for extra context. The best way to learn this stuff is to use it and dive deep as you go along, staying curious. Some resources will contain exercises, others are interactive, and others can have project suggestions. You should go through the guide in order.

The hardest thing about self-studying is keeping the motivation for the extended duration needed. Given a few hours a week and depnding on how familiar you are with the concepts evoked, it might take a few months to a year (or more) to fully cover the material. In person bootcamps are another alternative to break into the field and are a great way to keep yourself motivated, some even try to land you a job at the end. Define you goals and keep them in mind as you progress.



## Industry sources of information

- [Hacker News](https://news.ycombinator.com/) a reddit-style message board, hosted by the legendary ycombinator startup accelerator. It is software startup focused due to its origins, but is a general geek forum with a diversity of specialist posters on a variety of technical topics from software, physics, math, biology, finance and more. Use it to keep up with what's happening in the industry, as anything big in the software world will end up on its front page. Also hosts monthly 'who's hiring' and 'who wants to be hired' threads. I'll post a few links to hackernews discussions on something and want you to click through to the actual content in question, optionally reading the associated discussion for debates and extra context.
- [levels.fyi](https://www.levels.fyi/) - the most accurate source of dev salaries by company, position, location.
- [blind](https://www.teamblind.com/) - overpaid devs complaining, can be a good source of leaked info on company internal pay bands, etc. requires a company email to signup.




## General concepts that will apply everywhere: 

### Abstractions, APIs and implementations. 

Everything you interact with in software is an [abstraction](https://en.wikipedia.org/wiki/Abstraction_(computer_science)) offering an [API](https://en.wikipedia.org/wiki/API). An abstraction needs a concrete implementation - the code that actually enables the functionality. 
For example, reading and writing files involves using the file API offered by the OS and implemented by the file system which is an abstraction over storage devices. When writing object-oriented code, you can define abstract classes and interfaces which define the set of methods offered by all implementations of these interfaces and classes.


### Clients and Servers

Similarly to abstractions and APIs, almost everything in software can be viewed through the lens of a server and a client. The terms are commonly used to refer to web servers and clients but they are more of a conceptual view of anything returning (serving) data (of any kind) to something that has requested it (client). E.g. a program calling using the file API to open a file is a client and the file-system is the server. Client-server is often used in opposition to peer-to-peer systems, but really each peer is simply able to act as both a server and a client depending on the situation. 


# Topics

# UNIX - OS internals and the Shell

## Overview

An OS virtualizes and provides abstractions of the computer's physical resources, most notably the CPU, the memory and the storage, but also network interfaces and peripherals. OSes are conceptually split in 2 layers: the kernel the core of the OS that interfaces directly with the physical resources, and ["user-space"](https://en.wikipedia.org/wiki/User_space_and_kernel_space) which is where all non-kernel prgorams execute. The layer between the two is the system call (syscall) interface - the kernel's API are the system calls. 

We're mostly concerned with UNIX-based operating systems, which more or less follow the [POSIX API](https://en.wikipedia.org/wiki/POSIX), a standardized set of APIs for operating systems. The term UNIX is historical and used loosely to refer to all [Unix-like](https://en.wikipedia.org/wiki/Unix-like) systems, including [Linux](https://en.wikipedia.org/wiki/Linux), which is an open-source kernel invented by legendary programmer and [flamer](https://news.ycombinator.com/item?id=39191899) Linus Torvalds. Most UNIX-like OSes use the linux kernel (e.g. Ubuntu, Fedora, Redhat) so you can use the terms interchangeably.

When you log into your OS with your mouse and keyboard, you are actually running a window-manager graphical user interace (GUI) program that is making a ton of system calls to allow you and the other programs you launch to do their jobs. Another classic way of interacting with an OS is through a [shell](https://en.wikipedia.org/wiki/Shell_(computing)), which is a command-line interface (also called a [REPL](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop), a terminal). The shell is itself a program: an interpreter for a scripting language, which allows a user to enter commands, launch other programs and write scripts to automate the shell. The shell interpretor is the one calling the kernel API behind the scenes, it merely offers an abstraction to the user. The common shell for unix systems is [bash](https://en.wikipedia.org/wiki/Bash_(Unix_shell)).

Most UNIX-like OSes are written in C, making it the de-facto OS programming language. It is also infamous for being 'unsafe' and allowing a lot of 'footguns' leading to crashes and a huge amounts of security vulnerabilities. Nowadays, evangelical Rust users (rustaceans) push their language as a memory-safe alternative, because the Rust language has facilities that avoid a large class of bugs present in memory unsafe languages. [Memory safety](https://en.wikipedia.org/wiki/Memory_safety) refers to having to manually manage (allocate/deallocate) memory, which is notoriously hard to do at a large scale and handling pointers to memory locations directly (e.g. `char*`). Pointers can be complicated to reason about especially because you often have pointers to pointers (e.g. `char**`) and have thus been hidden (abstracted away) in more modern programming languages. But it's interesting to know that higher-level languages are often themselves written in C (see [CPython](https://github.com/python/cpython) or [this post](https://stackoverflow.com/questions/1220914/in-which-language-are-the-java-compiler-and-jvm-written)).


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

First, you'll need to learn how to use a terminal. Do (at least) the [Command Line tutorial](https://linuxjourney.com/lesson/the-shell) followed by the [Text-Fu tutorial](https://linuxjourney.com/lesson/stdout-standard-out-redirect), [Advanced Text-Fu](https://linuxjourney.com/lesson/regular-expressions-regex), [Processes] (https://linuxjourney.com/lesson/monitor-processes-ps-command), [Permissions](https://linuxjourney.com/lesson/file-permissions). 

After this you should know how to move around, create, read, edit, delete files, know what stdin/stdout/stderr are, how to pipe together different programs, what `.`, `..`, `/`, `~`, `|`, `grep` are and more. Realize that `echo`, `ls`, `cp`, `grep`, `vim`, `cat`, etc. (though not `cd`) are [all programs](https://stackoverflow.com/questions/11528267/how-do-i-read-the-source-code-of-shell-commands) (generally written in C, but could be anything) that you are invoking from bash (they should be in `/usr/bin`). They are part of the POSIX standard and you can see their source code online here: https://github.com/coreutils/coreutils/tree/master/src. You should also know what what the man pages are and how to get help about commands from the temrinal directly.

Additional:
- Readup on the standard UNIX directory structure: https://www.theochem.ru.nl/~pwormer/Knowino/knowino.org/wiki/Unix_directory_structure.html
- Fun fact: the equivalent of deleting system32 for linux is `sudo rm -rf /`.


## Operating Systems 101 - OSTEP Textbook
The [Operating Systems: Three Easy Pieces](https://pages.cs.wisc.edu/~remzi/OSTEP/) textbook is a great free online-accessible resource to learn about OS fundamentals with some coding examples that I encourage you to follow along.

Required reading:
- [Processes](https://pages.cs.wisc.edu/~remzi/OSTEP/cpu-intro.pdf)
- [Virtual Memory](https://pages.cs.wisc.edu/~remzi/OSTEP/vm-intro.pdf)
- [The file system](https://pages.cs.wisc.edu/~remzi/OSTEP/file-implementation.pdf)
- [Concurrency](https://pages.cs.wisc.edu/~remzi/OSTEP/threads-intro.pdf)

The rest is highly recommended but obviously it's a whole textbook so it would take a long time, I have not read it fully.

To do the coding examples, e.g. [https://pages.cs.wisc.edu/~remzi/OSTEP/cpu-api.pdf](https://pages.cs.wisc.edu/~remzi/OSTEP/cpu-api.pdf) see the [Setup a C dev environment](#setup-a-c-dev-environment) section. C is the ancestor to lots of other languages and is thus syntactically similar. 


In parallel, you can follow the [Process monitoring tutorial](https://linuxjourney.com/lesson/tracking-processes-top) to peek inside what's happening in the OS. I think the book shows off some of these tools in the examples as well.


Additional:
- The Unix API is more than just system calls or Posix (2018): https://news.ycombinator.com/item?id=32032588
- Stack vs Heap: https://stackoverflow.com/questions/79923/what-and-where-are-the-stack-and-heap
- Data vs Code: https://wiki.c2.com/?DataAndCodeAreTheSameThing
- https://news.ycombinator.com/item?id=39657991
- Skim through linux kernel source code online, try to see if you can understand what's going on: https://elixir.bootlin.com/linux/v5.6/source/fs/read_write.c#L446. Here it's code for the Virtual File System (VFS) layer - see if you can intuit what that means. https://tldp.org/LDP/khg/HyperNews/get/fs/vfstour.html


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

Learn to use `ssh` - the secure shell - to remotely connect to systems. In practice you will often do this. For example, you connect to the production server from you dev laptop, or you connect to a crazy datacenter cluster to run a computationally intensive job. ssh will drop you into an interactive shell on the target machine.

To practice this, I suggest playing [these capture the flag games](https://overthewire.org/wargames/). This will have a dual purpose to practice your shell-fu as well as learn about security topics, should you want to specialize into that after. The world of security is extremely cool and you can do security a both an extremely low level (reverse engineering binaries, finding and exploiting security vulnerabilities in code) where you'll learn to read ans speak hex fluently, or at a very high institutional policy level, and anything in between.

Additional:
- Another shell tutorial and intro to computer forensics: https://primer.picoctf.org/



# Programming Languages

## Langugages 101

At the lowest level, CPUs understand electrical signals which are the [physical representation](https://www.quora.com/What-actually-converts-machine-code-or-binary-code-to-an-electric-signal) of binary digits (high/low voltage for 1/0), specific patterns of parallel binary digits invokes circuitry defining operations like loading data (also electrical signals representing bits representing data). The set of operations the CPU can execute defines its [instruction set architecture (ISA)](https://en.wikipedia.org/wiki/Instruction_set_architecture) (hilariously referred to as abstract and the CPU as the implementation in the linked wiki article), and a listing of binary instructions is called [machine code](https://en.wikipedia.org/wiki/Machine_code). Common ISAs today are [x86](https://en.wikipedia.org/wiki/X86) and [ARM64](https://en.wikipedia.org/wiki/AArch64). [Assembly language](https://en.wikipedia.org/wiki/Assembly_language), is a (slightly more human readable) representation of the machine code, where instruction codes (opcodes) are replaced by keywords (e.g. load, store, jump) and the possibilty of using symbolic labels. A lot of early coding was done in assembly, and today still, if you specialize in reverse engineering malware, cracking software or working on core (to the operation of the modern world) software like [FFmpeg](https://twitter.com/FFmpeg/status/1762632400255742353) you might spend a lot of time reading and/or writing assembly. 

"High-level" (it's all relative) programming languages like [Fortran](https://en.wikipedia.org/wiki/Fortran) and C were then invented throughout the 20th century to facilitate computer programming. [Programming languages](https://en.wikipedia.org/wiki/Programming_language) are also abstract constructs defining a syntax and semantics to write computer programs, hence languages also need implementations, which will take care of converting it to machine code so the CPU can execute it. Langugage implementations are [compilers or interpreters](https://stackoverflow.com/questions/6889747/is-python-interpreted-or-compiled-or-both) and sometimes a runtime environment (like the JVM, or .NET runtime).

Languages come in different flavors such as [imperative, declarative](https://en.wikipedia.org/wiki/Programming_paradigm), [functional](https://en.wikipedia.org/wiki/Functional_programming) (apparently a subcategory of declarative programming, TIL). Another axis of comparison is if a language is statically typed (the implementation checks BEFORE running, so at compile time, that all functions are called on the appropriate data types avoiding a lot of type errors at runtime) or [dynamically typed](https://stackoverflow.com/questions/1517582/what-is-the-difference-between-statically-typed-and-dynamically-typed-languages) (e.g. Python where nothing will stop you from running a completely non-sensical program like `a = "main" / 56` and will instead throw a type error when running).

To learn more about programming languages, you should study compilers and interpreters. One of the practice projects below is actually following the [Crafting Interpreters book](https://www.craftinginterpreters.com/).


## Languages to learn

Which language to learn depends mostly on the specific type of work you are doing as there tends to be favorites in different subfields. The favorite is mostly historical fact and maintained by the presence of a large ecosystem of libraries making the use of another langugage less convenient.

I would recommend learning Java and Python. They are consistently at the top of the [most used and requested programming languages](https://spectrum.ieee.org/the-top-programming-languages-2023) and are not going anywhere. They provide a good diversity of languages as Java is statically typed, compiled, object-oriented language while Python is interpreted and dynamically typed (and also object-oriented). Java is widely used in entreprise and big tech as it is highly portable (because it targets the JVM which is supported on many target systems) and its relatively standardized C-like syntax means all programmers can read and write it. Python is widely used for scripting tasks, web development backend, data science and ML and is known to be more user firendly though the dynamic typing makes it harder to work on large codebases.


## Java 

Java, the [ubiquitous](https://skeptics.stackexchange.com/questions/9870/do-3-billion-devices-run-java) langugage that developers [love to hate](https://www.reddit.com/r/programming/comments/9dzpu/ask_reddit_why_does_everyone_hate_java/) is a staple of entreprise software development for various reasons including its [good performance](https://stackoverflow.blog/2021/02/22/choosing-java-instead-of-c-for-low-latency-systems/), [static type checking](https://en.wikipedia.org/wiki/Type_system#:~:text=Static%20type%20checking%20is%20the,properties%20for%20all%20possible%20inputs.), portability and large ecosystem. I found this [short video](https://www.youtube.com/watch?v=Ibjm2KHfymo) to give a nice high-level overview.

Something to know about Java is that it compiles to Java "bytecode" which runs on the Java Virtual Machine (JVM) instead of the OS itself (like a C program would). This is the source of its portability as you don't need to recompile Java bytecode between different platforms (e.g. Windows vs Linux) as long as both can run the JVM. Note that the JVM itself has to be compiled for each platform though. There are other languages which compile to the JVM, like [Kotlin](https://kotlinlang.org/docs/getting-started.html) and Scala, which offer more "flexible" languages compared to Java's rigid verbose writing style. These other JVM language are able to interoperate with the Java ecosystem since they share the same platform. Note that Java (and mostly Kotlin nowadays) are the languages of Android development should that interest you.

There are many versions of Java, old ones are confusingly referred to as e.g. Java 8, but are really version 1.8 when you download the JDK. We're up to version 21 now.

A similar programming language is C# by Microsoft, it's also object-oriented, statically typed, also targets a virtual machine (the .NET runtime) which also has supports other languages like F#. It's used a lot in Europe apparently, as well as to code in Unity and it is well loved by it's users.

Need to know:
- Inheritance and Composition - the bread and butter of OOP
- What is Garbage Collection?
- Dependency Injection (conceptually)

### Setting up a Java dev environment

The best IDE for Java is [Jetbrains IntelliJ IDEA](https://www.jetbrains.com/idea/download/). If you still have access to a university email, you can get the Ultimate version for free ,else get the Community edition. Then you will need a Java SDK (Software Development Kit), you most likely already have one on your machine, otherwise I believe you can download some directly from IntelliJ. If not, you can find some links [here](https://www.jetbrains.com/help/idea/sdk.html#jdk). The JDK comes with the JRE (Java Runtime Environment - which is the JVM as far as I understand it) and a Java compiler (`javac`).

You can code Java on Windows with no problem - see the portability difference between needing a separate OS to setup a C coding environement.


### Git

Git is a version control system (VCS), if you don't already have it on your machine download it here (git bash for windows): https://git-scm.com/downloads
You don't need to understand it much more than `git clone`, `git checkout -b new-branch`, `git branch -a`, `git add .`, `git restore .`, `git commit -m "my commit message`, `git push`, `git pull`, `git pull --rebase`, what `.gitignore` is.

Create a new repository on github and follow instructions to be able to push your code! (You will need to setup ssh keys or a github token to be able to push code nowadays I believe - an opportunity to learn about `ssh-keygen`!)


### Learning Java

At a very high-level, [this video](https://www.youtube.com/watch?v=TE3LyYW-AHQ) lays an overall map of the land for entreprise Java, that can be referred to as you progress. It'd be nice to at least google each of the items in this map (though not now). The database related stuff will also be covered in another section of this guide.

To start, go through the [official tutorials](https://docs.oracle.com/javase/tutorial/). Do the whole "Trails Covering the Basics" section. Yes it will be a bit boring but it will give you the basics of programming (in Java but also generally in imperative OO languages) as well as refer to OS concepts like file APIs and concurrency, and cover some of the most important data structures, like lists (arrays) and maps. 


Then, you should find some simple project tutorials to follow along. All found starting [here](https://www.reddit.com/r/learnprogramming/wiki/faq/#wiki_where_can_i_find_practice_exercises_and_project_ideas.3F).

- Writing a [simple HTTP server](https://javarevisited.blogspot.com/2015/06/how-to-create-http-server-in-java-serversocket-example.html) - bonus of learning about networking APIs and the internet.
- Writing [a simple web server using the Spring MVC framework](https://spring.io/guides/gs/serving-web-content). Spring is a widely used web application framework. [MVC (Model-View-Controller)](https://developer.mozilla.org/en-US/docs/Glossary/MVC) is a common web app design pattern (code organization method) where Models define the data received and sent to clients, Views define how the Models are shown to clients (in web, the views are web page [templates](https://www.baeldung.com/spring-template-engines) - which are rendered with the Model's values to give the final result shown in the browser) and Controllers define the various endpoints, handle requests and implement the business logic.
- Now [interact with a MySQL database](https://spring.io/guides/gs/accessing-data-mysql). Instead of writing raw SQL queries, web app developers will often use ORMs (Object Relational Mappers) which are libraries directly linking java objects to database records. So you only operate on objects and the changes get persisted (saved) to the DB. ORMs are frequently criticized for leading to suboptimal SQL however, and having ORMs is not an excuse to not learn SQL - it is extremely useful to know.
- MORE SPRING - learn what a REST API is: https://spring.io/guides/gs/rest-service. It is just an API using HTTP verbs like GET, POST, UPDATE - often used in to communicate with both clients and between services. 
- Learn how to use the debugger - set a breakpoint and step through a program: https://www.youtube.com/watch?v=IeUZZoZE3sU

Adavanced Projects:
- Read and follow along the [Crafting Interpreters book](https://www.craftinginterpreters.com/contents.html). You will learn a ton about data structures and programming languages this way, and it's much more interesting than Spring webapps. HIGHLY RECOMMEND - taking a compilers course if often a defining moment in a CS degree where a lot of stuff clicks.

Other projects:
- [These projects](https://aosabook.org/en/index.html) also seem interesting. They are implemented in Python so the exercise would be to translate the code to Java. It might make you appreciate the differences between the two.

Additional:

- JVM vs JDK vs JRE: https://stackoverflow.com/questions/11547458/what-is-the-difference-between-jvm-jdk-jre-openjdk
- Deep dive on Java build systems (Maven and Gradle): https://news.ycombinator.com/item?id=38875318
- l33t hacks in java: https://questdb.io/blog/1brc-merykittys-magic-swar/ - java is actually very performant and can be used for low level devlopment like C++ or C.

## Python

Python is similar to Java because it is also object-oriented but is generally considered more of a 'scripting' language due to its dynamic typing and more interpreted nature (it's actually also (Just-in-Time) compiled to bytecode and runs in a VM but that is a detail). Coming from Java, you might appreciate its ergonomics and its relative ease of writing, in a styler sometimes closer to english. It definitely has its quirks however, e.g. the program entrypoint being just as cryptic as Java (`if __name__ == '__main__':`), or that indentation has meaning.


### Setup a python dev environment.

Easy, you should already have python installed. I like to use VSCode for python development, you could also use Jetbrains PyCharm but I find it clunky. `pip` is the default package manager and you will often use it to install librairies. I would suggest installing the [Black formatter](https://marketplace.visualstudio.com/items?itemName=ms-python.black-formatter) plugin and enable format on save, the default settings are good and will ensur eyour code has a consistent style.

It is recommended to setup a [virtual environment](https://docs.python.org/3/library/venv.html) for each python project. This isolates its packages and avoid version conflicts that could occur if we always installed packages globally (think 2 projects using different, incompatible versions of the same package). You can code python on windows.

```bash
# Create a virtual env - here you are invoking the venv module of python
# You might have to install it separately on linux, follow instructions.
# The virtual environment gets created in a .venv folder in the curent directory
python -m venv .venv

# Then activate the virtual env
# On windows
.venv\Scripts\activate
# On linux
source .venv/bin/activate

```
Now, when running pip, packages will be installed under the virtual environment directory.


### Python 101

Unlike Java, python ships with an interpreter (the `python` program itself) which means you can code in a much more interactive way, directly at the terminal. 

Of course, the correct starting point are the [official tutorials](https://docs.python.org/3/tutorial/index.html) which you can skim through (or engage deeply with, you'll get something out of it for sure but it could be tedious depending on your learning style). It will be interesting to map python's data structures to Java's equivalents (i.e. what is dict in Java?), get a sense for the tradeoffs of static vs dynamic typing. 

### Python projects

- I love python for any small personal projects. I think it's well suited to write web scrapers which could be a good opportunity to get down and dirty with web technologies. Get to know the `requests` and `beautifulsoup` librairies: https://realpython.com/beautiful-soup-web-scraper-python/ output the data to a [csv file](https://docs.python.org/3/library/csv.html).
- Add a database to your scraper to store your data: you can start with [SQLite](https://docs.python.org/3/library/sqlite3.html) which stores the DB in a simple file, move on to [PostgreSQL](https://www.psycopg.org/docs/) which is a more involved RDBMS (Relational DB Management System)
- parallelize your scraper using the `multiprocessing` library: https://www.digitalocean.com/community/tutorials/python-multiprocessing-example. The python interpreter is single-threaded so multi processing is the way to do real parallelization in Python (vs multiple threads in Java).
- Do web development with django: https://docs.djangoproject.com/en/5.0/intro/tutorial01/
- Play around with ML models: https://huggingface.co/docs/transformers/tasks/object_detection


Find tons of other project ideas: https://github.com/florinpop17/app-ideas?tab=readme-ov-file

Additional:
- (deep dive) explore concurrency in python general: https://realpython.com/python-concurrency/.



# Leetcode - Data Structures and Algorithms

As mentionned, Leetcode is the interview prep grind! Can't get around it, you might actually enjoy it. If you discover you do, you could start joining [competitive programming](https://en.wikipedia.org/wiki/Competitive_programming) groups and flex your skills (there's also [code golf](https://code.golf/) competitions but that's a different concept). Now that you've coded a bit in Java and Python, learned a few data structures like lists and maps (and perhaps what operations they optimize), it's time to dig deeper into these, as well as the algorithms used to implement data structure functionality. 

This is where it gets a little mathematical, with the use of [big-O notation](https://web.mit.edu/16.070/www/lecture/big_o.pdf) (asymptotic performance) and general mathematical thinking to breakdown and solve problems.

I would suggest going through the [Blind 75](https://leetcode.com/discuss/general-discussion/460599/blind-75-leetcode-questions) list of the necessary problems to prepare for interview. Ideally, you do one a day and spend some time researching the solution, come back to it later, try to solve it again. There is a ton of content, notably from [Neetcode](https://www.youtube.com/c/neetcode), and [video courses from MiT](https://www.youtube.com/watch?v=ZA-tUyM_y7s&list=PLUl4u3cNGP63EdVPNLG3ToM6LaEUuStEY), Stanford, etc. to really get a deep understanding, proofs, etc. which could be worthwhile as a deep dive.

Need to know decently:
- Recursion/Divide and Conquer
- How to use maps to speed up problems
- Binary search
- Sorting algorithms
- What a Tree is, what a heap is
- Graph traversal algorithms - BFS, DFS
- shortest path - djisktra's algorithm
- Dynamic programming (similar to recursion)

Good to know:
- Tries - for language related tasks
- datastrucutres for geographic systems


# Databases

If you've done the above sections, you've already used SQL and setup your own databases, but you might not know what indices, primary and foreign keys, join operations are, so we'll deep dive into SQL here.
SQL is required to know as a dev, not necessarily well as it gets complicated bu enough to get around, even in the NoSQL world of today (we'll get into this below), SQL is stil lth emain interface to DBs and non-relational DBs offer a SQL interface since it is a great way to write data queries. 

## SQL

Interactive tutorials: 
- https://pgexercises.com/questions/basic/
- https://sqlbolt.com/lesson/select_queries_introduction

- basic syntax, what a database is, what a table is
- What an index is, what is it's purpose, what is the tradeoff we're doing: https://news.ycombinator.com/item?id=30594233
- What is a primary key, what is a foreign key, what are joins?: https://news.ycombinator.com/item?id=32731916
- What is normalized data? Why do we want to denormalize sometimes?
- How to scale a database server? What is partitioning?
- ACID
- CAP Theorem

## NoSQL

In opposition to traditional SQL databases, NoSQL databases have emerged recently as more scalable replacements for "internet"-scale businesses. NoSQL is a large category and contains many completely different types of databases.

Understand what an object store is (Amazon S3), what a Key-Value store is (dynamodb)
Cassandra DB https://cassandra.apache.org/_/cassandra-basics.html



# System Design and Architecture, Infrastructure

This is hard to get practical experience in as most personal projects don't need anywhere near the kind of complexity that is used in big entreprise. Therefore, I've personally mostly learned it by watching videos and reading big companies' engineering blogs.

Understand system architecture of common apps
- Bytebytego youtube channel: https://www.youtube.com/watch?v=M4lR_Va97cQ&list=PLCRMIe5FDPseVvwzRiCQBmNOVUIZSSkP8
- https://www.youtube.com/watch?v=R_agd5qZ26Y
- https://www.youtube.com/watch?v=_K-eupuDVEc


Good to know (at least conceptually):
- What is a VM: https://www.redhat.com/en/topics/virtualization/what-is-a-virtual-machine
- What is EC2: https://www.quora.com/How-does-EC2-work-Im-interested-in-learning-about-the-specific-infrastructure-that-makes-EC2-work-For-example-are-instances-actual-discrete-machines-or-are-they-totally-virtualized-e-g-one-quad-core-machine-could-run-4-micro-EC2-instances
- What is a container, how is it different from a VM: https://www.youtube.com/watch?v=0qotVMX-J5s
- What is a container orchestrater (like Kubernetes)
- What are serverless functions: https://www.youtube.com/watch?v=97q30JjEq9Y
- Horizontal vs Vertical scaling


Additional reading:
- The tail at scale: https://www.barroso.org/publications/TheTailAtScale.pdf
- Latency Numbers Every Programmer Should Know: (https://gist.github.com/jboner/2841832)


# So you want to do systems dev?

Let us first try to define systems development/programming as it is a bit fuzzy. We won't use the term 'systems engineering' as that is a separate "traditional" engineering discipline. In some [university programs](https://www.cs.mcgill.ca/graduate/masters/breadthrequirement/), the term is used to refer to work on compilers, database systems and distributed systems which all require working at and understanding pretty low levels of the metaphorical stack of abstractions starting from hardware. Compilers have to emit CPU instructions and require an understanding of the target ISAs, database systems generally manage their [memory directly](https://stackoverflow.com/questions/3171919/why-cant-dmbses-rely-on-the-os-buffer-pool) reimplementing some OS functionality and distributed systems (which can include databases) have to deal with hard physical problems related to synchronisation across space and time.  
Some people use an axis of [application vs systems](https://news.ycombinator.com/item?id=27584443) development to define it. Within this new split, a systems programmer develops software that run below applications and power them. 

In general systems programming necessitates deeper knowledge of how things works under the hood, as well as strong algorithms and data structure knowledge to be able to design and implement correct, and performant code. Software that, to me, qualifies as "systems" work would be: operating systems, drivers, web browsers, compilers, databases, game engines, virtualization platforms, video/audio codecs, deep learning training frameworks, other specialized systems.

Some discussion on the subject:
[Ask HN: What should a systems/low-level software engineer know?](https://news.ycombinator.com/item?id=18881649) 
[Ask HN: How to learn proper systems programming?](https://news.ycombinator.com/item?id=27577514)
[Ask HN: Is it hard to get into systems programming from back end engineer?](https://news.ycombinator.com/item?id=32915350)


Some resources:
- C/C++ projects: https://github.com/practical-tutorials/project-based-learning?tab=readme-ov-file#cc
- Rust projects: https://github.com/rust-unofficial/awesome-rust
- Kafka architecture: https://www.youtube.com/watch?v=HZklgPkboro
- Why Doom is Awesome: https://www.youtube.com/watch?v=hYMZsMMlubg
- Cool audio/video project: https://www.youtube.com/watch?v=MEMzo59CPr8&list=PLKucWgGjAuTbobNC28EaR9lbGQTVyD9IS&index=2


YouTube channels / streamers:
- https://www.youtube.com/user/gamozolabs/videos
- https://www.youtube.com/@TsodingDaily/featured


