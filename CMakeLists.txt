#########  #       #  ########  #########  #########                                    
#       #  #       #  #             #      #       #                         
#       #  #       #  #             #      #       #                            
#       #  #       #  #             #      #       #                       
#       #  #       #  #             #      #       #             << CMAKE CONFIGURATION FILE FOR THE PROJECT >>   
#########  #       #  ########      #      #       #                              
#       #  #       #         #      #      #       #                          
#       #  #       #         #      #      #       #                                     
#       #  #       #         #      #      #       #                                    
#       #  #########  ########      #      #########_______________________________________________________________________________________________________4
#__________________________________________________________________________________________________________________________________________________________
#__________________________________________________________________________________________________________________________________________________________
#__________________________________________________________________________________________________________________________________________________________
#__________________________________________________________________________________________________________________________________________________________
#__________________________________________________________________________________________________________________________________________________________


cmake_minimum_required(VERSION 3.2)

# Regured packages are defined here
project(ComputerVision_lvl2)
find_package( OpenCV REQUIRED )
#if this project only uses opencv... delete this if you dont dont have dlib
# but if you do have dlib.... change the path to your dlib path
add_subdirectory(C:/dlib-19.24/dlib dlib_build)
# optional tho...include directories
include_directories((src/include))

# add the executables for the project
add_executable(Runner
  main.cpp
   )

# the targeted link libraries...
target_link_libraries( Runner ${OpenCV_LIBS} )
target_link_libraries( Runner dlib::dlib )

#dunno what this does....
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++17")