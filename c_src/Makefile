
include ../config/include.mk

PRIV_FILES=../priv/RE_drv.so 


CFLAGS += -I$(ERL_C_INCLUDE_DIR) -I../config -I.


#
# Targets
#

all: $(PRIV_FILES)

clean:
	-rm -f $(PRIV_FILES) RE_drv.o 


install: 
	install -d $(ERLDIR)/lib/posregex
	cp -r `pwd` $(ERLDIR)/lib/posregex
	cp -r `pwd`/../ebin $(ERLDIR)/lib/posregex
	cp -r `pwd`/../priv $(ERLDIR)/lib/posregex


../priv/RE_drv.so: RE_drv.o 
	$(LD_SHARED) -o $@ RE_drv.o $(LIBS)


RE_drv.o: RE_drv.c
	$(CC) -o $@ -c -fpic $(CFLAGS) -DDYNAMIC_DRIVER RE_drv.c


