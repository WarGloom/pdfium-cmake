set(_folder "core/fxcrt")
# find_sources("core/fxcrt")
# find_sources("core/fxcrt/xml")

# file(GLOB _SOURCES "${PDFIUM_ROOT}/${_folder}/*")
# file(GLOB posix_platform_sources ${PDFIUM_ROOT}/${_folder}/*posix*)
# file(GLOB win_platform_sources ${PDFIUM_ROOT}/${_folder}/*win*)
# file(GLOB test_sources ${PDFIUM_ROOT}/${_folder}/*test.cpp)

# message(FATAL_ERROR " ${PDFIUM_ROOT}/${_folder}/*  ${_SOURCES}")
# HACK
list(FILTER _SOURCES EXCLUDE REGEX fx_memory_pa.cpp)
set(_SOURCES
  "${PDFIUM_ROOT}/${_folder}/autonuller.h"
  "${PDFIUM_ROOT}/${_folder}/autorestorer.h"
  "${PDFIUM_ROOT}/${_folder}/binary_buffer.cpp"
  "${PDFIUM_ROOT}/${_folder}/binary_buffer.h"
  "${PDFIUM_ROOT}/${_folder}/byteorder.h"
  "${PDFIUM_ROOT}/${_folder}/bytestring.cpp"
  "${PDFIUM_ROOT}/${_folder}/bytestring.h"
  "${PDFIUM_ROOT}/${_folder}/cfx_bitstream.cpp"
  "${PDFIUM_ROOT}/${_folder}/cfx_bitstream.h"
  "${PDFIUM_ROOT}/${_folder}/cfx_datetime.cpp"
  "${PDFIUM_ROOT}/${_folder}/cfx_datetime.h"
  "${PDFIUM_ROOT}/${_folder}/cfx_read_only_span_stream.cpp"
  "${PDFIUM_ROOT}/${_folder}/cfx_read_only_span_stream.h"
  "${PDFIUM_ROOT}/${_folder}/cfx_read_only_string_stream.cpp"
  "${PDFIUM_ROOT}/${_folder}/cfx_read_only_string_stream.h"
  "${PDFIUM_ROOT}/${_folder}/cfx_read_only_vector_stream.cpp"
  "${PDFIUM_ROOT}/${_folder}/cfx_read_only_vector_stream.h"
  "${PDFIUM_ROOT}/${_folder}/cfx_seekablestreamproxy.cpp"
  "${PDFIUM_ROOT}/${_folder}/cfx_seekablestreamproxy.h"
  "${PDFIUM_ROOT}/${_folder}/cfx_timer.cpp"
  "${PDFIUM_ROOT}/${_folder}/cfx_timer.h"
  "${PDFIUM_ROOT}/${_folder}/check.h"
  "${PDFIUM_ROOT}/${_folder}/check_op.h"
  "${PDFIUM_ROOT}/${_folder}/code_point_view.h"
  "${PDFIUM_ROOT}/${_folder}/component_export.h"
  "${PDFIUM_ROOT}/${_folder}/containers/adapters.h"
  "${PDFIUM_ROOT}/${_folder}/containers/contains.h"
  "${PDFIUM_ROOT}/${_folder}/data_vector.h"
  "${PDFIUM_ROOT}/${_folder}/debug/alias.cc"
  "${PDFIUM_ROOT}/${_folder}/debug/alias.h"
  "${PDFIUM_ROOT}/${_folder}/fileaccess_iface.h"
  "${PDFIUM_ROOT}/${_folder}/fixed_size_data_vector.h"
  "${PDFIUM_ROOT}/${_folder}/fx_2d_size.h"
  "${PDFIUM_ROOT}/${_folder}/fx_bidi.cpp"
  "${PDFIUM_ROOT}/${_folder}/fx_bidi.h"
  "${PDFIUM_ROOT}/${_folder}/fx_codepage.cpp"
  "${PDFIUM_ROOT}/${_folder}/fx_codepage.h"
  "${PDFIUM_ROOT}/${_folder}/fx_codepage_forward.h"
  "${PDFIUM_ROOT}/${_folder}/fx_coordinates.cpp"
  "${PDFIUM_ROOT}/${_folder}/fx_coordinates.h"
  "${PDFIUM_ROOT}/${_folder}/fx_extension.cpp"
  "${PDFIUM_ROOT}/${_folder}/fx_extension.h"
  "${PDFIUM_ROOT}/${_folder}/fx_folder.h"
  "${PDFIUM_ROOT}/${_folder}/fx_memcpy_wrappers.h"
  "${PDFIUM_ROOT}/${_folder}/fx_memory.cpp"
  "${PDFIUM_ROOT}/${_folder}/fx_memory.h"
  "${PDFIUM_ROOT}/${_folder}/fx_memory_wrappers.h"
  "${PDFIUM_ROOT}/${_folder}/fx_number.cpp"
  "${PDFIUM_ROOT}/${_folder}/fx_number.h"
  "${PDFIUM_ROOT}/${_folder}/fx_random.cpp"
  "${PDFIUM_ROOT}/${_folder}/fx_random.h"
  "${PDFIUM_ROOT}/${_folder}/fx_safe_types.h"
  "${PDFIUM_ROOT}/${_folder}/fx_stream.cpp"
  "${PDFIUM_ROOT}/${_folder}/fx_stream.h"
  "${PDFIUM_ROOT}/${_folder}/fx_string.cpp"
  "${PDFIUM_ROOT}/${_folder}/fx_string.h"
  "${PDFIUM_ROOT}/${_folder}/fx_string_wrappers.h"
  "${PDFIUM_ROOT}/${_folder}/fx_system.cpp"
  "${PDFIUM_ROOT}/${_folder}/fx_system.h"
  "${PDFIUM_ROOT}/${_folder}/fx_types.h"
  "${PDFIUM_ROOT}/${_folder}/fx_unicode.cpp"
  "${PDFIUM_ROOT}/${_folder}/fx_unicode.h"
  "${PDFIUM_ROOT}/${_folder}/fx_memory_malloc.cpp"
  "${PDFIUM_ROOT}/${_folder}/immediate_crash.h"
  "${PDFIUM_ROOT}/${_folder}/mask.h"
  "${PDFIUM_ROOT}/${_folder}/maybe_owned.h"
  "${PDFIUM_ROOT}/${_folder}/notreached.h"
  "${PDFIUM_ROOT}/${_folder}/numerics/checked_math.h"
  "${PDFIUM_ROOT}/${_folder}/numerics/checked_math_impl.h"
  "${PDFIUM_ROOT}/${_folder}/numerics/clamped_math.h"
  "${PDFIUM_ROOT}/${_folder}/numerics/clamped_math_impl.h"
  "${PDFIUM_ROOT}/${_folder}/numerics/safe_conversions.h"
  "${PDFIUM_ROOT}/${_folder}/numerics/safe_conversions_arm_impl.h"
  "${PDFIUM_ROOT}/${_folder}/numerics/safe_conversions_impl.h"
  "${PDFIUM_ROOT}/${_folder}/numerics/safe_math.h"
  "${PDFIUM_ROOT}/${_folder}/numerics/safe_math_arm_impl.h"
  "${PDFIUM_ROOT}/${_folder}/numerics/safe_math_clang_gcc_impl.h"
  "${PDFIUM_ROOT}/${_folder}/numerics/safe_math_shared_impl.h"
  "${PDFIUM_ROOT}/${_folder}/observed_ptr.cpp"
  "${PDFIUM_ROOT}/${_folder}/observed_ptr.h"
  "${PDFIUM_ROOT}/${_folder}/pauseindicator_iface.h"
  "${PDFIUM_ROOT}/${_folder}/ptr_util.h"
  "${PDFIUM_ROOT}/${_folder}/raw_span.h"
  "${PDFIUM_ROOT}/${_folder}/retain_ptr.h"
  "${PDFIUM_ROOT}/${_folder}/scoped_set_insertion.h"
  "${PDFIUM_ROOT}/${_folder}/shared_copy_on_write.h"
  "${PDFIUM_ROOT}/${_folder}/span.h"
  "${PDFIUM_ROOT}/${_folder}/span_util.h"
  "${PDFIUM_ROOT}/${_folder}/stl_util.h"
  "${PDFIUM_ROOT}/${_folder}/string_data_template.cpp"
  "${PDFIUM_ROOT}/${_folder}/string_data_template.h"
  "${PDFIUM_ROOT}/${_folder}/string_pool_template.h"
  "${PDFIUM_ROOT}/${_folder}/string_template.cpp"
  "${PDFIUM_ROOT}/${_folder}/string_template.h"
  "${PDFIUM_ROOT}/${_folder}/string_view_template.h"
  "${PDFIUM_ROOT}/${_folder}/template_util.h"
  "${PDFIUM_ROOT}/${_folder}/tree_node.h"
  "${PDFIUM_ROOT}/${_folder}/unowned_ptr.h"
  "${PDFIUM_ROOT}/${_folder}/utf16.h"
  "${PDFIUM_ROOT}/${_folder}/weak_ptr.h"
  "${PDFIUM_ROOT}/${_folder}/widestring.cpp"
  "${PDFIUM_ROOT}/${_folder}/widestring.h"
  "${PDFIUM_ROOT}/${_folder}/widetext_buffer.cpp"
  "${PDFIUM_ROOT}/${_folder}/widetext_buffer.h"
  "${PDFIUM_ROOT}/${_folder}/xml/cfx_xmlchardata.cpp"
  "${PDFIUM_ROOT}/${_folder}/xml/cfx_xmlchardata.h"
  "${PDFIUM_ROOT}/${_folder}/xml/cfx_xmldocument.cpp"
  "${PDFIUM_ROOT}/${_folder}/xml/cfx_xmldocument.h"
  "${PDFIUM_ROOT}/${_folder}/xml/cfx_xmlelement.cpp"
  "${PDFIUM_ROOT}/${_folder}/xml/cfx_xmlelement.h"
  "${PDFIUM_ROOT}/${_folder}/xml/cfx_xmlinstruction.cpp"
  "${PDFIUM_ROOT}/${_folder}/xml/cfx_xmlinstruction.h"
  "${PDFIUM_ROOT}/${_folder}/xml/cfx_xmlnode.cpp"
  "${PDFIUM_ROOT}/${_folder}/xml/cfx_xmlnode.h"
  "${PDFIUM_ROOT}/${_folder}/xml/cfx_xmlparser.cpp"
  "${PDFIUM_ROOT}/${_folder}/xml/cfx_xmlparser.h"
  "${PDFIUM_ROOT}/${_folder}/xml/cfx_xmltext.cpp"
  "${PDFIUM_ROOT}/${_folder}/xml/cfx_xmltext.h"
  "${PDFIUM_ROOT}/${_folder}/zip.h"
)

