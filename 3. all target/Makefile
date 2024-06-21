# By default the first target in the makefile will run.
# If one wants all of the targets to run, one can specify their names in the all target

all: one two three

# Multiple targets
# If their are multiple targets, the command will run for each of them.
# The `$@` is an automatic variable that contains the target name.

one two three:
	touch $@

# the above is equivalent to:
# ```
# one:
# 	touch one
# two:
# 	touch two
# three:
# 	touch three
# ```

clean:
	rm -f one two three
