#                                               -*- Autoconf -*-
# Process this file with autoconf to produce a configure script.

AC_PREREQ(2.61)
AC_INIT([MEOIP2],[0.9],[Chris Andreae <chris@andreae.gen.nz>])
AC_CONFIG_SRCDIR([minIni.h])
AC_CONFIG_HEADERS([config.h])

AC_ARG_ENABLE([debug], AS_HELP_STRING([--enable-debug], [Compile with debugging support]))

if test "x$enableval" == xyes; then
	CFLAGS="$CFLAGS -O0 -g"
else
	CFLAGS="$CFLAGS -O2 -DNDEBUG"
fi

# Checks for programs.
AC_PROG_CC
AM_PROG_CC_C_O

AM_INIT_AUTOMAKE([1.10 no-define])

# Checks for libraries.
AC_CHECK_LIB(pthread, pthread_create, [LIBS="$LIBS -lpthread"])

# Checks for header files.
AC_CHECK_HEADERS([fcntl.h netinet/in.h stdlib.h string.h sys/ioctl.h sys/socket.h unistd.h])

# Checks for typedefs, structures, and compiler characteristics.
AC_HEADER_STDBOOL
AC_TYPE_SIZE_T
AC_TYPE_UINT16_T
AC_TYPE_UINT32_T

# Checks for library functions.
AC_FUNC_MALLOC
AC_CHECK_FUNCS([bzero memset select socket])

#AC_SUBST(CFLAGS)

AC_CONFIG_FILES([Makefile])
AC_OUTPUT
