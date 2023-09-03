set(_folder "core/fpdfapi/render")

file(GLOB _SOURCES ${PDFIUM_ROOT}/${_folder}/*)
file(GLOB posix_platform_sources ${PDFIUM_ROOT}/${_folder}/*posix*)
file(GLOB test_sources ${PDFIUM_ROOT}/${_folder}/*test*)
file(GLOB win_platform_sources ${PDFIUM_ROOT}/${_folder}/*win*)

list(REMOVE_ITEM _SOURCES ${posix_platform_sources} ${win_platform_sources}
     ${test_sources})

add_library(
  pdfium_core_fpdfapi_render OBJECT
  EXCLUDE_FROM_ALL
  ${_SOURCES}
)
add_library(pdfium::core_fpdfapi_render ALIAS pdfium_core_fpdfapi_render)
target_link_libraries(
  pdfium_core_fpdfapi_render
  PRIVATE pdfium::strict_config
  PUBLIC pdfium::constants
         pdfium::core_fxcodec
         pdfium::core_fxcrt
         pdfium::core_fxge
         pdfium::core_fpdfapi_font
         pdfium::core_fpdfapi_page
         pdfium::core_fpdfapi_parser)
if(WIN32)
  target_sources(
    pdfium_core_fpdfapi_render
    PRIVATE ${win_platform_sources}
            # "${PDFIUM_ROOT}/${_folder}/cpdf_windowsrenderdevice.cpp"
            # "${PDFIUM_ROOT}/${_folder}/cpdf_windowsrenderdevice.h"
  )
endif()
