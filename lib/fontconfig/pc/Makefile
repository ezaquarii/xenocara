#	$OpenBSD: Makefile,v 1.5 2021/11/11 08:46:46 matthieu Exp $

FONTCONFIG =	${.CURDIR}/../../../dist/fontconfig

PKGCONFIG = fontconfig.pc

PACKAGE_VERSION = 2.13.0
PACKAGE = fontconfig
VERSION = $(PACKAGE_VERSION)

EXTRA_PKGCONFIG_SUBST = \
	-e 's,@PACKAGE@,'${PACKAGE}',g' \
	-e 's,@VERSION@,'${VERSION}',g' \
	-e 's,@LIBXML2_CFLAGS@,,g' \
	-e 's,@LIBXML2_LIBS@,,g' \
	-e 's,@PKG_EXPAT_CFLAGS@,,g' \
	-e 's,@PKG_EXPAT_LIBS@,-lexpat,g' \
	-e 's,@FREETYPE_CFLAGS@,-I${X11BASE}/include/freetype2,g' \
	-e 's,@FREETYPE_LIBS@,-L${X11BASE}/lib -lfreetype,g' \
	-e 's,@ICONV_CFLAGS@,,g' \
	-e 's,@ICONV_LIBS@,,g' \
	-e 's,@sysconfdir@,/etc,g' \
	-e 's,@localstatedir@,/var,g' \
	-e 's,@BASECONFIGDIR@,'${BASECONFIGDIR}',g' \
	-e 's,@fc_cachedir@,'${FC_CACHEDIR}',g' \
	-e 's,@PKGCONFIG_REQUIRES@,freetype2,g' \
	-e 's,@PKGCONFIG_REQUIRES_PRIVATELY@,expat,g' \

obj: _xenocara_obj

.PATH: ${FONTCONFIG}

.include <bsd.xorg.mk>
