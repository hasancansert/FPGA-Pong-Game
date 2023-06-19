![image](logo.png){width="4cm" height="6cm"} []{#fig:my_label
label="fig:my_label"}

# Quartus Software

## Introduction:

Quartus Prime is a software tool produced by Intel; used for the design
and synthesis of digital circuitry in Field Programmable Gate Arrays
(FPGAs). It includes a wide range of utilities that facilitate digital
logic design, such as the ability to handle high-level synthesis,
schematic design entry, and text-based Hardware Description Language
(HDL) design entry.\
Quartus is available in three versions: Quartus Prime Lite Edition
(free), Quartus Prime Standard Edition, and Quartus Prime Pro Edition.
These editions offer a varying range of capabilities, with the Pro
Edition being the most feature-rich.\

## How to Use Program:

To get started with Quartus Prime, follow the steps below:\
**Installation** Download and install Quartus Prime from the official
Intel website, choosing the edition that best suits your needs. Make
sure your system meets the software's hardware requirements.\
Implementation of this project achieved using the files below.\
FPGA Software Download Center (intel.com)\
**Creating a New Project:** After installation, open Quartus Prime and
select \"New Project Wizard\" from the \"File\" menu. Fill in the
requested details about the project, including the project directory,
name, and top-level design entity. Next, you can specify which FPGA
device you're targeting in the \"Device\" page.

![Creating a new project.](creating a new project.png){#fig:my_label
width="\\linewidth"}

