#	$OpenBSD: Makefile,v 1.3 2022/02/24 02:29:48 jsg Exp $

.include "config.mk"

SUBDIR=		include pkgconfig \
		libcompiler libdri libdricommon \
		libgallium libgalliumvl \
		libglapi_static libglcpp libglsl \
		libloader libmegadriver_stub \
		libmesa_classic libmesa_common libmesa_format \
		libmesa_gallium libmesa_util \
		libnir libpipe_loader_static libsoftpipe \
		libswdri libswkmsdri \
		libws_null libwsw libxmlconfig

.if ${XENOCARA_BUILD_DRI3:L} == "yes" || make(obj)
SUBDIR+=	libloader_dri3_helper
.endif

.if ${WITH_SSE41} == "yes" || make(obj)
SUBDIR+=	libmesa_sse41
.endif

.if ${WITH_AMD_VK} == "yes" || ${WITH_GALLIUM_RADEONSI} == "yes" || make(obj)
SUBDIR+=	libaddrlib libamd_common libamd_common_llvm libamdgpuwinsys
.endif

.if ${WITH_DRI_I965} == "yes" || ${WITH_GALLIUM_IRIS} == "yes" || \
    ${WITH_INTEL_VK} == "yes" || make(obj)
SUBDIR+=	libblorp libintel_common libintel_compiler libintel_dev \
		libintel_perf libisl libisl_tiled_memcpy \
		libisl_tiled_memcpy_sse41
.for GFX in 40 50 60 70 75 80 90 110 120 125
SUBDIR+=	libisl_gfx${GFX}
.endfor
.endif

.if ${WITH_GALLIUM_R300} == "yes" || ${WITH_GALLIUM_R600} == "yes" || \
    ${WITH_GALLIUM_RADEONSI} == "yes" || make(obj)
SUBDIR+=	libradeonwinsys
.endif

.if ${WITH_AMD_VK} == "yes" || ${WITH_INTEL_VK} == "yes" || make(obj)
SUBDIR+=	libvulkan_util libvulkan_wsi
.endif

.if ${WITH_LLVM} == "yes" || make(obj)
SUBDIR+=	libllvmpipe
.endif

.if ${WITH_AMD_VK} == "yes" || make(obj)
SUBDIR+=	libaco
SUBDIR+=	libvulkan_radeon
.endif

.if ${WITH_INTEL_VK} == "yes" || make(obj)
SUBDIR+=	libanv_common 
.for GEN in 70 75 80 90 110 120 125
SUBDIR+=	libanv_gen${GEN}
.endfor
SUBDIR+=	libvulkan_intel
.endif

.if ${WITH_GALLIUM_IRIS} == "yes" || make(obj)
SUBDIR+=	libiris libiriswinsys
.for GEN in 80 90 110 120 125
SUBDIR+=	libiris_gen${GEN}
.endfor
.endif

.if ${WITH_DRI_I915} == "yes" || make(obj)
SUBDIR+=	libi915
.endif

.if ${WITH_DRI_I965} == "yes" || make(obj)
SUBDIR+=	libi965
.for GEN in 40 45 50 60 70 75 80 90 110
SUBDIR+=	libi965_gen${GEN}
.endfor
.endif

.if ${WITH_DRI_R100} == "yes" || make(obj)
SUBDIR+=	libr100
.endif

.if ${WITH_DRI_R200} == "yes" || make(obj)
SUBDIR+=	libr200
.endif

.if ${WITH_GALLIUM_R300} == "yes" || make(obj)
SUBDIR+=	libr300
.endif

.if ${WITH_GALLIUM_R600} == "yes" || make(obj)
SUBDIR+=	libr600
.endif

.if ${WITH_GALLIUM_RADEONSI} == "yes" || make(obj)
.for GEN in 6 7 8 9 10 103
SUBDIR+=	libradeonsi_gfx${GEN}
.endfor
SUBDIR+=	libradeonsi
.endif

# installed libs
SUBDIR+=	libglapi libgbm libEGL libGL libGLESv1_CM libGLESv2 libOSMesa

SUBDIR+=	libmesa_dri_drivers libgallium_dri

.include <bsd.subdir.mk>
