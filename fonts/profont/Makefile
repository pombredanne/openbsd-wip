# $OpenBSD: Makefile,v 1.6 2013/02/09 14:49:51 sthen Exp $

COMMENT =		fixed width fonts especially for long hacking sessions

DISTNAME =		ProFont-2.2
EXTRACT_SUFX =		.zip
CATEGORIES =		fonts x11

HOMEPAGE =		http://www.fontsquirrel.com/fonts/ProFontWindows

MAINTAINER =		Andrew Fresh

# redistribute unmodified copies with included license
PERMIT_PACKAGE_CDROM =		Yes

MASTER_SITES =		http://www.fontsquirrel.com/fonts/download/ProFontWindows/

NO_BUILD=		Yes
NO_TEST =		Yes

FONTDIR =		${PREFIX}/lib/X11/fonts/profont

do-install:
	${INSTALL_DATA_DIR} ${PREFIX}/lib/X11/fonts/profont
	${INSTALL_DATA} ${WRKDIR}/*.t{tf,xt} ${PREFIX}/lib/X11/fonts/profont

.include <bsd.port.mk>
