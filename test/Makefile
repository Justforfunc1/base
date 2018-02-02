#LANG=C
SRC_PATH=../test
BIN_PATH=../bin
INC_PATH=-I. -I../include
LIB_PATH=-L../lib
SHRLIB_PATH = ../lib

LIB= -lpthread -ljsoncpp -llpbase
SHRLIB = $(SHRLIB_PATH)/liblpbase.so \
		 $(SHRLIB_PATH)/libjsoncpp.so

STLIB = 

CC= gcc
CPPFLAGS= -Wall -g 

OBJS = 

.PHONY:all clean 

all: log_test json_test

compile:
#	$(CC) $(CPPFLAGS) $(INC_PATH) $(LIB_PATH) -c epoll_connection.cpp -o epoll_connection.o
	
	
log_test:
	$(CC) $(CPPFLAGS) $(INC_PATH) $(LIB_PATH) $(SHRLIB) $(LIB) -Wl,-rpath=$(SHRLIB_PATH) log_test.cpp -o log_test_mian
	@printf "\033[32m LOG_TEST SUCCESS \033[0m\n"

json_test:
	$(CC) $(CPPFLAGS) $(INC_PATH) $(LIB_PATH) $(SHRLIB) $(LIB) -Wl,-rpath=$(SHRLIB_PATH) json_test.cpp -o json_test_main
	@printf "\033[32m JSON_TEST SUCCESS \033[0m\n"

run:

clean:
	rm -f *.o log_test_mian json_test_main

tags:
	rm -rf tags
	touch tags
	find . -iname '*.cpp' -or -iname '*.c' -or -iname '*.h'-or -iname '*.hpp' | xargs ctags --c++-kinds=+p --fields=+iaS --extra=+q --langmap=c++:+.inl -a tags

