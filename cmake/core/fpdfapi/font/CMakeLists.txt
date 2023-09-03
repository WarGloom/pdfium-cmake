set(_folder "core/fpdfapi/font")

file(GLOB _SOURCES ${PDFIUM_ROOT}/${_folder}/*)
file(GLOB posix_platform_sources ${PDFIUM_ROOT}/${_folder}/*posix*)
file(GLOB win_platform_sources ${PDFIUM_ROOT}/${_folder}/*win*)
file(GLOB test_sources ${PDFIUM_ROOT}/${_folder}/*unittest*)
# message(FATAL_ERROR "${_SOURCES}")
list(REMOVE_ITEM _SOURCES ${posix_platform_sources} ${win_platform_sources}
     ${test_sources})

add_library(pdfium_core_fpdfapi_font OBJECT EXCLUDE_FROM_ALL
${_SOURCES}
)
add_library(pdfium::core_fpdfapi_font ALIAS pdfium_core_fpdfapi_font)
target_link_libraries(pdfium_core_fpdfapi_font
    PRIVATE
        pdfium::strict_config
    PUBLIC
        pdfium::core_fxcrt
        pdfium::core_fxge
        pdfium::core_fpdfapi_cmaps
        pdfium::core_fpdfapi_parser
)
if(APPLE)
    target_link_libraries(pdfium_core_fpdfapi_font
        PRIVATE
            "-framework CoreFoundation"
    )
endif()
