blah: blah.c
	gcc blah.c -o blah

# blah.c is a dependency of blah. If timpestamp of blah.c changes, then make will recompile blah again using blah.c

# NOTE: to make the c file if it doesn't exist, one can use the following pattern:
# ```
# blah.c:
# 	echo "int main() { return 0; }" > blah.c
# ```