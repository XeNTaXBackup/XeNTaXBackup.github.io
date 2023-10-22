## Post #1
- Username: TheDyingInformant
- Rank: veteran
- Number of posts: 89
- Joined date: Mon Sep 01, 2003 8:41 am
- Post datetime: 2003-10-15T02:08:30+00:00
- Post Title: Can MultiEx Open Game Archives That Aren't Supported?

By this I mean, say the .dat format is supported in a few games in MultiEx.  But my game isn't one of those games, but it still uses .dat.  Could it not technically still open the .dat files of this 'unsupported' game?  Is it worth me trying or could I ruin the files by trying?  Or is the way the program is built to specifically look for information that it is a specific game?

Also, I want to know, this 'OpenMex' coming out, you say it will have multi platform support.  What do you mean by that?  Does that mean you could put console game CDs in your CDrom drive and it can extract files?  I know that this is possible, because there is a program called PSound that lets you do this.  Similarly to MultiEx, it supports certain games, so only those games are supposedly supported.

Anyway, it would be cool to be able to download the sound clips from Dreamcast games, but the GD rom is a different kind of format.  Ofcourse for now I want to access Metal Gear Solid 2's .dat sound files, but since I am not a scripter, it might be beyond my abilities. (I have MGS2 for PC so why shouldn't I have access to files that take up 7 gigs on my hard drive?) STILL, I'm so happy MultiEx exists so I can get someone else to do it for me!  And the source code being made available has GOT to be good too.

If you could answer my questions, that would be awesome of you.
## Post #2
- Username: Captain
- Rank: Site Admin
- Number of posts: 248
- Joined date: Thu Jan 16, 2003 1:25 am
- Post datetime: 2003-10-15T09:52:00+00:00
- Post Title: Can MultiEx Open Game Archives That Aren't Supported?

Hi,

Multiplatform, in the OpenMex context, means that OpenMex should be able to run on different OSs like Linux, Apple OSX, etc. Unfortunately for you, it doesn't mean that OpenMex will arbitrarily support console games. If there's enough interest, we may look at that in the future, but I can't make any promises for that. Another difficulty is that I don't own or plan to own a Dreamcast, so there's no way for me to try and test if things work.

About the .dat question: I think Mr. Mouse should answer that. As far as I know, MultiEx doesn't really check the format, so it will just try to read it. It is highly unlikely your files will be ruined (the worst that could happen is that MultiEx crashes), but you should always make a backup of the files you want to open before you try anything.
## Post #3
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-10-15T10:13:02+00:00
- Post Title: Can MultiEx Open Game Archives That Aren't Supported?

Quite frankly, no, MultiEx cannot open all .dat files, just because they're called .dat files. Anyone can name their archives .dat files, and the extension .dat is widely used for all kinds of things. DAT is just DATA. Dune 2 uses .PAK files, and so does Quake. But they're not the same. What MultiEx does is try to open it. If there is some kind of marker that identifies the archive as a give format it will check that first. Thus, if you opt to open any given .dat file as a .dat file from another game, if the id marker doesn't match, MultiEx will tell you so and abort process. If there is no ID marker, MultiEx will try to open it. If it fails, because it is not the right format, it will tell you so and abort further process. During the opening/analysis process of any given archive MultiEx only READS data, it never ever writes to these archives. So it will not harm any of your files, if you choose to open an archive with the wrong format selected. The worst that could happen is a crash of MultiEx Commander, although that is highly unlikely, as the analysis processes (MultiEx2 and MultiEx3) all have error handling and happen outside of MultiEx Commander. And if they crash, MultiEx Commander will kill them and tell you they could not process your format as specified.
## Post #4
- Username: TheDyingInformant
- Rank: veteran
- Number of posts: 89
- Joined date: Mon Sep 01, 2003 8:41 am
- Post datetime: 2003-10-18T03:38:35+00:00
- Post Title: Can MultiEx Open Game Archives That Aren't Supported?

Thanks for that.  Yeah I guess .dat is a pretty tricky format that simply means data but can be different.  That must be why i can't seem to find any .dat extracting programs.

