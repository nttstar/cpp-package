# cpp-package
One c/c++ program packaging toolkit.

Usage:

Require 'chrpath' package installed.
First copy cpp-package to /usr/bin/ then we can use it in anywhere.

cpp-package <binary_path> <resource_path> <package_name>

<package_name> should be a string and one directory named as package_name will be created under current working directory.

In package_name directory, there are 2 or 3 sub-directories: 
bin/
lib/
<resource_path>/:  this is optional, only exists if <resource_path> exists.
The ELF binary will be copied into bin/ and all dependencies shared libraries will be copied into lib/.
The runpath of that ELF binary will be changed to '..lib'. So you can run it on other servers under bin/ directories without any extra configuration.

