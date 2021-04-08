Bowling Scorekeeper
===
The objective is to TEST an application that can calculate the score of a single bowling game.
- There is no graphical user interface.  
- You work ONLY with JUnit test cases in this project.
- You have ONE HOUR to work on this project.
- You are free to consult/use any online resources, including documentations, tutorials, Q&A sites, and any Eclipse built-in tools or plug-ins.
 

**Project Template**  
You are provided with a completed project that contains three classes: `Frame`, `BowlingGame` and `BowlingException`, each contains some fields and methods. DO NOT CHANGE the names and functionalities of the existing fields and methods.

You are expected to create JUnit test cases to verify the behavior of this implementation as thorough as possible based on the following description of a bowling score keeper. Your program should throw `BowlingException` in all error situations. 

**Bowling Score Keeper Task Description**  
The game consists of 10 frames as shown below. In each frame the player has two opportunities to knock down 10 pins. The score for the frame is the total number of pins knocked down, plus bonuses for strikes and spares.

![ExampleImage](https://github.com/ginaBai/UT_BowlingScoreKeeper/blob/master/BowlingScoreKeeper/BowlingScoreKeeperExample.png)

A spare is when the player knocks down all 10 pins in two throws. The bonus for that frame is the number of pins knocked down by the next throw. So in frame 3 of the example game below, the score is 10 (the total number knocked down) plus a bonus of 5 (the number of pins knocked down on the next throw).

A strike is when the player knocks down all 10 pins on his first try. The bonus for that frame is the value of the next two throws. 

In the tenth frame, a player who rolls a spare or strike is allowed to have bonus throws to complete the frame. However, no more than three balls can be rolled in tenth frame.

**Examples**  
[Click for Detailed Rules and Examples of Scoring a Game of Bowling](https://slocums.homestead.com/gamescore.html)

[Online Bowling Game Score Calculator](https://bowlinggenius.com)


# Java Code Coverage Tool
During unit testing, use a Java code coverage tool (e.g., EclEmma or tools that you are familiar with) to measure the executed code. A statement/line coverage of 80% on every non-test class is highly recommended. The following is a tutorial on the EclEmma plugin.

## Setup Instruction
EclEmma comes installed on some versions of Eclipse, such as Eclipse Photon. You may also install EclEmma via Eclipse Marketplace. [Click for the offical installation instruction](https://www.eclemma.org/installation.html)  

- My preferred installation option: Eclipse > Help > Eclipse Marketplace > Search for "EclEmma" > Hit Install for the entry "EclEmma Java Code Coverage" > Follow the steps in the installation wizard

## User Guide
EclEmma records which parts of your Java code are executed during a particular program launch. This technique is called code coverage analysis and typically used with automated testing like JUnit unit tests. It helps to identify untested parts of a code base and improve the corresponding tests. [Click for the official user guide](https://www.eclemma.org/userdoc/index.html)

After you have installed the plugin, you can run the tests via: right click on the project folder BowlingScoreKeeper > Coverage As > JUnit Test. This will display the code coverage in a convenient tree view as well as directly in your code.

![TreeView](https://github.com/ginaBai/UT_BowlingScoreKeeper/blob/master/BowlingScoreKeeper/EclEmmaTreeView.png)

This view shows different coverage metrics (instructions, branches, lines...) and allows drilling-down from project to method level.

![CodeView](https://github.com/ginaBai/UT_BowlingScoreKeeper/blob/master/BowlingScoreKeeper/EclEmmaCodeView.png)

In addition, EclEmma highlights the execution status directly in the Java source editors, where
- Green lines were fully executed. 
  - In this case, the method `score()` is fully tested with the provided example tests (in `test.java`).
- Yellow lines were executed partially only. Little diamonds symbols in the editor's ruler (on the left to the source code), show the execution status of branches in your code. 
  - In this case, 2 of 4 branches missed in line 11, as the provided example tests only checked two branches: 1) `secondThrow > 10` is false , 2) `secondThrow < 0` is false.
- Red lines were not hit at all. 
  - In this case, no exception is thrown given the provided example tests. 

# Additional Reading Materials
[Assertions in JUnit 4 and 5](https://www.baeldung.com/junit-assertions)

[Assert an Exception is Thrown in JUnit 4 and 5](https://www.baeldung.com/junit-assert-exception)
