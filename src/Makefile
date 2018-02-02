#makefile 
SYSTYPE = LINUX2
LIB_PATH=-L. -L../lib
INC_DIR = -I. -I../src -I../include
CC      = g++
OPT     = -D__LINUX -O2 -Wall -Wl,--as-needed -shared -fPIC
DEBUG   = -g
DEFS    = $(INC_DIR) -lpthread -ljsoncpp
CFLAGS  = $(DEBUG) $(OPT) $(LIB_PATH) $(DEFS)
OBJS    = config.cpp logger.cpp string_util.cpp exception_util.cpp json_util.cpp md5.cpp rc4.cpp encrypt.cpp
LIBS    = liblpbase.so

.PHONY: all clean compile install  

all: clean compile install

compile:
	$(CC) $(CFLAGS) -o $(LIBS) $(OBJS)
	@printf "\033[32m SUCCESS \033[0m\n"

install:
	rm -f ../lib/$(LIBS)
#	cd ../include/ && find . -type f -name "*.h" | xargs -i rm {}
	cd ../include/ && rm -f *.h
	cp -rpf ../src/$(LIBS) ../lib/$(LIBS)
	cp -rpf *.h ../include

clean:
	rm -f $(LIBS)
