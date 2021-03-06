####################################################
# CMake is a build file generator.
# It does not compile your software, but
# rather uses the CMake Language to 
# figure out how to generate another file
# for which you can then use to build projects.
# CMake is a specification language for build tools.
####################################################

############### INSTALLATION #######################
# Installation on Mac
# 'brew install cmake'
#
# Installation on Linux
# 'sudo apt-get install cmake'
#
# Installation on Windows
# See download page and download
####################################################

############## How to use CMake ####################
# I recommend you create a separate directory for
# your CMake generated files. This is a clean way
# to separate out all of your binary files generated
# from the source code. An example on Linux is
# the following:
#
# mkdir bin	# Make a directory
# cd bin	# navigate to that directory
# cmake .. 	# Then execute the CMakeLists.txt
#		# file found one directory up.
####################################################

####################################################
# Writing a CMake file involves writing one
# cmake command per line.

# The minimum required version of CMake to use
cmake_minimum_required(VERSION 3.10)

# Set the project name to your project name
# Additionally, we specify the languages we need
# to use with our project 'App' which happen
# to be 'C++' (CXX), and 'C' is also included
# just in case we mix C in our C++ code
project(
        paintProgram    # Name of our application
        VERSION 1.0     # Version of our software
        LANGUAGES CXX)  # Language that we are using

# Set the langauge standard for
# C++
set(CMAKE_CXX_STANDARD 17)


# Where are the include directories
include_directories("/usr/local/include/")
include_directories("/usr/include/")
include_directories("./include/")


# Link library directories
link_directories("/usr/local/lib")

# Add the source code files
add_executable(App ./src/App.cpp ./src/Draw.cpp ./src/Command.cpp
        ./src/UDPNetworkServer.cpp ./src/UDPNetworkClient.cpp
        ./src/Packet.cpp ./src/main.cpp ./src/FillDisplay.cpp)

add_executable(App_Test ./src/App.cpp ./src/Draw.cpp ./src/Command.cpp
        ./src/UDPNetworkServer.cpp ./src/UDPNetworkClient.cpp
        ./src/Packet.cpp ./tests/main_test.cpp ./src/FillDisplay.cpp)

# Add the libraries
target_link_libraries(App sfml-graphics sfml-window sfml-system sfml-network "-framework OpenGL")

target_link_libraries(App_Test sfml-graphics sfml-window sfml-system sfml-network "-framework OpenGL")
