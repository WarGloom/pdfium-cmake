set(_folder "core/fxge")

# file(GLOB _SOURCES ${PDFIUM_ROOT}/${_folder}/*)
set(_SOURCES
  "${PDFIUM_ROOT}/${_folder}/agg/cfx_agg_bitmapcomposer.cpp"
  "${PDFIUM_ROOT}/${_folder}/agg/cfx_agg_bitmapcomposer.h"
  "${PDFIUM_ROOT}/${_folder}/agg/cfx_agg_cliprgn.cpp"
  "${PDFIUM_ROOT}/${_folder}/agg/cfx_agg_cliprgn.h"
  "${PDFIUM_ROOT}/${_folder}/agg/cfx_agg_devicedriver.cpp"
  "${PDFIUM_ROOT}/${_folder}/agg/cfx_agg_devicedriver.h"
  "${PDFIUM_ROOT}/${_folder}/agg/cfx_agg_imagerenderer.cpp"
  "${PDFIUM_ROOT}/${_folder}/agg/cfx_agg_imagerenderer.h"
  "${PDFIUM_ROOT}/${_folder}/calculate_pitch.cpp"
  "${PDFIUM_ROOT}/${_folder}/calculate_pitch.h"
  "${PDFIUM_ROOT}/${_folder}/cfx_color.cpp"
  "${PDFIUM_ROOT}/${_folder}/cfx_color.h"
  "${PDFIUM_ROOT}/${_folder}/cfx_defaultrenderdevice.cpp"
  "${PDFIUM_ROOT}/${_folder}/cfx_defaultrenderdevice.h"
  "${PDFIUM_ROOT}/${_folder}/cfx_drawutils.cpp"
  "${PDFIUM_ROOT}/${_folder}/cfx_drawutils.h"
  "${PDFIUM_ROOT}/${_folder}/cfx_face.cpp"
  "${PDFIUM_ROOT}/${_folder}/cfx_face.h"
  "${PDFIUM_ROOT}/${_folder}/cfx_fillrenderoptions.h"
  "${PDFIUM_ROOT}/${_folder}/cfx_folderfontinfo.cpp"
  "${PDFIUM_ROOT}/${_folder}/cfx_folderfontinfo.h"
  "${PDFIUM_ROOT}/${_folder}/cfx_font.cpp"
  "${PDFIUM_ROOT}/${_folder}/cfx_font.h"
  "${PDFIUM_ROOT}/${_folder}/cfx_fontcache.cpp"
  "${PDFIUM_ROOT}/${_folder}/cfx_fontcache.h"
  "${PDFIUM_ROOT}/${_folder}/cfx_fontmapper.cpp"
  "${PDFIUM_ROOT}/${_folder}/cfx_fontmapper.h"
  "${PDFIUM_ROOT}/${_folder}/cfx_fontmgr.cpp"
  "${PDFIUM_ROOT}/${_folder}/cfx_fontmgr.h"
  "${PDFIUM_ROOT}/${_folder}/cfx_gemodule.cpp"
  "${PDFIUM_ROOT}/${_folder}/cfx_gemodule.h"
  "${PDFIUM_ROOT}/${_folder}/cfx_glyphbitmap.cpp"
  "${PDFIUM_ROOT}/${_folder}/cfx_glyphbitmap.h"
  "${PDFIUM_ROOT}/${_folder}/cfx_glyphcache.cpp"
  "${PDFIUM_ROOT}/${_folder}/cfx_glyphcache.h"
  "${PDFIUM_ROOT}/${_folder}/cfx_graphstate.cpp"
  "${PDFIUM_ROOT}/${_folder}/cfx_graphstate.h"
  "${PDFIUM_ROOT}/${_folder}/cfx_graphstatedata.cpp"
  "${PDFIUM_ROOT}/${_folder}/cfx_graphstatedata.h"
  "${PDFIUM_ROOT}/${_folder}/cfx_path.cpp"
  "${PDFIUM_ROOT}/${_folder}/cfx_path.h"
  "${PDFIUM_ROOT}/${_folder}/cfx_renderdevice.cpp"
  "${PDFIUM_ROOT}/${_folder}/cfx_renderdevice.h"
  "${PDFIUM_ROOT}/${_folder}/cfx_substfont.cpp"
  "${PDFIUM_ROOT}/${_folder}/cfx_substfont.h"
  "${PDFIUM_ROOT}/${_folder}/cfx_textrenderoptions.h"
  "${PDFIUM_ROOT}/${_folder}/cfx_unicodeencoding.cpp"
  "${PDFIUM_ROOT}/${_folder}/cfx_unicodeencoding.h"
  "${PDFIUM_ROOT}/${_folder}/dib/blend.cpp"
  "${PDFIUM_ROOT}/${_folder}/dib/blend.h"
  "${PDFIUM_ROOT}/${_folder}/dib/cfx_bitmapstorer.cpp"
  "${PDFIUM_ROOT}/${_folder}/dib/cfx_bitmapstorer.h"
  "${PDFIUM_ROOT}/${_folder}/dib/cfx_cmyk_to_srgb.cpp"
  "${PDFIUM_ROOT}/${_folder}/dib/cfx_cmyk_to_srgb.h"
  "${PDFIUM_ROOT}/${_folder}/dib/cfx_dibbase.cpp"
  "${PDFIUM_ROOT}/${_folder}/dib/cfx_dibbase.h"
  "${PDFIUM_ROOT}/${_folder}/dib/cfx_dibitmap.cpp"
  "${PDFIUM_ROOT}/${_folder}/dib/cfx_dibitmap.h"
  "${PDFIUM_ROOT}/${_folder}/dib/cfx_imagestretcher.cpp"
  "${PDFIUM_ROOT}/${_folder}/dib/cfx_imagestretcher.h"
  "${PDFIUM_ROOT}/${_folder}/dib/cfx_imagetransformer.cpp"
  "${PDFIUM_ROOT}/${_folder}/dib/cfx_imagetransformer.h"
  "${PDFIUM_ROOT}/${_folder}/dib/cfx_scanlinecompositor.cpp"
  "${PDFIUM_ROOT}/${_folder}/dib/cfx_scanlinecompositor.h"
  "${PDFIUM_ROOT}/${_folder}/dib/cstretchengine.cpp"
  "${PDFIUM_ROOT}/${_folder}/dib/cstretchengine.h"
  "${PDFIUM_ROOT}/${_folder}/dib/fx_dib.cpp"
  "${PDFIUM_ROOT}/${_folder}/dib/fx_dib.h"
  "${PDFIUM_ROOT}/${_folder}/dib/scanlinecomposer_iface.h"
  "${PDFIUM_ROOT}/${_folder}/fontdata/chromefontdata/FoxitDingbats.cpp"
  "${PDFIUM_ROOT}/${_folder}/fontdata/chromefontdata/FoxitFixed.cpp"
  "${PDFIUM_ROOT}/${_folder}/fontdata/chromefontdata/FoxitFixedBold.cpp"
  "${PDFIUM_ROOT}/${_folder}/fontdata/chromefontdata/FoxitFixedBoldItalic.cpp"
  "${PDFIUM_ROOT}/${_folder}/fontdata/chromefontdata/FoxitFixedItalic.cpp"
  "${PDFIUM_ROOT}/${_folder}/fontdata/chromefontdata/FoxitSans.cpp"
  "${PDFIUM_ROOT}/${_folder}/fontdata/chromefontdata/FoxitSansBold.cpp"
  "${PDFIUM_ROOT}/${_folder}/fontdata/chromefontdata/FoxitSansBoldItalic.cpp"
  "${PDFIUM_ROOT}/${_folder}/fontdata/chromefontdata/FoxitSansItalic.cpp"
  "${PDFIUM_ROOT}/${_folder}/fontdata/chromefontdata/FoxitSansMM.cpp"
  "${PDFIUM_ROOT}/${_folder}/fontdata/chromefontdata/FoxitSerif.cpp"
  "${PDFIUM_ROOT}/${_folder}/fontdata/chromefontdata/FoxitSerifBold.cpp"
  "${PDFIUM_ROOT}/${_folder}/fontdata/chromefontdata/FoxitSerifBoldItalic.cpp"
  "${PDFIUM_ROOT}/${_folder}/fontdata/chromefontdata/FoxitSerifItalic.cpp"
  "${PDFIUM_ROOT}/${_folder}/fontdata/chromefontdata/FoxitSerifMM.cpp"
  "${PDFIUM_ROOT}/${_folder}/fontdata/chromefontdata/FoxitSymbol.cpp"
  "${PDFIUM_ROOT}/${_folder}/fontdata/chromefontdata/chromefontdata.h"
  "${PDFIUM_ROOT}/${_folder}/freetype/fx_freetype.cpp"
  "${PDFIUM_ROOT}/${_folder}/freetype/fx_freetype.h"
  "${PDFIUM_ROOT}/${_folder}/fx_font.cpp"
  "${PDFIUM_ROOT}/${_folder}/fx_font.h"
  "${PDFIUM_ROOT}/${_folder}/fx_fontencoding.h"
  "${PDFIUM_ROOT}/${_folder}/render_defines.h"
  "${PDFIUM_ROOT}/${_folder}/renderdevicedriver_iface.cpp"
  "${PDFIUM_ROOT}/${_folder}/renderdevicedriver_iface.h"
  "${PDFIUM_ROOT}/${_folder}/scoped_font_transform.cpp"
  "${PDFIUM_ROOT}/${_folder}/scoped_font_transform.h"
  "${PDFIUM_ROOT}/${_folder}/systemfontinfo_iface.h"
  "${PDFIUM_ROOT}/${_folder}/text_char_pos.cpp"
  "${PDFIUM_ROOT}/${_folder}/text_char_pos.h"
  "${PDFIUM_ROOT}/${_folder}/text_glyph_pos.h"
  "${PDFIUM_ROOT}/${_folder}/text_glyph_pos.cpp"
)

