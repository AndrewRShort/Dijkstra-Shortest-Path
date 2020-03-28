# Dijkstra-Shortest-Path
Dijkstra Shortest Path: Jack source code. 

This project is an implementation of Dijkstra's shortest path algorithm, which is used to find the shortest path from a source node to all other nodes in a graph. A classic example is mapping software that find the shortest route between 2 cities. 

The project is written in the Jack language, a high-level object-oriented language. You must have taken the Coursera online courses "nand2tetris" parts 1 and 2, in which you write your own Jack compiler (it also comes with a tool suite that includes a JackCompiler).

The Jack compiler compiles Jack source code to VM (virtual machine) code.   You can run the VM code in the VM Emulator provided by the nand2tetris tool set.  Or, assuming you have written your VM Translator to translate to highly optimized Hack Assembly code, you could use your VMTranslator to translate your VM code to Hack Assembly and then run the Hack program in the supplied CPUEmulator.  And furthermore, you could use your Assembler to translate the Hack Assembly to Hack machine language, and run it in the CPUEmulator.

In writing Dijkstra's shortest path algorithm in Jack, I decided to create my own linked-list class and use that in various parts of the program. It's a simple data structure that is easy to implement and understand.

When writing any Jack program in the Jack OS environment, there are of course some minor annoyances that have to be worked around, as the language was designed to be simple enough so that a new student could write a compiler without getting bogged down.  For this project, these issues took the most attention and care:

(1) There is no garbage collection.  As you examine the source code, note how dispose() has to be implemented for everything.  And when dealing with multiple pointers that point to an object, you have to be careful not to double-free an object. 

(2) String allocation and de-allocation can be tricky. The Jack language easily lets you allocate and deallocate string objects, but you can fall into a trap where you think a string is going to be de-alloced but it won't be.  I had to write my own String utility class that allows me to copy a string, and to concatenate strings with the option of disposing of either argument. See the StringUtil class. I also wrote an Output utility class to automatically dispose the string constant passed to printString. See the OutputUtil class.

Other than these issues, writing code in Jack felt normal and fun, like any other high level language. It's quite a powerful language. After all, the Jack OS is written in Jack.



