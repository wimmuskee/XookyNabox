#
#  Makefile
#  xooky_nabox
#
#  Created by Rafael Vega on 2011-03-02.
#

# Parameters
COMPILER = g++
LINKER = g++
COMPILER_FLAGS = -Wall -g -c -I/usr/include/pd
LINKER_FLAGS = -lpd -ljack
CPP_FILES = $(wildcard *.cpp)
OBJECTS = $(notdir $(CPP_FILES:.cpp=.o)) # List of .cpp files with .o extension

# Link app
main: $(OBJECTS)
	$(LINKER) $(LINKER_FLAGS) $(MORE_LINKER_FLAGS) $(OBJECTS) -o ../bin/xooky_nabox

# Compile all cpp files into their own .o files
%.o: %.cpp
	$(COMPILER) $(COMPILER_FLAGS) $*.cpp -o $*.o

# Install 
install: main
	mkdir -p $(DESTDIR)/usr/bin
	cp -f ../bin/xooky_nabox $(DESTDIR)/usr/bin

# Clean
.PHONY: clean
clean:
	-rm *.o
	-rm ../bin/*