# file(GLOB posix_platform_sources ${PDFIUM_ROOT}/${_folder}/linux/*)
set(win_platform_sources
  "${PDFIUM_ROOT}/${_folder}/cfx_windowsrenderdevice.cpp"
  "${PDFIUM_ROOT}/${_folder}/cfx_windowsrenderdevice.h"
  "${PDFIUM_ROOT}/${_folder}/win32/cfx_psfonttracker.cpp"
  "${PDFIUM_ROOT}/${_folder}/win32/cfx_psfonttracker.h"
  "${PDFIUM_ROOT}/${_folder}/win32/cfx_psrenderer.cpp"
  "${PDFIUM_ROOT}/${_folder}/win32/cfx_psrenderer.h"
  "${PDFIUM_ROOT}/${_folder}/win32/cgdi_device_driver.cpp"
  "${PDFIUM_ROOT}/${_folder}/win32/cgdi_device_driver.h"
  "${PDFIUM_ROOT}/${_folder}/win32/cgdi_display_driver.cpp"
  "${PDFIUM_ROOT}/${_folder}/win32/cgdi_display_driver.h"
  "${PDFIUM_ROOT}/${_folder}/win32/cgdi_plus_ext.cpp"
  "${PDFIUM_ROOT}/${_folder}/win32/cgdi_plus_ext.h"
  "${PDFIUM_ROOT}/${_folder}/win32/cgdi_printer_driver.cpp"
  "${PDFIUM_ROOT}/${_folder}/win32/cgdi_printer_driver.h"
  "${PDFIUM_ROOT}/${_folder}/win32/cps_printer_driver.cpp"
  "${PDFIUM_ROOT}/${_folder}/win32/cps_printer_driver.h"
  "${PDFIUM_ROOT}/${_folder}/win32/cpsoutput.cpp"
  "${PDFIUM_ROOT}/${_folder}/win32/cpsoutput.h"
  "${PDFIUM_ROOT}/${_folder}/win32/ctext_only_printer_driver.cpp"
  "${PDFIUM_ROOT}/${_folder}/win32/ctext_only_printer_driver.h"
  "${PDFIUM_ROOT}/${_folder}/win32/cwin32_platform.cpp"
  "${PDFIUM_ROOT}/${_folder}/win32/cwin32_platform.h"
)

