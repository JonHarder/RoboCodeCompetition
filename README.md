# RoboCodeCompetition
Welcome to the RoboCode competition! RoboCode is a game in which you program a robot in java to fight other
robots using only your wits and bits.

## Prerequisites
* java 8: [download](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)
  Accept the licence aggreement, selecte the **jdk-8u201-macosx-x64.dmg** option
* RoboCode: [download](https://sourceforge.net/projects/robocode/files/latest/download)
* InjelliJ: [download](https://www.jetbrains.com/idea/download/download-thanks.html?platform=mac&code=IIC)

## Resources/Links
* RoboCode Wiki: [link](http://robowiki.net/)
* RoboCode API: [link](https://robocode.sourceforge.io/docs/robocode/robocode/Robot.html)
* RoboCode Game Physics: [link](http://robowiki.net/wiki/Robocode/Game_Physics)
* Java Primer: [link](https://learnxinyminutes.com/docs/java/)


## Starting Bot
Included in this repository in the [src](/src) directory is a starter bot, it implements a few key strategies that most successful bots
employ. The two primary ones are [Wave Surfing](#wave-surfing), and [Guest Factor Targeting](#guess-factor-targeting).


## Concepts
### Wave Surfing
[RoboCode Wiki](http://robowiki.net/wiki/Wave_surfing)

Wave surfing is a technique used to avoid bullets by treating each fired shot as a wave eminating from
the enemy, representing all posible locations the bullet could be as a circle growing from its source,
the enemy robot.

Your starter bot has implemented a basic version of wave surfing, it's up to you to find ways to improve
it and beat your competition.

### Guess Factor Targeting
[RoboCode Wiki](http://robowiki.net/wiki/Guess_Factor)

Guess Factor Targeting is a technique used to record the history of shots fired at an enemy, and learn
which angles used resulted in the most hits. This information is then used to inform where to
aim the next time you take aim at your enemy.

# Getting Started

## Download RoboCode

## Configuring IntelliJ
Once you've downloaded intellij, open it up and open this project.

### Setup the SDK
hit the **Setup SDK** link in the upper right corner of intellij, it should find all of your versions of java,
select *1.8.0_201*

### Set the language level
1. Go to **File** -> **Project Structure...**
2. In the **Project language level** dropdown, select *8 - Lambdas, type annotations etc.*
3. hit **apply**, then **ok**

### Include the RoboCode libraries into the project
1. Go to **File** -> **Project Structure...**
2. On the left nav bar, select **Modules**
3. near the top of the window, select **Dependancies**
4. Hit the + at the bottom of the window, and select the first option: *JARs or directories*
5. in the file explorer, navigate to the folder you installed robocode into, and locate the **libs** folder, finally, select **robocode.jar**
within the libs folder
