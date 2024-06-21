# This Makefile has description about:
# 1) include directive
# 2) vpath directive
# 3) multilines with `\`
# 4) .PHONY
# 5) .DELETE_ON_ERROR

# include directive
# The include directive tells make to read other makefiles. It is written in the format `include filenames...`

# vpath directive
# The vpath directive is used to specify path to dependencies in other directories.
# - syntax: `vpath pattern directories`
# - example: `vpath %.h ../headers ../other-directory` will search for any `.h` files in headers or other-directory

vpath %.h ../headers ../other-directory

### .delete_on_error will delete the target of a rule if it results in an error. It is good practice to do it for every target.
.DELETE_ON_ERROR:
all: some_binary

# vpath allows blah.h to be found even if blah.h is not in the current directory
some_binary: ../headers blah.h
	echo This line is too long, so \
		it is broken up into another line.
	touch some_binary

# create headers folder if it doesn't exist in the current path and is not found through vpath either.
../headers:
	mkdir ../headers

# We call the target blah.h instead of ../headers/blah.h, because that's the prereq that some_binary is looking for, but blah.h is created inside headers so that it is found through vpath
# Typically, blah.h would already exist and you wouldn't need this.
blah.h:
	touch ../headers/blah.h

# .phony is used to specify that a target is NOT a file name. It is mostly used with `all` and `clean` targets to specify that even if the files all and clean exist, we shall run the commands inside the target.
.PHONY: clean
clean:
	rm -rf ../headers
	rm -f some_binary

