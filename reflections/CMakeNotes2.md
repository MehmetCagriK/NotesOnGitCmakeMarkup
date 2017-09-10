# [Source](https://vimeo.com/32212195)

# What is CMake?
CMake is the corss-platform , open source build system that lets you use the
native development tools you love the most. This allows projects to take 
advantage of most scarce resource, developer's time. People can use Visual
Studio or Emacs-Make to develop and build their projects and still use CMake to
generate build systems.

It is a build system generators, it does not build, it generates builds into
tools. It allows diverse set of tools to be used on same project.

CMake takes plaintext files as input that describe your project and produces
build environment that can be used with many native development tools.

>Note: Ninja is a command-line ``make`` replacement. It is built to be used with
a build system generator(hint: CMake). 

CMake takes a plaintext file that can be edited with a text editor. You describe
your project, which libraries/executables need to be built, from which source
files. CMakes uses these to create make files or any other build-related files.

## CMake Concepts

- Source Tree: The directory where your source files are, propbably under
  version control system. It makes up most of your code base.
-- ``CMAKE_SOURCE_DIR``: Top level source directory that contains source files
    of the project.
-- ``CMAKE_CURRENT_SOURCE_DIR``: Current directory in your source tree.
  These are really important to maintain out-of-source builds.
- Binary Tree(Build Tree): In many systems that use build system generators,
  binary trees coincide with source tree(in-source build). CMake allows and
  suggests that Source Tree and Binary Tree to be kept seperately.
  
  This allows a single source tree and multiple build trees that all point to
  same source treewhich might have, different configurations like(build, 
  release etc.)
-- ``CMAKE_BINARY_DIR``: Points to the build tree.
-- ``CMAKE_CURRENT_BINARY_DIR``: Current directory in your build/binary tree.
- Generator: Something in CMake that generates into different build tools. For
  example "Unix Makefiles". You select generator to choose final development
  tool.
-- CMAKE_GENERATOR: CMake sets this variable to your build tool(Like Visual
   Studio 11). Use this when you want to add extra CMake code depending on the 
   build tool you choose.
- Variable: Contains a value in your CMake code(like other languages). All Cmake
  variables are strings.
- Cache Entry(Cache Variable): CMake at the top of every build tree, contains a
  cache file(named CMakeCache.txt). Inside that cache file are persistent
  variables. Every platform has different configurations, environment variables
  etc. CMake solves this dependency by using cache variables instead of
  environment variables.
- Directory: Regular directories.
- Command: Tells CMake what you want to do(add_executable , add_library etc.)
- Target: An executable or library that can be built
- Test: Single regression test that has some expected output.
- Property: Something you can set on a target, directory etc.
- Install Tree: When you install your target(make install), CMake will create
  another directory called Install Tree. This will contain install version of
  whole project.
-- CMAKE_INSTALL_PREFIX: Top level path to the install tree(Like "C:\Program
   Files\To Do List").
- Installer/Package: A way of distributing the software. It is done by packing
  up the install tree. CMakes supports various packaging tools user can choose.



