# $OpenBSD$

COMMENT =	lightweight audio player with simple interface
DISTNAME =	potamus-14
CATEGORIES =	audio x11

HOMEPAGE =	http://offog.org/code/potamus/

MAINTAINER =	Brian Callahan <bcallah@openbsd.org>

# GPLv2+
PERMIT_PACKAGE_CDROM =	Yes

WANTLIB += FLAC X11 Xcomposite Xcursor Xdamage Xext Xfixes Xi
WANTLIB += Xinerama Xrandr Xrender ao atk-1.0 audiofile avcodec avformat
WANTLIB += avutil c cairo fontconfig freetype gdk-x11-2.0 gdk_pixbuf-2.0
WANTLIB += gio-2.0 glade-2.0 glib-2.0 gobject-2.0 gthread-2.0
WANTLIB += gtk-x11-2.0 m mad modplug ogg pango-1.0 pangocairo-1.0
WANTLIB += pangoft2-1.0 pthread samplerate vorbis vorbisfile xml2 z

MASTER_SITES =	http://offog.org/files/

MODULES =	devel/gettext

LIB_DEPENDS =	audio/libao \
		audio/libmad \
		audio/libmodplug \
		audio/libsamplerate \
		devel/libaudiofile \
		devel/libglade2 \
		graphics/ffmpeg \
		x11/gtk+2

RUN_DEPENDS =	devel/desktop-file-utils \
		x11/gtk+2,-guic

CONFIGURE_STYLE =	gnu
CONFIGURE_ARGS =	--disable-output-jack

.include <bsd.port.mk>