Now, I want to make support for Metal Gear Solid 2.  I don't know how to go about this.  I'm no programmer at all like I said in another thread.  But you include all you need to know you said.  I just don't know what to make of it (I tried reading some of the instructions).  I wonder if you could answer some of my questions:


1) Is there anything else I need besides MultiEx commander?  Do I need a script editor or it comes with one?  I know it comes with something. 

2) Can I do this without having any programming knowledge?

3) What are the documents I read ( I think something about the script for the Dos version and what else?) and does it tell me stuff step by step so I don't screw up?

4) What, if any, files do I need from  my game? I know they are in .dat extension, but if what you say is right, that doesn't mean I know the real format?



A seperate question.  My friend already started doing this.  But he doesn't have any archive files of the game (some are 1gig so he didn't want to download it from me).  He said he had the script done but he couldn't figure out how to make it seen by MultiEx or whatever program came with it.  He ran into 'error 9' .  What does that mean?

Also, could you take a look at the script and if this appears right to you?

Here it is:
(this is after the intro info at the top)




;ID is casesensitive

ID=multiex  			

;the filepointer is now 0+length of "multiex" (7)

;Now we tell MULTIEX that the format is up next:
EVENTS

;We save the long at pos 7, which is the number of files in the datafile.
GetLong 	FILECNTL
;Then we save the filepointer which is now 7+4 = 12
SavePos		FILESTART

;Now we create a loop

LOOP
;We jump to the saved position
GoTo		FILESTART

;We get the file info FILESIZE, FILEOFF and FILENAME
GetLong		FILESIZE
GetLong		FILEOFF

;Let's assume the filenames are all 13 in length
GetString	13	FILENAME

;In order to be able to come back to the following file we
SavePos		FILESTART

;We prompt the user for the file to extract and Extract it
PROMPTUSER
ExtractFILE ONE

;Then we end the loop, saying that it should end when extracted=filenumber
ENDLOOP EXTRCNT FILECNTL



Ofcourse I don't know if that's everything you need to know to check if that's correct.

I just really need some help with this.  For ME, I need total noob start from scratch help.  For my friend, if it looks like he's doing it right, I need to know what to tell him to do about 'error 9'.  

Please point me in the right direction, or tell me right now, if this is too much for me to take on.  I couldn't tell if the instructions were hard, cause I was confused about what even WAS the instructions.  There appeared to be one file, and then help files withen the two programs or something.

Eh... I am so confused...

And I don't want to bother you, and I am certainly not asking for you to make the game supported for me.  I want to learn how to do it so I don't need to bother you.    

Are there FAQs or help documents on this site that I seem to have missed?
## Post #5
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-10-18T06:14:29+00:00
- Post Title: Can MultiEx Open Game Archives That Aren't Supported?

> Reply from TheDyingInformant
>
> 1) Is there anything else I need besides MultiEx commander?  Do I need a script editor or it comes with one?  I know it comes with something.

It comes with Mex3Scriptor, where you can write additional scripts with.   

> Reply from TheDyingInformant
>
> 
2) Can I do this without having any programming knowledge?

Probably not, sorry to say. I think it will be difficult. However, everyone had to learn at some point!   

> Reply from TheDyingInformant
>
> 3) What are the documents I read ( I think something about the script for the Dos version and what else?) and does it tell me stuff step by step so I don't screw up?

Well, in Mex3Scriptor you can read the docs on the DOS version (to get into the script) and more importantly, docs on the commands for the windows version of MultiEx (MultiEx3). And no, it is very user unfriendly, so it won't take you by the hand.   

> Reply from TheDyingInformant
>
> 
4) What, if any, files do I need from  my game? I know they are in .dat extension, but if what you say is right, that doesn't mean I know the real format?

Exactly, you can't really tell a format just from the extension. Okay, so if you see a file called .zip or .jpg you can assume that they are pkzipped and JPEG picture files, granted, but with game archives, this is a different thing. You have to examine the file to see which format it is.  

> Reply from TheDyingInformant
>
> 
A seperate question.  My friend already started doing this.  But he doesn't have any archive files of the game (some are 1gig so he didn't want to download it from me).  He said he had the script done but he couldn't figure out how to make it seen by MultiEx or whatever program came with it.  He ran into 'error 9' .  What does that mean?

