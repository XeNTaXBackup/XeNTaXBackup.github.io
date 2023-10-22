## Post #1
- Username: Happeh
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Sep 05, 2004 11:23 am
- Post datetime: 2004-09-05T03:28:05+00:00
- Post Title: Error viewing Sacrifice WAD files

Hi. I tried to use MultiEx to view WAD files for the game Sacrifice. I choose open, change the file type to Sacrifice Wad, then click on one of the wad files. I receive the error message

dll not valid    (File Path)/Plugins\Wad\Sacrifice.dll

What should I do?

Thanks
## Post #2
- Username: Happeh
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Sep 05, 2004 11:23 am
- Post datetime: 2004-09-11T15:26:47+00:00
- Post Title: Error viewing Sacrifice WAD files

Helloooooooooooooooooooooooo.

Anybody home? Project still being maintained?
## Post #3
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-09-11T17:22:03+00:00
- Post Title: Error viewing Sacrifice WAD files

Is the plugin in the plugin directory?

Plugins are getting a major revamp.  So I don't know how much help you'll get.
## Post #4
- Username: Happeh
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Sep 05, 2004 11:23 am
- Post datetime: 2004-09-12T04:15:26+00:00
- Post Title: Error viewing Sacrifice WAD files

THe sacrifice dll is in plugins/wad folder

it says size on disk 64 kb so it must be a real dll
## Post #5
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-09-12T04:25:18+00:00
- Post Title: Error viewing Sacrifice WAD files

hmmm... my dll is only 49Kb
## Post #6
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-09-21T06:21:27+00:00
- Post Title: Error viewing Sacrifice WAD files

Oh well

It was worth a try
## Post #7
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-09-21T09:17:57+00:00
- Post Title: Error viewing Sacrifice WAD files

Look, you got a response, we are not monitoring these boards every minute of the day, naturally, as we DO have WORK to do. And sometimes we would like to respond, but can't at the time we read it. Then sometimes we forget to answer at all. Sorry 'bout that. 

The project is absolutely still maintained. 

The error you describe is known, I will see if I can upload a quick fix here. 

Meanwhile, as Rahly said, the plugin system is rebuild, so in the future better plugins are expected to surface.
## Post #8
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-09-21T09:31:46+00:00
- Post Title: Error viewing Sacrifice WAD files

