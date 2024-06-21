# function syntax: `$(fn, arguments)`

# substr function substitutes the second argument in place of the first argument in the third argument string.
superman := $(subst not,"totally", "I am not superman")
# do not put spaces between arguments unless required

# replacing spaces with commas
comma += ,
empty:=
space := $(empty) $(empty)
foo := a b c
bar := $(subst $(space),$(comma),$(foo))

# the foreach function replaces space separated strings with other space separated strings
regular_foo := who are you
exclaimed_foo := $(for word,$(regular_foo),$(word)!)

# the if function checks if the first argument is non-empty, if it is, then the second argument is run, otherwise the third.
nonempty_foo := $(if this-is-non-empty,then!,else!)
empty :=
empty_foo := $(if $(empty),then!,else!)

# to define your own function, create a variable with multiple commands, use $(1), $(2), etc. as arguments
# the function name is $(0)
# user defined functions are called by using a special call function
sweet_new_fn = @echo "function name: $(0), first arg: $(1), second arg: $(2)"


# the filter function is used to select only the elements that match some pattern
obj_files = foo.result bar.o lose.o
filtered_files = $(filter %.o,$(obj_files))
# to negate the pattern match and select everything except the pattern, use the function `filter-out`
# multiple patterns can be specified by separating them by space in the patterns argument

all:
	@echo $(superman)
	@echo $(bar)
	@echo $(exclaimed_foo)
	@echo $(nonempty_foo)
	@echo $(empty_foo)
	@echo $(filtered_files)
# the call function is used to call a user defined function
	$(call sweet_new_fn,go,tigers)
# the shell function is used to call shell functions, only the newlines are replaced by spaces
	@echo $(shell ls -la)
