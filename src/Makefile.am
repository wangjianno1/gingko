SUBDIRS = hash .
INCLUDES = -I$(srcdir)/src\
    -I$(srcdir)/hash \
    -include config.h \
    -I$(srcdir)/../lib/libev/include 
#    -I$(srcdir)/../../../../../../third-64/libev/include 
#    -I$(srcdir)/../../../../../../../third-64/libev/include 
#export INCLUDES

noinst_PROGRAMS=gingko_serv gingko_clnt

clnt_unittest_SOURCES=async_threads.cpp async_conn.cpp \
    gingko_base.cpp path.cpp log.cpp option.cpp socket.cpp limit.cpp \
    route.cpp snap.cpp clnt_unittest.cpp gingko_clnt.cpp progress.cpp
clnt_unittest_LDADD=$(srcdir)/../lib/libev/lib/libev.a \
	$(srcdir)/../../../../../../third-64/gtest/lib/libgtest.a \
    $(srcdir)/hash/libxor_hash.a \
    $(srcdir)/hash/libgko_zip.a
clnt_unittest_LDFLAGS=-D_GNU_SOURCE -ggdb -funsigned-char

serv_unittest_SOURCES=async_threads.cpp async_conn.cpp \
    gingko_base.cpp path.cpp log.cpp option.cpp socket.cpp limit.cpp \
    seed.cpp hash/xor_hash.cpp serv_unittest.cpp gingko_serv.cpp
serv_unittest_LDADD=$(srcdir)/../lib/libev/lib/libev.a \
	$(srcdir)/../../../../../../third-64/gtest/lib/libgtest.a \
    $(srcdir)/hash/libxor_hash.a \
    $(srcdir)/hash/libgko_zip.a
serv_unittest_LDFLAGS=-D_GNU_SOURCE -ggdb -funsigned-char

gingko_serv_SOURCES=async_threads.cpp async_conn.cpp gingko_serv.cpp serv_main.cpp\
    gingko_base.cpp path.cpp log.cpp option.cpp socket.cpp limit.cpp \
    seed.cpp 
gingko_serv_LDADD=$(srcdir)/../lib/libev/lib/libev.a \
    $(srcdir)/hash/libxor_hash.a \
    $(srcdir)/hash/libgko_zip.a
gingko_serv_LDFLAGS=-D_GNU_SOURCE -ggdb -funsigned-char -lpthread

gingko_clnt_SOURCES=async_threads.cpp async_conn.cpp gingko_clnt.cpp clnt_main.cpp\
    gingko_base.cpp path.cpp log.cpp option.cpp socket.cpp limit.cpp \
    route.cpp snap.cpp progress.cpp
gingko_clnt_LDADD=$(srcdir)/../lib/libev/lib/libev.a \
    $(srcdir)/hash/libxor_hash.a \
    $(srcdir)/hash/libgko_zip.a
gingko_clnt_LDFLAGS=-D_GNU_SOURCE -ggdb -funsigned-char -lpthread

DEFS=-D_GNU_SOURCE -ggdb -funsigned-char
