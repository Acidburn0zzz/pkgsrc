# $NetBSD: Makefile,v 1.28 2015/03/21 01:17:08 tnn Exp $

PKGNAME=	gcc3${GCC3_PKGMODIF}-c-${GCC_VERSION}
PKGREVISION=	1
COMMENT=	GNU Compiler Collection, v3 - C compiler

INFO_FILES=	yes

.include "../../lang/gcc3/Makefile.common"

# The "gcc" frontend knows all languages (by patch)
CONFIGURE_ARGS+=	--enable-languages=c

MAKE_ENV+=	ALL_GCC=${ALL_GCC:Q}
MAKE_ENV+=	ALL_GCC_C=${ALL_GCC_C:Q}
MAKE_ENV+=	ALL_GCC_CCC=${ALL_GCCXX_C:Q}

.include "../../mk/compiler.mk"

.if empty(PKGSRC_COMPILER:Mgcc)
BUILD_TARGET=	bootstrap
# make it find it's own libgcc_s.so.1, the system might not provide it
MAKE_ENV+=	LD_LIBRARY_PATH=${WRKSRC}/gcc
.endif

post-build:
	${SED} ${FILES_SUBST_SED} ${FILESDIR}/gcc3.mk > ${WRKDIR}/gcc3.mk

GENERATE_PLIST+=							\
	${FIND} ${DESTDIR:Q}${GCC_PREFIX} \( -type f -o -type l \) -print \
		| ${SORT} | ${SED} -e "s,${DESTDIR}${PREFIX}/,,g";

post-install:
.if ${OPSYS} == "SunOS"
	cd ${DESTDIR:Q}${GCC_ARCHDIR}/include && ${RM} -f fixed
.if exists(${DESTDIR}${GCC_ARCHDIR}/include/v7)
	${RMDIR} ${DESTDIR:Q}${GCC_ARCHDIR}/include/v7
.endif
.if exists(${DESTDIR}${GCC_ARCHDIR}/include/v9)
	${RMDIR} ${DESTDIR:Q}${GCC_ARCHDIR}/include/v9
.endif
.endif
	${INSTALL_DATA_DIR} ${DESTDIR:Q}${GCC_PREFIX}/mk
	${INSTALL_DATA} ${WRKDIR}/gcc3.mk ${DESTDIR:Q}${GCC_PREFIX}/mk/c.mk
	${LN} -f ${DESTDIR:Q}${GCC_PREFIX}/bin/gcc ${DESTDIR:Q}${GCC_PREFIX}/bin/cc

.include "../../mk/bsd.pkg.mk"
