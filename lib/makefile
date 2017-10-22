.PHONY:clean
CC=gcc
OBJECTS=func1.o func2.o
OUTPUT=libfuncs.so.1.0

libfuncs.so.1 libfuncs.so : libfuncs.so.1.0
	ln -s $(OUTPUT) libfuncs.so.1
	ln -s $(OUTPUT) libfuncs.so
$(OUTPUT):$(OBJECTS)
	$(CC) -fPIC -shared -Wl,-soname=libfuncs.so.1.0 $(OBJECTS) -o $(OUTPUT) -lc
%.o:%.c
	$(CC) -fPIC -c $< -I../include -o $@
clean:
	rm $(OBJECTS) $(OUTPUT) libfuncs.so.1 libfuncs.so

