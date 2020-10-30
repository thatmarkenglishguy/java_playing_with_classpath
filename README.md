# playing_with_classpath

Generates, compiles, and runs code to demonstrate java build tools including gradle.
This includes JNI extensions built in C and rust.
Can be run from any directory.

## Main scripts
### [clean](./clean)
Clean the source code and build artifacts (except the rust target directory because that would be slow).

### [generate [configuration_script]](./generate)
Generate the source code and directory structure.
Can pass a parameter of configuration script for naming.
e.g.
```bash
root_directory="."
configuration_name='playing_with_classpath'
package_name='com.me.example'
jar_name='example'
declare -a typical_java_classes
typical_java_classes=( 'Foo' 'Bar' )
```

### [compile](./compile)
Compile the source code into `.class` files and then a `.jar` file.

### [showinfo](./showinfo)
Dump some information including jar file.

### [run](./run)
Run the resulting jar file.

## Additional scripts
### [templatise](./templatise)
Aftering generating code in this directory, use it as the template for another directory (passed as a parameter).
Generated scripts build c/rust/java jni and run with gradle.

### [all](./all)
Run all the steps (apart from clean).
