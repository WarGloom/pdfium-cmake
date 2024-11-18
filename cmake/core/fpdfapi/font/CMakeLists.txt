set(_folder "core/fpdfapi/font")

# file(GLOB _SOURCES ${PDFIUM_ROOT}/${_folder}/*)
set(_SOURCES
    "${PDFIUM_ROOT}/${_folder}/cfx_cttgsubtable.cpp"
    "${PDFIUM_ROOT}/${_folder}/cfx_cttgsubtable.h"
    "${PDFIUM_ROOT}/${_folder}/cfx_stockfontarray.cpp"
    "${PDFIUM_ROOT}/${_folder}/cfx_stockfontarray.h"
    "${PDFIUM_ROOT}/${_folder}/cpdf_cid2unicodemap.cpp"
    "${PDFIUM_ROOT}/${_folder}/cpdf_cid2unicodemap.h"
    "${PDFIUM_ROOT}/${_folder}/cpdf_cidfont.cpp"
    "${PDFIUM_ROOT}/${_folder}/cpdf_cidfont.h"
    "${PDFIUM_ROOT}/${_folder}/cpdf_cmap.cpp"
    "${PDFIUM_ROOT}/${_folder}/cpdf_cmap.h"
    "${PDFIUM_ROOT}/${_folder}/cpdf_cmapparser.cpp"
    "${PDFIUM_ROOT}/${_folder}/cpdf_cmapparser.h"
    "${PDFIUM_ROOT}/${_folder}/cpdf_font.cpp"
    "${PDFIUM_ROOT}/${_folder}/cpdf_font.h"
    "${PDFIUM_ROOT}/${_folder}/cpdf_fontencoding.cpp"
    "${PDFIUM_ROOT}/${_folder}/cpdf_fontencoding.h"
    "${PDFIUM_ROOT}/${_folder}/cpdf_fontglobals.cpp"
    "${PDFIUM_ROOT}/${_folder}/cpdf_fontglobals.h"
    "${PDFIUM_ROOT}/${_folder}/cpdf_simplefont.cpp"
    "${PDFIUM_ROOT}/${_folder}/cpdf_simplefont.h"
    "${PDFIUM_ROOT}/${_folder}/cpdf_tounicodemap.cpp"
    "${PDFIUM_ROOT}/${_folder}/cpdf_tounicodemap.h"
    "${PDFIUM_ROOT}/${_folder}/cpdf_truetypefont.cpp"
    "${PDFIUM_ROOT}/${_folder}/cpdf_truetypefont.h"
    "${PDFIUM_ROOT}/${_folder}/cpdf_type1font.cpp"
    "${PDFIUM_ROOT}/${_folder}/cpdf_type1font.h"
    "${PDFIUM_ROOT}/${_folder}/cpdf_type3char.cpp"
    "${PDFIUM_ROOT}/${_folder}/cpdf_type3char.h"
    "${PDFIUM_ROOT}/${_folder}/cpdf_type3font.cpp"
    "${PDFIUM_ROOT}/${_folder}/cpdf_type3font.h"
)
# file(GLOB posix_platform_sources ${PDFIUM_ROOT}/${_folder}/*posix*)
# file(GLOB win_platform_sources ${PDFIUM_ROOT}/${_folder}/*win*)
# file(GLOB test_sources ${PDFIUM_ROOT}/${_folder}/*unittest*)

# message(FATAL_ERROR "${_SOURCES}")
# list(REMOVE_ITEM _SOURCES ${posix_platform_sources} ${win_platform_sources}
#     ${test_sources})

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
