# make has special flags for compiling C without explicitly stating the compilation
# Implicit compilation is done by expressing flags:
# CC (the c compiler) [ex. gcc, clang, etc.]
# CFLAGS (additional flags) [ex. -g, -c, -lm, etc.]
# CPPFLAGS (preprocessor flags) [ex. -E, -include, -D, etc.]
# LDFLAGS (linker flags)
# LOADLIBES/LDLIBS (linker libraries to load)

# These flags are specified as Makefile variables and are implicitly compiled in the form:
# C file to object file compilation rule:
# `$(CC) -c $(CPPFLAGS) $(CFLAGS) $^ -o $@`
# Object file to executable compilation rule:
# `$(CC) $(LDFLAGS) $^ $(LOADLIBES) $(LDLIBS) -o $@`

CC = gcc
CFLAGS = -g

# blah is built from blah.o using executable compilation rule automatically. 
# blah.o is built from blah.c using object compilation rule automatically.
blah: blah.o  

blah.c: # automatically make blah.c if it doesn't exist
	echo "int main() { return 0; }" > blah.c

clean:
	rm -f $(wildcard blah*)