## Post #1
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2005-01-07T21:27:08+00:00
- Post Title: Mex Scripting Tutorial

Well, the idea for this came from the following thread:
[viewtopic.php?t=1032](http://forum.xentax.com/viewtopic.php?t=1032). The reason behind it (like I need to give one) is to help me understand how to write my own scripts, but it could also help other n00bies to MexScripter. I'm here to learn, so teach me suckers!
## Post #2
- Username: elcondor
- Rank: VIP member
- Number of posts: 18
- Joined date: Tue Dec 14, 2004 6:28 pm
- Post datetime: 2005-01-08T19:49:50+00:00
- Post Title: Mex Scripting Tutorial

I'm probably not the right person to do this, but here goes.

Firstly, you need some idea of how the file format works (the guide hosted on the main page is particularly good for this)

So once you have your hex editor fired up, and looking at a sample file, think about how you'd instruct a person to read the file.

Say, for example, the ID for this filetype is ABCD, (IDString 0 ABCD  is the code for it, and that makes rudimentary sense "The IDString of File 0 is ABCD"

As for finding information, remember that you can Get the various file sizes, even if you don't need the information, and just want a surefire way of skipping so many bytes.

The rest is pretty much up to you, since every file is different, but unbinding the MC.MRF file and reading those scripts (particularly if you have one of the games to compare with) is normally a good start.

If there are any specific questions, I'm sure someone can answer them.
## Post #3
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-01-08T21:57:31+00:00
- Post Title: Mex Scripting Tutorial

Well, I do think you are one of those right persons to do this, as you created a script that worked so you have experienced possible pitfalls that others trying to create a script may also fall into. Although I created the script, it still shows some of MY way of thinking at the time of creation, and I realize that that may not be to easy. Not that it is at any higher level or something, but it is confined in my own brain, which may not be all that logical at times. So an "outsider" turned "insider" like you has all the knowledge! As such, you could show how to use it, and you did a good job already!
## Post #4
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2005-01-09T17:35:32+00:00
- Post Title: Mex Scripting Tutorial

Umm... where do I go to get MexScriptor? I've looked all over the place, but the closest to it that I could find was the MexBinder. Or I could just be blind... Yeah, we'll go with that.
## Post #5
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-01-09T18:21:25+00:00
- Post Title: Mex Scripting Tutorial

Get MexBinderPlus at the download page, and in it, start instance of Mex3Scriptor.
## Post #6
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2005-01-09T18:44:52+00:00
- Post Title: Mex Scripting Tutorial

I tried that, but I just get an error message:

mexbinderplus2

Run-time error '372':

Failed to load control 'RichTextBox' from RICHTX32.OCX. Your version of RICHTX32.OCX may be outdated. Make sure you are using the version of the control that was provided with your application.
## Post #7
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-01-09T19:03:10+00:00
- Post Title: Mex Scripting Tutorial

Really? How odd indeed. So that is what happens if you go to "Scriptor" and select "Start new instance"? Odd. 

Perhaps you do have an outdated version. Look in your windows/system32 dir and find the ocx. Then select Properties of it and then look in "Version".
## Post #8
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2005-01-09T19:12:16+00:00
- Post Title: Mex Scripting Tutorial

The version it gives in the title bar when MexBinderPlus is running is v1.5. The version of the ocx is 5.0.37.14.
## Post #9
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-01-09T19:25:57+00:00
- Post Title: Mex Scripting Tutorial

Okay, well, please back up the ocx and do the following:

(from [http://www.ascentive.com/support/new/su ... CHTX32.OCX](http://www.ascentive.com/support/new/support_dll.phtml?dllname=RICHTX32.OCX)) 

> Reply from Set it up
>
> 

Download RICHTX32.OCX (right click the text on the left and save to your Desktop).


Back up your current copy of RICHTX32.OCX and copy the new version to the same file location. This file should be located in the WINDOWS\SYSTEM directory on your C: drive (for Windows NT and 2000: \WINNT\system32). 


Using your mouse, click on the "Start" button and then click on "Run". 


According to your Operating System, type the following command to register this library file:

Windows 95, 98, or Me:
regsvr32 \windows\system\RICHTX32.OCX

Windows NT or 2000:
regsvr32 \WINNT\system32\RICHTX32.OCX

Windows XP:
regsvr32 \windows\system32\RICHTX32.OCX


You should see a message saying "DllRegisterServer ... succeeded" 

If you are getting an error telling you that the file is missing, then you are not typing the command in correctly. You will need to type it in *exactly* as as shown above for your operating system.

* Please note that there is a SPACE after "regsvr32" and before the rest of the command.

You should probably copy and paste the command so that you are unable to mistype it. 

Download RICHTX32.OCX now (right-click on the link and select "Save Target as...").
## Post #10
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2005-01-09T19:53:00+00:00
- Post Title: Mex Scripting Tutorial

Yes, yes, yes, it works, it works, it works!  Thanks for the help!
## Post #11
- Username: elcondor
- Rank: VIP member
- Number of posts: 18
- Joined date: Tue Dec 14, 2004 6:28 pm
- Post datetime: 2005-01-09T20:14:35+00:00
- Post Title: Mex Scripting Tutorial

Can I ask you not to include my script just yet - I've been studying the actual sound format, and it appears that I may need to keep all the snd stuff together, rather than split it apart to make it works as it was in the original application.

If that's the case, I'll have to send a corrected script.
## Post #12
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2005-01-09T20:38:21+00:00
- Post Title: Mex Scripting Tutorial

I'm about to try to write a bit of script for the following information on the 'master header' in Carnivores .car files:

```
(offset: 0000 0000 hex, 0 decimal) 

byte name[24] (name)
byte extra[8] (usually "msc: #", where "#" is a number)
long num_anims (number of animations)
long num_sounds (number of sounds)
long num_points (number of vertices)
long num_triang (number of triangles)
long bytes_tex (texture length in bytes)

```

Gotten from [http://machf.tripod.com/Hunt/Carn/car.htm](http://machf.tripod.com/Hunt/Carn/car.htm). If anyone wants to try and help, feel more than welcome to! I'll post what I've got when I get it.

EDIT: This is what I have so far. It is for the first two lines:

```
byte extra[8](usually "msc: #", where "#" is a number)

```

And the script that elcondor and Mr. Mouse wrote for me, since I'm clueless at this...:

```
GetDString FILENAME 24 0 ; 
SavePos JUMP 0 ; 
Math JUMP += DUMMYL 8 ; 
GoTo JUMP 0 ;

```


This is what I'm working on next:

```
long num_sounds (number of sounds)
long num_points (number of vertices)
long num_triang (number of triangles)
```
## Post #13
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-01-09T20:52:36+00:00
- Post Title: Mex Scripting Tutorial

> Reply from elcondor
>
> Can I ask you not to include my script just yet - I've been studying the actual sound format, and it appears that I may need to keep all the snd stuff together, rather than split it apart to make it works as it was in the original application.

If that's the case, I'll have to send a corrected script.

Okay, but rest assured the new release isn't due yet, so there's still plenty of time.
## Post #14
- Username: elcondor
- Rank: VIP member
- Number of posts: 18
- Joined date: Tue Dec 14, 2004 6:28 pm
- Post datetime: 2005-01-11T13:52:22+00:00
- Post Title: Mex Scripting Tutorial

If the MODELNAME is actually the filename you want and it's 24 bytes, it's best to just 
```
GetDString FILENAME 24 0 ;
```
 that way, all the formatting is preserved (using the ordinary get function tends to trash some filenames, turning them into numbers)

Setting DUMMYL to anything may not actually do much, if you're wanting to skip something you need to Get DUMMYL Long 0 ;
## Post #15
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-01-11T14:01:02+00:00
- Post Title: Mex Scripting Tutorial

Indeed, and each time you GET something the file pointer is reset to the new position in the file. SET will do nothing to the file. 

So to get the filename and then skip 8 bytes:

```
GetDString FILENAME 24 0 ;
SavePos JUMP 0 ;
Math JUMP += DUMMYL 8 ;
GoTo JUMP 0 ;

```


# explanation : 
Set DUMMYL to a long variable with the value 8
GetDETERMINEDSIZEString FILENAME of 24 bytes in length from FILE 0. 
Save the current position in the file in the variable JUMP. 
Add the value in DUMMLY to whatever JUMP became. 
Jump to the position of JUMP in the file.
## Post #16
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2005-01-11T23:19:09+00:00
- Post Title: 

Okay, I think I'm beginning to understand... So when I try to script it to read the number of animations, vertices, triangles, and sounds, is there any way I can tell it  to 'expect' that given number of what they happen to be? (the numbers are stored in hexadecimal, not just decimal) I know that I would have to set each one as a variable and then reference it later on when it's needed... (or I could just be reading way too deep into it)

EDIT: I tested the script you gave me, and it said "Error in line 3: Incorrect Number of Variables". Will the script compensate for this itself, or does it have to be fixed?
## Post #17
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-01-11T23:34:35+00:00
- Post Title: 

I'm not exactly sure what you mean. 
The script doesn't 'know' what the files are you want to extract. That's all up to MultiEx Commander to decide. 
The script is just there to extract (and provide information needed to import) files. 

Also, the 0 ; you will see after a lot of commands just means "filenumber". You see, you can open other files from the script that will get the number 1...n  (the 0 is the main archive, set when you let lose a script on an archive).
## Post #18
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2005-01-12T00:02:13+00:00
- Post Title: 

Umm... I think what I'm trying to say is, would I have to tell the program to get the number of, say, animations, and save that number as a variable, so that when it gets to the section of the animations, it calls the variable back up, and only goes through the number of animations specified by the variable, before calling up the next variable for the next section. But like I said before, I could be, and probably am, reading into it waaaaaaaaay too much.
## Post #19
- Username: elcondor
- Rank: VIP member
- Number of posts: 18
- Joined date: Tue Dec 14, 2004 6:28 pm
- Post datetime: 2005-01-12T19:39:37+00:00
- Post Title: 

It's possible to do that, I suppose it's a For loop, but I can't manage one of those yet (I think it would be the Get command for the number of animations, then a 'For A = 1 to TOTAL' type thing when you get there.
## Post #20
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2005-01-20T02:32:31+00:00
- Post Title: 

(bump) Any more help?
## Post #21
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2005-01-20T08:37:44+00:00
- Post Title: 

I'm  not sure how much you can do with the script engine to extract all these different data types. Sorry.

PS. This is EC, I just can't login right now.
## Post #22
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-01-20T08:42:48+00:00
- Post Title: 

The script is low-level in the sense that you will have to find or define a variable that is the number of "animations". 

If you mean, can you tell it to search for specific animation types and count them, then no. The script knows nothing about file types. It just deals with binary file access. 

Now, if you know that at a certain position in the archive there's a variable that is the number of "animations" then yes, you should load that intop a variable using the script. If the format of the archive allows it you can then use a For T=1 to (YourVariable) and do stuff you need to extract them. 

Perhaps El Condor can explain his script (line by line) to show you the principle of it all?
## Post #23
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2005-01-21T03:46:20+00:00
- Post Title: 

Yes, that would definitely help me! If he could take time to show me, I would be very appreciative!
## Post #24
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2005-02-02T16:19:22+00:00
- Post Title: 

Umm... anyone?
## Post #25
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-02-08T08:29:29+00:00
- Post Title: 

I guess he doesn't feel like it. When I have time, I might write a small step-by-step tutorial. in a way, such a thing is also in the manual/help that comes with MexBinderPlus.
## Post #26
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2005-02-08T15:49:24+00:00
- Post Title: 

Yes, but with the included manual, you have to take the information and figure out how to apply it yourself. If you take a sample script, broken down step-by-step, it would allow many more people to grasp the fine points of writing their own scripts.
## Post #27
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2005-02-08T15:50:20+00:00
- Post Title: 

Oops, sorry, that was me. Forgot to login...
## Post #28
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2005-04-16T18:19:51+00:00
- Post Title: 

hi

when iam start mex3scriptor show error message :

"run time error 430
class does not support..."
## Post #29
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-04-16T21:21:25+00:00
- Post Title: 

Yes, the new MexScriptor is not released yet. WIll work on it soon.
