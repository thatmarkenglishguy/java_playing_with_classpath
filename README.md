# playing_with_classpath

Generates, compiles, and runs code to demonstrate java build tools.
This includes JNI extensions built in C and rust.
Can be run from any directory.

## Main scripts
### [clean](./clean)
Clean the source code and build artifacts (except the rust target directory because that would be slow).

### [generate](./generate)
Generate the source code and directory structure.

### [compile](./compile)
Compile the source code into `.class` files and then a `.jar` file.

### [showinfo](./showinfo)
Dump some information including jar file.

### [run](./run)
Run the resulting jar file.

## Additional scripts
### [all](./all)
Run all the steps (apart from clean).
