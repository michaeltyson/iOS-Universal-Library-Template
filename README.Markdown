iOS-Universal-Library-Template
==============================

An Xcode 4 project template to create universal (armv6, armv7 and simulator) frameworks for iOS.

The existing static library template provided with Xcode only builds one architecture, which is not particularly suitable for distribution. A number of people have created scripts to create universal libraries, which require some mucking around with Xcode target settings to use.

This template draws on this work to provide all that is required to produce universal libraries - just select the 'Universal Static Library' type in the New Project/New Target dialog, and you're all set.


Installation
------------

Copy the `Universal Static Library.xctemplate` folder into `~/Library/Developer/Xcode/Templates/Framework & Library`

Sorted.


A Note About Universal Frameworks
---------------------------------

Frameworks are Apple's solution to the inconvenience of distributing and handling static libraries and their accompanying headers (which requires setting header search paths, etc.)

Karl Stenerud has created a fantastic set of Xcode templates for [universal iOS frameworks](https://github.com/kstenerud/iOS-Universal-Framework).

These will probably work just fine for many people, but we have recently discovered that LLVM appears to have a linking bug that causes unpredictable crashes when calling C functions within the static framework.  Frameworks that work fine in one app may crash in another app, without warning.

Consequently, if you are using C functions within your library, I recommend that you avoid frameworks for now and use a static library instead.


Credits
--------

Build script by [Adam Martin](http://twitter.com/redglassesapps)  
Tweaked and made into an Xcode template by [Michael Tyson](http://atastypixel.com/blog)  
Based on original script from Eonil

More info: see [this Stack Overflow question](http://stackoverflow.com/questions/3520977/build-fat-static-library-device-simulator-using-xcode-and-sdk-4)
