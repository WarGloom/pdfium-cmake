set(_files "access_permissions.h"
    "annotation_common.cpp"
    "annotation_common.h"
    "annotation_flags.h"
    "appearance.cpp"
    "appearance.h"
    "ascii.h"
    "font_encodings.cpp"
    "font_encodings.h"
    "form_fields.cpp"
    "form_fields.h"
    "form_flags.h"
    "page_object.cpp"
    "page_object.h"
    "stream_dict_common.cpp"
    "stream_dict_common.h"
    "transparency.cpp"
    "transparency.h")
foreach (_file  ${_files}
)
list(APPEND _SOURCES "${PDFIUM_ROOT}/constants/${_file}")
endforeach()

add_library(pdfium_constants OBJECT EXCLUDE_FROM_ALL
${_SOURCES})

add_library(pdfium::constants ALIAS pdfium_constants)
target_link_libraries(pdfium_constants
    PRIVATE
        pdfium::strict_config
)
