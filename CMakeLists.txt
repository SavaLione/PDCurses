# Minimum version
cmake_minimum_required (VERSION 2.8)
project(pdcurses C)

set(CMAKE_MODULE_PATH "${CMAKE_SOURCE_DIR}/cmake")

set(PDCURSES_MAJOR_VERSION 3)
set(PDCURSES_MINOR_VERSION 9)
set(PDCURSES_MICRO_VERSION 0)

set(PDCURSES_SOURCES_INCLUDE
    include/curses.h
    include/curspriv.h
    include/panel.h
)

set(PDCURSES_SOURCES_WINCON
    src/wincon/pdcclip.c
    src/wincon/pdcdisp.c
    src/wincon/pdcgetsc.c
    src/wincon/pdckbd.c
    src/wincon/pdcscrn.c
    src/wincon/pdcsetsc.c
    src/wincon/pdcutil.c
    src/wincon/pdcwin.h
)

set(PDCURSES_SOURCES_WINCON_RC
    src/common/pdcurses.rc
)

set(PDCURSES_SOURCES
    src/pdcurses/addch.c
    src/pdcurses/addchstr.c
    src/pdcurses/addstr.c
    src/pdcurses/attr.c
    src/pdcurses/beep.c
    src/pdcurses/bkgd.c
    src/pdcurses/border.c
    src/pdcurses/clear.c
    src/pdcurses/color.c
    src/pdcurses/debug.c
    src/pdcurses/delch.c
    src/pdcurses/deleteln.c
    src/pdcurses/getch.c
    src/pdcurses/getstr.c
    src/pdcurses/getyx.c
    src/pdcurses/inch.c
    src/pdcurses/inchstr.c
    src/pdcurses/initscr.c
    src/pdcurses/inopts.c
    src/pdcurses/insch.c
    src/pdcurses/insstr.c
    src/pdcurses/instr.c
    src/pdcurses/kernel.c
    src/pdcurses/keyname.c
    src/pdcurses/mouse.c
    src/pdcurses/move.c
    src/pdcurses/outopts.c
    src/pdcurses/overlay.c
    src/pdcurses/pad.c
    src/pdcurses/panel.c
    src/pdcurses/printw.c
    src/pdcurses/refresh.c
    src/pdcurses/scanw.c
    src/pdcurses/scroll.c
    src/pdcurses/scr_dump.c
    src/pdcurses/slk.c
    src/pdcurses/termattr.c
    src/pdcurses/touch.c
    src/pdcurses/util.c
    src/pdcurses/window.c
)

add_library(pdcurses SHARED ${PDCURSES_SOURCES_INCLUDE} ${PDCURSES_SOURCES} ${PDCURSES_SOURCES_WINCON} ${PDCURSES_SOURCES_WINCON_RC})
set_target_properties(pdcurses PROPERTIES PREFIX "")

target_include_directories(pdcurses PUBLIC ${CMAKE_SOURCE_DIR}/include)