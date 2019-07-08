# OBJS=../common/backgroundLayer.o ../common/imageGraphics.o ../common/key.o ../common/spriteLayer.o \
#  ../common/font.o ../common/imageKey.o ../common/loadpng.o \
#  ../common/hsv2rgb.o ../common/imageLayer.o ../common/savepng.o \
#  ../common/image.o ../common/imagePalette.o ../common/scrollingLayer.o

set(SOURCES
    ../common/backgroundLayer.c 
    ../common/imageGraphics.c
    ../common/imageKey.c
    ../common/spriteLayer.c
    ../common/imageLayer.c
    ../common/imagePalette.c
    ../common/scrollingLayer.c

    ../common/key.c
    ../common/font.c
    ../common/loadpng.c
    ../common/savepng.c
    ../common/hsv2rgb.c
    ../common/image.c
)

add_library(raspidmx SHARED ${SOURCES})
set_target_properties(raspidmx PROPERTIES SOVERSION 1)

install(TARGETS raspidmx
    LIBRARY DESTINATION lib)