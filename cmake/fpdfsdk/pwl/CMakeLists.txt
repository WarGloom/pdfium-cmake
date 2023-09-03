find_sources("fpdfsdk/pwl")


add_library(pdfium_fpdfsdk_pwl OBJECT EXCLUDE_FROM_ALL ${_SOURCES})
add_library(pdfium::fpdfsdk_pwl ALIAS pdfium_fpdfsdk_pwl)
target_link_libraries(
  pdfium_fpdfsdk_pwl
  PRIVATE pdfium::strict_config
  PUBLIC pdfium::public_headers
         pdfium::constants
         pdfium::core_fpdfapi_font
         pdfium::core_fpdfapi_render
         pdfium::core_fpdfdoc
         pdfium::core_fxcrt
         pdfium::core_fxge)
