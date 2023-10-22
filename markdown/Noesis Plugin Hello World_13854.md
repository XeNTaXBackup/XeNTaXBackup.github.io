## Post #1
- Username: PsowKion
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Aug 13, 2014 8:10 pm
- Post datetime: 2016-01-20T02:13:08+00:00
- Post Title: Noesis Plugin Hello World?

Are there any good resources or documentation for getting started with writing Noesis plugins (either c or python)? Or is it more one of those, "look at the source available and work it out yourself" kind of things?
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-01-20T07:45:59+00:00
- Post Title: Noesis Plugin Hello World?

> Reply from PsowKion
>
> Are there any good resources or documentation for getting started with writing Noesis plugins (either c or python)?Not what you may think of. For python read __NPReadMe.txt, for C there's pluginshare.h which can give you an overview of functions.

There's also some valuable info spread over the Xentax forum. (I was thinking about collecting a bunch of links at least but I lost focus on Noesis somehow - anyway it's one of the greatest tools I know especially concerning its handling of animations and export capabilities).

> Or is it more one of those, "look at the source available and work it out yourself" kind of things?Yes, "use the source, Luke!"  
To get a quick insight on how functions like rapi.rpgBindPositionBufferOfs() are to be handled
it's a good idea to start with python, imho.
(Guess you've read this one already? [viewtopic.php?f=29&t=7760](http://forum.xentax.com/viewtopic.php?f=29&t=7760))

For C I would suggest to look at Bayonetta project. But you'll need to get a model sample somehow - without it this project is rather useless, imho.
## Post #3
- Username: PsowKion
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2016-01-20T10:13:34+00:00
- Post Title: Noesis Plugin Hello World?

chrrox has written quite a few tutorials on Noesis Python over in the Tutorials section on the forum here, but they may be a little bit buried by now. The Bayonetta plugin isn't a great example as it's pretty gross and I never fleshed the format out fully. The most recent thing I released code for was the FF11 importer, which can be found [here](http://www.richwhitehouse.com/index.php?content=inc_res.php&rescat=Snippets) along with some DICOM importer code. Although it isn't a great example of full functionality since it only uses immediate-mode submission for geometry.

So yeah, things are mostly undocumented and scattered. You'll probably have more luck in the way of support (and not wanting to burn your own eyes out) working in Python, but whether that's the best thing really depends on what you want to accomplish. For example, if you're importing 100MB worth of animation data, a native plugin is probably going to churn through that data in 1 second instead of 15.
## Post #4
- Username: PsowKion
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2016-01-20T10:24:54+00:00
- Post Title: Noesis Plugin Hello World?

Oh, and you can find some other stuff on the [repository that Google murdered](https://code.google.com/p/noesis-plugins-official/source/browse/). I'll get around to making a new one some day.
## Post #5
- Username: PsowKion
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Aug 13, 2014 8:10 pm
- Post datetime: 2016-01-28T04:01:40+00:00
- Post Title: Noesis Plugin Hello World?

Thanks for the replies. I'll read over them and get started. I have a couple of dumb questions for developing and testing. For Python is there anything that I need to include, or can I just place a python script in the plugins folder and Noesis will recognize it. Does that also mean I'll need to restart Noesis to test a change, or is the some method of testing via the command line?

Out of curiosity I might as well ask for C as well. I suppose I need to compile a .dll, are there any dependencies such as compilers or headers that need to be included? Can I use MinGW to compile or is there anything special that I need to do there? And is there anyway to test or simulate the output of the plugin, or does it need to be done by starting Noesis each time?
## Post #6
- Username: Acewell
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2016-01-29T05:41:08+00:00
- Post Title: Noesis Plugin Hello World?

For the Python workflow you can:

A) Enable "Auto-reload scripts" in the data viewer, under Persistent settings->Other. This will auto-reload Python scripts when a modification is made to one of them, which will auto-reload whatever model is actively loaded too. The caveat here is that this uses Windows shell hooks, which are known to not work on some machines and/or some paths on some machines.
B) Hit alt+T-R (triggers the Tools->Reload plugins menu item) to manually reload scripts after making changes.

For the native code workflow, I strongly recommend using Visual Studio. You can potentially produce compatible DLL's with gcc/clang/etc., but I'd sooner recommend getting Noesis DLL's compiling in one of the free Visual Studio Express Editions. You should be able to open the solution files included in the Noesis plugin source zip and compile them out of the box, although migrating to newer Visual Studios may require very minor modifications. I've got a shitty mix of 2005 and 2010 going on, but the included solutions are still 2005.

Assuming you're using VS, you can set the post-build settings to copy your DLL to your Noesis plugins directory, and launch in debug out of the IDE, optionally providing your model file on the commandline so that Noesis loads it right away on startup. If you wanted you could also set Edit & Continue up for the plugin DLL in order to apply code changes (with mixed success, probably) without restarting Noesis. However, Noesis startup is super-fast so just restarting probably won't be an issue for you. If your file is somewhere deep in your directory structure, you may see significant delays on startup from the piece of shit MFC shell view controls that Noesis unfortunately uses. You can disable them by ticking "View->No browse to target" in the menu to get an extra-fast startup. If you wanted to set up some isolated unit tests for your DLL that don't depend on Noesis, you certainly could, but you'll probably find no reason to do so. You also have the option of invoking Noesis in commandline mode if you want it to just run your plugin to export to another format without loading any part of the GUI. So, good luck!
