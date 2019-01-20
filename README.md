# RoboCodeCompetition
Welcome to the RoboCode competition! RoboCode is a game in which you program a robot in java to fight other
robots using only your wits and bits.

## Prerequisites
* java 8: [download](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)
  Accept the licence aggreement, selecte the **jdk-8u201-macosx-x64.dmg** option
* RoboCode: [download](https://sourceforge.net/projects/robocode/files/latest/download)
* Gradle: `brew install gradle`
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

## Make your own bot
### Fork this codebase
#### Give the project and your bot a name unique to you.
For the rest of this documentation, **starterbot** is my package name, and **StarterBot** is my class name, you should come up with your own
and fill them in whenever you see a reference to **package** or **class**.
#### Clone your forked copy to your computer
#### Edit the `build.gradle` file with an updated reference to the `robocode.jar` file

``` gradle
dependencies {
    compile files('PATH_TO_YOUR_ROBOCODE_FOLDER/robocode/libs/robocode.jar')
}
```

#### Edit the properties file
In `/src/main/resources/`, you'll find a folder called `starterbot`
* Rename it from `starterbot` to your **package** name.
* Rename the file within that folder from `StarterBot.properties` to **class**.properties, replacing **class** with the name of the bot you've picked out
* within the file, change the value for `robot.description` to a brief description of your bot
* change the value for `robot.author.name` to you
* change the value for `robot.classname` to **package**.**class**, using whatever name you've picked out
* change the value for `uuid` to a random uuid, I suggest grabbing one from [here](https://www.uuidgenerator.net/)

#### Renaming java things
Navigate to `/src/main/java/`, you should see one folder there called starterbot, rename it to **package**.

within this folder, you should see two files, `EnemyWave.java`, and `StarterBot.java`

##### EnemyWave.java
All you should need to change in this file is the first line, where it lists the package name, change it from

``` java
package starterbot;
```

to

``` java
package YOUR_PACKAGE_NAME;
```

##### StarterBot.java
Rename this file to **class**.java, using the class name you picked out.

within, like for EnemyWave.java, replace the first line, specifying the package name to your **package** name.

Next, change the line opening the `StarterBot` class, changing `public class StarterBot extends AdvancedRobot {` to
`public class YOUR_CLASS_NAME extends AdvancedRobot {`

There are a few references to **StarterBot** in some comments, you can change them to your bots name if you wish, keeping
it as is won't impact your bot at all.

##### Naming your project
open `settings.gradle`, and change the value for `rootProject.name` to something unique, this will ultimately be the
prefix for the name of the jar that gradle will create.

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
6. hit **apply**, then **ok**


## Compiling your bot
from the command line, at the root of (your forked version of) this project, run

``` shell
gradle build
```

the output should have gone into a folder called `build`, with the final runnable jar file in a `libs` folder within the
build directory.


## Running your bot
You have a few options here, using gradle to build the project will produce both the class files, and the final jar file.

Open robocode by navigating to the robocode folder in the terminal and execute the `robocode.sh` script
``` shell
./robocode.sh
```

Regardles of which option offered below you end up choosing, to run an actual battle is the same.

1. Click **Battle** -> **New**
2. In the left-most column, there should called your **package** name, click it and then click **Add ->**
3. Find another bot, then click **Add ->** for that one as well
4. Then, click **Start Battle**
5. Enjoy

### Manual Import
In robocode

1. click **Options** -> **Clean robot cache**
2. **Robot** -> **Import robot or team**
3. in the file browser, navigate to (your forked copy of) this project, and select the jar file in `/build/libs/`

### Linking your project class files into robocode
In robocode

1. click **Options** -> **Preferences**
2. Select the **Development Options** tab, and click **Add**
3. In the file browser, navigate to this project, and then navigate to `/build/classes/java/main/` and select the folder there, it should be your **package** name


# TODO
* ~~configure robocode to external bot, linked to your forked copy of this repo (so you dont have to *clear cache*, *import*, *browse*, etc.)~~
* ~~rename project in build.gradle?~~
* Implement Guess Factor Targeting
* Send your jar file to ($somewhere)
* Battle server you can updload bots to (backend to run battles, front end to view results, select specific contenstants)
