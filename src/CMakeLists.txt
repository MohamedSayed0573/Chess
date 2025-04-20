# Setup sources

set(CHESS_SOURCES
    Bishop.cpp
    Game.cpp
    King.cpp
    Knight.cpp
    MainLoop.cpp
    Pawn.cpp
    Piece.cpp
    Queen.cpp
    Rook.cpp
    SDL_Handler.cpp
)

# Copy SDL2.dll for Windows builds
if(WIN32)
    file(COPY ${CMAKE_CURRENT_SOURCE_DIR}/SDL2.dll DESTINATION ${CMAKE_CURRENT_BINARY_DIR})
endif()

# Build executable
add_executable(Chess Main.cpp ${CHESS_SOURCES})
target_link_libraries(Chess ${SDL2_LIBRARIES} ${SDL2_IMAGE_LIBRARIES})
