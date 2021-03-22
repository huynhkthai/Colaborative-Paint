# Building Software

- [ ] Instructions on how to build your software should be written in this file
	- This is especially important if you have added additional dependencies.
	- Assume someone who has not taken this class (i.e. you on the first day) would have read, build, and run your software from scratch.
- You should have at a minimum in your project
	- [ ] A CMakeLists.txt in a root directory
    	- [ ] This should generate a 'release' version of your software
  - [ ] Run your code with the latest version of cppcheck before commiting your code (could be a github action)
  - [ ] (Optional) Run your code with the latest version of clang-tidy  (could be a github action)

*Modify this file to include instructions on how to build and run your software. Specify which platform you are running on. Running your software involves launching a server and connecting at least 2 clients to the server.*


# Instructions for Building Software:
This software is built to run on a Mac OS platform. It is easiest to build this software using CMake. To build the software: 
1. Move to the Final_App/bin/ directory on the command line, then type **"cmake .."** into the command line. 
2. Type **"make"**
3. Finally type **"./App"** to launch the program, or **"./App_Test"** to launch tests. The CMakeLists.txt file in the root directory of this project includes all specifications necessary to use CMake to build the app.

(Download CMake here: https://cmake.org/download/)

# Running from command line without CMake
To run the program from the command line without CMake on a Mac, go into the "Final_App" main directory and enter: <br><br>
**"clang++ ./src/App.cpp ./src/Draw.cpp ./src/Command.cpp ./src/UDPNetworkServer.cpp ./src/UDPNetworkClient.cpp ./src/Packet.cpp ./src/main.cpp ./src/FillDisplay.cpp -o App -I./include/ -lsfml-graphics -lsfml-window -lsfml-system -lsfml-network -framework OpenGL -std=c++17". <br>** Then, enter **"./App"**

**"clang++ ./src/App.cpp ./src/Draw.cpp ./src/Command.cpp ./src/UDPNetworkServer.cpp ./src/UDPNetworkClient.cpp ./src/Packet.cpp ./tests/main_test.cpp ./src/FillDisplay.cpp -o App_Test -I./include/ -lsfml-graphics -lsfml-window -lsfml-system -lsfml-network -framework OpenGL -std=c++17". <br>** Then, enter **"./App_Test"**

# Dependencies
This program depends on Nuklear and the SFML API to render its window. If you have any questions regarding Nuklear and SFML, please see their documentation. This project directory contains headers for nuklear.h and nuklear_sfml_g2.h (a header that integrates Nuklear with SFML functionality on Mac devices). It is necessary to download SFML on your device to run this program. Link: https://www.sfml-dev.org/download.php

# Testing
Testing in main_test.cpp runs on a Catch2 framework. You will need to download Catch2 to run these tests. Otherwise, compile:
**"clang++ ./src/App.cpp ./src/Draw.cpp ./src/Command.cpp ./src/UDPNetworkServer.cpp ./src/UDPNetworkClient.cpp ./src/Packet.cpp ./tests/main_test.cpp ./src/FillDisplay.cpp -o App_Test -I./include/ -lsfml-graphics -lsfml-window -lsfml-system -lsfml-network -framework OpenGL -std=c++17". <br>** Then, enter **"./App_Test"**
to run the tests.

# Launching server and connecting clients
A paint program server must be launched before clients (users) can connect to the server. To start the server, simply type "./App" in the command line. You will be prompted to indicate whether you wish to run the program as a server or client. Enter "s" for server.

To connect as a client, open a new command line window, follow "Instructions for Building Software" above, type "./App" to launch the program, and then when prompted with the question of whether you wish to run as server or client, select "c" for client.
