## Post #1
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2014-02-21T22:26:39+00:00
- Post Title: [PS3] Gundam Extreme Vs. Full Boost (2014)

Preview:



Notes:

1. Game uses some messed up cell-shading type shaders.
2. Good luck getting them to look good in Blender, Max, Maya, etc.

Instructions:
1. Create a fresh, empty directory somewhere.
2. Put DATA00.PAC and EXE inside this directory (not in C:\, I said A FRESH NEW DIRECTORY).
3. Right-click on EXE and Run As Administrator (temporary files, folders, etc. need to be created and removed).
4. Answer questions.
5. Wait an hour.
6. Browse DATA00 folder for files. _t are pure texture directories. Other folders contain other stuff.
[xentax.7z](https://xentaxbackup.github.io/file/7047_xentax.7z)
## Post #2
- Username: TallgeeseIV
- Rank: beginner
- Number of posts: 39
- Joined date: Mon Nov 15, 2010 10:32 am
- Post datetime: 2014-02-27T06:01:24+00:00
- Post Title: [PS3] Gundam Extreme Vs. Full Boost (2014)

After answering the questions, the command prompt shows text for a split second then closes. No files written, xentax.exe no longer in my running processes. Any idea what the issue could be?

Yes, I ran as administrator, and yes DATA00.PAC and xentax.exe are the only files in a brand new folder.

I recall reading something about there being several methods of psarc extracting and they don't all produce the same file. I used the "PSARC PS3 Extractor" command line tool. Could that be related?

EDIT: I just tried Total Commander, the extracted file was a totally different size than the other, but same result.

I ran xentax.exe in an administrator command prompt and it stated that it failed to open the file.
## Post #3
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2014-02-27T06:09:56+00:00
- Post Title: [PS3] Gundam Extreme Vs. Full Boost (2014)

to prevent console window from closing, open up a command prompt in windows using

Start > Accessories > Command Prompt

use the "cd" command to navigate to where the EXE and DATA00.PAC are.

type in xentax.exe at the prompt.

what is the error message?

screencaps also help
## Post #4
- Username: TallgeeseIV
- Rank: beginner
- Number of posts: 39
- Joined date: Mon Nov 15, 2010 10:32 am
- Post datetime: 2014-02-27T06:12:29+00:00
- Post Title: [PS3] Gundam Extreme Vs. Full Boost (2014)

> Reply from howfie
>
> to prevent console window from closing, open up a command prompt in windows using

Start > Accessories > Command Prompt

use the "cd" command to navigate to where the EXE and DATA00.PAC are.

type in xentax.exe at the prompt.

what is the error message?

screencaps also help

Ah, yep, I just edited my post, that was my next thought to try as well.
## Post #5
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2014-02-27T06:21:42+00:00
- Post Title: [PS3] Gundam Extreme Vs. Full Boost (2014)

can i see screencap of console window along with your folder window?

BTW, I use a tool called PSARC GUI from [aldostool](http://aldostools.org/ps3tools.html)s.
## Post #6
- Username: TallgeeseIV
- Rank: beginner
- Number of posts: 39
- Joined date: Mon Nov 15, 2010 10:32 am
- Post datetime: 2014-02-27T06:58:20+00:00
- Post Title: [PS3] Gundam Extreme Vs. Full Boost (2014)

Ah, ok, just tried that tool, same result:
[xentax.exe_error.jpg](https://xentaxbackup.github.io/file/7046_xentax.exe_error.jpg)
## Post #7
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2014-02-27T07:34:07+00:00
- Post Title: [PS3] Gundam Extreme Vs. Full Boost (2014)

i found the problem... update will be soon.
## Post #8
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2014-02-27T07:44:07+00:00
- Post Title: [PS3] Gundam Extreme Vs. Full Boost (2014)

updated OP
## Post #9
- Username: TallgeeseIV
- Rank: beginner
- Number of posts: 39
- Joined date: Mon Nov 15, 2010 10:32 am
- Post datetime: 2014-02-27T08:48:45+00:00
- Post Title: [PS3] Gundam Extreme Vs. Full Boost (2014)

Ahh, yep, seems to be working now. Great work, thank you!
## Post #10
- Username: leyme
- Rank: advanced
- Number of posts: 50
- Joined date: Wed Apr 04, 2012 5:17 pm
- Post datetime: 2014-03-08T05:46:26+00:00
- Post Title: [PS3] Gundam Extreme Vs. Full Boost (2014)

Please help...
How to use smcimport.py?
I'm a mere beginner.
## Post #11
- Username: Strife1989
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Jan 12, 2012 9:52 pm
- Post datetime: 2014-03-08T13:06:37+00:00
- Post Title: [PS3] Gundam Extreme Vs. Full Boost (2014)

thank you very much for the ripper howfie !!!! 
do you by any chance have a ripper for Another Century`s Episode R ??? there are some really nice models there
## Post #12
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2014-03-08T20:00:11+00:00
- Post Title: [PS3] Gundam Extreme Vs. Full Boost (2014)

You're welcome. And about ACER, no, very sorry; like chrrox, i have entered into a state of semi-retirement lol. Really only doing projects that I know are going to be easy (like this one was similar to Tekken Revolution). Was thinking about doing the Macross 30 one next...

Anyways, for Gundam Extreme Vs. Full Boost:

00000 - : scene models
00509 - : gundam models
00857 - : gundam animation data
01031 - : more scene models
02440 - : garbage data
02729 - : weapon GUI textures
03323 - : character GUI textures
06148 - : garbage data
06258 - : garbage data
06263 - : font graphics
06273 - : garbage data
06287 - : character GUI textures
07588 - : GUI textures
08499 - : garbage data
08500 - : GUI textures
08544 - : garbage data
08655 - : GUI textures
08901 - : box art textures
08908 - : GUI textures
13699 - : Gundam GUI textures
13825 - : character GUI textures
14848 - : GUI textures
15266 - : Gundam GUI textures
15421 - : GUI textures
15789 - : garbage data
15790 - : armor GUI textures
34638 - : GUI textures
34722 - : Gundam GUI textures
35564 - : garbage data
35716 - : GUI textures
35939 - : garbage data
36092 - : GUI textures
36490 - : character GUI textures
36551 - : box art textures
36569 - : garbage data
36570 - : Gundam models
36572 - : Gundam animation data
36573 - : effects models
36588 - : garbage data
36591 - : GUI textures
36612 - : garbage data
36614 - : GUI textures
36640 - : garbage data
36643 - : Gundam models
36649 - : Gundam animation data
36652 - : effects models
36679 - : garbage data
36685 - : GUI textures
36748 - : garbage data
36756 - : Gundam models
36760 - : Gundam animation data
36762 - : effects models
36791 - : garbage data
36795 - : GUI textures
36840 - : garbage data
36859 - : Gundam models
36889 - : Gundam animation data
36904 - : effects models
37050 - : garbage data
37080 - : GUI textures
37158 - : character GUI textures
37379 - : garbage data
37409 - end: GUI textures
## Post #13
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2014-03-08T20:05:15+00:00
- Post Title: [PS3] Gundam Extreme Vs. Full Boost (2014)

> Reply from leyme
>
> Please help...
How to use smcimport.py?
I'm a mere beginner.

* Download Blender 2.49b. The script only works for that version because I used Mariusz's scripts as a reference for my own.
* Open a Text Panel in Blender. 
* Choose Text > Open (Alt + O).
* Load the scmimport.py script.
* Choose Text > Run Python Script (Alt + P).
* Select script and OK.
* It will ask you for an SMC file. Navigate to one and select it.
* Click OK.
* You now have model.
## Post #14
- Username: Strife1989
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Jan 12, 2012 9:52 pm
- Post datetime: 2014-03-09T14:12:29+00:00
- Post Title: [PS3] Gundam Extreme Vs. Full Boost (2014)

macross 30 sounds nice too ! looking forward to it !!!!
## Post #15
- Username: leyme
- Rank: advanced
- Number of posts: 50
- Joined date: Wed Apr 04, 2012 5:17 pm
- Post datetime: 2014-03-22T06:11:45+00:00
- Post Title: [PS3] Gundam Extreme Vs. Full Boost (2014)

> Reply from howfie
>
> leyme wrote:Please help...
How to use smcimport.py?
I'm a mere beginner.

* Download Blender 2.49b. The script only works for that version because I used Mariusz's scripts as a reference for my own.
* Open a Text Panel in Blender. 
* Choose Text > Open (Alt + O).
* Load the scmimport.py script.
* Choose Text > Run Python Script (Alt + P).
* Select script and OK.
* It will ask you for an SMC file. Navigate to one and select it.
* Click OK.
* You now have model.


I only followed orders from howfie, nothing happened.
Could you elaborate on that?
## Post #16
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2014-03-22T20:54:17+00:00
- Post Title: Re: [PS3] Gundam Extreme Vs. Full Boost (2014)

Well, I'm going to release a combined tool pretty soon with maybe support for 10 - 20 games, most of them DW engine games + a few others. I will create a video on how to use the script. I just don't have time right now to teach people how to use Blender, very sorry.
## Post #17
- Username: sh0ck1
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Jan 11, 2011 8:50 pm
- Post datetime: 2014-05-30T05:55:05+00:00
- Post Title: Re: [PS3] Gundam Extreme Vs. Full Boost (2014)

> Reply from howfie
>
> Well, I'm going to release a combined tool pretty soon with maybe support for 10 - 20 games, most of them DW engine games + a few others. I will create a video on how to use the script. I just don't have time right now to teach people how to use Blender, very sorry.

Any update on this combined tool Howfie?

Namco is releasing a new game based off their Gundam engine called Rise of Incarnates (at least I think it is because there are GDAT files and BILZ headers all over the place).  Alpha is only available May 30 to June 1, so if you wanna download the game files you'd have to do it soon.  (apologies if this isn't at all related)
## Post #18
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2014-05-30T08:30:43+00:00
- Post Title: Re: [PS3] Gundam Extreme Vs. Full Boost (2014)

i posted combined tool in last few posts of one piece thread.
## Post #19
- Username: PureEvil
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Aug 01, 2015 8:54 pm
- Post datetime: 2015-08-01T13:32:41+00:00
- Post Title: Re: [PS3] Gundam Extreme Vs. Full Boost (2014)

big thanks for you howfie. This tool bring epicness to my favorite games Windom XP.
Here's the result. extracted by Strife1989
## Post #20
- Username: cosmos28
- Rank: n00b
- Number of posts: 10
- Joined date: Tue May 08, 2012 1:56 am
- Post datetime: 2015-09-15T15:01:37+00:00
- Post Title: Re: [PS3] Gundam Extreme Vs. Full Boost (2014)

Thank you very much Howfie for such this.
Everything ran smooth as usual.
Regards!!
## Post #21
- Username: luciferdm
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Dec 20, 2015 10:08 am
- Post datetime: 2016-08-16T01:53:08+00:00
- Post Title: Re: [PS3] Gundam Extreme Vs. Full Boost (2014)

hello, howfie. I use your script  export the model of the Extreme VS.  It's really very good.
and  I want ask a question: Is there any way to export the animation data .
## Post #22
- Username: pecel
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jun 16, 2016 5:09 pm
- Post datetime: 2016-08-22T03:24:06+00:00
- Post Title: Re: [PS3] Gundam Extreme Vs. Full Boost (2014)

> Reply from leyme
>
> howfie wrote:leyme wrote:Please help...
How to use smcimport.py?
I'm a mere beginner.

* Download Blender 2.49b. The script only works for that version because I used Mariusz's scripts as a reference for my own.
* Open a Text Panel in Blender. 
* Choose Text > Open (Alt + O).
* Load the scmimport.py script.
* Choose Text > Run Python Script (Alt + P).
* Select script and OK.
* It will ask you for an SMC file. Navigate to one and select it.
* Click OK.
* You now have model.


I only followed orders from howfie, nothing happened.
Could you elaborate on that?

Sorry I'm newbie, I already tried to extract data00.pac, it give me a lot of folder but there's nothing smc file. There're FHM file, unknown file, etc. So when the script already loaded in blender what file should i choose?

Ah, nevermind. I tried again and it work. Thx to Howfie for great script
## Post #23
- Username: Thanos168
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Aug 13, 2016 2:18 pm
- Post datetime: 2017-04-30T02:29:33+00:00
- Post Title: Re: [PS3] Gundam Extreme Vs. Full Boost (2014)

I can load some of the 3D models of the Gundams

inside the DATA00 folder are 100s of folders

how do i find out which folder have 3D files of a complete Gundam 3D model?

Does any one have a complete list of which folders have 3D files of a complete Gundam 3D model?

the gundam I am interested in are :

Psycho Gundam
Psycho Gundam MK II
GP01
gerbera tetra


Thank you much much
## Post #24
- Username: Dingzhen
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jun 04, 2022 2:13 pm
- Post datetime: 2023-03-21T08:44:32+00:00
- Post Title: Re: [PS3] Gundam Extreme Vs. Full Boost (2014)

Any methods to rip animation files ? They are omo format and I haven't seen this kind of thing.
## Post #25
- Username: Dingzhen
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jun 04, 2022 2:13 pm
- Post datetime: 2023-04-04T15:35:58+00:00
- Post Title: Re: [PS3] Gundam Extreme Vs. Full Boost (2014)

Does anyone know how to rip animation files ? They are omo format. I found Smash Forger but couldn't use it to load omo.
