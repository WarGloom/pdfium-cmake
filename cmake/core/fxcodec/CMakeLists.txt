set(_folder "core/fxcodec")

add_library(pdfium_core_fxcodec OBJECT EXCLUDE_FROM_ALL
    "${PDFIUM_ROOT}/${_folder}/basic/basicmodule.cpp"
    "${PDFIUM_ROOT}/${_folder}/basic/basicmodule.h"
    "${PDFIUM_ROOT}/${_folder}/data_and_bytes_consumed.cpp"
    "${PDFIUM_ROOT}/${_folder}/data_and_bytes_consumed.h"
    "${PDFIUM_ROOT}/${_folder}/fax/faxmodule.cpp"
    "${PDFIUM_ROOT}/${_folder}/fax/faxmodule.h"
    "${PDFIUM_ROOT}/${_folder}/flate/flatemodule.cpp"
    "${PDFIUM_ROOT}/${_folder}/flate/flatemodule.h"
    "${PDFIUM_ROOT}/${_folder}/fx_codec.cpp"
    "${PDFIUM_ROOT}/${_folder}/fx_codec.h"
    "${PDFIUM_ROOT}/${_folder}/fx_codec_def.h"
    "${PDFIUM_ROOT}/${_folder}/icc/icc_transform.cpp"
    "${PDFIUM_ROOT}/${_folder}/icc/icc_transform.h"
    "${PDFIUM_ROOT}/${_folder}/jbig2/JBig2_ArithDecoder.cpp"
    "${PDFIUM_ROOT}/${_folder}/jbig2/JBig2_ArithDecoder.h"
    "${PDFIUM_ROOT}/${_folder}/jbig2/JBig2_ArithIntDecoder.cpp"
    "${PDFIUM_ROOT}/${_folder}/jbig2/JBig2_ArithIntDecoder.h"
    "${PDFIUM_ROOT}/${_folder}/jbig2/JBig2_BitStream.cpp"
    "${PDFIUM_ROOT}/${_folder}/jbig2/JBig2_BitStream.h"
    "${PDFIUM_ROOT}/${_folder}/jbig2/JBig2_Context.cpp"
    "${PDFIUM_ROOT}/${_folder}/jbig2/JBig2_Context.h"
    "${PDFIUM_ROOT}/${_folder}/jbig2/JBig2_Define.h"
    "${PDFIUM_ROOT}/${_folder}/jbig2/JBig2_DocumentContext.cpp"
    "${PDFIUM_ROOT}/${_folder}/jbig2/JBig2_DocumentContext.h"
    "${PDFIUM_ROOT}/${_folder}/jbig2/JBig2_GrdProc.cpp"
    "${PDFIUM_ROOT}/${_folder}/jbig2/JBig2_GrdProc.h"
    "${PDFIUM_ROOT}/${_folder}/jbig2/JBig2_GrrdProc.cpp"
    "${PDFIUM_ROOT}/${_folder}/jbig2/JBig2_GrrdProc.h"
    "${PDFIUM_ROOT}/${_folder}/jbig2/JBig2_HtrdProc.cpp"
    "${PDFIUM_ROOT}/${_folder}/jbig2/JBig2_HtrdProc.h"
    "${PDFIUM_ROOT}/${_folder}/jbig2/JBig2_HuffmanDecoder.cpp"
    "${PDFIUM_ROOT}/${_folder}/jbig2/JBig2_HuffmanDecoder.h"
    "${PDFIUM_ROOT}/${_folder}/jbig2/JBig2_HuffmanTable.cpp"
    "${PDFIUM_ROOT}/${_folder}/jbig2/JBig2_HuffmanTable.h"
    "${PDFIUM_ROOT}/${_folder}/jbig2/JBig2_Image.cpp"
    "${PDFIUM_ROOT}/${_folder}/jbig2/JBig2_Image.h"
    "${PDFIUM_ROOT}/${_folder}/jbig2/JBig2_Page.h"
    "${PDFIUM_ROOT}/${_folder}/jbig2/JBig2_PatternDict.cpp"
    "${PDFIUM_ROOT}/${_folder}/jbig2/JBig2_PatternDict.h"
    "${PDFIUM_ROOT}/${_folder}/jbig2/JBig2_PddProc.cpp"
    "${PDFIUM_ROOT}/${_folder}/jbig2/JBig2_PddProc.h"
    "${PDFIUM_ROOT}/${_folder}/jbig2/JBig2_SddProc.cpp"
    "${PDFIUM_ROOT}/${_folder}/jbig2/JBig2_SddProc.h"
    "${PDFIUM_ROOT}/${_folder}/jbig2/JBig2_Segment.cpp"
    "${PDFIUM_ROOT}/${_folder}/jbig2/JBig2_Segment.h"
    "${PDFIUM_ROOT}/${_folder}/jbig2/JBig2_SymbolDict.cpp"
    "${PDFIUM_ROOT}/${_folder}/jbig2/JBig2_SymbolDict.h"
    "${PDFIUM_ROOT}/${_folder}/jbig2/JBig2_TrdProc.cpp"
    "${PDFIUM_ROOT}/${_folder}/jbig2/JBig2_TrdProc.h"
    "${PDFIUM_ROOT}/${_folder}/jbig2/jbig2_decoder.cpp"
    "${PDFIUM_ROOT}/${_folder}/jbig2/jbig2_decoder.h"
    "${PDFIUM_ROOT}/${_folder}/jpeg/jpeg_common.c"
    "${PDFIUM_ROOT}/${_folder}/jpeg/jpeg_common.h"
    "${PDFIUM_ROOT}/${_folder}/jpeg/jpegmodule.cpp"
    "${PDFIUM_ROOT}/${_folder}/jpeg/jpegmodule.h"
    "${PDFIUM_ROOT}/${_folder}/jpx/cjpx_decoder.cpp"
    "${PDFIUM_ROOT}/${_folder}/jpx/cjpx_decoder.h"
    "${PDFIUM_ROOT}/${_folder}/jpx/jpx_decode_utils.cpp"
    "${PDFIUM_ROOT}/${_folder}/jpx/jpx_decode_utils.h"
    "${PDFIUM_ROOT}/${_folder}/scanlinedecoder.cpp"
    "${PDFIUM_ROOT}/${_folder}/scanlinedecoder.h"
)
add_library(pdfium::core_fxcodec ALIAS pdfium_core_fxcodec)
target_link_libraries(pdfium_core_fxcodec
    PRIVATE
    pdfium::strict_config
    PUBLIC
    pdfium::thirdparty_lcms2
    pdfium::thirdparty_libopenjpeg2
    pdfium::thirdparty_zlib
    pdfium::thirdparty_libjpeg
    pdfium::core_fxcrt
    pdfium::core_fxge
)

