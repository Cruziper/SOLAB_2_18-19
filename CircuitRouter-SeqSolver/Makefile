# Makefile, versao 1
# Sistemas Operativos, DEI/IST/ULisboa 2018-19

SOURCES1 = router.c maze.c grid.c coordinate.c CircuitRouter-SeqSolver.c
SOURCES1+= ../lib/vector.c ../lib/queue.c ../lib/list.c ../lib/pair.c

SOURCES2 = ../lib/commandlinereader.c ../lib/vector.c ../CircuitRouter-SimpleShell/CircuitRouter-SimpleShell.c

SOURCES3 = ../CircuitRouter-ParSolver/CircuitRouter-ParSolver.c

OBJS1   = $(SOURCES1:%.c=%.o)
OBJS2   = $(SOURCES2:%.c=%.o)
OBJS3   = $(SOURCES3:%.c=%.o)	
CC      = gcc
CFLAGS  =-Wall -std=gnu99 -I../
LDFLAGS =-lm
TARGET1 = CircuitRouter-SeqSolver
TARGET2 = CircuitRouter-SimpleShell
TARGET3 = CircuitRouter-ParSolver

all: $(TARGET1) $(TARGET2) $(TARGET3)

$(TARGET1): $(OBJS1)
	$(CC) $(CFLAGS) $^ -o $(TARGET1) $(LDFLAGS)

$(TARGET2): $(OBJS2)
	$(CC) $(CFLAGS) $^ -o $(TARGET2) $(LDFLAGS)

$(TARGET3): $(OBJS3)
	$(CC) $(CFLAGS) $^ -o $(TARGET3) $(LDFLAGS)

CircuitRouter-SeqSolver.o: CircuitRouter-SeqSolver.c maze.h router.h ../lib/list.h ../lib/timer.h ../lib/types.h
../CircuitRouter-SimpleShell/CircuitRouter-SimpleShell.o: ../CircuitRouter-SimpleShell/CircuitRouter-SimpleShell.c ../CircuitRouter-SimpleShell/CircuitRouter-SimpleShell.h ../lib/commandlinereader.h ../lib/vector.h
../CircuitRouter-ParSolver/CircuitRouter-ParSolver.o: ../CircuitRouter-ParSolver/CircuitRouter-ParSolver.c
maze.o: maze.c maze.h coordinate.h grid.h ../lib/list.h ../lib/queue.h ../lib/pair.h ../lib/types.h ../lib/vector.h
grid.o: grid.c grid.h coordinate.h ../lib/types.h ../lib/vector.h
router.o: router.c router.h coordinate.h grid.h ../lib/vector.h ../lib/queue.h
coordinate.o: coordinate.c coordinate.h ../lib/pair.h ../lib/types.h
../lib/vector.o: ../lib/vector.c ../lib/vector.h ../lib/types.h ../lib/utility.h
../lib/queue.o: ../lib/queue.c ../lib/queue.h ../lib/types.h
../lib/list.o: ../lib/list.c ../lib/list.h ../lib/types.h
../lib/pair.o: ../lib/pair.c ../lib/pair.h
../lib/commandlinereader.o: ../lib/commandlinereader.c

$(OBJS1):
	$(CC) $(CFLAGS) -c -o $@ $<

$(OBJS2):
	$(CC) $(CFLAGS) -c -o $@ $<

$(OBJS3):
	$(CC) $(CFLAGS) -c -o $@ $<

clean:
	@echo Cleaning...
	rm -f $(OBJS1) $(OBJS2) $(OBJS3) $(TARGET1) $(TARGET2) $(TARGET3)
