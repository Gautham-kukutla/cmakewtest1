include_directories(${gtest_SOURCE_DIR}/include)

add_executable(mytest day1-gtests.cpp day1.cpp)
target_link_libraries(mytest gtest_main)