Here's the correct dll, overwrite the dll in the plugin/wad directory (sacrifice.dll)
[Sacrifice.zip](https://xentaxbackup.github.io/file/73_Sacrifice.zip)
## Post #9
- Username: Happeh
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Sep 05, 2004 11:23 am
- Post datetime: 2004-09-25T16:48:48+00:00
- Post Title: Error viewing Sacrifice WAD files

Installed the new dll and it works. I can open the WAD and view the file list.

How do I know what I am looking at? Is there a file description for Sacrifice WAD's somewhere? Am I looking at texture files or model formats or sound or music or.......

When I click on a file within the models.wad, I see a small window pop up with what looks like a text representation of a binary file. I want to look at the textures or the models the same way a program like WinMPQ can open and show the textures and models for warcraft 3.

Is this possible for the Sacrifice game? Am I missing something obvious?

Thanks
## Post #10
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-09-25T21:06:36+00:00
- Post Title: Error viewing Sacrifice WAD files

At the moment, the purpose of multiex commander is to extract files from game archives.  Not provide support for whats in the archives, unless perhaps they are another archive.  Although, this could change in the future.  The bigger problem, is that we don't actually own a lot of these games, so other people send us "PARTS" of the files, in an attempt to extract them, we for the most part have no idea what are in the files, which makes it hard to know what your looking at.

Your best bet is to guess, or maybe extract and try them with various programs?
## Post #11
- Username: Crass Spektakel
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-09-28T07:03:20+00:00
- Post Title: Error viewing Sacrifice WAD files

> Reply from Happeh
>
> Hi. I tried to use MultiEx to view WAD files for the game Sacrifice. I choose open, change the file type to Sacrifice Wad, then click on one of the wad files. I receive the error message

dll not valid    (File Path)/Plugins\Wad\Sacrifice.dll

What should I do?

Thanks

Just tried the 49kb-dll but it still doesn't work: DLL Plugin not valid: C:\PROGRAMME\...Sacrifice.dll

I even deleted it and let it autoupdate.

Maybe its my real old OS, Win98SE?

Mr.Mouse wrote 
> Here's the correct dll, overwrite the dll in the plugin/wad directory (sacrifice.dll) but I somehow missed a link or something to click at, I even greped through the HTML-Source, no Link
## Post #12
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-09-28T13:40:25+00:00
- Post Title: Error viewing Sacrifice WAD files

> Reply from Crass Spektakel
>
> Happeh wrote:Hi. I tried to use MultiEx to view WAD files for the game Sacrifice. I choose open, change the file type to Sacrifice Wad, then click on one of the wad files. I receive the error message

dll not valid    (File Path)/Plugins\Wad\Sacrifice.dll

What should I do?

Thanks

Just tried the 49kb-dll but it still doesn't work: DLL Plugin not valid: C:\PROGRAMME\...Sacrifice.dll

I even deleted it and let it autoupdate.

Maybe its my real old OS, Win98SE?

Mr.Mouse wrote Here's the correct dll, overwrite the dll in the plugin/wad directory (sacrifice.dll) but I somehow missed a link or something to click at, I even greped through the HTML-Source, no Link

1. make sure you have the latest MultiEx Commander
2. make sure you don't have a sacrifice.dll in the windows system32 dir

3. You must register at this forum to be able to download stuff. Including that dll.
## Post #13
- Username: Happeh
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Sep 05, 2004 11:23 am
- Post datetime: 2004-10-03T16:51:10+00:00
- Post Title: Error viewing Sacrifice WAD files

Rahly: 

Ya I thought about extracting files and checking them. The problem is there is a file name only. I have to add extensions like .jpg or .mdx to the files to see if I can open them. Tedious does not even begin to describe the job. .jpg .bmp. .tga .tff  .mdx etc etc etc etc. 

Crass Spectakell:

There was something wrong with the forums or my browser. The first time I looked for the new dll, there was no link anywhere. I looked all over. Then I returned to this thread and for some reason the download link was there this time. Did you ever get the file?
## Post #14
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-10-03T20:25:16+00:00
- Post Title: Error viewing Sacrifice WAD files

> Reply from Happeh
>
> Rahly: 

Ya I thought about extracting files and checking them. The problem is there is a file name only. I have to add extensions like .jpg or .mdx to the files to see if I can open them. Tedious does not even begin to describe the job. .jpg .bmp. .tga .tff  .mdx etc etc etc etc.

Unfortunately, we don't have the extensions as well, we would have to look at every file individually as well.  if you have a unix system, you can try using the "file" command, which might tell you a lot more information if it was a standard type of file.
## Post #15
- Username: Ashur
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Feb 08, 2006 6:54 pm
- Post datetime: 2006-02-08T11:07:20+00:00
- Post Title: Error viewing Sacrifice WAD files

the sacrifice WAD files all contain sound files

i cant open them though

they dont have a file extension

when extracting "sfx_english.wad" i get many folders with files without any extension in them

an example: one of the folders is called "necr", i zipped it: [http://members.aon.at/mywebspace/necr.zip](http://members.aon.at/mywebspace/necr.zip)
it contains the sounds of the creature named "NECRYL"

please help me opening this file format !
## Post #16
- Username: Dinoguy1000
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2006-02-15T15:00:57+00:00
- Post Title: 

Well, for now, you might want to try a Google search. I guarantee that someone has written a tool to automatically add the appropriate extension, not because I've seen it, but because the WAD archives are so well known.

In the meantime, I believe that Mr.Mouse is working on a feature in the BMS scripting engine to allow you to automatically add such things... but don't quote me on that.
## Post #17
- Username: Ashur
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Feb 08, 2006 6:54 pm
- Post datetime: 2006-02-15T22:36:47+00:00
- Post Title: 

look at [http://sacrificeplanet.net/modules.php? ... opic&t=823](http://sacrificeplanet.net/modules.php?name=Forums&file=viewtopic&t=823)
and tell me what you think (my forum name is grakkus)

i cant find out which file format these soundfiles are...
## Post #18
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-03-10T15:16:00+00:00
- Post Title: 

I can write an converter for these files kinda easly,
just tell me if you need it, or if you have found a tool that allready does this.
## Post #19
- Username: Ashur
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Feb 08, 2006 6:54 pm
- Post datetime: 2006-03-10T16:11:56+00:00
- Post Title: 

Strobe, i need this! can u convert the sound files from the WAD-archive to sound files a normal person can play? (wav, mp3, or whatever)
## Post #20
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-03-10T16:55:37+00:00
- Post Title: 

I have absolutely no idea if the converter works, but i did it by a fast analyzation of the audio files, and it SHOULD work. but the 
only way to know is to test it througly.

so, please go ahead, and tell me if it works, or if there are any errors.

[http://jaedernaub.ath.cx](http://jaedernaub.ath.cx)

Grab v1.8.2f

First you do is go into Optionscreen , make sure "Sacrifice PCM" is
ON, and "Jaeder Naub naming" is OFF! if you are converting 
single files. also, make sure Nestling Skip is OFF.  (else it wont detect this file)

after all this is set up, you can start converting how much you like.
Jaeder Naub naming must be set to off because it will otherwise name
the files after where they are found, and if you convert single files
they will all have the same name, and overwrite eachother when converting a new one. with this option OFF it will create a total random number name for the file instead eliminating the chances for overwriting.

hope this makes any sense =o

any trouble, just post here, or Pm , take care!

also keep in mind that there are nowhere stored in the files how long the
sample data is, so ive made some stupid checks to try to determine the correct file sizes, so there might be a chance of corrupt wave files when
converting.
## Post #21
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-03-10T17:00:10+00:00
- Post Title: 

maybe it's time to make a new naming option...

like...original file name + something...so its easier to find when converted =o ...but thats a later task.
## Post #22
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-03-10T17:28:51+00:00
- Post Title: 

I belive the easiest way around would be to load the whole WAD file into
jaeder naub with Sacrifce PCM selected. then it should go through
the whole archive and convert all the sounds it finds, without having to
single click them.

(i hope) ...i dont have the WAD file so i havent tested it :///


GAAAAh, after compiling that version ive found a Length Header in the 
audio files. well well....:X ill add it later. *giggle*
## Post #23
- Username: Ashur
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Feb 08, 2006 6:54 pm
- Post datetime: 2006-03-10T20:13:06+00:00
- Post Title: 

amazing!

it works! i'll upload the whole WAD file soon, so you can try to make the names useful.

thanks from me and the all other freaks from [sacrificeplanet.net](http://sacrificeplanet.net/index.php)
## Post #24
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-03-10T20:54:47+00:00
- Post Title: 

glad to be of any help! =)

and besides...im learning new stuff here =o
## Post #25
- Username: Ashur
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Feb 08, 2006 6:54 pm
- Post datetime: 2006-05-05T19:31:25+00:00
- Post Title: 

i'm back, sorry i was offline that long. i'd really appreciate if u can resume your great work on this sound extractor.

u asked for the whole WAD file... it is quite big, and i can only host 20 MB.

contact me on ICQ or MSN, i could rar the file and split it up, then send it to you... or maybe i'll just set up an ftp server for u to connect to (with LeechGet maybe? )

send a PM if thats ok with u!

liebe grÃ¼ÃŸe,
ashur
## Post #26
- Username: Ashur
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Feb 08, 2006 6:54 pm
- Post datetime: 2006-05-21T13:27:42+00:00
- Post Title: 

the dialogues are stored in the map files (eg "(et01).scp")
scapex calls them Samples, MultiEx Commander can open them, but not without errors on extracting. (\[Lt0\SAMP\*dialogues*)

most of those files can be converted with JN, but only the first 2 seconds or so are working !


edit: only the map files in "C:\programfiles\Shiny\Sacrifice\maps\Campaign\Sacrifice" contain Samples (=dialogues)
edit: "Samples are simply sound files that you create or input into the scenario. They have to be in 8 bit wave format. It doesn't really matter whether they are in mono or stereo and the quality (11,025hz/22,050hz/44,100hz,etc) is up to you." found at [strategyplanet.com](http://www.strategyplanet.com/sacrifice/sacmaps/Scapex.htm)
## Post #27
- Username: Ashur
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Feb 08, 2006 6:54 pm
- Post datetime: 2006-06-01T05:34:09+00:00
- Post Title: 

works fine now, with your settings. thanks again
