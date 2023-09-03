set(_folder "core/fpdfapi/page")

file(GLOB _SOURCES ${PDFIUM_ROOT}/${_folder}/*)
file(GLOB posix_platform_sources ${PDFIUM_ROOT}/${_folder}/*posix*)
file(GLOB win_platform_sources ${PDFIUM_ROOT}/${_folder}/*win*)
file(GLOB test_sources ${PDFIUM_ROOT}/${_folder}/*unittest*
     ${PDFIUM_ROOT}/${_folder}/test_*)
# message(FATAL_ERROR "${_SOURCES}")
list(REMOVE_ITEM _SOURCES ${posix_platform_sources} ${win_platform_sources}
     ${test_sources})

add_library(pdfium_core_fpdfapi_page OBJECT EXCLUDE_FROM_ALL ${_SOURCES})
add_library(pdfium::core_fpdfapi_page ALIAS pdfium_core_fpdfapi_page)
target_link_libraries(
  pdfium_core_fpdfapi_page
  PRIVATE pdfium::strict_config
  PUBLIC pdfium::constants pdfium::core_fdrm pdfium::core_fxcodec
         pdfium::core_fxcrt pdfium::core_fpdfapi_font
         pdfium::core_fpdfapi_parser)
