# Dijkstra-Shortest-Path
Dijkstra Shortest Path: Jack source code. 

This project is an implementation of Dijkstra's shortest path algorithm, which is used to find the shortest path from a source node to all other nodes in a graph. A classic example is mapping software that finds the shortest route between 2 cities. 

The project is written in the Jack language, a high-level object-oriented language. You must have taken the Coursera online courses "nand2tetris" parts 1 and 2, in which you write your own Jack compiler.

The Jack compiler compiles Jack source code to VM (virtual machine) code.   You can run the VM code in the VM Emulator provided by the nand2tetris tool set.  Or, assuming you have written your VM Translator to translate to highly optimized Hack Assembly code, you could run the Hack Assembly program in the supplied CPU Emulator.  And furthermore, you could use the Hack Assembler you wrote to translate the Hack Assembly to Hack machine language, and run it in the CPU Emulator.

In writing Dijkstra's shortest path algorithm in Jack, I decided to create my own linked-list class and use that in various parts of the program. It's a simple data structure that is easy to implement and understand.

When writing any Jack program in the Jack OS environment, there are of course some minor annoyances that have to be worked around, as the language was designed to be simple enough so that a new student could write a compiler without getting too bogged down.  For this project, the following issues took the most attention and care:

(1) There is no garbage collection.  As you examine the source code, note how dispose() has to be implemented for everything.  And when dealing with multiple pointers that point to an object, you have to be careful not to double-free an object. Take care to understand who is the owner of every object you allocate, so you can properly recycle the memory. 

(2) String allocation and de-allocation can be tricky. I had to write my own String utility class that allows me to concatenate strings with the option of disposing of either argument. See the StringUtil class. I also wrote an Output utility class to automatically dispose the string constant passed to printString. See the OutputUtil class.

Other than these issues, writing code in Jack felt normal and fun, like any other high level language. It's quite a powerful language. After all, the Jack OS is written in Jack.

I decided the easiest way to experiment with different source nodes or different graphs entirely is to edit the source code directly. If you look at Main.jack, it is self-explanatory. You can define a node and directed edges and add the nodes to the graph. Between nodes you can have 1-way or 2-way direction, simply by adding the appropriate edges to the appropriate nodes.  You can also see in Main.jack how to specify the source node.  

The screen output of the program shows the shortest path from the source node to all other nodes (and the total distance for each), and will indicate if a node is unreachable from the source node.  Here is sample output:

Shortest path from Node A to:

Node B: A -> B (total distance = 10)

Node C: A -> C (total distance = 20)

Node D: A -> C -> D (total distance = 40)

Node E: A -> B -> E (total distance = 20)

Node F: A -> B -> E -> F (total distance = 21)

Node G: unreachable



--------------------
** Note: there are many example implementations of this algorithm online. The one I borrowed from the most was:
https://www.baeldung.com/java-dijkstra