if(PDF_ENABLE_XFA)
    target_sources(pdfium_core_fxcodec PRIVATE
        "${PDFIUM_ROOT}/core/fxcodec/jpeg/jpeg_progressive_decoder.cpp"
        "${PDFIUM_ROOT}/core/fxcodec/jpeg/jpeg_progressive_decoder.h"
        "${PDFIUM_ROOT}/core/fxcodec/progressive_decoder.cpp"
        "${PDFIUM_ROOT}/core/fxcodec/progressive_decoder.h"
        "${PDFIUM_ROOT}/core/fxcodec/progressive_decoder_iface.h"
    )

    if(PDF_ENABLE_XFA_BMP)
        target_sources(pdfium_core_fxcodec PRIVATE
            "${PDFIUM_ROOT}/core/fxcodec/bmp/bmp_decoder.cpp"
            "${PDFIUM_ROOT}/core/fxcodec/bmp/bmp_decoder.h"
            "${PDFIUM_ROOT}/core/fxcodec/bmp/bmp_progressive_decoder.cpp"
            "${PDFIUM_ROOT}/core/fxcodec/bmp/bmp_progressive_decoder.h"
            "${PDFIUM_ROOT}/core/fxcodec/bmp/cfx_bmpcontext.cpp"
            "${PDFIUM_ROOT}/core/fxcodec/bmp/cfx_bmpcontext.h"
            "${PDFIUM_ROOT}/core/fxcodec/bmp/cfx_bmpdecompressor.cpp"
            "${PDFIUM_ROOT}/core/fxcodec/bmp/cfx_bmpdecompressor.h"
            "${PDFIUM_ROOT}/core/fxcodec/bmp/fx_bmp.h"
        )
    endif()

    if(PDF_ENABLE_XFA_PNG)
        target_sources(pdfium_core_fxcodec PRIVATE
            "${PDFIUM_ROOT}/core/fxcodec/png/png_decoder.cpp"
            "${PDFIUM_ROOT}/core/fxcodec/png/png_decoder.h"
        )
        target_link_libraries(pdfium_core_fxcodec
            PUBLIC
            pdfium::thirdparty_png
        )
    endif()

    if(PDF_ENABLE_XFA_TIFF)
        target_sources(pdfium_core_fxcodec PRIVATE
            "${PDFIUM_ROOT}/core/fxcodec/tiff/tiff_decoder.cpp"
            "${PDFIUM_ROOT}/core/fxcodec/tiff/tiff_decoder.h"
        )
        target_link_libraries(pdfium_core_fxcodec
            PUBLIC
            pdfium::thirdparty_tiff
        )
    endif()
endif()
