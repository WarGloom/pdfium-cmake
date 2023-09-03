# set(_folder "core/fxcrt")
find_sources("core/fxcrt")
find_sources("core/fxcrt/xml")

# file(GLOB _SOURCES "${PDFIUM_ROOT}/${_folder}/*")
# file(GLOB posix_platform_sources ${PDFIUM_ROOT}/${_folder}/*posix*)
# file(GLOB win_platform_sources ${PDFIUM_ROOT}/${_folder}/*win*)
# file(GLOB test_sources ${PDFIUM_ROOT}/${_folder}/*test.cpp)

# message(FATAL_ERROR " ${PDFIUM_ROOT}/${_folder}/*  ${_SOURCES}")
# HACK
list(FILTER _SOURCES EXCLUDE REGEX fx_memory_pa.cpp)
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
  PUBLIC pdfium::thirdparty_pdfium_base pdfium::thirdparty_freetype ICU::uc
         pdfium::thirdparty_absl)
if(POSIX OR FUCHSIA)
  target_compile_options(pdfium_core_fxcrt PRIVATE "-Wno-stringop-overflow")
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
