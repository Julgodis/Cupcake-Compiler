
![Cupcake](logo.png "Title is optional")

# Cupcake
Cupcake is a compiler for Jonathan Blows new programming language **JAI**. The compiler is built from the ideas and temporary specification that Blow has given in his Youtube and Twitch [videos](https://www.youtube.com/user/jblow888/videos). Cupcake has almost everything implemented that Jonathan Blow has shown in his videos so far (2016-06-12). 

Both Cupcake and me has no association with Jonathan Blow or JAIs development. The experience you have with Cupcake should not be reflected towards JAI and your opinion of it, **_Cupcake is not JAI_**. Cupcake is my hobby project, created for me to learn how a compiler works and how programs goes from source code to machine code.

### Platform support ###

|| **Status** |
|---|---|
|**Windows 32bit**         |[v0.1-alpha](https://github.com/Julgodis/Cupcake-Compiler/releases/tag/v0.1-alpha)|

More platforms will be supported later. There is a lot of windows specific code in this release and it will take a while to port everything over. 

# Download #
Here is the latest release: [Cupcake v0.1-alpha](https://github.com/Julgodis/Cupcake-Compiler/releases/tag/v0.1-alpha).

Version  | Date | Link
------------- | ------------- | ------------- 
v0.1-alpha  | 2016-06-12 | [Download](https://github.com/Julgodis/Cupcake-Compiler/releases/tag/v0.1-alpha)

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

Cupcake, as JAI, does not generate machine code (yet). There are two ways to execute your code, run the code in the compiler itself  through bytecode (#run) or compile/convert your JAI code to C++ code. Currently a C++ file will always be generated and there is no way to turn it off. The output location for the C++ file is `%EXECUTABLE_PATH%/output/output.cpp`, the location can be changed by using the compiler workspace feature.

# Documentation #

The release includes a few examples, but there is no other documentation available to Cupcake. The game example is the invaders game Jonathan Blow showed in the first few demos. To test the examples just type this in to the console.
```
cupcake examples/EXAMPLE_NAME/main.jai
```

Because the specification for JAI is not complete, writing a documentation is stupid. Though some nice people have written stuff about the language that could be used as documentation. 

[Jai Primer](https://sites.google.com/site/jailanguageprimer/) by Jorge Rodríguez.

[Jai Programming Language – Resources and Information](https://sites.google.com/site/jailanguageprimer/) by Inductive.

After using Cupcake, if you have any nice code examples, please send them to [support@jonathanwase.se](mailto://support@jonathanwase.se) and I added them to the examples folder.


### Features ###
The progress of JAI features that Cupcake has:

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


# Issues #
The goal is to make Cupcake as great as possible and to do that i need your help. If you find any problems/bugs, please report them and don't forget to send example code that demonstrates the problem. You can use the Github issue section or send me an email at [support@jonathanwase.se](mailto://support@jonathanwase.se) (use the email if you don't want the demonstration source code to be public).

# Source Code? #
For now I have decided to not release the source code. Why, because I don't know if it would be fair to Jonathan Blow and I am not very proud of the quality of the code. There is a huge amount of unnecessary code that could and should be removed, Cupcake v0.1-alpha is around 45k LOC. 

# Licence #

MIT License

Copyright (c) 2016 Jonathan Wase

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
