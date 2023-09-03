add_subdirectory(formfiller)
add_subdirectory(pwl)

find_sources("fpdfsdk")

# message(FATAL_ERROR ${_SOURCES})

add_library(pdfium_fpdfsdk OBJECT EXCLUDE_FROM_ALL ${_SOURCES}
)
add_library(pdfium::fpdfsdk ALIAS pdfium_fpdfsdk)
target_link_libraries(pdfium_fpdfsdk
    PRIVATE
        pdfium::strict_config
    PUBLIC
        pdfium::public_headers
        pdfium::constants
        pdfium::core_fpdfapi_edit
        pdfium::core_fpdfapi_font
        pdfium::core_fpdfapi_page
        pdfium::core_fpdfapi_parser
        pdfium::core_fpdfapi_render
        pdfium::core_fpdfdoc
        pdfium::core_fpdftext
        pdfium::core_fxcrt
        pdfium::core_fxge
        pdfium::fxjs
        pdfium::fpdfsdk_formfiller
        pdfium::fpdfsdk_pwl
)
if(PDF_ENABLE_XFA)
    target_link_libraries(pdfium_fpdfsdk
        PUBLIC
            pdfium::xfa_fxfa
            pdfium::xfa_ffa_parser
            pdfium::fpdfxfa
    )
endif()
