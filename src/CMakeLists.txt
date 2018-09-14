add_executable(gaia main.cpp) # The main executable
add_library(gaia-lib hello_world.cpp) # A library for tests

SET_TARGET_PROPERTIES(gaia-lib PROPERTIES PREFIX "") # Remove the lib prefix

target_link_libraries(gaia gaia-lib) # Link our sources to the executable

install(TARGETS gaia DESTINATION bin)
install(TARGETS gaia-lib
    ARCHIVE DESTINATION lib
    LIBRARY DESTINATION lib
    RUNTIME DESTINATION bin
)
