# RoboCodeCompetition
Welcome to the RoboCode competition! Robocode is a game in which you program a robot in java to fight other
robots using only your wits and bits.

## Prerequisites
* java 8: [download](https://download.oracle.com/otn-pub/java/jdk/8u201-b09/42970487e3af4f5aa5bca3f542482c60/jdk-8u201-macosx-x64.dmg)
* RoboCode: [download](https://sourceforge.net/projects/robocode/files/latest/download)
* InjelliJ: [download](https://www.jetbrains.com/idea/download/download-thanks.html?platform=mac&code=IIC)

## Resources/Links
* RoboCode Wiki: [link](http://robowiki.net/)
* RoboCode API: [link](https://robocode.sourceforge.io/docs/robocode/robocode/Robot.html)
* Java Primer: [link](https://learnxinyminutes.com/docs/java/)


## Starting Bot
Included in this repository in the [src](/src) directory is a starter bot, it implements a few key strategies that most successful bots
employ. The two primary ones are [Wave Surfing](#Wave Surfing), and [Guest Factor Targeting](#Guess Factor Targeting).


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
