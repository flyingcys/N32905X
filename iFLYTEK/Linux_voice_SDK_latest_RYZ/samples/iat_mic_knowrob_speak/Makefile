#common makefile header

DIR_INC = ../../include
DIR_BIN = ../../bin
DIR_LIB = ../../libs

TARGET	= iChat6
BIN_TARGET = $(DIR_BIN)/$(TARGET)

#TAR_TTS = tts_know
#BIN_TAR_TTS = $(DIR_BIN)/$(TAR_TTS)

CROSS_COMPILE =arm-linux-
CFLAGS = -Os -g -Wall -I$(DIR_INC)
#CFLAGS = -O0 -g -Wall -I$(DIR_INC)

#可根据实际需要修改，选择所需平台SDK，默认为x64或x86平台。
ifdef LINUX64
LDFLAGS := -L$(DIR_LIB)/x64
else
LDFLAGS := -L$(DIR_LIB)/x86 
endif

LDFLAGS += -lmsc -lrt -ldl -lpthread -lasound -lm

OBJECTS := $(patsubst %.c,%.o,$(wildcard *.c))

$(BIN_TARGET) : $(OBJECTS)
	$(CROSS_COMPILE)gcc $(CFLAGS) $^ -o $@ $(LDFLAGS)

#$(BIN_TAR_TTS) : $(OBJECTS)
#	$(CROSS_COMPILE)gcc $(CFLAGS) $^ -o $@ $(LDFLAGS)

%.o : %.c
	$(CROSS_COMPILE)gcc -c $(CFLAGS) $< -o $@
clean:
	@rm -f *.o $(BIN_TARGET)

.PHONY:clean

#common makefile foot
