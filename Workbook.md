# Graphical Languages Concepts Notebook

The aim of this notebook is to sift through and organize research papers, real world examples, and comparisons of visual programming languages. Ultimatly the goal of this project is to determine where visual programming languages are most effective and worth thier cost to create. 

## Introduction

Visual programming languages allow non-programmers to contribute to our continuously digitizing world by abstracting away complicated detail oriented syntax and commands. Computers began by being operated directly with 1’s and 0’s (machine code), their native language. When computers became more powerful they were programmed in assembly code, which a less cryptic method of writing instructions for a computer that can still be translated into machine code. This trend continues into higher level languages that reduced the nuances programmers had to deal with.
We moved from text only terminals, into graphical operating systems that we know today, like Windows, Linux, and MacOS. Providing a graphical interface opened the doors on computing to more than just the scientists, more and more individuals could take advantages of what computers offer. This trend can be seen in every corner of computer science. If you wanted to create a website for your business a few years ago it would have required hiring a web developer, someone who knew the ins and outs of https, html code, and java script. Today, you can hire an artist that can create webpages without ever seeing a line of code, they can insert images, connect twitter feeds, stylize a page, and setup a web store all with one of many services like Wordpress. Game developers used to work exclusively inside of a text editor to write the code for their game, now they build games using tools like Unity, which although does allow scripting and programming if necessary, it is now possible to make a great game in much the same way as you would edit together a movie in Adobe After effects.
Text is a powerful tool because our brains are incredible language processors, but about 30% of our cortex is dedicated to sight which explains why we are so good at interpreting symbols and graphics. It seems natural that we can enhance our ability to understand something with the aid of some graphical representations of the thing we are trying to understand.
Visual programming has many potential benefits over textual programming. To turn that potential into something tangible, I would like to enumerate the possible advantages visual programming could have.
1.	**Solution navigation**. Most projects exist as many source files that are linked together. There are many tools that simplify navigating across those invisible links. Those tools enable programmers to go to function or class definitions by simply clicking on the token referring to that function or class, or listing out the dependencies of a section of code. Visual programming languages could allow more intuitive navigation by displaying the links between source files that are normally just abstract links with no representation in the editor.
2.	**Information Density**. Textual languages are extremely information dense in most areas. Mathematical expressions, for example, are normally expressed in text and representing them in the traditional way visual programming languages do with nodes and wires makes them less information dense. Other relationships, such as class hierarchies, are not represented well in textual languages but visual representations such as the familiar UML allow programmers to see a large swath of a project in a single screen. Software architecture is always represented visually as box and pointer diagrams because they allow extreme information density.
3.	**Programming Speed**. Visual programming languages are regarded as being more fun to work in than traditional textual programming languages. Seasoned textual programmers usually prefer to stick to their roots and contest that visual programming is more fun, but as software development becomes more abstract and powerful, new programmers might be able to understand concepts better if they are represented graphically. Having fun is an important factor in a programmers productivity because it allows them to focus more easily and get more done in the same amount of time.
4.	**Good Software Engineering**. Software engineering is all about good design. Traditionally, design starts as architecture diagrams, moves to more detailed class diagrams, and then finally transitions into actual code. Lots of planning goes into the high-level architecture of a project so that the code ends up being easy to extend and modify. For object oriented programming, when decisions are made at the architecture or class diagram level, they normally translate to quality code. When decisions are made at the source level, it becomes easy to cheat good design principles and leads to a system that is difficult to maintain. Visual programming languages could bridge the gaps between the design diagrams and the actual source code which would enforce quality code.

## List of Popular Visual Languages I want to Research

- TraceLab
- Labview
- Scratch
- Unity
- Luna (http://www.luna-lang.org/)
- Blocky (https://developers.google.com/blockly/)
- Unreal Engine Blueprints
- Alice

## Categories of Visual Languages

- General-purpose languages
- Database languages
- Image-processing languages
- Scientific visualization languages
- User-interface generation languages
- Languages for programming web-based applications
- Languages for education
- Visualization tools for textual languages

## Research Papers
- https://link.springer.com/chapter/10.1007/BFb0026431
- http://www-ist.massey.ac.nz/plyons/776/VPL%20papers.html
- http://web.engr.oregonstate.edu/~burnett/vpl.html
- https://www.cl.cam.ac.uk/~afb21/publications/ESP97-kirsten.html (Visual Programming: The Outlook from Academia and Industry)
- http://crpit.com/confpapers/CRPITV30Flint.pdf


## Notes

Visual programming languages are based on nodes and interconnecting wires to graph relations between nodes.  One observation is that while the nodes can be layed out in an order that makes sense, often the interconnected wires make the visual representation look messy.  There are four types of intercepts I've seen so far:

- Stright lines (ex. tracelab)
- right angle lines (ex. labview)
- spline curves (ex. blueprints)
- puzzle (ex. blocky)

I would like to explore which is best, or what applications each has.  What other ways could you graphically represent data flow?

"However, our surveys reflect an increasing concern with whole lifecycle costs of software, including design, test and maintenance, as many statements about productivity referred explicitly to tasks other than coding." - https://www.cl.cam.ac.uk/~afb21/publications/ESP97-kirsten.html 

Since the whole lifecycle of a programming project is becoming more and more important and integrated, it makes sense that we should have and use tools that integrate those items.  
