cmake_minimum_required(VERSION 3.13)

project(js_ReaScriptAPI)

add_library(${PROJECT_NAME} SHARED)

target_compile_features(${PROJECT_NAME} PRIVATE cxx_std_14)

target_compile_definitions(${PROJECT_NAME} PRIVATE -DSWELL_PROVIDED_BY_APP -DSWELL_TARGET_OSX )

set_target_properties(${PROJECT_NAME} PROPERTIES POSITION_INDEPENDENT_CODE ON)

find_library(CORE_FOUNDATION CoreFoundation)
find_library(COCOA Cocoa)
find_library(ZLIB NAMES z)
find_library(JPEG jpeg)
find_library(PNG png)
target_link_libraries(${PROJECT_NAME} PRIVATE ${CORE_FOUNDATION} ${COCOA} ${ZLIB} ${PNG} ${JPEG})

target_sources(${PROJECT_NAME} PRIVATE js_ReaScriptAPI.cpp js_ReaScriptAPI_ObjC.mm)

target_sources(${PROJECT_NAME} PRIVATE
# WDL/swell/swell-appstub-generic.cpp
# WDL/swell/swell-dlg-generic.cpp
# WDL/swell/swell-gdi-generic.cpp
# WDL/swell/swell-gdi-lice.cpp
# WDL/swell/swell-generic-gdk.cpp
# WDL/swell/swell-generic-headless.cpp
# WDL/swell/swell-ini.cpp
# WDL/swell/swell-kb-generic.cpp
# WDL/swell/swell-menu-generic.cpp
# WDL/swell/swell-misc-generic.cpp
# WDL/swell/swell-miscdlg-generic.cpp
# WDL/swell/swell-modstub-generic.cpp
# WDL/swell/swell-wnd-generic.cpp
# WDL/swell/swell.cpp

WDL/swell/swell-appstub.mm
WDL/swell/swell-misc.mm
WDL/swell/swell-dlg.mm
WDL/swell/swell-miscdlg.mm
WDL/swell/swell-gdi.mm
WDL/swell/swell-modstub.mm
WDL/swell/swell-kb.mm
WDL/swell/swell-wnd.mm
WDL/swell/swell-menu.mm
#WDL/swell/swellappmain.mm
)

target_sources(${PROJECT_NAME} PRIVATE
WDL/lice/lice.cpp
WDL/lice/lice_lcf.cpp
WDL/lice/lice_arc.cpp
WDL/lice/lice_line.cpp
WDL/lice/lice_bmp.cpp
WDL/lice/lice_lvg.cpp
WDL/lice/lice_colorspace.cpp
WDL/lice/lice_palette.cpp
#WDL/lice/lice_gif.cpp		
WDL/lice/lice_pcx.cpp
#WDL/lice/lice_gif_write.cpp
WDL/lice/lice_png.cpp
#WDL/lice/lice_gl_ctx.cpp
WDL/lice/lice_png_write.cpp
#WDL/lice/lice_glbitmap.cpp
#WDL/lice/lice_svg.cpp
WDL/lice/lice_ico.cpp
WDL/lice/lice_texgen.cpp
WDL/lice/lice_image.cpp	
WDL/lice/lice_text.cpp
WDL/lice/lice_jpg.cpp
WDL/lice/lice_textnew.cpp
WDL/lice/lice_jpg_write.cpp
)
