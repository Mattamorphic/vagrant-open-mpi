##
# Reusable Makefile  
#
# usage: `make [PROCESS] TARGET=[FILENAME_NO_EXT] NODES=node1,node2,node3`
# example: `make all TARGET=hello-world NODES=node1,node2,node3`
COMPILER=mpic++
COMPILER_FLAGS=-g -std=c++0x -O0
OBJECTS=$(TARGET).o
HOSTS=--host $(NODES)
PROCESS_COUNT = -np $(shell echo $(NODES), | grep -o "," | wc -l)

SUFFIXES: .cpp .o 

all: $(OBJECTS)
	$(COMPILER) -o $(TARGET) $(OBJECTS)  

clean:
	rm $(OBJECTS) $(TARGET)

.cpp.o:
	$(COMPILER) $(COMPILER_FLAGS) -c $*.cpp 

run:
	mpirun --mca btl_tcp_if_exclude lo,eth0 $(PROCESS_COUNT) $(HOSTS) $(TARGET)

build-and-run: all run
