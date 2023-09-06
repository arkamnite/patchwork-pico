add_executable(game
    main.cpp
)

# Pull in common dependencies
target_link_libraries(game pico_stdlib)

# create map/bin/hex file
pico_add_extra_outputs(game)