find_sources("fpdfsdk/formfiller" "perwindowdata")
# message(FATAL_ERROR ${_SOURCES})
add_library(pdfium_fpdfsdk_formfiller OBJECT EXCLUDE_FROM_ALL ${_SOURCES})
add_library(pdfium::fpdfsdk_formfiller ALIAS pdfium_fpdfsdk_formfiller)
target_link_libraries(
  pdfium_fpdfsdk_formfiller
  PRIVATE pdfium::strict_config
  PUBLIC pdfium::public_headers
         pdfium::constants
         pdfium::core_fpdfapi_page
         pdfium::core_fpdfdoc
         pdfium::core_fxcrt
         pdfium::core_fxge
         pdfium::fpdfsdk_pwl)
