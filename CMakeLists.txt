cmake_minimum_required(VERSION 3.3)
project(caprice32 CXX)

FIND_PACKAGE(SDL REQUIRED)
FIND_PACKAGE(Freetype REQUIRED)
FIND_PACKAGE(ZLIB REQUIRED)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")

set(SOURCE_FILES
    gui/includes/CapriceAbout.h
    gui/includes/CapriceGui.h
    gui/includes/CapriceGuiView.h
    gui/includes/CapriceLoadSave.h
    gui/includes/CapriceMemoryTool.h
    gui/includes/CapriceOptions.h
    gui/includes/CapriceRomSlots.h
    gui/includes/std_ex.h
    gui/includes/wg_application.h
    gui/includes/wg_button.h
    gui/includes/wg_checkbox.h
    gui/includes/wg_color.h
    gui/includes/wg_dropdown.h
    gui/includes/wg_editbox.h
    gui/includes/wg_error.h
    gui/includes/wg_fontengine.h
    gui/includes/wg_frame.h
    gui/includes/wg_groupbox.h
    gui/includes/wg_label.h
    gui/includes/wg_listbox.h
    gui/includes/wg_menu.h
    gui/includes/wg_message.h
    gui/includes/wg_message_client.h
    gui/includes/wg_message_server.h
    gui/includes/wg_messagebox.h
    gui/includes/wg_navigationbar.h
    gui/includes/wg_painter.h
    gui/includes/wg_picture.h
    gui/includes/wg_point.h
    gui/includes/wg_progress.h
    gui/includes/wg_radiobutton.h
    gui/includes/wg_range_control.h
    gui/includes/wg_rect.h
    gui/includes/wg_renderedstring.h
    gui/includes/wg_resource_handle.h
    gui/includes/wg_resources.h
    gui/includes/wg_scrollbar.h
    gui/includes/wg_tab.h
    gui/includes/wg_textbox.h
    gui/includes/wg_timer.h
    gui/includes/wg_toolbar.h
    gui/includes/wg_tooltip.h
    gui/includes/wg_view.h
    gui/includes/wg_window.h
    gui/includes/wgui.h
    gui/includes/wgui_config.h
    gui/includes/wgui_include_config.h
    gui/includes/wgui_win32_config.h
    gui/includes/wutil_config_store.h
    gui/includes/wutil_debug.h
    gui/includes/wutil_log.h
    gui/src/CapriceAbout.cpp
    gui/src/CapriceGui.cpp
    gui/src/CapriceGuiView.cpp
    gui/src/CapriceLoadSave.cpp
    gui/src/CapriceMemoryTool.cpp
    gui/src/CapriceOptions.cpp
    gui/src/CapriceRomSlots.cpp
    gui/src/std_ex.cpp
    gui/src/wg_application.cpp
    gui/src/wg_button.cpp
    gui/src/wg_checkbox.cpp
    gui/src/wg_color.cpp
    gui/src/wg_dropdown.cpp
    gui/src/wg_editbox.cpp
    gui/src/wg_fontengine.cpp
    gui/src/wg_frame.cpp
    gui/src/wg_groupbox.cpp
    gui/src/wg_label.cpp
    gui/src/wg_listbox.cpp
    gui/src/wg_menu.cpp
    gui/src/wg_message.cpp
    gui/src/wg_message_client.cpp
    gui/src/wg_message_server.cpp
    gui/src/wg_messagebox.cpp
    gui/src/wg_navigationbar.cpp
    gui/src/wg_painter.cpp
    gui/src/wg_picture.cpp
    gui/src/wg_point.cpp
    gui/src/wg_progress.cpp
    gui/src/wg_radiobutton.cpp
    gui/src/wg_rect.cpp
    gui/src/wg_renderedstring.cpp
    gui/src/wg_resource_handle.cpp
    gui/src/wg_resources.cpp
    gui/src/wg_scrollbar.cpp
    gui/src/wg_tab.cpp
    gui/src/wg_textbox.cpp
    gui/src/wg_timer.cpp
    gui/src/wg_toolbar.cpp
    gui/src/wg_tooltip.cpp
    gui/src/wg_view.cpp
    gui/src/wg_window.cpp
    gui/src/wutil_config_store.cpp
    gui/src/wutil_log.cpp
    cap32.cpp
    cap32.h
    crtc.c
    crtc.h
    fdc.c
    fileutils.cpp
    fileutils.h
    glfunclist.h
    glfuncs.cpp
    glfuncs.h
    psg.c
    tape.c
    tape.h
    video.cpp
    video.h
    z80.c
    z80.h
    z80daa.h)

set_source_files_properties(crtc.c PROPERTIES LANGUAGE CXX)
set_source_files_properties(fdc.c PROPERTIES LANGUAGE CXX)
set_source_files_properties(psg.c PROPERTIES LANGUAGE CXX)
set_source_files_properties(tape.c PROPERTIES LANGUAGE CXX)
set_source_files_properties(z80.c PROPERTIES LANGUAGE CXX)

add_executable(caprice32 ${SOURCE_FILES})

target_include_directories(caprice32 PRIVATE
        ${PROJECT_SOURCE_DIR}/
        ${PROJECT_SOURCE_DIR}/gui/includes
        ${SDL_INCLUDE_DIR}
        ${FREETYPE_INCLUDE_DIRS})

target_link_libraries(caprice32 PRIVATE
        ${SDL_LIBRARY}
        ${FREETYPE_LIBRARIES}
        ${ZLIB_LIBRARIES})