if(WIN32)
  list(APPEND _SOURCES
    "${PDFIUM_ROOT}/${_folder}/cfx_fileaccess_windows.cpp"
    "${PDFIUM_ROOT}/${_folder}/cfx_fileaccess_windows.h"
    "${PDFIUM_ROOT}/${_folder}/code_point_view.cpp"
    "${PDFIUM_ROOT}/${_folder}/fx_folder_windows.cpp"
    "${PDFIUM_ROOT}/${_folder}/win/scoped_select_object.h"
    "${PDFIUM_ROOT}/${_folder}/win/win_util.cc"
    "${PDFIUM_ROOT}/${_folder}/win/win_util.h"
  )
elseif(POSIX)
  list(APPEND _SOURCES
    "${PDFIUM_ROOT}/${_folder}/cfx_fileaccess_posix.cpp"
    "${PDFIUM_ROOT}/${_folder}/cfx_fileaccess_posix.h"
    "${PDFIUM_ROOT}/${_folder}/fx_folder_posix.cpp"
  )
endif()

add_library(
  pdfium_core_fxcrt OBJECT
  EXCLUDE_FROM_ALL
  ${_SOURCES}
)
add_library(pdfium::core_fxcrt ALIAS pdfium_core_fxcrt)
find_package(ICU REQUIRED COMPONENTS ICU::uc)
target_compile_definitions(pdfium_core_fxcrt PUBLIC USE_SYSTEM_ICUUC)
target_link_libraries(
  pdfium_core_fxcrt
  PRIVATE pdfium::strict_config
  PUBLIC
  pdfium::thirdparty_freetype ICU::uc
  pdfium::thirdparty_absl

  # pdfium::thirdparty_pdfium_base
)

