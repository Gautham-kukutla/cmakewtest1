include_directories(${gtest_SOURCE_DIR}/include)

add_executable(mytest day1-gtests.cpp)
target_include_directories(mytest PRIVATE CMAKE_SOURCE_DIR)
target_link_libraries(mytest gtest_main)
