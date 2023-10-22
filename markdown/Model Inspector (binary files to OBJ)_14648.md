## Post #1
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2016-07-19T21:47:44+00:00
- Post Title: Model Inspector (binary files to OBJ)

Hey guys,

I'm working on a tool to analyze binary files of 3D models. The result can be saved as OBJ file.
Obviously I was inspired by shak-otay's Hex2obj Mesh Extractor  

I created it primarily for my personal use but it might be interesting for other people too.
You can request new features (and report bugs) simply by replying to this post or via PM.



screenshot.png (52.02 KiB) Viewed 942 times


Download Model Inspector v0.9 (x64)
[https://www.mediafire.com/?s1ub8hgcx66d074](https://www.mediafire.com/?s1ub8hgcx66d074)

Model Inspector (x86)
[http://www.mediafire.com/file/4mpm8ggn5 ... or_x86.zip](http://www.mediafire.com/file/4mpm8ggn5xug3fb/ModelInspector_x86.zip)


Requires Java Runtime Environment (JRE) 1.8.0 or higher

Changelog v0.9
- Different vertex and UV formats
- Additional UV types
- Count increased from 1000 to 10000
- Open a file by dragging it onto the EXE
- Files bigger than 2GB don't crash the application anymore
- The filename of the currently opened file is shown in the title bar 
- Texture coordinate indices are exported if the vertex and UV count are the same
## Post #2
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2016-07-20T10:42:51+00:00
- Post Title: Model Inspector (binary files to OBJ)

please keep on ?
extend and update your tool
nice idea
## Post #3
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2016-07-20T14:22:13+00:00
- Post Title: Model Inspector (binary files to OBJ)

Please add padding offsets. Nice work btw.
## Post #4
- Username: mono24
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-07-20T15:13:34+00:00
- Post Title: Model Inspector (binary files to OBJ)

Excellent tool, thanks for sharing!
## Post #5
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2016-07-21T22:34:51+00:00
- Post Title: Model Inspector (binary files to OBJ)

Great ! I edited the post so it is an attachment here (since mediafire links tend to go dead after a while).
## Post #6
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2016-09-10T22:13:15+00:00
- Post Title: Model Inspector (binary files to OBJ)

Just a little update, I added the download link and changelog in my initial post.
Padding offsets are still absent in this version - but this feature is on my TODO list
## Post #7
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2016-09-29T01:51:21+00:00
- Post Title: Model Inspector (binary files to OBJ)

Hi again!
I need your opinion on something.

Recently I kind of recreated a shareware program called HexDataEdit. The latest version of this program was released 10 years ago and the website is long gone. It's a neat tool for analyzing and structuring an unknown binary file. But it's not possible to legally obtain the full version of the program any longer and in my opinion it's missing some important features.

Ok, here's the first version of my recreation:
[http://www.mediafire.com/file/h5a5p9cis ... or0.5b.zip](http://www.mediafire.com/file/h5a5p9cisxpgs6y/BinaryInspector0.5b.zip)
I also included an example folder (the .xml is the template file) so you can see how the program works.

Screenshot:


So my question is:
Is there any need for this program AND should I continue adding new features?

At the moment the program exports the segment and type information as XML document.
I'm thinking about switching to JSON in the future.

Plus I also want to add the possibility to use variable names instead of static numbers in the input fields, like this:


Please tell me what you think about it, I'm thankful for every suggestion!
## Post #8
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-09-29T04:21:48+00:00
- Post Title: Model Inspector (binary files to OBJ)

> Reply from herbert3000
>
> Is there any need for this program AND should I continue adding new features?
never question the need for something you enjoy working on, people 
typically don't know what they want until you give it to them.   

i would give it a try but it won't launch on XP  
i have Java 1.8.0_101
## Post #9
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2016-09-29T06:05:14+00:00
- Post Title: Model Inspector (binary files to OBJ)

Thanks for the reply!
I've also uploaded a runnable JAR:
[http://www.mediafire.com/file/j2nzii4pe ... pector.jar](http://www.mediafire.com/file/j2nzii4penekfrr/Binary_Inspector.jar)
## Post #10
- Username: Marvey
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Sep 03, 2003 8:12 pm
- Post datetime: 2017-04-07T18:10:56+00:00
- Post Title: Model Inspector (binary files to OBJ)

i cant run it on Windows 10, i have last java installed, and when i run your file nothing happens, can you help me please? thanks
## Post #11
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2017-04-08T15:46:15+00:00
- Post Title: Model Inspector (binary files to OBJ)

> Reply from Marvey
>
> i cant run it on Windows 10, i have last java installed, and when i run your file nothing happens, can you help me please? thanks
Hi, are you talking about the .exe or the .jar?
In both cases, make sure that you have the latest version of Java installed on your PC.

To run the .jar, you can also create a new txt file in the same folder. Copy this into the txt:

```
pause
```
Then rename the txt file to "Run it.bat" and double-click it.
## Post #12
- Username: Lazov
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Oct 08, 2016 6:56 pm
- Post datetime: 2017-04-09T10:06:00+00:00
- Post Title: Model Inspector (binary files to OBJ)

The program is not working.
Checked on Win7 (x64), WinXP (x32).
The EXE file does not start, JAR produces an error:
Exception in thread "main" java.lang.UnsatisfiedLinkError: Cannot load 64-bit SWT libraries on 32-bit JVM
## Post #13
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2017-04-10T02:39:44+00:00
- Post Title: Model Inspector (binary files to OBJ)

> Reply from Lazov
>
> The program is not working.
Checked on Win7 (x64), WinXP (x32).
The EXE file does not start, JAR produces an error:
Exception in thread "main" java.lang.UnsatisfiedLinkError: Cannot load 64-bit SWT libraries on 32-bit JVMOk, this one works with a 32-bit JVM:
[http://www.mediafire.com/file/1jbkzhkwg ... or_x86.zip](http://www.mediafire.com/file/1jbkzhkwg9qjag9/BinaryInspector_x86.zip)
I wasn't aware of the fact, that the SWT libraries were platform dependent
## Post #14
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-04-10T04:25:18+00:00
- Post Title: Model Inspector (binary files to OBJ)

cool it finally launches on XP   and i can load the truck.d3d and d3d.xml you had in the 0.5b release example, 
now how do you save it out to obj, "File>Save file as..." is greyed out. i can copy the entire contents of the window to 
clipboard but it isn't formatted properly when pasted.
what version is that shown in the image in the first post, is that version 0.9?
0.5b is not the latest version is it?
sorry for all the questions, just trying to get caught up.
## Post #15
- Username: Lazov
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Oct 08, 2016 6:56 pm
- Post datetime: 2017-04-10T07:10:46+00:00
- Post Title: Model Inspector (binary files to OBJ)

Everything is working. Please post the version that is in the screenshot in the header.
Disable auto-update. The program hangs for large structures.
## Post #16
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2017-04-10T13:54:04+00:00
- Post Title: Re: Model Inspector (binary files to OBJ)

> Reply from AceWell
>
> cool it finally launches on XP   and i can load the truck.d3d and d3d.xml you had in the 0.5b release example, 
now how do you save it out to obj, "File>Save file as..." is greyed out. i can copy the entire contents of the window to 
clipboard but it isn't formatted properly when pasted.
what version is that shown in the image in the first post, is that version 0.9?
0.5b is not the latest version is it?
sorry for all the questions, just trying to get caught up.
That are actually two different tools, Model Inspector is for 3D models only, Binary Inspector is for multi-purpose usage 
I also uploaded a 32bit version of the Model tool, link is in the first post (and yes, the image shows v0.9)
And for the Binary tool 0.5b is the latest version - well, I just uploaded 0.51b with the auto update option (see next line...).

@Lazov: Binary Inspector x86 now also has the option to uncheck auto update. For a manual update, just check the option and uncheck it again. Link is in my previous post.
## Post #17
- Username: RyLeo154
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat May 11, 2019 7:49 pm
- Post datetime: 2019-05-11T12:16:09+00:00
- Post Title: Re: Model Inspector (binary files to OBJ)

It doesn't seem to work on Windows 10 Professional (Version 10.0.17763 Build 17763) that I'm using; after I double-click it, nothing happens. Any fixes?
## Post #18
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2019-05-12T14:51:27+00:00
- Post Title: Re: Model Inspector (binary files to OBJ)

> Reply from RyLeo154 ↑Sat May 11, 2019 8:16 pm at Sat May 11, 2019 8:16 pm
>
> 
It doesn't seem to work on Windows 10 Professional (Version 10.0.17763 Build 17763) that I'm using; after I double-click it, nothing happens. Any fixes?
Do you have Java installed on your computer?

Also check out [3D Model Researcher](https://forum.xentax.com/viewtopic.php?f=33&t=16163) (by Lazov) which is much more advanced than my program.
