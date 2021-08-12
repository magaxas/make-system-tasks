CC:=gcc
CPPFLAGS:=-I$(CURDIR)
CFLAGS:=-Wall

BIN:=calculator
SRC:=$(wildcard *.c)
OBJS:=$(SRC:.c=.o)

.PHONY: all clean

all: $(BIN)

$(BIN): $(OBJS)
	$(CC) $(CPPFLAGS) $(CFLAGS) -o $@ $^

clean:
	$(RM) $(BIN) $(OBJS)
