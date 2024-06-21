hello:
	echo "Hello, world!"
	echo "This line will print if the file hello does not exist."

# makefile syntax generally looks like this:
# ```
# targets: dependencies/prerequisites
# command01
# command02
# more commands...
# ```

some_file: other_file  # this will run if timestamp of other_file changes, or if other_file does not exist.
	echo "This will run last."
	touch some_file

other_file: yet_another_file  # this will run if timestamp of yet_another_file changes, or if yet_another_file doesn't exist.
	echo "This will run after yet_another_file."
	touch other_file

yet_another_file: 
	echo "This has no dependencies, so this will run first."


# Variables
# variables are made using :=, and references using either ${} or $()
# all variables are strings of characters
files := file1 file2
some_file: $(files)
	echo "Constructed some_file using: " $(files)
	touch some_file

file1:
	touch file_1
file2:
	touch file_2

clean:
	rm -f $(files) some_file