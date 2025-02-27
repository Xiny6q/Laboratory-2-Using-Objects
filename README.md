Download link :https://programming.engineering/product/laboratory-2-using-objects/

# Laboratory-2-Using-Objects
Laboratory 2: Using Objects
Java API

In this lab, you will practice creating/instantiating objects and passing messages to them. Two short, unrelated exercises will review basic programming concepts and provide substantial practice in using objects.

Lab:

Craps

Maze Recursion

Download Lab02Files.zip from ilearn and extract the files into your Lab02 directory

Part I: Computing the percentage of times that craps is rolled

You will use the following files:

SingleDie.class //you won’t directly use this class, representing a six-sided die

CrapsDice.class //has the following public interface:

public CrapsDice() //constructor (creates and uses 2 SingleDie objects, this is called

composition or a has-a relationship)

public int roll() //rolls two SingleDies (six-sided dies) and returns the result

Roll the dice 752 times and report the percentage of times that a 2, 3, or 12 is rolled (one number). You will need to cast to a double to get the correct percentage (or you will be performing integer division). Call your driver class Craps.java and, in addition to your main method, include the following static method:

public static int playCraps(int num_rolls) //returns the number of times that a 2, 3, or 12 is rolled

Call your playCraps method from within your main method and pass in 752 (as you are rolling the dice 752 times). Also, make sure you convert the value you receive from playCraps into a percentage. Your value should be approximately between 8 and 12 %.

To Compile:

javac Craps.java

To run:

java Craps

Part II: Maze Recursion

First, we’ll show you a demo of what you are trying to accomplish.

Starting Files:

Drawable.java

DrawPanel.java

CenterFrame.java

MazeGUI.java

SimpleDialogs.java

MazeDriver.java

Maze.java //all of your work is in this file

Lab:

Recursion

Return Values

Part I: Maze Recursion

A maze is an excellent application for recursion. From a specific location in the maze (a 2D array of 0s for walls and 1s for paths), make recursive calls for all four possible directions (right, left, up, down) by adding or subtracting to the current row or column. Remember that the call stack maintains the order that methods are called, the values of the local variables for each method call, and where the method call occurred in the calling method. When a direction that has not been tried is explored, mark that location as tried by placing the appropriate integer (from the 5 possible final integers) in the current location within the 2D array (blue in the figure). Marking a direction as tried will prevent the algorithm from exploring that location again later. If there is no solution, every location will eventually be marked as tried, and then the user is informed that there is no solution.

A recursive call in a direction already tried or a direction that is a wall can simply terminate without doing anything (removing themselves from the call stack as there is no solution in that direction). When a particular location has had all four directions leading from that location explored (either walls or directions that have been tried), the algorithm must back track or move to previous locations that have not had all four directions explored. This is easily done by letting the current location’s method terminate and pick up where the previous method call left off. When this occurs, mark as tried (seen in red in the figure below). This previous method may have directions that have not been tried, or may now also be completed, in which case the back tracking continues.

If there is a solution to the maze, eventually the recursive calls will find the solution. The important idea is that once the solution is found, the methods that are still on the method call stack are those methods that led to the solution. All other method calls corresponding to directions that have been tried and led to a dead end have completed and were removed from the call stack. Thus, marking the solution path is trivial. As the methods that led to the solution complete and come off the stack, mark those locations as part of the solution (green in the figure).

Note that you will need to make use of a return value in your recursive calls to the traverse method. Although it is just a boolean, it is an essential component to getting your maze to work. Don’t simply make recursive calls, store what the recursive calls return to you in a variable to help in decision making. In particular, you need to determine whether the current location led to a solution. If so, mark as path and terminate, returning true. Otherwise, try other directions. If all directions have been tried, mark as back track and return false.

Also note that the grid variable is a 2D array representing your maze. To access the number of rows within grid, you will need to access grid.length, and to access the number of columns within your grid, you will need to access grid[index].length.

You will complete two methods in total within Maze.java: solve() & traverse(int row, int column). Solve simply calls traverse, starting from the upper left of grid. Traverse is a recursive function that tests where you are in grid, marks the location appropriately (via one of the 5 final variables), and then recursively calls itself in each direction (up, down, left, and right).

Complete Maze.java. Your red region may look different than mine (why?) but your green region should look the same.

To compile: javac *.java

To run: java MazeDriver

Or you can run the provided batch file: make.bat

Once finished, you should submit the lab on ilearn.
