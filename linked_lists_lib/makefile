# Compiler and flags
CC = gcc
CFLAGS = -Wall -Wextra -Wformat-security
PGFLAG = -pg
CGCV = -fprofile-arcs -ftest-coverage # gcov testing flags
GCOVFILES = linked_list*gc*  
PGFILES = *.data *.out 
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
	$(CC) $(CFLAGS) $(LIBS) $(CGCV) $(PGFLAG) $(MAIN) -o $@ $^

# Compile source files
$(OBJFILES): $(CFILES)
	$(CC) $(CFLAGS) $(CGCV) $(PGFLAG) -c $^ 

clean:
	rm $(BIN)* $(OBJFILES) $(GCOVFILES) $(PGFILES)  

start:
		 $(BIN)
