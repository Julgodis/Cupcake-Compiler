
![Cupcake](logo.png "Title is optional")

# Cupcake
Cupcake is a compiler for Jonathan Blows new programming language **JAI**. The compiler is build from the ideas and temporary specification that Blow gives in his youtube/twitch [videos](https://www.youtube.com/user/jblow888/videos). Cupcake has almost implemented everything that Jonathan Blow has shown in his videos so far (2016-06-12). 

Both Cupcake and me has no association with Jonathan Blow or JAIs development. The experience you have with Cupcake should not be reflect towards JAI and your opinon of it, **_Cupcake is not JAI_**. Cupcake is my hobby project, create for me to learn how i real compiler works and how programs goes from source code to machine code.

Cupcake, as JAI, does not generate machine code (yet). There are two way to execute your code, run the code in the compiler itself  through bytecode (#run) or compile/convert your JAI code to C++ code. Currently a C++ file will always be generate and there is no way to turn it off. Output folder for the C++ file is in `%EXECUTABLE_PATH%/output/output.cpp`, the folder can be changed by using the compiler introspection feature.

### Platform support ###

|| **Status** |
|---|---|
|**Windows 32bit**         |[v0.1-alpha](http://)|

More platform will be added later. There is a lot of windows specific code in the first release so it will take a while to port everthing. 

### Features ###

Video  | Implemented Status | Tested Status
------------- | ------------- | ------------- 
[Base language, compile-time execution](https://www.youtube.com/watch?v=UTqZNujQOlA)  | Everything implemented | Good enough
[Iteration and arrays, uninitialized values, enums](https://www.youtube.com/watch?v=-UPFH0eWHEI)  | Everything but inlining | Good enough
[SOA, composition](https://www.youtube.com/watch?v=ZHqFrNyLlpA)  | Everything implemented | Good enough
[Run-Time (and Compile-Time) Type Information](https://www.youtube.com/watch?v=JoNkttD_MUs)  | Everything but check calls and embedded systems | Good enough
[Arguments and Return Values](https://www.youtube.com/watch?v=CttIYXCUeVY)  | Everything but double multi-return and #must | Good enough
Polymorphic Procedures [Part 1](https://www.youtube.com/watch?v=BwqeFrlSpuI) & [Part 2](https://www.youtube.com/watch?v=7Fsy2WaxLOY)  | Everything implemented | Good enough
[Implicit Context](https://www.youtube.com/watch?v=ciGQCP6HgqI)  | Everything implemented | Good enough
[Bounds check, here strings, overloading](https://www.youtube.com/watch?v=4h-0Sc2jK88)  | Everything implemented | Good enough
[Self-browsing code, compiler message loop, workspaces](https://www.youtube.com/watch?v=OHZwYYW9koI)  | Everything but self-browsing code | Good enough
[Code Modification](https://www.youtube.com/watch?v=59lKAlb6cRg)  | Can not be implemented without self-browsing code | Not tested
[Structs with Parameters](https://www.youtube.com/watch?v=2IBr0XZOPsk)  | Everything implemented | Good enough
[First-Class (-Ish?) Types](https://www.youtube.com/watch?v=iVN3LLf4wMg)  | Everything implemented | Good enough
[Iterators, (Overloading x Polymorphism)](https://www.youtube.com/watch?v=COQKyOCAxOQ)  | Everything implemented | Good enough

# Download #
Here is the latest release [Cupcake v0.1-alpha](http://).

Version  | Date | Link
------------- | ------------- | ------------- 
v0.1-alpha  | 2016-06-12 | [Download](http://)

# Usage #
1. Download the latest release.
2. Unpack in a seperate folder.
3. Run the compiler through the console.

```
cupcake main.jai
```

```
Usage: cupcake <source>... [options]
Options:
  -v --version           Show version
  -h --help              Show this screen
     --nologo            Disable Cupcake logo
  -r --run <code>        Executes the code
  -l --modules <path>    Include modules from folder [include already: ./modules/]
  -m --module <file>     Include module
```

# Issues #
The goal is to make Cupcake as great as possible and to do that i need your help. If you find any problem/bugs please report them to me, don't forget to send exemple code that demostrates the problem. You can use the github issue section or send me an email at [support@jonathanwase.se](mailto://support@jonathanwase.se) (use the email if you don't want the demostrantion source code to be public).

# Source Code? #
I have decided to not release the source code yet. Why is because I don't know if it would be fair to Jonathan Blow (everyone creating their own version of JAI) and I am not very proud of the code. There is a huge amount of unnecessery code that could be removed, Cupcake is around 45k LOC. 

# Not implemented / Changed #
#### Check calls ####
Not so useful when you have access to #modify and #body_text.

#### Double multi-return ####
Double multi-return is a special case that is not yet implemented. The code below show where the problem occurs.
```jai
VeryGoodProcedure :: () -> s64, s64 {
     return 13, 37
}

VeryBadProcedure :: () -> s64, s64 {
     return VeryGoodProcedure() // ERROR
}
```

#### Auto Bake ####
In Jonathan Blow demo he is using $$ to mean can be baked and $$ $$ to mean requiers to be baked. At the Q&A part he talks about changing it to $ for can be baked and $$ for requiers to be baked. Cupcake is using the second syntax.

#### Self-browsing code ####
I have not had the time. :(

# Licence #

