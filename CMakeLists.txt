cmake_minimum_required(VERSION 3.0) # Specify the minimum version for CMake
project(dp) # Project's name

enable_testing()

# The following folder will be included
# include_directories("${PROJECT_SOURCE_DIR}")
include_directories(${CMAKE_CURRENT_SOURCE_DIR})

# set(SOURCE hello.cpp SOLID/ocp.cpp SOLID/srp.cpp SOLID/lsp.cpp SOLID/isp.cpp SOLID/dip.cpp ) # add more files
set(CMAKE_CXX_FLAGS "-Wall -std=c++14 -DCXX11")
# set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} /std:c++17") #warning: decomposition declarations are a C++1z extension [-Wc++1z-extensions]


add_subdirectory(SOLID)
add_subdirectory(adapter)
add_subdirectory(builder)
add_subdirectory(factories)
add_subdirectory(prototype)
add_subdirectory(singleton)
add_subdirectory(bridge)
add_subdirectory(decorator)
add_subdirectory(composite) 
add_subdirectory(flyweight)
add_subdirectory(facade)
add_subdirectory(chainofresponsibilty)
add_subdirectory(command)
add_subdirectory(interpreter)
add_subdirectory(iterator)
add_subdirectory(mediator)
add_subdirectory(state)
add_subdirectory(strategy)
add_subdirectory(templatemethod)
add_subdirectory(visitor)

# add_executable(${PROJECT_NAME} ${SOURCE})
add_executable(${PROJECT_NAME} hello.cpp)
target_link_libraries(${PROJECT_NAME} libsolid libadapter libbuilder libcomposite libfacade libfactories libprototype libsingleton libbridge libdecorator libflyweight libchainofresponsibility libcommand libinterpreter libiterator libmediator libstate libstrategy libtemplatemethod libvisitor)


# sets GTEST_INCLUDE_DIRS and GTEST_LIBRARIES
find_package( GTest REQUIRED )      

# adds the gtest include directory
include_directories( ${GTEST_INCLUDE_DIRS} )

# links gtest
target_link_libraries( ${PROJECT_NAME}  ${GTEST_LIBRARIES} )

# Set the output folder where your program will be created
set(CMAKE_BINARY_DIR ${CMAKE_SOURCE_DIR}/bin)
set(EXECUTABLE_OUTPUT_PATH ${CMAKE_BINARY_DIR})
set(LIBRARY_OUTPUT_PATH ${CMAKE_BINARY_DIR})











##############################################################