if(LINUX)
  list(APPEND _SOURCES "${PDFIUM_ROOT}/${_folder}/linux/fx_linux_impl.cpp")
elseif(WIN32)
  list(APPEND _SOURCES ${win_platform_sources})
endif()

# find_sources("core/fxge/dib")
# find_sources("core/fxge/fontdata/chromefontdata")
# find_sources("core/fxge/freetype")

# set(_folder "core/fxge/dib")
# file(GLOB _sources_dib ${PDFIUM_ROOT}/${_folder}/*)
# file(GLOB _test_dib_sources ${PDFIUM_ROOT}/${_folder}/*unittest*
# ${PDFIUM_ROOT}/${_folder}/test_* ${PDFIUM_ROOT}/${_folder}/*test.cpp)
# list(REMOVE_ITEM _sources_dib ${_test_dib_sources})
add_library(
  pdfium_core_fxge OBJECT
  EXCLUDE_FROM_ALL
  ${_SOURCES}
  ${_sources_dib}

  # "${PDFIUM_ROOT}/core/fxge/fontdata/chromefontdata/FoxitDingbats.cpp"
  # "${PDFIUM_ROOT}/core/fxge/fontdata/chromefontdata/FoxitFixed.cpp"
  # "${PDFIUM_ROOT}/core/fxge/fontdata/chromefontdata/FoxitFixedBold.cpp"
  # "${PDFIUM_ROOT}/core/fxge/fontdata/chromefontdata/FoxitFixedBoldItalic.cpp"
  # "${PDFIUM_ROOT}/core/fxge/fontdata/chromefontdata/FoxitFixedItalic.cpp"
  # "${PDFIUM_ROOT}/core/fxge/fontdata/chromefontdata/FoxitSans.cpp"
  # "${PDFIUM_ROOT}/core/fxge/fontdata/chromefontdata/FoxitSansBold.cpp"
  # "${PDFIUM_ROOT}/core/fxge/fontdata/chromefontdata/FoxitSansBoldItalic.cpp"
  # "${PDFIUM_ROOT}/core/fxge/fontdata/chromefontdata/FoxitSansItalic.cpp"
  # "${PDFIUM_ROOT}/core/fxge/fontdata/chromefontdata/FoxitSansMM.cpp"
  # "${PDFIUM_ROOT}/core/fxge/fontdata/chromefontdata/FoxitSerif.cpp"
  # "${PDFIUM_ROOT}/core/fxge/fontdata/chromefontdata/FoxitSerifBold.cpp"
  # "${PDFIUM_ROOT}/core/fxge/fontdata/chromefontdata/FoxitSerifBoldItalic.cpp"
  # "${PDFIUM_ROOT}/core/fxge/fontdata/chromefontdata/FoxitSerifItalic.cpp"
  # "${PDFIUM_ROOT}/core/fxge/fontdata/chromefontdata/FoxitSerifMM.cpp"
  # "${PDFIUM_ROOT}/core/fxge/fontdata/chromefontdata/FoxitSymbol.cpp"
  # "${PDFIUM_ROOT}/core/fxge/fontdata/chromefontdata/chromefontdata.h"
  # "${PDFIUM_ROOT}/core/fxge/freetype/fx_freetype.cpp"
  # "${PDFIUM_ROOT}/core/fxge/freetype/fx_freetype.h"
)

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
  # target_sources(
  # pdfium_core_fxge PRIVATE "${PDFIUM_ROOT}/core/fxge/agg/fx_agg_driver.cpp"
  # "${PDFIUM_ROOT}/core/fxge/agg/fx_agg_driver.h")
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
    "${PDFIUM_ROOT}/core/fxge/apple/fx_quartz_device.h"
  )
  target_link_libraries(
    pdfium_core_fxge
    PUBLIC "-framework CoreGraphics" # FIXME: master pdfium target needs to have

    # this too
  )
