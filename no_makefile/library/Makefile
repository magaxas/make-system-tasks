CC:=gcc
LDFLAGS:=-L$(CURDIR) -lfilereader
CFLAGS:=-Wall -fpic -shared
CPPFLAGS:=-I$(CURDIR)
PREFIX?=/usr
LD_LIBRARY_PATH=$(CURDIR)/

BIN:=main
LIB:=libfilereader.so

SRC:=$(wildcard *.c)
OBJS:=$(SRC:.c=.o)
HEADERS=$(wildcard *.h)

.PHONY: all lib clean install uninstall

all: $(LIB) $(BIN)
lib: $(LIB)
bin: $(BIN)

$(LIB): $(OBJS)
	$(CC) $(CFLAGS) $(CPPFLAGS) -o $@ $^ $(LDFLAGS)

install:
	install -d $(PREFIX)/lib
	install -d $(PREFIX)/include
	install -m 444 $(LIB) $(PREFIX)/lib/$(LIB)
	install -m 444 $(HEADERS) $(PREFIX)/include/

uninstall:
	$(RM) $(foreach header,$(HEADERS),$(PREFIX)/include/$(header))
	$(RM) $(PREFIX)/lib/$(LIB)

clean:
	$(RM) $(LIB) $(OBJS) $(BIN)
