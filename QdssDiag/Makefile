#obj-m := QdssDiag.o ../InfParser/qtiDevInf.o
obj-m := QdssDiag.o
QdssDiag-objs := qtiDiag.o qtiEvt.o
KDIR := /lib/modules/$(shell uname -r)/build
PWD := $(shell pwd)
EXTRA_CFLAGS:= -D QCUSB_TEST_ONLY

all: clean
	$(MAKE) -C $(KDIR) M=$(PWD) modules

clean:
	rm -rf *.o *~ core .depend .*.cmd *.ko *.mod.c .tmp_versions Module.* modules.order *.ur-safe