elseif(WIN32)
  find_sources("core/fxge/win32")
  target_sources(
    pdfium_core_fxge
    PRIVATE "${PDFIUM_ROOT}/core/fxge/cfx_windowsrenderdevice.cpp"
    "${PDFIUM_ROOT}/core/fxge/cfx_windowsrenderdevice.h"
    ${_SOURCES}

    # "${PDFIUM_ROOT}/core/fxge/dib/cfx_dibextractor.cpp"
    # "${PDFIUM_ROOT}/core/fxge/dib/cfx_dibextractor.h"
    # "${PDFIUM_ROOT}/core/fxge/win32/cfx_psrenderer.cpp"
    # "${PDFIUM_ROOT}/core/fxge/win32/cfx_psrenderer.h"
    # "${PDFIUM_ROOT}/core/fxge/win32/cgdi_device_driver.cpp"
    # "${PDFIUM_ROOT}/core/fxge/win32/cgdi_device_driver.h"
    # "${PDFIUM_ROOT}/core/fxge/win32/cgdi_display_driver.cpp"
    # "${PDFIUM_ROOT}/core/fxge/win32/cgdi_display_driver.h"
    # "${PDFIUM_ROOT}/core/fxge/win32/cgdi_plus_ext.cpp"
    # "${PDFIUM_ROOT}/core/fxge/win32/cgdi_plus_ext.h"
    # "${PDFIUM_ROOT}/core/fxge/win32/cgdi_printer_driver.cpp"
    # "${PDFIUM_ROOT}/core/fxge/win32/cgdi_printer_driver.h"
    # "${PDFIUM_ROOT}/core/fxge/win32/cps_printer_driver.cpp"
    # "${PDFIUM_ROOT}/core/fxge/win32/cps_printer_driver.h"
    # "${PDFIUM_ROOT}/core/fxge/win32/cpsoutput.cpp"
    # "${PDFIUM_ROOT}/core/fxge/win32/cpsoutput.h"
    # "${PDFIUM_ROOT}/core/fxge/win32/ctext_only_printer_driver.cpp"
    # "${PDFIUM_ROOT}/core/fxge/win32/ctext_only_printer_driver.h"
    # "${PDFIUM_ROOT}/core/fxge/win32/cwin32_platform.cpp"
    # "${PDFIUM_ROOT}/core/fxge/win32/cwin32_platform.h"
  )
endif()