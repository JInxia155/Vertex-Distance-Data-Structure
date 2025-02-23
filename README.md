# Vertex-Distance-Data-Structure
Vertex Distance Data Structure

Download Link : https://programming.engineering/product/vertex-distance-data-structure/


In the Graph class and Dijkstra’s algorithm, you will be using the VertexDistance class implementation that we have provided. In the Graph class, this data structure is used by the adjacency list to represent which vertices a vertex is connected to. In Dijkstra’s algorithm, you should use this data structure along with a PriorityQueue. At any stage throughout the algorithm, the PriorityQueue of VertexDistance objects will tell you which vertex currently has the minimum cumulative distance from the source vertex.

Search Algorithms

Breadth-First Search is a search algorithm that visits vertices in order of “level”, visiting all vertices one edge away from start, then two edges away from start, etc. Similar to levelorder traversal in BSTs, it depends on a Queue data structure to work.

Depth-First Search is a search algorithm that visits vertices in a depth based order. Similar to pre/post/in-order traversal in BSTs, it depends on a Stack data structure to work. However, in your implementation, the Stack will be the recursive stack. It searches along one path of vertices from the start vertex and backtracks once it hits a dead end or a visited vertex until it finds another path to continue along. Your implementation of DFS must be recursive to receive credit.

Single-Source Shortest Path (Dijkstra’s Algorithm)

The next algorithm is Dijkstra’s Algorithm. This algorithm finds the shortest path from one vertex to all of the other vertices in the graph. This algorithm only works for non-negative edge weights, so you may assume all edge weights for this algorithm will be non-negative.

There are two main variants of Dijkstra’s Algorithm related to the termination condition of the al-gorithm. The first variant is where you depend purely on the PriorityQueue to determine when to terminate the algorithm. You only terminate once the PriorityQueue is empty. The other variant, the classic variant, is the version where you maintain both a PriorityQueue and a visited set. To terminate, still check if the PriorityQueue is empty, but you can also terminate early once all the vertices are in the visited set. You should implement the classic variant for this assignment. The classic variant, while using more memory, is usually more time efficient since there is an extra condition that could allow it to terminate early.

Minimum Spanning Trees (MST – Prim’s Algorithm)

An MST has two components. By definition, it is a tree, which means that it is a graph that is acyclic and connected. A spanning tree is a tree that connects the entire graph. It must also be minimum, meaning the sum of edge weights of the tree must be the smallest possible while still being a spanning tree.

By the properties of a spanning tree, any valid MST must have |V | − 1 edges in it. However, since all undirected edges are specified as two directional edges, a valid MST for your implementation will have 2(|V | − 1) edges in it.

Prim’s algorithm builds the MST outward from a single component, starting with a starting vertex. At each step, the algorithm adds the cheapest edge connected to the incomplete MST that does not cause a cycle. Cycle detection can be handled with a visited set like in Dijkstra’s.

Self-Loops and Parallel Edges

In this framework, self-loops and parallel edges work as you would expect. If you recall, self-loops are edges from a vertex to itself. Parallel edges are multiple edges with the same orientation between two vertices. These cases are valid test cases, and you should expect them to be tested. However, most

Homework 10: Graph Algorithms Due: See Canvas

implementations of these algorithms handle these cases automatically, so you shouldn’t have to worry too much about them when implementing the algorithms.

Homework 10: Graph Algorithms Due: See Canvas

A note on JUnits

We have provided a very basic set of tests for your code, in GraphAlgorithmsStudentTests.java. These tests do not guarantee the correctness of your code (by any measure), nor do they guarantee you any grade. You may additionally post your own set of tests for others to use on the Georgia Tech GitHub as a gist. Do NOT post your tests on the public GitHub. There will be a link to the Georgia Tech GitHub as well as a list of JUnits other students have posted on the class Piazza.

If you need help on running JUnits, there is a guide, available on Canvas under Files, to help you run JUnits on the command line or in IntelliJ.

Style and Formatting

It is important that your code is not only functional but is also written clearly and with good style. We will be checking your code against a style checker that we are providing. It is located on Canvas, under Files, along with instructions on how to use it. We will take off a point for every style error that occurs. If you feel like what you wrote is in accordance with good style but still sets off the style checker please email the Head TA(s) with the subject header of “[CS 1332] CheckStyle XML”.

Javadocs

