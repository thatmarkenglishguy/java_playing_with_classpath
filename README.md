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
Compile
* the rust source (release and debug)
* the c source (release and debug)
* the java source code into `.class` files
* a `.jar` file containing the java `.class` files, and rust and c release and debug jni dynamic libraries.

### [showinfo](./showinfo)
Dump some information including jar file.

### [run](./run)
Run the resulting jar file both by calling `java` directly, and via `./gradlew run`.
The jar's behaviour is manipulated by specifying system properties for which jni library to use, and running debug or release.

## Additional scripts
### [templatise [TARGET_DIRECTORY]](./templatise)
Aftering generating code in this directory, use it as the template for a project in another directory (passed as a parameter).
Generated compile scripts build c/rust jni. java should be compiled by running `./gradlew build`.
Generated run script runs with gradle.

### [all](./all)
Run all the steps (apart from clean).

## Common Usage.
### Creating a new project
```bash
cp project_configuration my_project_configuration
# Edit my_project_configuration as necessary
./clean
./generate my_project_configuration
./templatise ../my_new_project
cd ../my_new_project
./compile
./gradlew build
./run
```

### Running example project from scratch
```bash
./clean
./generate
./compile
./run
./showinfo
```

