MAINTAINERCLEANFILES =  $(srcdir)/Makefile.in

AM_CPPFLAGS =   -I$(srcdir)/..                  \
                -I$(srcdir)/../common           \
                -I$(srcdir)/../crypto           \
                -I$(srcdir)/../data_mgr         \
                -I$(srcdir)/../object_store     \
                -I$(srcdir)/../session_mgr      \
                -I$(SGXSDKDIR)/include          \
                -I$(SGXSDKDIR)/include/tlibc    \
                -I$(SGXSDKDIR)/include/libcxx   \
                -I$(SGXSDKDIR)/include/stdc++   \
                -I$(SGXSDKDIR)/include/stlport 

if WITH_P11_KIT
AM_CPPFLAGS += -I$(P11_KIT_INCLUDE_PATH)
else
AM_CPPFLAGS += -I$(srcdir)/../pkcs11
endif

AM_CFLAGS = -D_FORTIFY_SOURCE=2 -DOSID=1 -m64 -std=c11 -O3 -Wall -Wno-implicit-function-declaration -nostdinc -fno-builtin-printf -fvisibility=hidden -fstack-protector -fpie -fpic -Wformat -Wformat-security -fno-strict-overflow -fno-delete-null-pointer-checks -fwrapv -Wreturn-type -Werror=return-type
AM_CXXFLAGS = -D_FORTIFY_SOURCE=2 -DOSID=1 -m64 -std=c++11 -O3 -Wall -nostdinc++ -fstack-protector -fpie -fpic -Wformat -Wformat-security -fno-strict-overflow -fno-delete-null-pointer-checks -fwrapv -Wreturn-type -Werror=return-type

noinst_LTLIBRARIES =	libsofthsm_slotmgr.la

libsofthsm_slotmgr_la_SOURCES = SlotManager.cpp \
                                Slot.cpp        \
                                Token.cpp

EXTRA_DIST = $(srcdir)/*.h