Javadoc any helper methods you create in a style similar to the existing Javadocs. If a method is overridden or implemented from a superclass or an interface, you may use @Override instead of writing Javadocs. Any Javadocs you write must be useful and describe the contract, parameters, and return value of the method; random or useless javadocs added only to appease Checkstyle may lose points.

Vulgar/Obscene Language

Any submission that contains profanity, vulgar, or obscene language will receive an automatic zero on the assignment. This policy applies not only to comments/javadocs but also things like variable names.

Exceptions

When throwing exceptions, you must include a message by passing in a String as a parameter. The message must be useful and tell the user what went wrong. “Error”, “BAD THING HAP-PENED”, and “fail” are not good messages. The name of the exception itself is not a good message. For example:

Bad: throw new IndexOutOfBoundsException(‘‘Index is out of bounds.’’);

Good: throw new IllegalArgumentException(‘‘Cannot insert null data into data structure.’’);

In addition, you may not use try catch blocks to catch an exception unless you are catching an exception you have explicitly thrown yourself with the throw new ExceptionName(‘‘Exception Message’’); syntax (replacing ExceptionName and Exception Message with the actual exception name and message respectively).

Generics

If available, use the generic type of the class; do not use the raw type of the class. For example, use new LinkedNode<Integer>() instead of new LinkedNode(). Using the raw type of the class will result in a penalty.

Forbidden Statements

You may not use these in your code at any time in CS 1332.

Homework 10: Graph Algorithms Due: See Canvas

    package

    System.arraycopy()

    clone()

    assert()

    Arrays class

    Array class

    Thread class

    Collections class

    Collection.toArray()

    Reflection APIs

    Inner or nested classes

    Lambda Expressions

    Method References (using the :: operator to obtain a reference to a method)

If you’re not sure on whether you can use something, and it’s not mentioned here or anywhere else in the homework files, just ask.

Debug print statements are fine, but nothing should be printed when we run your code. We expect clean runs – printing to the console when we’re grading will result in a penalty. If you submit these, we will take off points.

Visualizations of Graphs

The directed graph used in the student tests is:

1 4 6

2 3 5 7

The undirected graph used in the student tests is:

7

A B

        5
        	

        8

    3

    C
    			

    F

    2
    	

    D
    	

    E
    	

    6
    	
    		

    1
    	

Homework 10: Graph Algorithms Due: See Canvas

Grading

Here is the grading breakdown for the assignment. There are various deductions not listed that are incurred when breaking the rules listed in this PDF, and in other various circumstances.

Methods:
	
	

BFS
	

15pts
	

DFS
	

15pts
	

Dijkstra’s
	

25pts
	

Prim’s
	

20pts
	

Other:
	
	

Checkstyle
	

10pts
	

Efficiency
	

15pts
	

Total:
	

100pts
	

Provided

The following file(s) have been provided to you. There are several, but we’ve noted the ones to edit.

    GraphAlgorithms.java

This is the class in which you will implement the different graph algorithms. Feel free to add private static helper methods but do not add any new public methods, new classes, instance variables, or static variables.

    GraphAlgorithmsStudentTests.java

This is the test class that contains a set of tests covering the basic operations on the GraphAlgorithms class. It is not intended to be exhaustive and does not guarantee any type of grade. Write your own tests to ensure you cover all edge cases. The graphs used for these tests are shown above in the pdf.

    Graph.java

This class represents a graph. Do not modify this file.

    Vertex.java

This class represents a vertex in the graph. Do not modify this file.

    Edge.java

This class represents an edge in the graph. It contains the vertices connected to this edge and its weight. Do not modify this file.

    VertexDistance.java

This class holds a vertex and a distance together as a pair. It is meant to be used with Dijkstra’s algorithm. Do not modify this file.

Deliverables

You must submit all of the following file(s) to the course Gradescope. Make sure all file(s) listed below are in each submission, as only the last submission will be graded. Make sure the filename(s) matches the filename(s) below, and thatonly the following file(s) are present. If you resubmit, be sure only one copy of each file is present in the submission. If there are multiple files, do not zip up the files before submitting; submit them all as separate files.

Homework 10: Graph Algorithms Due: See Canvas

Once submitted, double check that it has uploaded properly on Gradescope. To do this, download your uploaded file(s) to a new folder, copy over the support file(s), recompile, and run. It is your sole responsibility to re-test your submission and discover editing oddities, upload issues, etc.

    GraphAlgorithms.java

