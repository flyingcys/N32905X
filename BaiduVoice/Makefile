.SUFFIXES : .x .o .c .s

CC = gcc
CXX = g++

TARGET = BaiduVoice
SRCS := sample.cpp base64.cpp 
LIBS = -lcurl
LDFLAGS= ./json-cpp/lib/libjson.a ./curl/lib/libcurl.a

all: 
	$(CXX) $(SRCS) -o $(TARGET) $(LIBS) $(LDFLAGS)
clean:
	rm -f *.o 
	rm -f *.x 
	rm -f *.flat
	rm -f *.map
	rm -f temp
	rm -f *.img
	rm -f $(TARGET)	
	rm -f *.gdb
	rm -f *.bak
