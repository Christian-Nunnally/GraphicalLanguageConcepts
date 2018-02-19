# Graphical Language Concepts

## Final Report

### The project goals

During the final 5 weeks of this class, I set out to build a prototype version of a programming environment that combines UML class diagrams with traditional code editing. I wanted to see what such a system of programming would look like in a prototype to inspire a discussion of what advantages and disadvantages such a system has for software engineering.

After finishing the project, the plan is to take what I've learned and continue to move this idea forward with a better idea of what works and what doesn't. If the prototype shows us that combining UML and implementation is a reasonable way to represent a project, then a more complete project plan can be constructed and I can work toward building a more polished tool.


### Pyagramr

Pyagramr ended up being the prototype tool I created. Its named was inspired by a combination of the chosen programming language that users are able to edit with it, and the Diiagramr project that inspired that I forked in order to make this prototype possible. Diiagramr is a simple graphical scripting language which can be found here https://christiannunnally.visualstudio.com/Diiagramr.

#### The chosen language, python

Python was picked as the language that can be edited with Pyagramr for a couple of reasons

1. (+) I had already created a python node in Diiagramr that had syntax highlighting and some rudimentary execution capabilities. I was able to reuse many of the elements for this project.

2. (+) Python being an interpreted language made it really easy to execute because I did not need to pull in any build tools to make Pyagramr work.

Since python is a dynamically typed language, I had two options for inferring the dependencies and uses arrows in my UML, either I generate type information by compiling the code, or I cheat and require types be explicitly declared for local variables and method signatures. I went with the second option given that this is a prototype. This project would probably make more sense in the long run if I went with the first option and automatically got the type information by semi compiling the code and tracking types. This will not be a problem for statically typed languages.

#### Pyagramr features

Pyagramr ended up being a great prototype and had all of the basic set of features needed to test out this type of tool:

- Class nodes can be added to a diagram.
- Class nodes allow specifying fields.
- Class nodes allow specifying methods.
- Class nodes allow inline editing of method implementations.
- Inline method implementation is syntax highlighted python.
- Inheritance between class nodes achieved by dragging an inheritance arrow between class nodes.
- Uses arrows are automatically added and removed from the diagram when field text changes.
- Dependency arrows are automatically added and removed from the diagram when method signature text changes.
- Dependency arrows are automatically added and removed from the diagram when implementation text changes.
- Each class node generates a python source file with automatically generated source code which includes imports of classes it depends on, the fields for the class, and the methods for the class with their implementation.
- Arrows originate from the side of the node that makes the most sense to keep the diagram clean.
- Code can be executed in the editor with a run and stop button.
- Console node shows standard output, error, and captures input of executed code.
- Classes that generate an error during execution highlight their corresponding class node on the UML diagram.

For the scope of this prototype, there was a small set of features that I did not get to implementing:

- Methods on class nodes allow adding test cases to them.
- Test cases are automatically run when editing a method implementation.
- Test results are updated in real time and shown while editing method bodies.

#### Images

Code execution displays results in a built in console node.
![alt text](https://github.com/Christian-Nunnally/GraphicalLanguageConcepts/tree/master/Images/Pyagramr.png "Execution of code in inline console")

Introducing an error in the main class shows how the error is both printed in the console and the problem class is highlighted red.
![alt text](https://github.com/Christian-Nunnally/GraphicalLanguageConcepts/tree/master/Images/Error.png "Error during execution")

Showcasing the three types of arrows, inheritance, dependency, and uses.
![alt text](https://github.com/Christian-Nunnally/GraphicalLanguageConcepts/tree/master/Images/Arrows.png "Arrow Types")

The code generated automatically by Pyagramr for the previous example.
![alt text](https://github.com/Christian-Nunnally/GraphicalLanguageConcepts/tree/master/Images/CodeOutput.png "Generated Code")

#### Future of Pyagramr

During the development process for the Pyagramr prototype I discussed the project with a number of people to get their insights into what works and what does not with this new style of development. I also thought about changes I would make to remedy some of the pain points that came up during testing. Here I will outline some of the major adjustments I would make to make this tool more usable.

- **Source to UML conversion** - While I like the ability to write code directly in the UML class node, I think faster development could be obtained if clicking on a node would open the source file for that class in a side by side view and code written in that editor would translate directly over to the UML diagram. This would eliminate the need to click on small buttons to open up the editor that is in-lined with the node and would give the developer more space to write their code, while still maintaining the UML perspective side by side with the code they are editing. This also allows loading projects from source code instead of a special save format, and developers could utilize existing VCS like Git.

- **UML Pattern Detection** - One of the most critical advantages to developing from UML instead of source code is the ability to see the use of design patterns more easily. This tool could scan through your code looking for common design patterns and then color and annotate the use of those patterns automatically on your UML class diagram. This would be a huge advantage for new developers working on a system they are unfamiliar with so they can quickly see where the source code is open for extension without modification.

- **Modularization** - External dependencies should have some representation on the UML diagram to give programmers a complete picture of what they are working with. They should also be able to modularize their project so as to not have a single UML diagram for a large scale project. Diiagramr already supports having multiple diagrams which can have references to each other which might be able to be taken advantage of. I am not sure exactly how modularizing would work, but it is something that will have to be considered for future versions of this tool.


### Cutting edge editor

The concept of integrating UML class diagrams into source code is the next cutting edge method of development, as such, it should have all of the cutting edge features a modern IDE delivers to us

- **Language Agnostic** - With the help of special parsing rules, developers should be able to use any object oriented source code.
- **Intelligent code completion** - While editing from UML removes a lot of boiler plate code, developers should have just as much assistance as they currently have for writing method implementations.
- **Step by Step Debugging** - The debugging experience can be enhanced by showing values of class fields on the UML diagram as a developer steps through their programming.
- **Coverage statistics** - Unit test coverage and passing percentage should be displayed on each method on the UML class nodes.
- **Easy Navigation** - Navigating code becomes much easier when you combine tools that take you to a method implementation with an always visible map of your code in the form of the UML class diagram.

### Concluding thoughts

This project was a great way of exploring what is possible if we equip software engineers with a more visual way of architecting and implementing their code. I hope that by paying more attention to high level design it will force programmers to make better decisions at the implementation level. Unit testable, concise, code will become more natural without even training for it. The law of demeter and the open closed principal will find its way into more of the software engineers produce which will give those who maintain and extend code a better chance of survival. I hope to take this project to the next level and explore some of the more difficult issues with it such as dependencies, efficiency, and making it language agnostic, in the future when I have time.