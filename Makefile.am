##  Makefile.am
# 
# Copyright (C) 2009  The University of Texas at Austin.
# 
# This file is part of Hydra: A wireless multihop testbed.
# 
# This program is free software: you can redistribute it and/or modify
# it under the terms of the GNU General Public License as published by
# the Free Software Foundation, either version 3 of the License, or
# (at your option) any later version.
# 
# This program is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
# GNU General Public License for more details.
# 
# You should have received a copy of the GNU General Public License
# along with this program.  If not, see <http://www.gnu.org/licenses/>.
# 

include $(top_srcdir)/Makefile.common

meta80211nsrcdir=$(top_srcdir)/src
DSPLINK := /home/root/ti/dsplink_linux_1_65_00_03/dsplink


META80211N_INCLUDES = -I$(DSPLINK)/gpp/inc -I$(DSPLINK)/gpp/inc/usr -I$(DSPLINK)/gpp/inc/sys/Linux -I$(DSPLINK)/gpp/inc/sys/Linux/2.6.18 -I$(BASE_TOOLCHAIN)/arm-angstrom-linux-gnueabi/include/c++/4.5.3 -I$(DSPLINK)/gpp/BUILD/INCLUDE/USER  -I$(DSPLINK)/gpp/export/INCLUDE/Linux/OMAP3530/internal -I./

INCLUDES = $(META80211N_INCLUDES) $(STD_DEFINES_AND_INCLUDES)

noinst_LTLIBRARIES = libdsplinkapi.la
libdsplinkapi_la_SOURCES = ring_io.c \
                           ring_io_os.c
libdsplinkapi_la_LDFLAGS = -lpthread
libdsplinkapi_la_CPPFLAGS = -DOS_LINUX -DMAX_DSPS=1 -DMAX_PROCESSORS=2 -DID_GPP=1 -DOMAP3530 -DPROC_COMPONENT -DPOOL_COMPONENT -DNOTIFY_COMPONENT -DMPCS_COMPONENT -DRINGIO_COMPONENT -DMPLIST_COMPONENT -DMSGQ_COMPONENT -DMSGQ_ZCPY_LINK -DCHNL_COMPONENT -DCHNL_ZCPY_LINK -DZCPY_LINK -DKFILE_DEFAULT -DOMAP3530 -DOMAP3530_PHYINTERFACE=SHMEM_INTERFACE -DGPP_SWI_MODE -D_REENTRANT 
libdsplinkapi_la_LIBADD  = $(DSPLINK)/gpp/export/BIN/Linux/OMAP3530/DEBUG/dsplink.lib 

metainclude_HEADERS =  ring_io.h \
                       ring_io_os.h
