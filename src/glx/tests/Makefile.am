if HAVE_SHARED_GLAPI
AM_CFLAGS = $(PTHREAD_CFLAGS)
AM_CPPFLAGS = \
	-I$(top_srcdir)/src/gtest/include \
	-I$(top_srcdir)/src \
	-I$(top_srcdir)/src/mapi \
	-I$(top_srcdir)/src/mesa \
	-I$(top_builddir)/src/glx \
	-I$(top_srcdir)/src/glx \
	-I$(top_srcdir)/include \
	-I$(top_srcdir)/include/GL/internal \
	$(DEFINES) \
	$(LIBDRM_CFLAGS) \
	$(X11_INCLUDES)

TESTS = glx-test dispatch-index-check
check_PROGRAMS = glx-test
EXTRA_DIST = dispatch-index-check meson.build

glx_test_SOURCES =			\
	clientinfo_unittest.cpp		\
	create_context_unittest.cpp	\
	enum_sizes.cpp			\
	fake_glx_screen.cpp		\
	fake_glx_screen.h		\
	indirect_api.cpp		\
	mock_xdisplay.h			\
	query_renderer_unittest.cpp

if HAVE_DRI2
glx_test_SOURCES += \
	query_renderer_implementation_unittest.cpp
endif

glx_test_LDADD = \
	$(top_builddir)/src/glx/libglx.la \
	$(top_builddir)/src/gtest/libgtest.la \
	$(top_builddir)/src/mapi/shared-glapi/libglapi.la \
	$(PTHREAD_LIBS)
endif
