---
title: Build
---

# [Contents](#user-content-scirun-5-prototype "generated with DocToc(http://doctoc.herokuapp.com/)")

- [SCIRun 5](#user-content-scirun-5)
	- [Goals](#user-content-goals)
	- [Documentation](#user-content-documentation)
	- [Platform Notes](#user-content-platform-notes)
		- [Build requirements](#user-content-build-requirements)
		- [CMake Build Generators](#user-content-cmake-build-generators)
		- [Unix Makefiles notes](#user-content-unix-makefiles-notes)
	- [Questions and Answers](#user-content-questions-and-answers)
	- [License and Credits](#user-content-license-and-credits)

###Goals
SCIRun 5 is a complete rewrite of the GUI front end and graphical components of SCIRun 4, including a more stable and
efficient middle layer, with support for Python scripting.

### Documentation
For documentation, please see: http://sciinstitute.github.io/SCIRun/

### Platform Notes
#### Build requirements
* OS X (tested on 10.7 and 10.8)
  - Apple clang 5.1
  - Qt 4.8
    + Download from http://releases.qt-project.org/qt4/source/qt-mac-opensource-4.8.4.dmg.
* Windows (tested on Windows 7, 8)
  - Visual Studio 2013
  - Qt 4.8
    + Build from source (see http://scirundocwiki.sci.utah.edu/SCIRunDocs/index.php/CIBC:Seg3D2:Building_Releases#Installing_Qt_on_your_system_and_building_from_scratch for instructions), but be sure to download http://releases.qt-project.org/qt4/source/qt-everywhere-opensource-src-4.8.4.tar.gz.
* Linux (tested on Ubuntu 12.10)
  - gcc 4.6, 4.7
  - Qt 4.8
    + Build from source (http://releases.qt-project.org/qt4/source/qt-everywhere-opensource-src-4.8.4.tar.gz), or use system libraries if available.
* All platforms
  - CMake 2.8
    + Root cmake file is SCIRun/src/CMakeLists.txt.
    + Building in the source directory is not permitted.
    + Make sure BUILD_SHARED_LIBS is on (default setting).
    + BUILD_WITH_PYTHON works on Windows, not yet (easily) on MacOS.

#### CMake Build Generators
* Windows
  - Visual Studio 2013
* OS X (tested on 10.7 and 10.8 and 10.10)
  - Unix Makefiles
  - Xcode
* Linux (tested on Ubuntu 12.10)
  - Unix Makefiles

#### Unix Makefiles notes
* Boost must be built before the SCIRun libraries.
* Parallel make builds can be used as long the Boost target is built first, for example:
  - make -j4 Boost_external && make -j4
