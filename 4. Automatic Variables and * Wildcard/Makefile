# automatic variables are set by make and hold special values

hey: one two
	# outputs name of the target
	echo $@

	# outputs all dependencies
	echo $^

	# outputs all dependencies newer than target
	echo $?

	# outputs first dependency
	echo $<

# $(wildcard pattern*pattern) matches * with anything that has the specified pattern

print: $(wildcard *.c)  # matches every c file as prerequisite and prints info about the ones newer than target
	ls -la $?

clean:
	rm $(wildcard *.c)