As it says in the docs that come with MultiEx2 (readable from Mex3Scriptor) :

9       | Unable to Create ExtractFile  | doserror, check name etc

> Reply from TheDyingInformant
>
> 
Also, could you take a look at the script and if this appears right to you?

Here it is:
(this is after the intro info at the top)




;ID is casesensitive

ID=multiex  			

;the filepointer is now 0+length of "multiex" (7)

;Now we tell MULTIEX that the format is up next:
EVENTS

;We save the long at pos 7, which is the number of files in the datafile.
GetLong 	FILECNTL
;Then we save the filepointer which is now 7+4 = 12
SavePos		FILESTART

;Now we create a loop

LOOP
;We jump to the saved position
GoTo		FILESTART

;We get the file info FILESIZE, FILEOFF and FILENAME
GetLong		FILESIZE
GetLong		FILEOFF

;Let's assume the filenames are all 13 in length
GetString	13	FILENAME

;In order to be able to come back to the following file we
SavePos		FILESTART

;We prompt the user for the file to extract and Extract it
PROMPTUSER
ExtractFILE ONE

;Then we end the loop, saying that it should end when extracted=filenumber
ENDLOOP EXTRCNT FILECNTL
 Who is this friend of yours? Because, if I remember correctly, this multiex2 (dos) script was written by me! And only as an example of how the script works, and certainly not for Metal Gear files. The "ID=multiex" shows this. .I do not think Metal Gear files have an ID string that reads "multiex"!   


> Reply from TheDyingInformant
>
> 
Ofcourse I don't know if that's everything you need to know to check if that's correct.

The script is just an example of how the language works. To my knowledge I made it up to show it off. So this won't work no. Besides, it is MultiEx2 (dos) script, although you can still use that, I would advise people to write in MultiEx3 script, with MultiEx3Scriptor. 

> Reply from TheDyingInformant
>
> 
I just really need some help with this.  For ME, I need total noob start from scratch help.  For my friend, if it looks like he's doing it right, I need to know what to tell him to do about 'error 9'. 
Please point me in the right direction, or tell me right now, if this is too much for me to take on.  I couldn't tell if the instructions were hard, cause I was confused about what even WAS the instructions.  There appeared to be one file, and then help files withen the two programs or something.
Eh... I am so confused...
And I don't want to bother you, and I am certainly not asking for you to make the game supported for me.  I want to learn how to do it so I don't need to bother you.    
Are there FAQs or help documents on this site that I seem to have missed?

No, all the docs there are come with the package. And they are limited in a sense that beginners will probably have a hard time grasping the concept. If you haven't a clue as to how the file system works, or how archives are made up, I wouldn't try to write scripts. General knowledge on these basics you will need first. As for your friend, I am not too sure he knows what he is doing. 

Anyway, don't hesitate to ask away, the Metal Gear file format is noted on our to-do list. We may figure it out and implement it in OpenMex! You will be notified!
## Post #6
- Username: Captain
- Rank: Site Admin
- Number of posts: 248
- Joined date: Thu Jan 16, 2003 1:25 am
- Post datetime: 2003-10-18T10:45:12+00:00
- Post Title: Can MultiEx Open Game Archives That Aren't Supported?

