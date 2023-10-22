## Post #1
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2014-07-28T03:50:00+00:00
- Post Title: [HOW-TO] Assembling 3DS Homebrew for Gateway

credit all goes to Sylantemp from gbatemp
Step 1: Setting Up

> Obviously, you'll need to start by having everything set up to actually be able to compile. To start, you'll need the basic developer essentials for your given operating system. That goes beyond the scope of this guide, but if you're developing homebrew, it's a safe assumption that you've already carried this step out, or at least know how to on your own.
>
> 
>
> Next, you'll need to install GCC for ARM embedded systems. You can download the files for that here. Windows users will have a straightforward installer, while OSX and Linux users will have to do a little extra setup later. For now, if you're one of these people, extract your associated download in some folder that you'll be able to conveniently remember. Alternatively, Ubuntu users can install an alternate PPA available here.
>
> 
>
> You'll also need DevKitPro set up as you would if you were developing standard DS homebrew, along with all optional libraries (included in the following guide). A fairly straightforward guide for doing so is available here. Windows users have an easy installer available, and while scripts can handle the task for OSX and Linux users, I highly recommend they follow the guide for a manual setup. It isn't very long or difficult, and will give you a good grasp on where everything you'll be using is located.
>
> 
>
> Finally, you'll need makerom, this file for compiling ctrulib software with makerom, and this workaround for using makerom with Gateway. Put those all somewhere convenient; we won't be using them right now, but they'll be needed at the end of this guide.
>
> 
>
> makerom http://3dbrew.org/wiki/Makerom
>
> his file for compiling ctrulib software with makerom https://gist.github.com/3DSGuy/53475c0cc74996b1606e
>
> and this workaround for using makerom https://anonfiles.com/file/2a887e7e7b99 ... defefdec01

Step 2: Compiling ctrulib and homebrew

> So you're all set up and ready to go! Now we get to the fun part. You're going to want to download ctrulib from here. If you're familiar with git, this process should be straightforward. Otherwise, just click the "Download ZIP" button on the right side of the screen. You're going to want to get everything from that link somewhere on your computer, with the same organization as it has on there. This is for convenience sake, as you'll have everything downloaded at once and readily available. As well, the makefiles of all the example programs assume that everything will be in the same places that it is on github, so moving things around may cause issues.
>
> 
>
> Now that you've got ctrulib downloaded, open up your command line/terminal and navigate to your newly created ctrulib directory (for most operating systems, the command to do this will be cd). navigate into the "libctru" folder, and type "make". If all goes well, you should now have ctrulib ready for use!*
>
> 
>
> *If you were one of the users in step 1 who had to just extract the GCC ARM toolkit into a convenient location, then you'll need to make some slight changes to the Makefile first. Open up the Makefile in a text editor, and the first line should say "CC = arm-none-eabi-gcc". Get rid of the last part so it simply reads "CC = ", and then add the directory you extracted it to, plus "bin/arm-none-eabi-gcc", all in quotation marks. So, if I extracted to /usr/local, I would replace arm-none-eabi-gcc with "/usr/local/gcc-arm-none-eabi-[version]/bin/arm-none-eabi-gcc". Repeat this process for the second line, and just replace the "gcc" at the end with "ar".
>
> 
>
> But we didn't just come here to compile ctrulib, we want to be able to use it. So let's go compile an example program. Pull up your command line/terminal again, and go up a directory ("cd .."). Now, navigate into the "arm11u" folder. We almost have everything we need to compile this homebrew right now (You'll have to repeat the above steps for this makefile as well, if you're an OSX/Linux user). However, if you try to compile this right now, you'll find that you're missing a file- a linker named "ccd00.ld". Our makefile needs this in order to determine how to compile our homebrew.
>
> 
>
> Thankfully, if you followed step 1, you should already have this file- it was the file you downloaded immediately after makerom (This one, in case you skipped over it). All you need to do is copy/paste that into the "arm11u" folder, and rename it to "ccd00.ld". If everything went right, you should now be able to type make into your command line/terminal to create a file called "arm11u.elf"!
>
> 
>
> (This one, in case you skipped over it) https://gist.github.com/3DSGuy/53475c0cc74996b1606e

Step 3: Converting the .elf into a .3ds

> Thankfully, this is the easiest step so far. Now that you've got your homebrew file ("arm11u.elf" in the step 2 example), go ahead and paste it into the same folder where you keep makerom and the workaround you downloaded in step 1. Now, use your command line/terminal to navigate to this folder. If you're a Windows user, at this point you can simple type "build.bat arm11u.elf arm11u.3ds". If you're an OSX or Linux user, the steps aren't much harder. Open up the "build.bat" file in a text editor, change "%1" to "arm11u.elf" and "%2" to "arm11u.3ds", and copy/paste the whole thing into your terminal. You should now have a Gateway usable 3DS file.
