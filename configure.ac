AC_INIT([libmailio], 0.19.0, [maarten@hekkelman.com])

dnl Switch to a C++ compiler, and check if it works.
AC_LANG(C++)
AX_CXX_COMPILE_STDCXX_17([noext])

AC_CONFIG_SRCDIR([src/base64.cpp])
AC_CONFIG_AUX_DIR(config)
AC_CONFIG_MACRO_DIR([config/m4])

AC_PREFIX_DEFAULT(/usr/local)

AC_PROG_INSTALL
AC_ENABLE_STATIC
AC_DISABLE_SHARED
AC_PROG_LIBTOOL
AC_SUBST(LIBTOOL_DEPS)

AC_PATH_PROG([SHELL], [sh])

AX_PTHREAD(
	[
		LIBS="$PTHREAD_LIBS $LIBS"
		CXXFLAGS="$CXXFLAGS $PTHREAD_CFLAGS"
	]
)

AX_BOOST_BASE([1.70.0], [], [
	AC_MSG_ERROR([Sorry, your boost is not found or not up-to-date.])
])
AX_BOOST_ASIO

dnl Process Makefile.in to create Makefile
AC_OUTPUT([GNUmakefile
		   mailio.pc])

