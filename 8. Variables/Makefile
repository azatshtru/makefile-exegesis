# `=` makes recursive variables, the value of which can be set by changing it's components later.
one = one ${later_variable}

# `:=` makes simple variables, the value of which cannot be set later by changing it's components later.
two := two ${later_variable}

# later_variable is a component of both one and two, but only one will be affected.
later_variable = later

# `?=` sets variables only if they are not already set.
one ?= will not be set
three ?= will be set

# `+=` appends something to the variable
two += something

# variables can be passed to make in command line by writing `make option_one=hi`
# to override variables, write `override option_one=byebye`

# To store a sequence of commands in a variable such that they run in different shells use `define`
define hello_one
export blah="I was set!"
echo $$blah
endef

# To store a sequence of commands running in the same shell use semicolon between the commands on the same line.
hello_two = export blah="I was set!"; echo $$blah

all: some_target
	@echo $(one)
	@echo $(two)
	@echo $(three)
	@echo $(specific_one)  # this command will print nothing
	$(hello_one)  # this command will print nothing
	$(hello_two)

# variables can be set for specific targets
some_target: specific_one = cool

#variables can be set for specific patterns
%.c: specific_two = cool

some_target:
	@echo $(specific_one)  # this will print
	@echo $(specific_two)  # this will not print
	touch some_target

blah.c:
	@echo $(specific_two)  # this will print
	@echo $(specific_one)  # this will not print

# undefined variables are empty strings
# spaces at the end of the variable are not stripped while the ones at the beginning are.