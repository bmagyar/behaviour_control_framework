#Behaviour Control Framework#

**Author:** Philipp Allgeuer

**Version:** 1.0.2

**Date:** 21/11/14

##General Overview##
The Behaviour Control Framework is a generic platform-independent C++ framework that implements a control architecture consisting of a hierarchical network of behaviour layers. These layers each contain behaviours that can inhibit one another and interact to achieve control. A full discussion of the structure and ideas behind this framework can be found in the Doxygen documentation that comes with the release. This documentation is well worth a read before you decide if the library is for you!

The structure and implementation of this library focuses on the application of the inhibition-based behaviour control architecture to real-time control loops, but can reasonably be adapted for a wide variety of other artificial intelligence applications. Emphasis has been placed on having very low overhead so as not to hurt overall system performance, while still maintaining ease of use.

##Feature List##
- Small and highly efficient performance-oriented cross-platform C++ library
- Independent code with few external dependencies
- Can be used to implement behaviour control code in the form of a hierarchically layered behaviour-based control architecture
- Tried and tested by the author on various robotic platforms
- Documented using the Doxygen documentation generation tool, including code samples and a discussion of all usage caveats
- Well-commented library source code to allow easy modification/extension by users (who are encouraged to submit improvements/bug fixes to the author, so that the library can be improved!)
- Academic paper on the framework: *Hierarchical and State-based Architectures for Robot Behavior Planning and Control*, published in Proceedings of 8th Workshop on Humanoid Soccer Robots @ Humanoids 2013

##Installation##
This library is implemented as a collection of platform-independent C++ source files. To get started just clone the `behaviour_control_framework` repository.

There are three ways of using the library:

1. Directly include the (non-test) source files in your project, and build them with the rest of your project.

2. Build a static library (e.g. `*.a` or `*.lib`) of the source code and link your project to it.

3. Build a dynamic library (e.g. `*.so` or `*.dll`) of the source code and link your project to it.

Due to the rather small and efficient nature of the library, one of the first two options is recommended. Minimal benefit is expected from building a dynamic library.

Note that as at release `v1.0.2`, the required (non-test) source files are:

Header Files                       | Source Files
-----------------------------------|------------------------
behaviour_control.h                | behaviour_control.cpp
classes/behaviour_common.h         | behaviour_common.cpp
classes/behaviour_manager.h        | behaviour_manager.cpp
classes/behaviour_layer.h          | behaviour_layer.cpp
classes/behaviour.h                | behaviour.cpp
classes/behaviour_sensors.h        | behaviour_sensors.cpp
classes/behaviour_actuators.h      | behaviour_actuators.cpp
classes/behaviour_template_defns.h | 

A sample makefile for building the static and dynamic libraries using `gcc` is included in the release. The makefile also demonstrates how the `test_behaviour_control` unit test can be built. As mentioned in the makefile however, the Behaviour Control Framework could equivalently be built using any other compiler, such as for example MSVC.

##Dependencies##
This library depends on the following external libraries (to avoid requiring C++11):
- Boost [Static Assert](http://www.boost.org/doc/libs/release/libs/static_assert/)
- Boost [Type Traits](http://www.boost.org/doc/libs/release/libs/type_traits/)
- Boost [Utility](http://www.boost.org/doc/libs/release/libs/utility/) (specifically [`enable_if`](http://www.boost.org/doc/libs/release/libs/utility/enable_if.html))

For more information, or to download the Boost Libraries, please refer to [http://www.boost.org/](http://www.boost.org/).

A unit test for the library (`test_behaviour_control`) is included in the release. It is not required to build this executable in order to use the library - it is for demonstration and testing purposes only. The unit test has one additional dependency, namely the [Google Test Framework](https://code.google.com/p/googletest/).

##Documentation##
###Doxygen Documentation###
The first place to look for help and guidance when trying to use the Behaviour Control Framework is the Doxygen documentation. This can be generated by running `Behaviour Control Framework vX.X.X/doc/generate_doc.sh`, and is then located at:

`Behaviour Control Framework vX.X.X/doc/Behaviour Control Framework.html`

Or equivalently:

`Behaviour Control Framework vX.X.X/doc/out/html/index.html`

The Doxygen documentation provides a complete explanation of the entire framework, including all caveats and details, and includes code samples to make the task of learning the framework a lot easier. Complete documentation of all functions, classes and namespaces of the library is also included. As such, the Doxygen documentation is intended to be the primary help resource when working with the library.

###Source Code###
If anything is not adequately explained in the Doxygen documentation, or more details as to the inner workings of the library are required, the next place to look would be in the library source code. The code is well-commented and should be fairly self-explanatory. A good starting point is `behaviour_manager.h`. A look inside the source code for `test_behaviour_control` should also shed some light on how the library is intended to be used.

###Where To Get More Help?###
If neither the Doxygen documentation nor a look into the source code can resolve your issues for whatever reason, you can contact the author at the email address given in the *Bugs and Improvements* section.

##Bugs and Improvements##
I welcome all feedback, suggestions and bug reports. If you improve or fix anything about the library then I encourage you to let the author know so that the library can be improved for everyone!

**Email:** `pallgeuer[at]ais.uni-bonn.de`
