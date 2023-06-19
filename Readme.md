<a name="br1"></a> 

Hacettepe University

Electrical and Electronics Engineering

ELE432-Advanced Digital Design

Project

Associated Prof. : Prof. Ali Ziya Alkar

İhsan Batuhan Yelken - 21829079

Oğulcan Uğuroğlu - 21828973

Barış Büyükyılmaz - 21828241

Hasan Can Sert - 21828839

30\.05.2023

1



<a name="br2"></a> 

Contents

[1](#br4)

[Quartus](#br4)[ ](#br4)[Software](#br4)

[1.1](#br4)[ ](#br4)[Introduction:](#br4)[ ](#br4). . . . . . . . . . . . . . . . . . . . . . . . . . . . .

[1.2](#br4)[ ](#br4)[How](#br4)[ ](#br4)[to](#br4)[ ](#br4)[Use](#br4)[ ](#br4)[Program:](#br4)[ ](#br4). . . . . . . . . . . . . . . . . . . . . . . .

4

4

4

[2](#br8)

[Introduction](#br8)

8

8

8

[2.1](#br8)[ ](#br8)[Aim](#br8)[ ](#br8)[of](#br8)[ ](#br8)[the](#br8)[ ](#br8)[Project](#br8)[ ](#br8). . . . . . . . . . . . . . . . . . . . . . . . . .

[2.2](#br8)[ ](#br8)[Motivation](#br8)[ ](#br8). . . . . . . . . . . . . . . . . . . . . . . . . . . . . .

[3](#br9)

[4](#br10)

[Background](#br9)[ ](#br9)[Information](#br9)

9

[Methodology](#br10)

10

[4.1](#br10)[ ](#br10)[State](#br10)[ ](#br10)[Logic](#br10)[ ](#br10)[and](#br10)[ ](#br10)[Initialization:](#br10)[ ](#br10). . . . . . . . . . . . . . . . . . . . 10

[4.2](#br10)[ ](#br10)[Clock](#br10)[ ](#br10)[Divider:](#br10)[ ](#br10). . . . . . . . . . . . . . . . . . . . . . . . . . . . 10

[4.3](#br10)[ ](#br10)[Position](#br10)[ ](#br10)[Counters:](#br10)[ ](#br10). . . . . . . . . . . . . . . . . . . . . . . . . . 10

[4.4](#br10)[ ](#br10)[VGA](#br10)[ ](#br10)[Synchronization:](#br10)[ ](#br10). . . . . . . . . . . . . . . . . . . . . . . . 10

[4.5](#br11)[ ](#br11)[Video](#br11)[ ](#br11)[On/Oﬀ](#br11)[ ](#br11)[Control:](#br11)[ ](#br11). . . . . . . . . . . . . . . . . . . . . . . . 11

[4.6](#br11)[ ](#br11)[Drawing](#br11)[ ](#br11)[Objects:](#br11)[ ](#br11). . . . . . . . . . . . . . . . . . . . . . . . . . . 11

[4.7](#br11)[ ](#br11)[Player](#br11)[ ](#br11)[Movements:](#br11)[ ](#br11). . . . . . . . . . . . . . . . . . . . . . . . . . 11

[4.8](#br11)[ ](#br11)[Ball](#br11)[ ](#br11)[Movements:](#br11)[ ](#br11). . . . . . . . . . . . . . . . . . . . . . . . . . . 11

[5](#br13)

[6](#br15)

[7](#br15)

[8](#br17)

[Finite](#br13)[ ](#br13)[State](#br13)[ ](#br13)[Machine](#br13)

[In](#br15)[ ](#br15)[Game](#br15)[ ](#br15)[Footage](#br15)

[Conclusion](#br15)

13

15

15

17

[Appendix:VHDL](#br17)[ ](#br17)[Codes](#br17)

2



<a name="br3"></a> 

List of Figures

[1](#br5)

[2](#br5)

[3](#br6)

[4](#br6)

[5](#br7)

[6](#br7)

[7](#br8)

[8](#br13)

[9](#br15)

[Creating](#br5)[ ](#br5)[a](#br5)[ ](#br5)[new](#br5)[ ](#br5)[project.](#br5)[ ](#br5). . . . . . . . . . . . . . . . . . . . . . .

5

5

6

6

7

7

8

[Device](#br5)[ ](#br5)[select.](#br5)[ ](#br5). . . . . . . . . . . . . . . . . . . . . . . . . . . . .

[Create](#br6)[ ](#br6)[a](#br6)[ ](#br6)[new](#br6)[ ](#br6)[VHDL](#br6)[ ](#br6)[ﬁle.](#br6)[ ](#br6). . . . . . . . . . . . . . . . . . . . . . .

[Compile](#br6)[ ](#br6)[toolbar](#br6)[ ](#br6)[location.](#br6)[ ](#br6). . . . . . . . . . . . . . . . . . . . . .

[Compile](#br7)[ ](#br7)[task](#br7)[ ](#br7)[status.](#br7)[ ](#br7). . . . . . . . . . . . . . . . . . . . . . . . .

[Compilation](#br7)[ ](#br7)[Report.](#br7)[ ](#br7). . . . . . . . . . . . . . . . . . . . . . . . .

[Adding](#br8)[ ](#br8)[.sof](#br8)[ ](#br8)[ﬁle.](#br8)[ ](#br8). . . . . . . . . . . . . . . . . . . . . . . . . . . .

[Pong](#br13)[ ](#br13)[Game](#br13)[ ](#br13)[State](#br13)[ ](#br13)[Machine](#br13)[ ](#br13). . . . . . . . . . . . . . . . . . . . . . 13

[Game](#br15)[ ](#br15)[Scenes](#br15)[ ](#br15). . . . . . . . . . . . . . . . . . . . . . . . . . . . . 15

3



<a name="br4"></a> 

1 Quartus Software

1\.1 Introduction:

Quartus Prime is a software tool produced by Intel; used for the design and

synthesis of digital circuitry in Field Programmable Gate Arrays (FPGAs). It

includes a wide range of utilities that facilitate digital logic design, such as the

ability to handle high-level synthesis, schematic design entry, and text-based

Hardware Description Language (HDL) design entry.

Quartus is available in three versions: Quartus Prime Lite Edition (free), Quar-

tus Prime Standard Edition, and Quartus Prime Pro Edition. These editions

oﬀer a varying range of capabilities, with the Pro Edition being the most feature-

rich.

1\.2 How to Use Program:

To get started with Quartus Prime, follow the steps below:

Installation Download and install Quartus Prime from the oﬃcial Intel

website, choosing the edition that best suits your needs. Make sure your system

meets the software’s hardware requirements.

Implementation of this project achieved using the ﬁles below.

FPGA Software Download Center (intel.com)

Creating a New Project: After installation, open Quartus Prime and

select "New Project Wizard" from the "File" menu. Fill in the requested de-

tails about the project, including the project directory, name, and top-level

design entity. Next, you can specify which FPGA device you’re targeting in the

"Device" page.

4



<a name="br5"></a> 

Figure 1: Creating a new project.

Figure 2: Device select.

Design Entry: For the design entry, you can either use the in-built schematic

editor, text editor for VHDL/Verilog code, or import existing code ﬁles. The

5



<a name="br6"></a> 

Quartus Prime software also supports high-level synthesis using C/C++ or

OpenCL, allowing for easier design of complex hardware systems.

Figure 3: Create a new VHDL ﬁle.

Compilation:After the design entry, click on the "Compile" button. Quar-

tus Prime will then perform several steps including synthesis, ﬁtting, assembly,

and timing analysis. The output will be a binary conﬁguration ﬁle that can be

programmed onto your target FPGA device.

Figure 4: Compile toolbar location.

6



<a name="br7"></a> 

Figure 5: Compile task status.

Debugging and Analysis: Quartus Prime includes tools such as Signal

Tap Logic Analyzer for on-chip debugging, and TimeQuest Timing Analyzer for

comprehensive timing analysis.

Figure 6: Compilation Report.

Booting a Project to the FPGA Board: 1. Connect the FPGA board:

Connect your FPGA board to your computer using the USB-Blaster cable.

2\. Open Quartus Programmer: In Quartus Prime, navigate to "Tools" ->

"Programmer". 3. Select the Programming File: In the Programmer window,

select the .sof ﬁle (generated after a successful compilation) associated with your

project. 4. Program the FPGA: Make sure your FPGA board is selected and

click "Start" to program your FPGA. Note: The steps may vary depending

on the FPGA board you’re using. Refer to the board’s documentation for any

board-speciﬁc instructions.

7



<a name="br8"></a> 

(a) Tools section.

(b) Programmer screen.

Figure 7: Adding .sof ﬁle.

2 Introduction

2\.1 Aim of the Project

The aim of this project extends beyond just creating a game; it’s about melding

hardware and software to construct a rich and engaging interactive experience.

The game is designed to be a digital Pong game, a classic in the realm of

video games, using VGA display technology to render the game interface and

elements. It allows two players to control individual paddles and use them to

hit a ball back and forth on screen. The unique feature of this game is that it

is not created through typical game development software or coding languages

such as C++, Python, or JavaScript. Instead, it is entirely programmed using

VHDL (VHSIC Hardware Description Language), a language primarily used

for describing digital and mixed-signal systems such as Field-Programmable

Gate Arrays (FPGAs) and integrated circuits. The core game logic and screen

rendering processes are all built into the hardware, with VHDL providing the

link between the game logic and the physical display. The victory condition of

the game is based on a points system - a player needs to score 3 points to win.

2\.2 Motivation

This project is primarily driven by academic and professional considerations.

It oﬀers an opportunity to apply abstract ideas from computer engineering to

a real-world task. We want to demonstrate the adaptability and potential of

hardware-oriented programming in actual applications by developing a gaming

experience using VHDL programming and VGA display manipulation. Second,

it’s driven by a desire to use hardware programming to reinvent the beloved

and enduring game Pong. We’re aiming to rediscover the simplicity and charm

of vintage games while investigating new approaches to game development by

using VGA technology for display and VHDL for game logic. For gamers and

8



<a name="br9"></a> 

enthusiasts who enjoy the classics, this nostalgic element is very appealing. Last

but not least, a bigger goal of this project is to spur innovation in the gaming

sector. We’re motivated to investigate how we can advance game development,

going beyond conventional procedures and introducing more hardware-focused

methodologies. With this project, we hope to gain a better understanding of how

hardware and software can work together to produce fresh gaming experiences,

potentially inﬂuencing future trends in game development. In essence, the goal

of this project is to develop a fun and interesting game while also advancing

computer engineering and video game development by showcasing an innovative

method of game development.

3 Background Information

The game makes use of a VGA display to render the gaming environment and

elements. VGA, or Video Graphics Array, is a computing standard that was

developed to display interface hardware for PCs. It deﬁnes both the physical

and logical layout of the display. In this game, the VHDL (VHSIC Hardware

Description Language) is used to create game logic and directly manipulate the

VGA display to create the desired visual output. The provided code includes

various processes that handle diﬀerent aspects of the game:

• Next State Logic:This includes new game initialization and handling of

the visibility of labels for players and game status.

• Clock Division:This handles the synchronization of game actions with

a master clock signal, allowing for accurate timekeeping and movement

within the game.

• Position Counters:These processes manage the vertical and horizontal

positioning of game elements, such as players and the ball.

• Synchronisation: Both horizontal and vertical synchronisation processes

are included to ensure the VGA display correctly represents the game state

and updates in sync with the game logic.

• Video Control: The videoon process enables the video display, control-

ling when the video output (and hence the game) is active.

• Game Element Rendering:The draw process manages the game dis-

play, controlling the colors and visibility of game elements like the players

and the ball.

• Movement Handling: Separate processes handle the movement of both

players and the ball within the game, responding to player inputs and

game logic to move game elements appropriately.

• Scoring: Scoring is calculated within the game logic, and the game ends

when one player reaches a score of 3.

9



<a name="br10"></a> 

This game represents an innovative integration of VHDL programming with

VGA technology to create a unique and engaging gaming experience. The design

considerations for this game focused on the eﬃcient use of resources, as well as

on ensuring the game is fun and intuitive to play.

4 Methodology

This game represents an innovative integration of VHDL programming with

VGA technology to create a unique and engaging gaming experience. The design

considerations for this game focused on the eﬃcient use of resources, as well as

on ensuring the game is fun and intuitive to play.

4\.1 State Logic and Initialization:

The code starts by initializing several variables such as newGame, game-

LabelVisible, p1\_label\_visible, p1\_label\_visible, etc. These variables

control the game state, deﬁning whether a new game has begun or whether

certain labels should be displayed. This section mainly sets the initial state of

these variables, which will later be updated as the game progresses.

4\.2 Clock Divider:

A clock divider is deﬁned, halving the frequency of the input clock. This eﬀec-

tively means that any logic relying on this divided clock signal will operate at a

slower rate. This can be useful for synchronizing diﬀerent parts of your design

or, in this case, controlling the game’s update rate.

4\.3 Position Counters:

Horizontal and vertical position counters are set, incrementing for each rising

edge of the clock. These counters are used to determine the current position

of the game objects and the video signal. The values reset after reaching cer-

tain thresholds deﬁned by display parameters (HD + HFP + HSP + HBP for

horizontal position, and VD + VFP + VSP + VBP for vertical position).

4\.4 VGA Synchronization:

Two processes are set up for horizontal and vertical synchronization of the VGA

(Video Graphics Array) signal. This is essential to ensure that the game’s

display aligns with the monitor’s refresh rate. When the horizontal or vertical

position reaches a speciﬁc range, the synchronization signals hs and vs are set

to low, indicating the beginning of a new line or frame.

10



<a name="br11"></a> 

4\.5 Video On/Oﬀ Control:

The ’video\_on’ process deﬁnes when the video signal is on, which occurs when

the counters are within the visible area of the screen (hPos < HD and vPos <

VD). During this time, game objects can be drawn on the screen.

4\.6 Drawing Objects:

This is where the visuals for the game are created. For each rising edge of the

clock, the draw process is executed, which updates the VGA’s Red, Green, and

Blue signals based on the game’s state and the current positions of objects.

These objects include game labels, player paddles, and the ball.

4\.7 Player Movements:

Two processes (player1\_move and player2\_move) manage player movements

based on speciﬁc inputs (p1\_up and p1\_down for player 1, p2\_up and p2\_down

for player 2). The players’ vertical positions are adjusted according to the inputs

and bounded within the display parameters to prevent them from moving oﬀ-

screen.

4\.8 Ball Movements:

The ball\_move process controls the ball’s movement. The ball’s position is

updated according to its current motion trajectory, and it checks for collisions

with the screen boundaries and the player paddles. When a collision occurs,

the direction of the ball is reversed. Scoring events are also triggered when

the ball reaches the edges of the screen. In conclusion, this code is a thorough

illustration of a game created in VHDL. The game’s state, object positioning,

and graphic rendering on a VGA monitor are all successfully managed by it. The

code demonstrates the usefulness of VHDL in digital system design by showing

how complex interactions and behaviors can be managed using the language.

11



<a name="br12"></a> 

Process Name

Description

Initializes several variables such as newGame,

init

gameLabelVisible,

p1\_label\_visible,

p2\_label\_visible, and sets their initial state.

Deﬁnes a clock divider which halves the frequency

of the input clock.

These are horizontal and vertical position coun-

ters, incrementing for each rising edge of the

clock. They are used to determine the current

position of the game objects and the video sig-

nal.

clk\_divider

hCounter & vCounter

HSync & VSync

video\_on

draw

Two processes are set up for horizontal and verti-

cal synchronization of the VGA (Video Graphics

Array) signal. This ensures that the game’s dis-

play aligns with the monitor’s refresh rate.

Deﬁnes when the video signal is on. This occurs

when the counters are within the visible area of

the screen. During this time, game objects can

be drawn on the screen.

This is where the visuals for the game are created.

For each rising edge of the clock, the draw pro-

cess is executed, which updates the VGA’s Red,

Green, and Blue signals based on the game’s state

and the current positions of objects.

player1\_move & player2\_move These processes manage player movements based

on speciﬁc inputs. The players’ vertical positions

are adjusted according to the inputs and bounded

within the display parameters to prevent them

from moving oﬀ-screen.

ball\_move

Controls the ball’s movement. The ball’s position

is updated according to its current motion trajec-

tory. It also checks for collisions with the screen

boundaries and the player paddles. When a col-

lision occurs, the direction of the ball is reversed.

Scoring events are also triggered when the ball

reaches the edges of the screen.

Table 1: Description of Processes

12



<a name="br13"></a> 

5 Finite State Machine

The diagram visualizes the transitions between diﬀerent states of the game and

the conditions that trigger these transitions.

Figure 8: Pong Game State Machine

MENU: This is the initial state when the game is turned on. From this

state, if the switch (SW) is turned on (SW=’1’), the state machine stays in the

MENU state, indicating that the game is in idle state waiting for user input. If

the switch is turned oﬀ (SW=’0’), the FSM transitions to the INITIAL state,

starting the game.

INITIAL: This is the setup state of the game, where all parameters are

initialized. From this state, when any key is pressed (press any key), the state

transitions to the GAME state, and the game begins.

GAME: This is the main state where the game is in progress. The game

continues to stay in this state until a player scores 4 points. If Player 1 scores 4

points ﬁrst (p1\_score = 4), the state transitions to the P1\_W state, indicating

Player 1’s victory. Conversely, if Player 2 scores 4 points ﬁrst (p2\_score = 4),

the state transitions to the P2\_W state, indicating Player 2’s victory.

P1\_W and P2\_W: These are the win states for Player 1 and Player 2

respectively. When a player wins, the FSM transitions to the respective win

state. From these states, if switch 2 (SW2) is turned on (SW2 = ’1’), the FSM

13



<a name="br14"></a> 

transitions back to the MENU state, allowing a new game to start.

There are additional self-loops in each state except the win states, indicating

that the FSM stays in its current state unless a transition condition is met.

This design was chosen to ensure a smooth ﬂow of gameplay with clear

transitions between states. It provides a straightforward representation of the

game’s progression, from starting at the MENU to a player winning, and then

returning to the MENU for a new game. This makes the game easily under-

standable and user-friendly.

It also allows ﬂexibility in the game. For example, by adjusting the score

at which a player wins, the length of a game can be modiﬁed. This state

machine design encapsulates the entire functionality of the Pong game, making

it a powerful tool for understanding and modifying the game.

14



<a name="br15"></a> 

6 In Game Fo otage

(a) Start Screen

(b) Game Screen

(c) Player 1 Won Screen

(d) Player 2 Won Screen

Figure 9: Game Scenes

7 Conclusion

This FPGA-based Pong game project’s successful completion serves as an im-

pressive case study showcasing the capabilities of FPGA programming for inter-

active, graphical applications. We have successfully illustrated the adaptability

and power of FPGA in digital system design and implementation by implement-

ing a simple video game with recognisable gameplay and graphical elements.

Including real-time user input, collision detection, and a scoring mechanism,

the project has successfully incorporated all of the key components of the Pong

game. According to the ﬁndings, responsiveness, dependability, and accuracy

were all displayed in a satisfactory manner. This accomplishment highlights

the value of FPGA as a ﬂexible platform for creating appealing, user-friendly

15



<a name="br16"></a> 

applications. It also demonstrates how a simple game like Pong can be used

as a teaching aid for the fundamental ideas of FPGA programming and digital

system design.

Future work involving more complex systems can be built upon the experi-

ences and insights from this project. It has given a foundation for comprehend-

ing and putting VHDL coding and hardware-software integration principles into

practice. The foundation of a video game is now established, but there is still

room for improvement through the integration of more complex user interfaces,

the addition of complicated game features, and improved graphics.

In conclusion, this project is more than just a test of an FPGA’s ability to

recreate a vintage arcade game. It is evidence of the enormous potential and op-

portunities provided by FPGA programming. As technology develops, we can

continue to push the limits of what is possible with FPGAs, from improving

video game designs to creating complex digital systems that can spur techno-

logical innovation in a variety of industries. This project serves as an example

of how the knowledge gained from a game as basic as Pong can be applied to

the complex issues involved in designing digital systems.

16



<a name="br17"></a> 




