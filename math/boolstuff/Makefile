# $NetBSD: Makefile,v 1.2 2017/08/16 20:45:40 wiz Exp $

DISTNAME=	boolstuff-0.1.16
CATEGORIES=	math
MASTER_SITES=	http://perso.b2b2c.ca/~sarrazip/dev/

MAINTAINER=	pkgsrc-users@NetBSD.org
#HOMEPAGE=	http://perso.b2b2c.ca/~sarrazip/dev/boolstuff.html
COMMENT=	Disjunctive Normal Form boolean expression C++ library
LICENSE=	gnu-gpl-v2

GNU_CONFIGURE=	yes
USE_LIBTOOL=	yes
USE_TOOLS+=	pkg-config
USE_LANGUAGES=	c c++

PKGCONFIG_OVERRIDE+=	boolstuff-0.1.pc.in

.include "../../mk/bsd.pkg.mk"
