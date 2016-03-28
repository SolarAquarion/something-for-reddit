AC_PREREQ(2.63)
AC_INIT([reddit-is-gtk],
        [0.1],
        [https://github.com/samdroid-apps/reddit-is-gtk/issues],
        [reddit-is-gtk],
        [https://github.com/samdroid-apps/reddit-is-gtk])
AC_CONFIG_MACRO_DIR([m4])
AC_CONFIG_SRCDIR([Makefile.am])
AC_CONFIG_HEADERS(config.h)
AM_INIT_AUTOMAKE([1.11 tar-ustar dist-xz no-dist-gzip -Wno-portability subdir-objects])
AM_MAINTAINER_MODE([enable])
m4_ifdef([AM_SILENT_RULES],[AM_SILENT_RULES([yes])])

AM_PATH_PYTHON([3.3])

AC_PROG_CC
AM_PROG_CC_C_O
LT_INIT([disable-static])

PKG_PROG_PKG_CONFIG([0.22])

GETTEXT_PACKAGE=reddit-is-gtk
AC_SUBST(GETTEXT_PACKAGE)
AC_DEFINE_UNQUOTED(GETTEXT_PACKAGE, "$GETTEXT_PACKAGE",
                   [The prefix for our gettext translation domains.])
IT_PROG_INTLTOOL(0.26)

AX_PYTHON_MODULE([arrow], [For date humanization])
AX_PYTHON_MODULE([markdown], [For reddit markdown])
# pip3 install git+https://github.com/r0wb0t/markdown-urlize
AX_PYTHON_MODULE([mdx_urlize], [For autolinking in reddit markdown])

GLIB_GSETTINGS
GOBJECT_INTROSPECTION_REQUIRE([1.35.9])
PKG_CHECK_MODULES([GTK], [gtk+-3.0 >= 3.13.2])
PKG_CHECK_MODULES([LIBSOUP], [libsoup-2.4 >= 2.4])

GLIB_COMPILE_RESOURCES=`$PKG_CONFIG --variable glib_compile_resources gio-2.0`
AC_SUBST(GLIB_COMPILE_RESOURCES)

AC_CONFIG_FILES([
  Makefile
  data/Makefile
  src/Makefile
  po/Makefile.in
])
AC_OUTPUT