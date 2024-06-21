obj_files = foo.result bar.o lose.o
src_files = foo.raw bar.c lose.c

all: $(obj_files)

# `%` has a stem that can be replaced by something while matching target
# after that `%` can be used in dependencies and will be replaced by the stem matched in target

# filter `.o` targets from obj_files and replace % with their names,
# then set corresponding `.c` files with same names in % as their dependencies.
$(filter %.o,$(obj_files)): %.o: %.c 
	echo "target: $@ prereq: $<"

# filter `.result` targets from obj_files and replace % with their names,
# then set corresponding `.raw` files with same names in % as their dependencies.
$(filter %.result,$(obj_files)): %.result: %.raw
	echo "target: $@ prereq: $<"

# these are the core dependencies, `%` is used here as a specific wildcard to build these when needed
%.c %.raw:
	touch $@

clean:
	rm -f $(src_files)

# % wildcard can also be used to define your own implicit rules. The syntax is:
%.result: %.raw  # This specifies how to build result using raw
	(cat $< | echo "Result: ") > $@
