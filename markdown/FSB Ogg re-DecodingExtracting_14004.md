## Post #1
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2016-02-21T20:19:26+00:00
- Post Title: FSB Ogg re-Decoding|Extracting

Found in Babel Choice, Dead Acres Demo, Defragmented, Doors, Life is Hard, Monumental. (all based on Unity Engine)

Fsbext detects them as ogg 44100 2 16, but data dont contain Oggs header, so extracted oggs unplayable.
Try to use fsbii, but he dont understand these fsbs.

Interesting in FSB Ogg re-decoder or something like what.

Few samples - [http://www.multiupfile.com/f/f0f248df](http://www.multiupfile.com/f/f0f248df)
## Post #2
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-02-21T21:21:28+00:00
- Post Title: FSB Ogg re-Decoding|Extracting

[viewtopic.php?f=17&t=13615](http://forum.xentax.com/viewtopic.php?f=17&t=13615)
## Post #3
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2016-02-22T02:54:26+00:00
- Post Title: FSB Ogg re-Decoding|Extracting

Dont like output method to WAV even if original is Ogg or MP3.

viewtopic.php?f=17&t=4662 - example of game with MP3 FSB, which can be extracted as is without output to WAV format. Want something like that.
## Post #4
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-02-22T07:37:47+00:00
- Post Title: FSB Ogg re-Decoding|Extracting

Then you can install linux, or try and compile this on windows:

[https://github.com/tmiasko](https://github.com/tmiasko)
## Post #5
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2016-03-03T16:17:59+00:00
- Post Title: FSB Ogg re-Decoding|Extracting

> Reply from daemon1
>
> Then you can install linux, or try and compile this on windows:

https://github.com/tmiasko

Try to compile, but got this error message:

> CMake Error in CMakeLists.txt:
>
>   The CMAKE_C_COMPILER:
>
> 
>
>     cl
>
> 
>
>   is not a full path and was not found in the PATH.
>
> 
>
>   To use the NMake generator with Visual C++, cmake must be run from a shell
>
>   that can use the compiler cl from the command line.  This environment is
>
>   unable to invoke the cl compiler.  To fix this problem, run cmake from the
>
>   Visual Studio Command Prompt (vcvarsall.bat).
>
> 
>
>   Tell CMake where to find the compiler by setting either the environment
>
>   variable "CC" or the CMake cache entry CMAKE_C_COMPILER to the full path to
>
>   the compiler, or to the compiler name if it is in the PATH.
>
> 
>
> 
>
> CMake Error in CMakeLists.txt:
>
>   The CMAKE_CXX_COMPILER:
>
> 
>
>     cl
>
> 
>
>   is not a full path and was not found in the PATH.
>
> 
>
>   To use the NMake generator with Visual C++, cmake must be run from a shell
>
>   that can use the compiler cl from the command line.  This environment is
>
>   unable to invoke the cl compiler.  To fix this problem, run cmake from the
>
>   Visual Studio Command Prompt (vcvarsall.bat).
>
> 
>
>   Tell CMake where to find the compiler by setting either the environment
>
>   variable "CXX" or the CMake cache entry CMAKE_CXX_COMPILER to the full path
>
>   to the compiler, or to the compiler name if it is in the PATH.
>
> 
>
> 
>
> CMake Warning (dev) in CMakeLists.txt:
>
>   No cmake_minimum_required command is present.  A line of code such as
>
> 
>
>     cmake_minimum_required(VERSION 3.4)
>
> 
>
>   should be added at the top of the file.  The version specified may be lower
>
>   if you wish to support older CMake versions for this project.  For more
>
>   information run "cmake --help-policy CMP0000".
>
> This warning is for project developers.  Use -Wno-dev to suppress it.

Do I need to install Visual Studio? Or I need to do something another?
## Post #6
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-03-03T17:36:08+00:00
- Post Title: FSB Ogg re-Decoding|Extracting

> Reply from Researchman
>
> Do I need to install Visual Studio? Or I need to do something another?

I don't know. Nobody was able to compile it yet...
## Post #7
- Username: Phrozen Shade
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Nov 03, 2015 4:56 am
- Post datetime: 2021-10-27T19:51:33+00:00
- Post Title: FSB Ogg re-Decoding|Extracting

It seems to me that unpacking OGG data from an FDB file, it lacks the standard file header. I'm not good at programming and can only guess. But if you add a standard OGG file header to the raw data, then it may well be reproduced as a regular OGG file.
