# cpp-package
One c/c++ program packaging toolkit.

Usage:

Require 'chrpath' package installed.

First copy cpp-package to /usr/bin/ then we can use it in anywhere.

```
cpp-package <binary-path> <resource-path> <package-name>
```

**package-name** should be a string and one directory named as package-name will be created under current working directory.

In package-name directory, there are 2 or 3 sub directories: 

bin/

lib/

*resource-path*/:  this is optional, only exists if *resource-path* exists.

The ELF binary will be copied into bin/ and all dependencies shared libraries will be copied into lib/.

The runpath of that ELF binary will be changed to '..lib'. So you can run it on other servers under bin/ directories without any extra configuration.

Finally, the package-name directory will be compressed into a tar.gz file.

