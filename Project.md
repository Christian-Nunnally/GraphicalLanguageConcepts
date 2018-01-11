## Overall Project Idea

I want to create a tool for editing object oriented source code directly from a UML diagram. Users would use this tool to create a uml class diagram of their project, nodes would contain signatures for methods and fields just like any normal class diagram. When the user was ready to implement some of the functionality for their class diagram, that should be able to write the code for a function directly into the node by preforming a simple action such as double clicking on the method name that they want to implement. Users should be able to write some tests for each of the functions in the class diagram before writing the implementation for the function. Then when it comes time to run the project, they should be able to execute it without ever looking at source files.

The overall process should go like this:

1. **Design** - Users design their application as a UML class diagram.
2. **Test** - Users write unit tests for each of the proposed methods in their design without leaving the UML diagram.
3. **Implement** - Users can write the implementation for each of the methods in their design without leaving the UML diagram. The tests can automatically be run as they are writing the implementation so they can get the implementation right without ever switching context.
4. **Execute** - Users can execute their project from within the UML class diagram to see their work.

### Existing Tools

There are many existing tools that facilitate syncing source code and uml. Most of these tools generate source from uml or uml from source or both, which is very helpful. 

- Enterprise Architect from Sparx Systems will take either code or uml and turn it into uml or code, respectively.
- Visual Studio Enterprise allows generating a project template from a uml diagram
- Epydoc doc is a somewhat outdated free tool to generate uml from python source
- Pyreverse is a tool to generate GraphViz uml diagrams from python source
- The list goes on...

While these tools are great, many of the more feature rich and easy to use ones cost hefty amounts of money. They also do not fully integrate the processes of creating uml and creating code. What is a tool existed that fully bridged the gap between uml and source to the extend that all of your architecture was composed in a uml class diagram and all that was left to code was the implementations of the functions? Such a system might force good software engineering principles such as having high cohesion and low coupling.

### Implementation

I first explored writing this tool as a visual studio extension that supports working with C# source code. I tried to find some form of open source UML editor for visual studio that I could work off of but could not find an open source option. Visual studio code does have a UML editor that I could potentially extend to make this project work, but this tool is going to be a proof of concept at first and I want to be able to develop it in less that 5 weeks which I'm not confident I can do working with an extensibility system I've never used before.

Since writing a new UML editor that supports inline code editing sounds time consuming and is not the point of this experimental tool, I've decided to tie together a few tools I've already made with some slight modifications and create what i'm calling a 'UML IDE' for python source.

To patch this proof of concept MVP together I will,

1. Create a fork of the Diiagramr visual programming language and add support for different types of connections between nodes (this will allow the association arrows for the uml).
2. Create a Diiagramr node library that has a class node which allows the user to **a)** connect it to other nodes to represent inheritance and dependencies **b)** specify a list of fields and methods and **c)** click on methods to open up an inline, syntax highlighted, editor for implementing the method.
3. Create a special node that is capable of traversing the graph and generating an interpretable source file, and running it.