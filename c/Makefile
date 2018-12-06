CFLAGS_XMMS2=`pkg-config --cflags xmms2-client`
CFLAGS_GLIB=`pkg-config --cflags glib-2.0`
LIBS_XMMS2=`pkg-config --libs xmms2-client`
LIBS_GLIB=`pkg-config --libs xmms2-client-glib` `pkg-config --libs glib-2.0`

all: xmms2 xmms2glib

xmms2: CFLAGS=$(CFLAGS_XMMS2)
xmms2: LIBS=$(LIBS_XMMS2)
xmms2: tut1 tut2 tut3 tut4 tut5

xmms2glib: CFLAGS=$(CFLAGS_XMMS2) $(CFLAGS_GLIB)
xmms2glib: LIBS=$(LIBS_XMMS2) $(LIBS_GLIB)
xmms2glib: tut6 tut7 tut8

%.o: %.c
	gcc $(CFLAGS) -Wall -c -o $@ $< 

tut%: tut%.o
	gcc -o $@ $< $(LIBS)

clean:
	rm -f tut? *.o

