cmake_minimum_required(VERSION  "3.18.3")
project ("MyProject")	# The name of the project.

add_executable("${PROJECT_NAME}" "Main.cpp")	# The executable required to create the project.


set(CMAKE_INSTALL_PREFIX "D:/")
message("The value of STRING_VARIABLE is: ${CMAKE_INSTALL_PREFIX}" )

install(TARGETS MyProject DESTINATION bin) # ${CMAKE_INSTALL_PREFIX}/bin
install(FILES "Main.cpp" "Other.cpp" "CMakeLists.txt" DESTINATION src) #${CMAKE_INSTALL_PREFIX}/src

include(CTest)

add_test(test1, "${PROJECT_BINARY_DIR}/${PROJECT_NAME}") # This test shall pass!
add_test(test2, "${PROJECT_BINARY_DIR}/${PROJECT_NAME}" "someparameter") # This test shall not pass!
