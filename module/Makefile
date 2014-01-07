MODULE_NAME = FileNVRAM
MODULE_AUTHOR = xZenue LLC.
MODULE_DESCRIPTION = FileNVRAM module for preloading NVRAM values
MODULE_VERSION = "1.1.4"
MODULE_COMPAT_VERSION = "1.0.0"
MODULE_START = $(MODULE_NAME)_start
MODULE_DEPENDENCIES = 

DIR = FileNVRAM

MODULE_OBJS   = FileNVRAM.o kernel_patcher.o

HAS_EMBEDED:=$(shell test -f FileNVRAM.mkext && echo "true")

include ../MakeInc.dir


ifeq (${HAS_EMBEDED},true)
${warning ${HAS_EMBEDED}}
DEFINES:=-DHAS_MKEXT ${DEFINES}
else
DEFINES:=-DNO_MKEXT ${DEFINES}
endif




FileNVRAM.mkext.h: FileNVRAM.mkext
	xxd -i FileNVRAM.mkext > $@
