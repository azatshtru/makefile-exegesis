# Commands
- Every command runs in its own shell
- To silence a command use @: `@echo "This command will not be printed, but this sentence will be."`
- To supress the error from a command use -: `-command` will ignore any errors generated.
- default shell of make is /bin/bash, to change it: modify the SHELL flag variable
- double dollar sign (`$$`) is used to write `$`.
- run `make -k` to run make with errors, run `make -i` to ignore errors
- other arguments to run make with are `--dry-run` `--touch` `--old-file`

# Environment exports
- To use variables everywhere/globally in Makefile, export them using `export var=something`
- To export every variable, use: 
```
    .EXPORT_ALL_VARIABLES:
    var=something
    another_var=another_thing
```

# Recursion
- to recursively run make, copy the Makefile in the subdirectory and run $(MAKE) from inside the Makefile
- to use variables after recursion, export them