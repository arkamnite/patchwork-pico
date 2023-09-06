add_executable(game
    main.cpp
)

# function(copy_binary target)
#     add_custom_command(
#         TARGET ${target}
#         POST_BUILD
#         COMMAND ${CMAKE_COMMAND} -E copy_
#     )
# end function()
add_custom_command(
    TARGET game
    POST_BUILD
    COMMAND
    ${CMAKE_COMMAND} -E copy
        ${CMAKE_BINARY_DIR}/src/game.uf2
        /Volumes/RPI-RP2
)
# Pull in common dependencies
target_link_libraries(game pico_stdlib)

# create map/bin/hex file
pico_add_extra_outputs(game)