# Compiler and flags
CC = gcc
CFLAGS = -Wall -Wextra -Wformat-security
CGCV = -fprofile-arcs -ftest-coverage # gcov testing flags
GCOVFILES = linked_list*gc*  
LIBS = 
MAIN = main.c

# Source and object files
CFILES = ./src/*.c
OBJFILES = *.o  

# Target binaries
BIN = ./bin/Linked_list_test

all: $(BIN)

# Build executable
$(BIN): $(OBJFILES)
	$(CC) $(CFLAGS) $(LIBS) $(CGCV) $(MAIN) -o $@ $^

# Compile source files
$(OBJFILES): $(CFILES)
	$(CC) $(CFLAGS) $(CGCV) -c $^ 

clean:
	rm $(BIN) $(OBJFILES) $(GCOVFILES)   
start:
	 $(BIN)
