# make-system-tasks


## bad_makefile

Installing library:\
`make -C bad_makefile/library`\
`sudo make -C bad_makefile/library install`

Uninstalling library:\
`sudo make -C bad_makefile/library uninstall`\
`make -C bad_makefile/library clean` (optional)

Installing and running the program:\
`make -C bad_makefile/program`\
`./bad_makefile/program/calculator`

Cleaning program dir:\
`make -C bad_makefile/program clean` (optional)

## no_makefile

`make -C no_makefile/program`\
`make -C no_makefile/library`

Build just the file reader library:\
`make -C no_makefile/library lib`

Build program:\
`make -C bad_makefile/program`

Run:\
`./no_makefile/program/calculator`
```
(cd ./no_makefile/library/ && export LD_LIBRARY_PATH=`pwd` && exec ./main)
```