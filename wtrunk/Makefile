CFLAGS=-O2 -g -Wall -W $(shell pkg-config --cflags librtlsdr libhackrf libairspy soxr)
LDLIBS+=$(shell pkg-config --libs librtlsdr libhackrf libairspy soxr) -lpthread -lm
CC=gcc
PROGNAME=motorola

all: motorola

%.o: %.cpp
	$(CC) $(CFLAGS) -I. -c $<


motorola: dumper2.o edacs.o eedump.o etrunk.o infoact.o inthdlr.o mdt.o motfreq.o moto.o platform.o scrlog.o stats.o stubs.o trunksys.o tsysinfo.o
	$(CC) -g -o motorola dumper2.o edacs.o eedump.o etrunk.o infoact.o inthdlr.o mdt.o motfreq.o moto.o platform.o scrlog.o stats.o stubs.o trunksys.o tsysinfo.o  $(LDFLAGS) $(LDLIBS)

clean:
	rm -f *.o motorola
