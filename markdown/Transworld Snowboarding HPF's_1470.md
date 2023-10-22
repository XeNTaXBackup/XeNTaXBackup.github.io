## Post #1
- Username: Jille
- Rank: VIP member
- Number of posts: 38
- Joined date: Mon Aug 29, 2005 10:07 pm
- Post datetime: 2005-08-29T14:14:27+00:00
- Post Title: Transworld Snowboarding HPF's

Hi all,

I recently bought the game Transworld Snowboarding for Xbox.
Since I'm done playing with it, I want to try and export some of the textures of this game to Supreme Snowboarding (aka Boarder Zone) on my PC.

Transworld Snowboarding has HPF-files. These are Housemarque Packet Files, and are nothing more than this:

------------------
header
------------------
contents of the packet
------------------
file 1
------------------
file 2

etc.

Everything is unencrypted, I can just copy/paste the binary code into a new file, and have a working DDS. But for 100's of files, this is a bit too much work  

There's no demo available, so I included an example file, which includes some DDS-files. Other packages might also contain other files, like TXT and GBO.
[Cubemaps_Night.rar](https://xentaxbackup.github.io/file/411_Cubemaps_Night.rar)
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-08-29T14:22:27+00:00
- Post Title: Transworld Snowboarding HPF's

Ok, thanks ! Let us see!
## Post #3
- Username: Jille
- Rank: VIP member
- Number of posts: 38
- Joined date: Mon Aug 29, 2005 10:07 pm
- Post datetime: 2005-08-29T14:32:05+00:00
- Post Title: Transworld Snowboarding HPF's

thanks 
ps, check your PM
## Post #4
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-08-29T14:33:37+00:00
- Post Title: Transworld Snowboarding HPF's

By the way, do you have another example of such a file? Must check something.
## Post #5
- Username: Jille
- Rank: VIP member
- Number of posts: 38
- Joined date: Mon Aug 29, 2005 10:07 pm
- Post datetime: 2005-08-29T14:37:28+00:00
- Post Title: Transworld Snowboarding HPF's

Dang, you are fast 

here are some more
If you want bigger ones too, let me know
[TransWorld Snowboarding.rar](https://xentaxbackup.github.io/file/412_TransWorld Snowboarding.rar)
## Post #6
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-08-29T15:03:28+00:00
- Post Title: Transworld Snowboarding HPF's

Here's the BMS script to be used in the "Run custom script on..." option. 

```
Set S Long 32 ;
GoTo S 0 ;
Get OriginalName String 0 ;
Math S += 256 ;
GoTo S 0 ;
Get Entries Long 0 ;
SavePos S 0 ;
Math Entries *= 80 ;
Math S += Entries ;
Get AType Long 0 ;
Get Unknown Long 0 ;
Get Unknown Long 0 ;
Get FileNum Long 0 ;
SavePos J 0 ;
Math J += 64 ;
GoTo J 0 ;
For T = 1 To FileNum ;
Get RType Long 0 ;
Get Unknown Long 0 ;
Get ROff Long 0 ;
Get Size Long 0 ;
GetDString Name 64 0 ;
Math ROff += S ;
Log Name ROff Size 0 0 ;
Next T ;

```


Compiled in MexBinderPlus' Scriptor (in your MexCom directory). 

See attachment for the compiled script. Please note that this functionality is only for Friends of MultiEx (registered users).
[hpf.zip](https://xentaxbackup.github.io/file/413_hpf.zip)
## Post #7
- Username: Jille
- Rank: VIP member
- Number of posts: 38
- Joined date: Mon Aug 29, 2005 10:07 pm
- Post datetime: 2005-08-29T15:11:22+00:00
- Post Title: Transworld Snowboarding HPF's

Thanks man 
 

I will look for a way to contribute/support, so I am able to get a key.  

edit: I just sent 15 newseditor-emailaddresses, I hope you like it
## Post #8
- Username: Jille
- Rank: VIP member
- Number of posts: 38
- Joined date: Mon Aug 29, 2005 10:07 pm
- Post datetime: 2005-08-29T20:25:25+00:00
- Post Title: Transworld Snowboarding HPF's

update:

I just tried to import and it works perfect... except for a few files:
boards.hpf
audio_1.hpf
audio.hpf

download boards.hpf here:
 [1.34MB][Boards.rar](http://people.freenet.de/jille/boards.rar)

It does open the files, but for some reason it picks the wrong offsets or something like that... 

Other than that: it works PERFECT!
## Post #9
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-08-29T20:40:52+00:00
- Post Title: Transworld Snowboarding HPF's

Thanks! I'm glad you enjoy it!  I will take a look at the other file.
## Post #10
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-08-30T15:03:47+00:00
- Post Title: Transworld Snowboarding HPF's

Looks like the file is somewhat corrupted, not following the universal rule. I'll have to take a closer look.
## Post #11
- Username: Jille
- Rank: VIP member
- Number of posts: 38
- Joined date: Mon Aug 29, 2005 10:07 pm
- Post datetime: 2005-08-30T19:31:43+00:00
- Post Title: Transworld Snowboarding HPF's

cool thanks
if you want more 'corrupted' files, let me know.
## Post #12
- Username: Jille
- Rank: VIP member
- Number of posts: 38
- Joined date: Mon Aug 29, 2005 10:07 pm
- Post datetime: 2005-09-07T23:18:36+00:00
- Post Title: Transworld Snowboarding HPF's

Okay, I looked trough all the available HPK files, and it appears that only the three files I mentioned are bugging.
Is there something that I can do about this?
## Post #13
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-09-08T07:17:21+00:00
- Post Title: Transworld Snowboarding HPF's

Probably not...I'll have to see if I can write a new script for those.
## Post #14
- Username: Jille
- Rank: VIP member
- Number of posts: 38
- Joined date: Mon Aug 29, 2005 10:07 pm
- Post datetime: 2005-09-09T15:25:26+00:00
- Post Title: Transworld Snowboarding HPF's

okay cool   
if you need more files let me know!
