cmake_minimum_required(VERSION 3.5)

project(stm LANGUAGES C)

add_executable(stm main.c
    byte_utils.c byte_utils.h
    byte_utils.c byte_utils.h COPYING error.h espstlink.c espstlink.h ihex.c ihex.h INSTALL libespstlink.c libespstlink.h LICENSE-CHANGE main.c Makefile pgm.h README.md srec.c srec.h stlink.c stlink.h stlinkv2.c stlinkv2.h stm8.c stm8.h try.h utils.h)


include(GNUInstallDirs)
install(TARGETS stm
    LIBRARY DESTINATION ${CMAKE_INSTALL_LIBDIR}
    RUNTIME DESTINATION ${CMAKE_INSTALL_BINDIR}
)
target_link_libraries(stm usb-1.0)
