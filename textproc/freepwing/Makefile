# $NetBSD: Makefile,v 1.20 2016/07/09 06:39:05 wiz Exp $

DISTNAME=	freepwing-1.4.4
PKGREVISION=	9
CATEGORIES=	japanese textproc
MASTER_SITES=	ftp://ftp.sra.co.jp/pub/misc/freepwing/

MAINTAINER=	uebayasi@NetBSD.org
HOMEPAGE=	http://www.sra.co.jp/people/m-kasahr/freepwing/
COMMENT=	Free JIS X 4081 (subset of EPWING V1) formatter

DEPENDS+=	p5-Jcode-[0-9]*:../../converters/p5-Jcode

USE_TOOLS+=		gmake perl:run
GNU_CONFIGURE=		yes
CONFIGURE_ARGS+=	--with-perllibdir=${PERL5_INSTALLVENDORLIB:Q}
CONFIGURE_ARGS+=	--with-pkgdocdir=${PREFIX}/share/doc/freepwing
CONFIGURE_ENV+=		GNUMAKE=${GMAKE:Q}

.include "../../mk/bsd.pkg.mk"
