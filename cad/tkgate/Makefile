# $OpenBSD$

COMMENT = 		Tcl/Tk based digital circuit editor and simulator

DISTNAME = 		tkgate-1.8.7
CATEGORIES = 		cad

HOMEPAGE = 		http://www.tkgate.org/
MASTER_SITES = 		http://www.tkgate.org/downloads/
EXTRACT_SUFX = 		.tgz

# GPLv2
PERMIT_PACKAGE_CDROM = 	Yes

WANTLIB = 		X11 c m ${MODTK_WANTLIB}

MODULES = 		x11/tk
BUILD_DEPENDS = 	devel/imake
LIB_DEPENDS = 		${MODTK_LIB_DEPENDS}

CONFIGURE_STYLE = 	gnu

NO_TEST = 		Yes

post-extract:
	@find ${WRKSRC} -name *.orig -exec rm {} \;

pre-configure:
	@perl -pi -e 's,!!PREFIX!!,${PREFIX},g' ${WRKSRC}/Imakefile \
		${WRKSRC}/src/gsim/Imakefile ${WRKSRC}/scripts/parms.tcl
	@perl -pi -e 's,!!CFLAGS!!,${CFLAGS},g;' \
		-e 's,!!LOCALBASE!!,${LOCALBASE},g;' \
		-e 's,!!PREFIX!!,${PREFIX},g;' ${WRKSRC}/config.h

post-install:
	${INSTALL_MAN} ${WRKSRC}/tkgate.man ${PREFIX}/man/man1/tkgate.1
	${INSTALL_MAN} ${WRKSRC}/gmac.man ${PREFIX}/man/man1/gmac.1
	${INSTALL_DATA_DIR} ${PREFIX}/share/tkgate/
	${INSTALL_DATA} ${WRKSRC}/doc/license.txt ${PREFIX}/share/tkgate/
	${INSTALL_DATA_DIR} ${PREFIX}/share/tkgate/locale/
	@cd ${WRKSRC}/locale/ && tar cf - . | \
		tar xf - -C ${PREFIX}/share/tkgate/locale/

.include <bsd.port.mk>