if(POSIX OR FUCHSIA)
  # target_compile_options(pdfium_core_fxcrt PRIVATE "-Wno-stringop-overflow")
  target_sources(pdfium_core_fxcrt PRIVATE ${posix_platform_sources})

  # target_sources(pdfium_core_fxcrt PRIVATE
  # "${PDFIUM_ROOT}/core/fxcrt/cfx_fileaccess_posix.cpp"
  # "${PDFIUM_ROOT}/core/fxcrt/cfx_fileaccess_posix.h"
  # "${PDFIUM_ROOT}/core/fxcrt/fx_folder_posix.cpp" )
endif()

if(WIN32)
  target_sources(
    pdfium_core_fxcrt
    PRIVATE ${win_platform_sources}

    # "${PDFIUM_ROOT}/core/fxcrt/cfx_fileaccess_windows.cpp"
    # "${PDFIUM_ROOT}/core/fxcrt/cfx_fileaccess_windows.h"
    # "${PDFIUM_ROOT}/core/fxcrt/fx_folder_windows.cpp"
  )
endif()

if(PDF_ENABLE_XFA)
  target_sources(
    pdfium_core_fxcrt PRIVATE "${PDFIUM_ROOT}/${_folder}/cfx_memorystream.cpp"
    "${PDFIUM_ROOT}/${_folder}/cfx_memorystream.h")
endif()
