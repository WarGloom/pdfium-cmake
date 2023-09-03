set(_folder "core/fxge")

file(GLOB _SOURCES ${PDFIUM_ROOT}/${_folder}/*)
# file(GLOB posix_platform_sources ${PDFIUM_ROOT}/${_folder}/linux/*)
file(GLOB win_platform_sources ${PDFIUM_ROOT}/${_folder}/*windows*)
file(GLOB apple_platform_sources ${PDFIUM_ROOT}/${_folder}/apple/*)

file(GLOB test_sources ${PDFIUM_ROOT}/${_folder}/*unittest*
     ${PDFIUM_ROOT}/${_folder}/test_* ${PDFIUM_ROOT}/${_folder}/*test.cpp)

list(REMOVE_ITEM _SOURCES ${posix_platform_sources} ${win_platform_sources}
     ${apple_platform_sources} ${test_sources})

set(_folder "core/fxge/dib")
file(GLOB _sources_dib ${PDFIUM_ROOT}/${_folder}/*)
file(GLOB _test_dib_sources ${PDFIUM_ROOT}/${_folder}/*unittest*
     ${PDFIUM_ROOT}/${_folder}/test_* ${PDFIUM_ROOT}/${_folder}/*test.cpp)
list(REMOVE_ITEM _sources_dib ${_test_dib_sources})

add_library(
  pdfium_core_fxge OBJECT
  EXCLUDE_FROM_ALL
  ${_SOURCES}
  ${_sources_dib}
  "${PDFIUM_ROOT}/core/fxge/fontdata/chromefontdata/FoxitDingbats.cpp"
  "${PDFIUM_ROOT}/core/fxge/fontdata/chromefontdata/FoxitFixed.cpp"
  "${PDFIUM_ROOT}/core/fxge/fontdata/chromefontdata/FoxitFixedBold.cpp"
  "${PDFIUM_ROOT}/core/fxge/fontdata/chromefontdata/FoxitFixedBoldItalic.cpp"
  "${PDFIUM_ROOT}/core/fxge/fontdata/chromefontdata/FoxitFixedItalic.cpp"
  "${PDFIUM_ROOT}/core/fxge/fontdata/chromefontdata/FoxitSans.cpp"
  "${PDFIUM_ROOT}/core/fxge/fontdata/chromefontdata/FoxitSansBold.cpp"
  "${PDFIUM_ROOT}/core/fxge/fontdata/chromefontdata/FoxitSansBoldItalic.cpp"
  "${PDFIUM_ROOT}/core/fxge/fontdata/chromefontdata/FoxitSansItalic.cpp"
  "${PDFIUM_ROOT}/core/fxge/fontdata/chromefontdata/FoxitSansMM.cpp"
  "${PDFIUM_ROOT}/core/fxge/fontdata/chromefontdata/FoxitSerif.cpp"
  "${PDFIUM_ROOT}/core/fxge/fontdata/chromefontdata/FoxitSerifBold.cpp"
  "${PDFIUM_ROOT}/core/fxge/fontdata/chromefontdata/FoxitSerifBoldItalic.cpp"
  "${PDFIUM_ROOT}/core/fxge/fontdata/chromefontdata/FoxitSerifItalic.cpp"
  "${PDFIUM_ROOT}/core/fxge/fontdata/chromefontdata/FoxitSerifMM.cpp"
  "${PDFIUM_ROOT}/core/fxge/fontdata/chromefontdata/FoxitSymbol.cpp"
  "${PDFIUM_ROOT}/core/fxge/fontdata/chromefontdata/chromefontdata.h"
  "${PDFIUM_ROOT}/core/fxge/freetype/fx_freetype.cpp"
  "${PDFIUM_ROOT}/core/fxge/freetype/fx_freetype.h")

add_library(pdfium::core_fxge ALIAS pdfium_core_fxge)
target_link_libraries(
  pdfium_core_fxge
  PRIVATE pdfium::strict_config
  PUBLIC pdfium::core_fxcrt)
target_compile_definitions(pdfium_core_fxge PRIVATE DEFINE_PS_TABLES_DATA)
if(PDF_ENABLE_XFA)
  target_sources(
    pdfium_core_fxge
    PRIVATE "${PDFIUM_ROOT}/core/fxge/cfx_unicodeencodingex.cpp"
            "${PDFIUM_ROOT}/core/fxge/cfx_unicodeencodingex.h")
endif()
if(PDF_USE_SKIA OR PDF_USE_SKIA_PATHS)
  target_sources(pdfium_core_fxge
                 PRIVATE "${PDFIUM_ROOT}/core/fxge/skia/fx_skia_device.cpp")
  target_link_libraries(pdfium_core_fxge PUBLIC skia # FIXME: third party skia?
  )
else()
  target_sources(
    pdfium_core_fxge PRIVATE "${PDFIUM_ROOT}/core/fxge/agg/fx_agg_driver.cpp"
                             "${PDFIUM_ROOT}/core/fxge/agg/fx_agg_driver.h")
  target_link_libraries(pdfium_core_fxge PUBLIC pdfium::thirdparty_fx_agg)
endif()
if(ANDROID)
  message(FATAL_ERROR "Unsupported PLATFORM")
elseif(LINUX OR CHROMEOS)
  target_sources(pdfium_core_fxge
                 PRIVATE "${PDFIUM_ROOT}/core/fxge/linux/fx_linux_impl.cpp")
elseif(APPLE)
  target_sources(
    pdfium_core_fxge
    PRIVATE "${PDFIUM_ROOT}/core/fxge/apple/fx_apple_impl.cpp"
            "${PDFIUM_ROOT}/core/fxge/apple/fx_apple_platform.cpp"
            "${PDFIUM_ROOT}/core/fxge/apple/fx_apple_platform.h"
            "${PDFIUM_ROOT}/core/fxge/apple/fx_quartz_device.cpp"
            "${PDFIUM_ROOT}/core/fxge/apple/fx_quartz_device.h")
  target_link_libraries(
    pdfium_core_fxge
    PUBLIC "-framework CoreGraphics" # FIXME: master pdfium target needs to have
                                     # this too
  )
elseif(WIN32)
  target_sources(
    pdfium_core_fxge
    PRIVATE "${PDFIUM_ROOT}/core/fxge/cfx_windowsrenderdevice.cpp"
            "${PDFIUM_ROOT}/core/fxge/cfx_windowsrenderdevice.h"
            "${PDFIUM_ROOT}/core/fxge/dib/cfx_dibextractor.cpp"
            "${PDFIUM_ROOT}/core/fxge/dib/cfx_dibextractor.h"
            "${PDFIUM_ROOT}/core/fxge/win32/cfx_psrenderer.cpp"
            "${PDFIUM_ROOT}/core/fxge/win32/cfx_psrenderer.h"
            "${PDFIUM_ROOT}/core/fxge/win32/cgdi_device_driver.cpp"
            "${PDFIUM_ROOT}/core/fxge/win32/cgdi_device_driver.h"
            "${PDFIUM_ROOT}/core/fxge/win32/cgdi_display_driver.cpp"
            "${PDFIUM_ROOT}/core/fxge/win32/cgdi_display_driver.h"
            "${PDFIUM_ROOT}/core/fxge/win32/cgdi_plus_ext.cpp"
            "${PDFIUM_ROOT}/core/fxge/win32/cgdi_plus_ext.h"
            "${PDFIUM_ROOT}/core/fxge/win32/cgdi_printer_driver.cpp"
            "${PDFIUM_ROOT}/core/fxge/win32/cgdi_printer_driver.h"
            "${PDFIUM_ROOT}/core/fxge/win32/cps_printer_driver.cpp"
            "${PDFIUM_ROOT}/core/fxge/win32/cps_printer_driver.h"
            "${PDFIUM_ROOT}/core/fxge/win32/cpsoutput.cpp"
            "${PDFIUM_ROOT}/core/fxge/win32/cpsoutput.h"
            "${PDFIUM_ROOT}/core/fxge/win32/ctext_only_printer_driver.cpp"
            "${PDFIUM_ROOT}/core/fxge/win32/ctext_only_printer_driver.h"
            "${PDFIUM_ROOT}/core/fxge/win32/cwin32_platform.cpp"
            "${PDFIUM_ROOT}/core/fxge/win32/cwin32_platform.h")
endif()
