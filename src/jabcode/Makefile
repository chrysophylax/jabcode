PREFIX 	=
CC 	= $(PREFIX)gcc
AR 	= $(PREFIX)ar
RANLIB	= $(PREFIX)ranlib
CFLAGS	= -O2 -std=c11 -no-pie

TARGET = build/libjabcode.a

OBJECTS := $(patsubst %.c,%.o,$(wildcard *.c))

$(TARGET): $(OBJECTS)
	$(AR) cru $@ $?
	$(RANLIB) $@

$(OBJECTS): %.o: %.c
	$(CC) -fPIC -c -I. -I./include $(CFLAGS) $< -o $@

clean:
	rm -f $(TARGET) $(OBJECTS)


bing:
	$(CC) *.o -fPIC -L/home/billy/projects/buildroot/build/libpng -L/home/billy/projects/buildroot/build/libtiff -L/home/billy/projects/buildroot/build/libz -lpng -ltiff -lz -shared -o libjabcode.so
