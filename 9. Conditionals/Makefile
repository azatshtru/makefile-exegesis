# sets foo if not already given through the command line
foo = ok

all:
# conditionals can be used to check the value of variables
ifeq ($(foo), ok)
	@echo "foo equals ok"
else
	@echo "foo doesn't equal ok"
endif

# conditionals can be used to check if a variable is empty
ifeq ($(strip $(foo)),)
	@echo "foo is just whitespace"
endif

# conditionals can be used to check if a variable is defined
ifdef foo
	@echo "foo is defined"
endif
ifndef foo
	@echo "foo is not defined"
endif

# conditionals can be used to check makeflags passed during execution. The $(MAKEFLAGS) variable contains the passed flags.
ifneq (,$(findstring i, $(MAKEFLAGS)))
	echo "i was passed to make"
endif