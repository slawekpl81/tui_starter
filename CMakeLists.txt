cmake_minimum_required(VERSION 4.0)
project(tui_starter)

set(CMAKE_CXX_STANDARD 20)

# Włącz moduł FetchContent
include(FetchContent)

# 1. Definicja FTXUI: podaj repozytorium i tag/commit (zalecane użycie tagu dla stabilności)
FetchContent_Declare(
        ftxui
        GIT_REPOSITORY https://github.com/ArthurSonzogni/FTXUI.git
        GIT_TAG        v5.0.0  # Zmień na najnowszą stabilną wersję
)

# 2. Pobierz zawartość (jeśli jeszcze jej nie ma)
FetchContent_MakeAvailable(ftxui)

add_executable(tui_starter main.cpp)

# Użyj celu udostępnionego przez FTXUI
target_link_libraries(tui_starter PRIVATE ftxui::dom ftxui::component ftxui::screen)