![Device select.](creating2.png){#fig:my_label}

**Design Entry:** For the design entry, you can either use the in-built
schematic editor, text editor for VHDL/Verilog code, or import existing
code files. The Quartus Prime software also supports high-level
synthesis using C/C++ or OpenCL, allowing for easier design of complex
hardware systems.

![Create a new VHDL file.](creating3.png){#fig:my_label}

**Compilation:**After the design entry, click on the \"Compile\" button.
Quartus Prime will then perform several steps including synthesis,
fitting, assembly, and timing analysis. The output will be a binary
configuration file that can be programmed onto your target FPGA device.

![Compile toolbar location.](compile.png){#fig:my_label}

![Compile task status.](compailer2.png){#fig:my_label}

**Debugging and Analysis:** Quartus Prime includes tools such as Signal
Tap Logic Analyzer for on-chip debugging, and TimeQuest Timing Analyzer
for comprehensive timing analysis.

![Compilation Report.](debugging and analysis.png){#fig:my_label}

**Booting a Project to the FPGA Board:** 1. Connect the FPGA board:
Connect your FPGA board to your computer using the USB-Blaster cable. 2.
Open Quartus Programmer: In Quartus Prime, navigate to \"Tools\" -\>
\"Programmer\". 3. Select the Programming File: In the Programmer
window, select the .sof file (generated after a successful compilation)
associated with your project. 4. Program the FPGA: Make sure your FPGA
board is selected and click \"Start\" to program your FPGA. Note: The
steps may vary depending on the FPGA board you're using. Refer to the
board's documentation for any board-specific instructions.

![Tools section.](booting a project.png){#fig:sub1
width=".9\\linewidth"}

![Programmer screen.](booting a project2.png){#fig:sub1
width=".6\\linewidth"}

# Introduction

## Aim of the Project

The aim of this project extends beyond just creating a game; it's about
melding hardware and software to construct a rich and engaging
interactive experience. The game is designed to be a digital Pong game,
a classic in the realm of video games, using VGA display technology to
render the game interface and elements. It allows two players to control
individual paddles and use them to hit a ball back and forth on screen.
The unique feature of this game is that it is not created through
typical game development software or coding languages such as C++,
Python, or JavaScript. Instead, it is entirely programmed using VHDL
(VHSIC Hardware Description Language), a language primarily used for
describing digital and mixed-signal systems such as Field-Programmable
Gate Arrays (FPGAs) and integrated circuits. The core game logic and
screen rendering processes are all built into the hardware, with VHDL
providing the link between the game logic and the physical display. The
victory condition of the game is based on a points system - a player
needs to score 3 points to win.

## Motivation

This project is primarily driven by academic and professional
considerations. It offers an opportunity to apply abstract ideas from
computer engineering to a real-world task. We want to demonstrate the
adaptability and potential of hardware-oriented programming in actual
applications by developing a gaming experience using VHDL programming
and VGA display manipulation. Second, it's driven by a desire to use
hardware programming to reinvent the beloved and enduring game Pong.
We're aiming to rediscover the simplicity and charm of vintage games
while investigating new approaches to game development by using VGA
technology for display and VHDL for game logic. For gamers and
enthusiasts who enjoy the classics, this nostalgic element is very
appealing. Last but not least, a bigger goal of this project is to spur
innovation in the gaming sector. We're motivated to investigate how we
can advance game development, going beyond conventional procedures and
introducing more hardware-focused methodologies. With this project, we
hope to gain a better understanding of how hardware and software can
work together to produce fresh gaming experiences, potentially
influencing future trends in game development. In essence, the goal of
this project is to develop a fun and interesting game while also
advancing computer engineering and video game development by showcasing
an innovative method of game development.

# Background Information

The game makes use of a VGA display to render the gaming environment and
elements. VGA, or Video Graphics Array, is a computing standard that was
developed to display interface hardware for PCs. It defines both the
physical and logical layout of the display. In this game, the VHDL
(VHSIC Hardware Description Language) is used to create game logic and
directly manipulate the VGA display to create the desired visual output.
The provided code includes various processes that handle different
aspects of the game:

-   **Next State Logic:**This includes new game initialization and
    handling of the visibility of labels for players and game status.

-   **Clock Division:**This handles the synchronization of game actions
    with a master clock signal, allowing for accurate timekeeping and
    movement within the game.

-   **Position Counters:**These processes manage the vertical and
    horizontal positioning of game elements, such as players and the
    ball.

-   **Synchronisation:** Both horizontal and vertical synchronisation
    processes are included to ensure the VGA display correctly
    represents the game state and updates in sync with the game logic.

-   **Video Control:** The videoon process enables the video display,
    controlling when the video output (and hence the game) is active.

-   **Game Element Rendering:**The draw process manages the game
    display, controlling the colors and visibility of game elements like
    the players and the ball.

-   **Movement Handling:** Separate processes handle the movement of
    both players and the ball within the game, responding to player
    inputs and game logic to move game elements appropriately.

-   **Scoring:** Scoring is calculated within the game logic, and the
    game ends when one player reaches a score of 3.

This game represents an innovative integration of VHDL programming with
VGA technology to create a unique and engaging gaming experience. The
design considerations for this game focused on the efficient use of
resources, as well as on ensuring the game is fun and intuitive to play.

# Methodology

This game represents an innovative integration of VHDL programming with
VGA technology to create a unique and engaging gaming experience. The
design considerations for this game focused on the efficient use of
resources, as well as on ensuring the game is fun and intuitive to play.

## State Logic and Initialization:

The code starts by initializing several variables such as **newGame**,
**gameLabelVisible**, **p1_label_visible**, **p1_label_visible**, etc.
These variables control the game state, defining whether a new game has
begun or whether certain labels should be displayed. This section mainly
sets the initial state of these variables, which will later be updated
as the game progresses.

## Clock Divider:

A clock divider is defined, halving the frequency of the input clock.
This effectively means that any logic relying on this divided clock
signal will operate at a slower rate. This can be useful for
synchronizing different parts of your design or, in this case,
controlling the game's update rate.

## Position Counters:

Horizontal and vertical position counters are set, incrementing for each
rising edge of the clock. These counters are used to determine the
current position of the game objects and the video signal. The values
reset after reaching certain thresholds defined by display parameters
(HD + HFP + HSP + HBP for horizontal position, and VD + VFP + VSP + VBP
for vertical position).

## VGA Synchronization:

Two processes are set up for horizontal and vertical synchronization of
the VGA (Video Graphics Array) signal. This is essential to ensure that
the game's display aligns with the monitor's refresh rate. When the
horizontal or vertical position reaches a specific range, the
synchronization signals **hs** and **vs** are set to low, indicating the
beginning of a new line or frame.

## Video On/Off Control:

The 'video_on' process defines when the video signal is on, which occurs
when the counters are within the visible area of the screen (hPos \< HD
and vPos \< VD). During this time, game objects can be drawn on the
screen.

## Drawing Objects:

This is where the visuals for the game are created. For each rising edge
of the clock, the draw process is executed, which updates the VGA's Red,
Green, and Blue signals based on the game's state and the current
positions of objects. These objects include game labels, player paddles,
and the ball.

## Player Movements:

Two processes (player1_move and player2_move) manage player movements
based on specific inputs (p1_up and p1_down for player 1, p2_up and
p2_down for player 2). The players' vertical positions are adjusted
according to the inputs and bounded within the display parameters to
prevent them from moving offscreen.

## Ball Movements:

The ball_move process controls the ball's movement. The ball's position
is updated according to its current motion trajectory, and it checks for
collisions with the screen boundaries and the player paddles. When a
collision occurs, the direction of the ball is reversed. Scoring events
are also triggered when the ball reaches the edges of the screen. In
conclusion, this code is a thorough illustration of a game created in
VHDL. The game's state, object positioning, and graphic rendering on a
VGA monitor are all successfully managed by it. The code demonstrates
the usefulness of VHDL in digital system design by showing how complex
interactions and behaviors can be managed using the language.

::: {#tab:processes}
        **Process Name**        **Description**
  ----------------------------- --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
              init              Initializes several variables such as newGame, gameLabelVisible, p1_label_visible, p2_label_visible, and sets their initial state.
           clk_divider          Defines a clock divider which halves the frequency of the input clock.
       hCounter & vCounter      These are horizontal and vertical position counters, incrementing for each rising edge of the clock. They are used to determine the current position of the game objects and the video signal.
          HSync & VSync         Two processes are set up for horizontal and vertical synchronization of the VGA (Video Graphics Array) signal. This ensures that the game's display aligns with the monitor's refresh rate.
            video_on            Defines when the video signal is on. This occurs when the counters are within the visible area of the screen. During this time, game objects can be drawn on the screen.
              draw              This is where the visuals for the game are created. For each rising edge of the clock, the draw process is executed, which updates the VGA's Red, Green, and Blue signals based on the game's state and the current positions of objects.
   player1_move & player2_move  These processes manage player movements based on specific inputs. The players' vertical positions are adjusted according to the inputs and bounded within the display parameters to prevent them from moving off-screen.
            ball_move           Controls the ball's movement. The ball's position is updated according to its current motion trajectory. It also checks for collisions with the screen boundaries and the player paddles. When a collision occurs, the direction of the ball is reversed. Scoring events are also triggered when the ball reaches the edges of the screen.

  : Description of Processes
:::

[]{#fig:my_label label="fig:my_label"}

# Finite State Machine

The diagram visualizes the transitions between different states of the
game and the conditions that trigger these transitions.

![Pong Game State Machine](state_machine.png){#fig:my_label
width="\\linewidth"}

**MENU:** This is the initial state when the game is turned on. From
this state, if the switch (SW) is turned on (SW='1'), the state machine
stays in the MENU state, indicating that the game is in idle state
waiting for user input. If the switch is turned off (SW='0'), the FSM
transitions to the INITIAL state, starting the game.\
**INITIAL:** This is the setup state of the game, where all parameters
are initialized. From this state, when any key is pressed (press any
key), the state transitions to the GAME state, and the game begins.\
**GAME:** This is the main state where the game is in progress. The game
continues to stay in this state until a player scores 4 points. If
Player 1 scores 4 points first (p1_score = 4), the state transitions to
the P1_W state, indicating Player 1's victory. Conversely, if Player 2
scores 4 points first (p2_score = 4), the state transitions to the P2_W
state, indicating Player 2's victory.\
**P1_W and P2_W:** These are the win states for Player 1 and Player 2
respectively. When a player wins, the FSM transitions to the respective
win state. From these states, if switch 2 (SW2) is turned on (SW2 =
'1'), the FSM transitions back to the MENU state, allowing a new game to
start.\
There are additional self-loops in each state except the win states,
indicating that the FSM stays in its current state unless a transition
condition is met.\
This design was chosen to ensure a smooth flow of gameplay with clear
transitions between states. It provides a straightforward representation
of the game's progression, from starting at the MENU to a player
winning, and then returning to the MENU for a new game. This makes the
game easily understandable and user-friendly.\
It also allows flexibility in the game. For example, by adjusting the
score at which a player wins, the length of a game can be modified. This
state machine design encapsulates the entire functionality of the Pong
game, making it a powerful tool for understanding and modifying the
game.

# In Game Footage

![Start Screen](start.jpg){#fig:sub1 width=".6\\linewidth"}

![Game Screen](game.jpg){#fig:sub2 width=".6\\linewidth"}

![Player 1 Won Screen](player1won.jpg){#fig:sub2 width=".7\\linewidth"}

![Player 2 Won Screen](player2won.jpg){#fig:sub2 width=".6\\linewidth"}

# Conclusion

This FPGA-based Pong game project's successful completion serves as an
impressive case study showcasing the capabilities of FPGA programming
for interactive, graphical applications. We have successfully
illustrated the adaptability and power of FPGA in digital system design
and implementation by implementing a simple video game with recognisable
gameplay and graphical elements.\
Including real-time user input, collision detection, and a scoring
mechanism, the project has successfully incorporated all of the key
components of the Pong game. According to the findings, responsiveness,
dependability, and accuracy were all displayed in a satisfactory manner.
This accomplishment highlights the value of FPGA as a flexible platform
for creating appealing, user-friendly applications. It also demonstrates
how a simple game like Pong can be used as a teaching aid for the
fundamental ideas of FPGA programming and digital system design.\
Future work involving more complex systems can be built upon the
experiences and insights from this project. It has given a foundation
for comprehending and putting VHDL coding and hardware-software
integration principles into practice. The foundation of a video game is
now established, but there is still room for improvement through the
integration of more complex user interfaces, the addition of complicated
game features, and improved graphics.\
In conclusion, this project is more than just a test of an FPGA's
ability to recreate a vintage arcade game. It is evidence of the
enormous potential and opportunities provided by FPGA programming. As
technology develops, we can continue to push the limits of what is
possible with FPGAs, from improving video game designs to creating
complex digital systems that can spur technological innovation in a
variety of industries. This project serves as an example of how the
knowledge gained from a game as basic as Pong can be applied to the
complex issues involved in designing digital systems.\
