cmake_minimum_required(VERSION "3.21")

project("Assessment")
add_subdirectory(test)
add_executable("${PROJECT_NAME}" main.cpp  day1.cpp StringHelper.cpp FileLoader.cpp )


