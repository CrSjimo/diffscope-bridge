cmake_minimum_required(VERSION 3.17)

project(DiffScopeBridge VERSION 0.0.1 LANGUAGES CXX)

add_subdirectory(lib)

ck_add_audio_plugin(DiffScopeBridge
    VERSION ${CMAKE_PROJECT_VERSION}
    ENABLE_ARA TRUE
    PLUGIN_NAME "DiffScope Bridge"
    VENDOR OpenVPI
    FORMATS VST3 Standalone
)

ck_target_plugin_config(DiffScopeBridge
    PLUGIN_EDITOR_NAME "DiffScope Editor"
    PLUGIN_CONFIG_ENV DIFFSCOPE_BRIDGE_CONFIG
    COLOR_FOREGROUND 154c39
    COLOR_FOREGROUND_ON 0f694b
    COLOR_FOREGROUND_LABEL ffffff
    COLOR_BACKGROUND_MAIN 1e1e1e
    COLOR_BACKGROUND_SIDEBAR 252525
    COLOR_BACKGROUND_MESSAGE ffffff
    COLOR_BACKGROUND_ERROR ff0000
)