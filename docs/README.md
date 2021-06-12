# How do I find all files containing specific text on Linux?



### Do the following:

       grep -rnw '/path/to/somewhere/' -e 'pattern'
     #  -r or -R is recursive,
     #  -n is line number, and
     #  -w stands for match the whole word.
     #  -l (lower-case L) can be added to just give the file name of matching files.
       Along with these, --exclude, --include, --exclude-dir flags could be used for efficient searching:

     #  This will only search through those files which have .c or .h extensions:

       grep --include=\*.{c,h} -rnw '/path/to/somewhere/' -e "pattern"

    #   This will exclude searching all the files ending with .o extension:

       grep --exclude=\*.o -rnw '/path/to/somewhere/' -e "pattern"

    #   For directories it's possible to exclude one or more directories using the --exclude-dir parameter. For example, this will exclude the dirs dir1/, dir2/ and all of them matching *.dst/:

       grep --exclude-dir={dir1,dir2,*.dst} -rnw '/path/to/somewhere/' -e "pattern"
