cmake_minimum_required(VERSION 3.17)

project(DiffScopeBridge VERSION 0.0.1 LANGUAGES CXX)

add_subdirectory(lib)

set(_formats VST3 LV2 Standalone)

if (APPLE)
    list(APPEND _formats AU)
endif()

ck_add_audio_plugin(DiffScopeBridge
    VERSION ${CMAKE_PROJECT_VERSION}
    ENABLE_ARA TRUE
    PLUGIN_NAME "DiffScope Bridge"
    VENDOR OpenVPI
    FORMATS ${_formats}
    LV2URI https://github.com/CrSjimo/diffscope-bridge
)

ck_target_plugin_config(DiffScopeBridge
    PLUGIN_EDITOR_NAME "DiffScope Editor"
    PLUGIN_CONFIG_PATH OpenVPI/DiffScope/vstconfig.json
    COLOR_FOREGROUND 5566FF
    COLOR_FOREGROUND_BORDER 404144
    COLOR_FOREGROUND_LABEL ffffff
    COLOR_BACKGROUND_MAIN 212124
    COLOR_BACKGROUND_SIDEBAR 252629
    COLOR_BACKGROUND_MESSAGE ffffff
    COLOR_BACKGROUND_ERROR ff0000
)