I would like to add that OpenMex will have a new, more powerful script engine. OpenMex scripts are written in pure [Python](http://www.python.org), which makes them a lot more flexible. In the future, it should be easier to write your own scripts for OpenMex because you don't have to learn the MultiEx script format (which, as stated, has limited documentation). You would have to learn Python though.

Also, it is our intention to push ahead with OpenMex, so support for new games will probably be released for OpenMex only.

In other news: I will release an alpha-version of OpenMex this weekend, capable of extracting (not importing yet) almost all MultiEx formats. It does not nearly have all the functionality of MultiEx, and probably a lot of bugs, but the GUI looks pretty sexy if you ask me.
## Post #7
- Username: TheDyingInformant
- Rank: veteran
- Number of posts: 89
- Joined date: Mon Sep 01, 2003 8:41 am
- Post datetime: 2003-10-19T04:15:29+00:00
- Post Title: Can MultiEx Open Game Archives That Aren't Supported?

> And no, it is very user unfriendly, so it won't take you by the hand

Well, maybe it can't be helped that you have to know how to program/edit scripts to do this.  But I would like to suggest that in OpenMex you try and add step by step instructions, so that there aren't so many people emailing you asking for new support.  There are far more people out there that simply have games they want to get files from than those who in addition also know how to program.      Even if such support could only be added by people who have programming knowledge, if in your instructions you direct people to where they can learn what to do, and then from there, follow your instructions, you will have less people bugging you.    

> Exactly, you can't really tell a format just from the extension. Okay, so if you see a file called .zip or .jpg you can assume that they are pkzipped and JPEG picture files, granted, but with game archives, this is a different thing. You have to examine the file to see which format it is.

Hmm.... I have no idea what so ever how to go about finding out.  I don't think I'll be getting very far adding this support myself or from my friend....    

> Who is this friend of yours? Because, if I remember correctly, this multiex2 (dos) script was written by me!
   Guess he really doesn't know what he's doing!  Well, he says he knows some type of programming, maybe not the right kind for the task at hand.  Yeah lol, ID=MultiEx    

> Anyway, don't hesitate to ask away, the Metal Gear file format is noted on our to-do list. We may figure it out and implement it in OpenMex! You will be notified!
   That would be so awesome of you! (Metal Gear Solid 2 btw).  I can't find any way to get access to these files.  I've tried different things, asked on different boards.  Heck, I even tried to go to a board where to-be game developers go, and they got all upset that I am trying to get other people's creative work, and what not, so didn't want to help me at all.  I really would be thrilled if you did this.  If you need any further 'encouragement', don't hesitate to ask.      Also, if you require any of the files,  or need any information that I could get you from the game, I got it.  Mind you some are HUGE size files.  But I will ofcourse offer you whatever you need to support the game.    



To 'Captain': 

Well by the sounds of things, OpenMex is going to be everything that MultiEx is and then some.  Am I correct?  If so, it makes sense you would only focus on that from now on.  And again, if there is better documentation included and its easier to write scripts, that would be wonderful.  Learning Python I hope is easier, but there is always something to learn, isn't there?  I know one of these days I plan on making a new 2D sprite monster for Duke Nukem 3D, or a new playable character, since I always wanted to do that.  It does require some C++ knowledge, but I have a book that describes it a little, and I'm sure there are tutorials too.

I guess I'm trying to say, sometimes, people who don't program like myself might want to learn a bit of it.  You never know when it could come in handy.  But for the record, I'm awful at math, and I can't hardly decipher 'leet speek', so I don't think programming is for me.   


Thanks again.  I will keep an eye on this OpenMex.  And I'll ofcourse let others know about it.
## Post #8
- Username: Captain
- Rank: Site Admin
- Number of posts: 248
- Joined date: Thu Jan 16, 2003 1:25 am
- Post datetime: 2003-10-23T18:52:18+00:00
- Post Title: Can MultiEx Open Game Archives That Aren't Supported?

Could you link us to a small Metal Gear file (a file you want to extract from) for us to examine?
## Post #9
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-10-23T19:32:00+00:00
- Post Title: Can MultiEx Open Game Archives That Aren't Supported?

Yes, please do, because I have a hard time finding a demo for MGS2:Substance. Or would the MGSTrial also do...hmm...I'll have a look at those files.
## Post #10
- Username: TheDyingInformant
- Rank: veteran
- Number of posts: 89
- Joined date: Mon Sep 01, 2003 8:41 am
- Post datetime: 2003-10-24T01:00:45+00:00
- Post Title: Can MultiEx Open Game Archives That Aren't Supported?

YES!  I will provide whatever you need!  Unfortunately, I don't have access to my computer right now, but in a few hours I can help you.  I have uploaded the over 1gig size dialog archive to my webspace, but, this is webspace my friend just gave me, and I don't remember the URL for it....     But I'll let you know in a few hours.  

In the meantime, I don't want you to think your fruits of labour (or however the expression goes) is just for me.  So the other day or so, I created a thread at the IGN MGS board.  Now you know more people will download your program and check it out, if it gets MGS2 access.  

[CHECK IT OUT HERE](http://boards.ign.com/message.asp?topic=47060518&start=47162436)

Why didn't I write down my webspace URL... 


Oh, btw, no the MGStrial is the demo for the first one.  MGS2 doesn't have a demo.  Which is REALLY a shame since it would help people know if it would run well or like crap on their computer.  So you will need my help, indeed.  Actually, if you guys have MSN messenger, we could talk through that (or even through PM if you want) while I check the files in my directory, and you could tell me specifically what would help the most, and I will upload those.  But my space is 1 gig, so it would have to be one file at a time, if its the bigger files like that.






Damn, I have no access to my webspace right now!  Is there some other way I could get the file to you?  Smallest is 25MB, largest is 1.4 Gig.....  But these are the .dat files that looks like it contains all the games files.  vox.dat, demo.dat, faces.dat, movie.dat etc.  but, there are alot of other folders, so, I'm not sure what it is I need to give you, but, I can't give you anything without webspace.....

My friend who gave me the webspace account isn't online, so I can't ask him the URL.
## Post #11
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-10-24T07:54:39+00:00
- Post Title: Can MultiEx Open Game Archives That Aren't Supported?

Yes, well, the DAT files seem the business, looking at their names (and size probably). Then we need to get a link to one or two of these files (preferably with sounds and graphics) so we can download them. 

Great thread you started at IGN, by the way!   Now all we need is those files.  Really a SHAME that Konami did not release a demo of this.    

I looked at the MSGTrial and it did not have any archives, all the files were saved individually in the directories, so that's of no use. 

So I hope you can fix your webspace or from some other SolidSnake fan at IGN?
## Post #12
- Username: TheDyingInformant
- Rank: veteran
- Number of posts: 89
- Joined date: Mon Sep 01, 2003 8:41 am
- Post datetime: 2003-10-24T23:50:09+00:00
- Post Title: Can MultiEx Open Game Archives That Aren't Supported?

Ok, my webspace is sorted out, but, maybe I should upload the smaller files for you to check out.  Vox.dat is going to take over 15 hours to upload, and I don't know how long it will take to download.  That should have dialog in it.  So, I am going to upload one or two other files instead, so you have something.  If you only study one or two archive files, does that mean the format is similar for all of them?  Cause I don't know if I want to upload or if you want to download vox.dat.  But it has dialog (I think) and that is what I want the most.

I don't know what these files have in them.  My GUESS is they are videos.


[movievr.dat (32kb)](http://210.49.130.84:8080/rkpellagirl/files/movievr.dat) (probably the small video clips of the VR missions showing you what they are like)

[face.dat (25mb)](http://210.49.130.84:8080/rkpellagirl/files/face.dat) (probably all of the face animations in the codec in the game)

These are the smallest files too....

Tomorrow I will upload a file that is almost 300mb.  If you need it.  Let me know when you download these, so I can take them down and put others up.  There are 5 more files left, if you need all of them.  2 are almost 300mb.  2 are between 1 gig and 1.5 gig.  The other one is 80mb.  For now, I hope these two files will be of use.

Let me know when you download them.    


Some of the files, cause of the name, I can guess what could be in them, but also for Metal Gear Solid 1 on Playstation, there was a program made by someone called 'PSound' that could extract the sound effects and dialog files from the Playstation CDs.  The names of the archives for that game looked exactly the same.  Demo.dat, vox.dat, etc.  I don't know if information about PSound will help.  Probably just MGS2's files.      I can provide both.

Glad you like that thread.  You may as well know how much it will be appreciated, right.
## Post #13
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-10-25T09:54:45+00:00
- Post Title: Can MultiEx Open Game Archives That Aren't Supported?

Ok, I have them. If you have more, please post them!
## Post #14
- Username: TheDyingInformant
- Rank: veteran
- Number of posts: 89
- Joined date: Mon Sep 01, 2003 8:41 am
- Post datetime: 2003-10-25T10:59:30+00:00
- Post Title: Can MultiEx Open Game Archives That Aren't Supported?

Do you need ALL of them?  Or atleast that gives you the best chances to figure the game files out, huh?


Here are two more, and let me know when you get these, and if I can delete them once you got them.


[bgm.dat (292MB)](http://210.49.130.84:8080/rkpellagirl/files/bgm.dat)  This has GOT to be music.  

[movie.dat (291MB)](http://210.49.130.84:8080/rkpellagirl/files/movie.dat) I would guess cinemas, the visual portion, unless they are saved as one thing


The two most important ones are left, and they are 1 gig each.  It will take me all day to upload just one, so look for that Monday morning, and the next one Tuesday morning.  But you'll have to get these files first so I can delete them and make room for the 1 gig file.

Thank you ever so much.
## Post #15
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-10-26T16:28:00+00:00
- Post Title: Can MultiEx Open Game Archives That Aren't Supported?

ok , I got BGM.DAT , downloading the other one.
## Post #16
- Username: TheDyingInformant
- Rank: veteran
- Number of posts: 89
- Joined date: Mon Sep 01, 2003 8:41 am
- Post datetime: 2003-10-26T18:45:35+00:00
- Post Title: 

Good good.      I just got up, uploading vox.dat.  I'm 'resuming' download since it got cut off yesterday.  Does that really work?  Anyway, it says it will take 16 hours, so, I should have it uploaded for you before 3am.

After you get all these, if that's not enough, let me know.  I am also curious where the games models and textures are saved.  These files I'm sending to you are from the folder 'cdrom.img', along with folders that are called 'face', 'image', 'module', 'pac' and 'stage'.  I won't send them unless you need them.  I mean, I could, but one is over 3gigs and that's just gonna be too big to upload.  

Gosh, is this the biggest PC game ever?   


For fun, you could [download this too.](http://211.28.233.228:8080/rkpellagirl/audio/01_-_metal_gear_solid_main_theme.mp3)  Maybe listen to it while you work on these files.  It's the theme song of the game.  You won't regret it if you decide to download it.   

Ofcourse that's totally optional.
.
.
.
.
.
.
.
Here is a biggy (and important)!

[vox.dat (1.07Gb)](http://210.49.130.84:8080/rkpellagirl/files/vox.dat) (probably all the dialog in the game, aside from the cinemas - which will come tomorrow).

I feel bad for you though.  It's so nice of you to do this, but how much space is this taking up on your hard drive I wonder?  Its so cool of you to do this.

Let me know when you get movie.dat and vox.dat.
## Post #17
- Username: TheDyingInformant
- Rank: veteran
- Number of posts: 89
- Joined date: Mon Sep 01, 2003 8:41 am
- Post datetime: 2003-10-28T08:19:42+00:00
- Post Title: 

So do you think you have enough to work with now?  Let me know when you get those.  If you need the other huge file I have, I can't upload it until vox.dat is deleted from my space.  So let me know when you get that and if you need the other one too.

Thanks.
## Post #18
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-10-28T11:15:19+00:00
- Post Title: 

Well, I'm downloading the vox thing now. It will take a while at 14kbs. I can already say though, that every single dat file I looked at is different. Up to now, there seems no general MSG2 dat format. We will see. 
Meanwhile , I've been busy demystifying the .CDDS format from Lock On. 
And added it to the XeNTaX [OpenGRAF database](http://www.xentax.com/opengraf/index.html).
## Post #19
- Username: TheDyingInformant
- Rank: veteran
- Number of posts: 89
- Joined date: Mon Sep 01, 2003 8:41 am
- Post datetime: 2003-10-28T20:32:19+00:00
- Post Title: 

Uh oh... I wonder what this means....  Oh dear, could it be that Konami was actually so clever to make MGS2 not even possible to be hacked?  Or a real headacke to do so?

An interesting note is that all files in the PAC folder can be played in Windows Media Player.  They are all the videos in the game (not cinemas but other videos).  So that can be accessed... hmm.  So that makes me wonder what the heck is movievr....

There's no rush ofcourse, just keep me posted.   


OMG why didn't I think to compress these???  It didn't occur to me at all.   I read that is what the guy did in the .cdds thread.  It's nice you were able to help him so quickly.  I guess MGS2 is being a b****.   



Okay.  So I don't know how far along you are on vox.dat, maybe we should continue with that as planned.  But then the other one I can upload in a zip folder.  OR if you're not far along with getting VOX than you could cancel that, and I can upload both files zipped, which would be a 1.5 gig download, and over 2 gig after extraction.  Uploading takes a long time, and I'm sure downloading does too.  But just let me know how you want to do it, and I can proceed with uploading zip files instead.

I can't BELIEVE I forgot to do that before.
## Post #20
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-10-30T10:41:14+00:00
- Post Title: 

Indeed, just RAR or ZIP the VOX file and put it up again. My computer crashed at halfway the previous time and all was lost.   

This entices me to write a small app that I can give an URL to and that will download a file. Just so I can see at an earlier download time point how the format works, without having to down the whole file.   
I will call it XeNTaX' DownScanner. .. . . . .. .  .
## Post #21
- Username: TheDyingInformant
- Rank: veteran
- Number of posts: 89
- Joined date: Mon Sep 01, 2003 8:41 am
- Post datetime: 2003-10-30T22:30:31+00:00
- Post Title: 

I inspired you to make a new program!    

Well, I have two more huge files to send, but since it is too risky for it to take too long, I will upload them individually zipped.  I have two in a zip folder right now, but that is 1.5 Gb.  Too risky IMO.

Uploading right now.  I'll let you know when its done. 


Oh no!  Webspace is sucking again!      Maybe I should be realistic.  I ain't ever gonna get those files.  Cause they are too big and my webspace sucks.
## Post #22
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-10-31T18:37:41+00:00
- Post Title: 

Well, different dat file formats doesn't mean I can;t figure them all out!
## Post #23
- Username: TheDyingInformant
- Rank: veteran
- Number of posts: 89
- Joined date: Mon Sep 01, 2003 8:41 am
- Post datetime: 2003-11-04T01:46:34+00:00
- Post Title: 

Ok, my webspace is back in action now.  Uploading vox (again) now.  Will be done later (and I hope you don't mind if I post again to let you know).

And as far as the formats being tricky go, I was hoping you would have come across other tricky games too, but, I don't know.  This game maybe was designed to be 'hack proof' or something.  I'm not going to tell you all MGS fans who want the files depend on YOU guys, but I really have not found any other places that could be of help to me.  If you could point me in the right direction, while you keep working on your program, and trying to figure out the formats if you want, that would be great.  Once I get the files uploaded, you can get them, but they may still seem difficult or impossible to figure out.  Which sure sucks.
## Post #24
- Username: TheDyingInformant
- Rank: veteran
- Number of posts: 89
- Joined date: Mon Sep 01, 2003 8:41 am
- Post datetime: 2003-11-05T04:56:07+00:00
- Post Title: 

[FINALLY! (739MB)](http://211.28.233.228:8080/rkpellagirl/files/vox.zip)

Uploading the next one.  It will be done by the end of tomorrow or so.  So I'll edit this post to include it.  Just be sure to check late tomorrow, or early Thursday.
## Post #25
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-11-05T10:00:40+00:00
- Post Title: 

Ok, donwloading it. I quickly fixed me that DownScanner I was talking about. Much to my surprise, it downloads the file faster than Internet Explorer. Anyway, the program is not of much use with this file, because it is zipped and I cannot look at the dat file yet, but it may come in handy in the future.
## Post #26
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-11-06T08:12:59+00:00
- Post Title: 

damn    error in zip file...downloading again...(last time took me 22 h)  

Btw : this is a screenshot of that downscanner as it downloads the file again....
## Post #27
- Username: TheDyingInformant
- Rank: veteran
- Number of posts: 89
- Joined date: Mon Sep 01, 2003 8:41 am
- Post datetime: 2003-11-06T09:46:57+00:00
- Post Title: 

Heh, pretty cool.  So you can sort of see some of the file - maybe enough to find the format without getting the whole file?  Neat idea.

Error in zip file huh? Hmm.... I don't know why.... You can probably get a download accellerator.  I'm really sorry about this.  They are HUGE files, I can not help it.  It will be even bigger on your hard drive too.  I hope the eventual result is something will catch your eye and you go 'AHA!' and figure out the format.     Maybe not directly, but maybe you find a format out for a similar game's format, leading you to know how to figure out this game.  Like other games use .dat format I notice, but as you said, that just stands for 'data'.  The formats can be totally different program to program.

The good news is the last file!  Well, I have a small one, but I don't think its important.  I could send it some other time.  Would be fast.  Its' only KB.  For now, another WHOPPER.  So you can get it when you're ready.

[DEMO.DAT (787MB)](http://211.28.233.228:8080/rkpellagirl/files/demo.zip) 

If it is similar to MGS1 on PS with PSound extractor, this would be all the audio for the cutscenes.  Where vox.dat should be all the rest of the dialog.  And I forget what file is sound fx.

Good luck.  And be sure to let me know if I should look for other files/folders that may contain something with more useful/crackable information in it.
## Post #28
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-11-08T10:08:06+00:00
- Post Title: 

Bloody @$@#$#@$@#@$#@ 

The demo.zip is okay, BUT THE VOX.ZIP still has that error. SO, it's not my downloading that corrupted it. It's probably during the upload that the wrong byte was saved. Where's PKZipFIX when you need it. Come to think of it, if I knew which byte was corrupted, I might simply replace it with all other combinations, 0-255, and only one would work....the right one...Hmm.....
## Post #29
- Username: TheDyingInformant
- Rank: veteran
- Number of posts: 89
- Joined date: Mon Sep 01, 2003 8:41 am
- Post datetime: 2003-11-08T12:12:23+00:00
- Post Title: 

Hmm... might I need to upload it again?  It was uploaded while my webspace was s***, maybe problems occurred.  Then my space got all reliable on me, and I proceeded to upload demo.dat which you say is ok.

SO, I will surely do that tomorrow. Holy crap, its 4am.  Guess I should go.  I'll be lucky to get up pre-noon...

And hey, if you have any probs figuring these files out, there has got to be some things you could still get from me. Either form the same game, or from PSound with the MGS1 CDs.  I can extract the audio files, tho I think it saves them to wav, but if the games were made similarly, there might be some hints there.  I have no idea.  If you think of any further ways I can be of help, or any bribes you would accept if doing it for free doesn't seem interesting, be sure to let me know, ok?

Cause you have no idea how much this would mean to me.  And as you saw, other fans would love this support as well.
## Post #30
- Username: TheDyingInformant
- Rank: veteran
- Number of posts: 89
- Joined date: Mon Sep 01, 2003 8:41 am
- Post datetime: 2003-11-10T01:22:26+00:00
- Post Title: 

OK, lets try this again, shall we?  

[VOX.ZIP](http://211.28.233.228:8080/rkpellagirl/files/vox.zip)

I hope its alright now. Nothing went wrong this time, so it should be ok, unless its the ZIPPING process that was screwy
## Post #31
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-11-10T23:13:57+00:00
- Post Title: 

Ok downloading it...see if this works.   

edit: omg, the download broke, your url is not accessible...
## Post #32
- Username: TheDyingInformant
- Rank: veteran
- Number of posts: 89
- Joined date: Mon Sep 01, 2003 8:41 am
- Post datetime: 2003-11-13T08:38:55+00:00
- Post Title: 

This webspace ain't too reliable hmm... what else can I do?  My very reliable shaw webspace (where you saw my pictures) is only 10MB, and its more than half full.

Is there some other way to send it? P2P program or something???
## Post #33
- Username: TheDyingInformant
- Rank: veteran
- Number of posts: 89
- Joined date: Mon Sep 01, 2003 8:41 am
- Post datetime: 2003-11-18T20:57:13+00:00
- Post Title: 

What's your status with getting this file?  Is there anything I can do to help?  This is my second time uploading it - I don't know what else to do.   Let me know what else, if anything I can do, besides wait another 6 months.
