## Post #1
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2004-08-13T22:18:28+00:00
- Post Title: Driv3r

Hello

this is file *.img package for driver3(Ps2) game

please help me

thank you
## Post #2
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-08-14T06:46:28+00:00
- Post Title: Driv3r

> Reply from sajad
>
> Hello

this is file *.img package for driver3 game

please help me

thank you
Trying img tool for gta3.
## Post #3
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-14T07:53:39+00:00
- Post Title: Driv3r

THere's a font, a game config file (.ini) another config file and a large chunk before all that that I can't identify at first glance. Do you have more of these .IMG files? So we can compare?
## Post #4
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2004-08-14T13:12:37+00:00
- Post Title: Driv3r

this is one archive with 3.7gb large

email to you one file with 15mb from split this file (463kbsize)
## Post #5
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2004-08-14T14:27:43+00:00
- Post Title: Driv3r

Hi there,

Any chance that you could supply a piece of the file starting at offset 41504727 (or 2794FD7 in hex), maybe about 100kb would be good. This is because I estimate that this is the most probably location of the directory.

Through studying the piece of file you attached in the first post, I have determined that the entire archive is based around padding of size 2048 - ie every file that does not have a length of a multiple of 2048 will have null padding added to the end of it until it reaches a multiple of 2048 bytes.

I think there is 1 byte added at the beginning that shouldn't be there, maybe this was when the file was cut up

So the structure is...

```
4 - Unknown (maybe Directory Size?)
4 - Directory Offset?
4 - Size of first file

// for each file
X - file data
0-2047 - padding to a multiple of 2048 bytes


X - directory???

```


If you could supply the file piece I mentioned above, that would be most helpful. Thanks.

EDIT: It is also possible that the offset I gave you is the length of the archive. If this is so, maybe there is another file with the same name that contains the directory information. For example, if this archive is myFile.img and there is a file called myFile.dir or something similar, the other file might contain the directory information. Please check both these things please.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #6
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2004-08-14T20:11:52+00:00
- Post Title: Driv3r

this is file starting at offset 41504727
## Post #7
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2004-08-15T04:51:24+00:00
- Post Title: Driv3r

OK, I will take a look at it - thanks for the file 

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #8
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2004-08-15T10:41:44+00:00
- Post Title: Driv3r

Well i took a look, but I can't see any way of determining exactly where the files are - like there is no directory, and nothing that gives anything like file sizes. There must be a file in the same directory that contains the directory - look for a file with the same name as the archive, but with a different extension. The file will be pretty small, probably under 100kb in size. Are there any files like this?

For example, if the archive is driver.img, the file I am looking for would be driver.xxx where xxx is some other extension, such as .dir or .dat etc.

If there is something like this, then we can take a look at it. Otherwise, I can't see anything that can be done.

Sorry about the problems 

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #9
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2004-08-17T05:11:18+00:00
- Post Title: Driv3r

thank you for Comments
## Post #10
- Username: Moon
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu May 06, 2004 12:08 am
- Post datetime: 2004-08-18T00:20:40+00:00
- Post Title: Driv3r

I doubt companies that hate each other's guts (Rockstar/GTA <-> Reflections/Driver) would use each other's proprietary file formats.
## Post #11
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-18T00:35:56+00:00
- Post Title: Driv3r

Unless they aren't proprietary, and something they purchased from another company.
## Post #12
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2005-03-27T08:13:12+00:00
- Post Title: Driv3r

hello again

please see package driv3r ver pc

thanks.
## Post #13
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-03-27T13:12:55+00:00
- Post Title: Driv3r

Here are the specs

```
| Driver 3 *.gsd |
+----------------+

4 - Header (01KB)
4 - Number Of Files

// for each file
  4 - File Offset

4 - Archive Size?
X - Padding to multiple of 2048 bytes

// for each file
  4 - File ID?
  4 - Header Size
  4 - File Length
  4 - null
  X - Header (size of field = headerSize)
  X - File Data
  X - Padding to a multiple of 2048 bytes
```


And here is a script for you - just grab the compiled script that is attached to this post...

```
Get Header Long 0 ;
Get FNum Long 0 ;
For n = 1 to FNum ;
Get FO Long 0 ;
SavePos NextFile 0 ;
Get FS Long 0 ;
Math FS -= FO ;
GoTo NextFile 0 ;
Log "" FO FS 0 0 ;
Next n ;

```


WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #14
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-03-27T13:23:05+00:00
- Post Title: Driv3r

Hmm, it didn't attach - try here instead for the script.

WATTO
## Post #15
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-03-27T13:25:23+00:00
- Post Title: Driv3r

Still nothing...  - I think there is something wrong with the message board.

Anyway - get the script here --> [http://www.watto.org/xzistenz/gsd.bms](http://www.watto.org/xzistenz/gsd.bms)

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #16
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2005-03-27T19:20:45+00:00
- Post Title: Driv3r pc

hello mr watto

this is code open gsd file but :

1.incorrect file name
2.don't extract file: show message "run time error 9 subscrip out of range " after message close multiex

thank you
## Post #17
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-03-28T14:18:21+00:00
- Post Title: Driv3r pc

Mr Mouse will need to take a look at this.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #18
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-03-28T14:53:22+00:00
- Post Title: Driv3r pc

Download the new version (released today!) and email me for a serial code, Sajad. Then try again. I think the script is not working. I will need to take a look at it. 

Correction: it seems to work fine. 

Please use the new version of Multiex Commander... [http://multiex.xentax.com](http://multiex.xentax.com)

Correction 2: this format can't do import, although there's the ImpType Standard. There's not enough info.
## Post #19
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2005-03-28T20:08:38+00:00
- Post Title: Driv3r pc

hello

first :thanks from mr mouse for sent code

second : script work and open gsd file and don't show error message for extract file but extract file without correct file name and file type

please try again

thanks
## Post #20
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2005-03-28T20:13:26+00:00
- Post Title: Driv3r pc

i think files incorrect because me open package with raw and play
but files extracted not open with raw
## Post #21
- Username: DRAVEN
- Rank: advanced
- Number of posts: 74
- Joined date: Sun Oct 09, 2005 6:07 pm
- Post datetime: 2006-06-27T18:27:37+00:00
- Post Title: Driv3r pc

Please look at fixing this...
## Post #22
- Username: gamehead
- Rank: advanced
- Number of posts: 48
- Joined date: Sat Nov 17, 2007 4:11 am
- Post datetime: 2009-11-25T08:50:45+00:00
- Post Title: Driv3r pc

hi i'm trying to open a Game archive File it is the DRIVER3.IMG file on the PS2 Game Driv3r. Please note that I legally own this copy of this game and all I want to do is open this file and look inside for audio and music files and anything else cool. Im trying to extract the soundtrack and the sound effects and anything else cool from the PS2 game Driv3r (Driver 3) but I'm faced with about 5-6 files on the disc with a single large file on the disc named DRIVER3.IMG. I am trying to open this file and view its contents. windows shows it as a psudoarchive or something. the file is 3-4 gigs in size and can be found on the PS2 version of Driv3r. All I want to do is listen to the music and sound effects like the sound zones like in istanbul the singing churches and the disco club from Driv3r on my iPod w/o resorting to recording via the line out cables b/c I don't do game music that way. I have found a program called Game extractor but that program is unable to open the archive, it says no plugins exist for this archive so if anyone has that plugin or a link to one that would be awesome. any help that you can provide will be most useful and thank you very much I appreciate you taking the time to read this.
## Post #23
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-11-25T09:01:02+00:00
- Post Title: Driv3r pc

If you can use a filecutter to have us take a look at pieces of those large files, that would help. Check [http://www.xentax.com](http://www.xentax.com) for the tools pack that includes the FileCutter.
## Post #24
- Username: gamehead
- Rank: advanced
- Number of posts: 48
- Joined date: Sat Nov 17, 2007 4:11 am
- Post datetime: 2009-11-25T09:09:21+00:00
- Post Title: Driv3r pc

> Reply from Mr.Mouse
>
> If you can use a filecutter to have us take a look at pieces of those large files, that would help. Check http://www.xentax.com for the tools pack that includes the FileCutter.

Hello there Mr. Mouse. Iv'e tried to use file cutter but for some reason I cant get it to spit out the zip file that I need to send you. it jus doinks at me twice and thats it. what am i doing wrong? and what file snippit setting should I use? the 256, 512 or 1024 file size. I would post the entire file but Im sure you dont feel like downloading a 4GB file. whats going on with filecutter? i've downloaded it from the link provided in the forum rules section. Thanks alot. I'm
not sure how to thank ppl on here I heard you can do that.
## Post #25
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-11-25T09:17:42+00:00
- Post Title: Driv3r pc

No, get the FileCutter in the Tools pack 1.2 : [http://www.xentax.com/downloads/Xentax_ ... ck_1_2.zip](http://www.xentax.com/downloads/Xentax_Tools_Pack_1_2.zip)
Use 1024K. 

To thank people, look at their post, there is a *thank post* button to thank the author, next to the Profile button.
## Post #26
- Username: gamehead
- Rank: advanced
- Number of posts: 48
- Joined date: Sat Nov 17, 2007 4:11 am
- Post datetime: 2009-11-25T09:32:21+00:00
- Post Title: Driv3r pc

> Reply from Mr.Mouse
>
> No, get the FileCutter in the Tools pack 1.2 : http://www.xentax.com/downloads/Xentax_ ... ck_1_2.zip
Use 1024K. 

To thank people, look at their post, there is a *thank post* button to thank the author, next to the Profile button.

I tried that set of programs and it still does the same thing I load up the file where it says select file to cut and I browse to where I have the IMG file then i go to the output part and I've tried all of the snippit settings all of them give me this little blank message with nothing on it and an OK button and windows doinks at me. it does this twice then thats it and it doesnt spit out the file into the folder ive requested. I have copied the DRIVER3.IMG file to my HD so im not trying to do it from the game disc. whats going on with filecutter? Thanks.
## Post #27
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-11-25T09:58:51+00:00
- Post Title: Driv3r pc

Ok, I'll see if I can take a look at this later. How many bytes large are all the IMG files?
## Post #28
- Username: gamehead
- Rank: advanced
- Number of posts: 48
- Joined date: Sat Nov 17, 2007 4:11 am
- Post datetime: 2009-11-25T10:05:47+00:00
- Post Title: Driv3r pc

> Reply from Mr.Mouse
>
> Ok, I'll see if I can take a look at this later. How many bytes large are all the IMG files?

It's a single IMG file 3.82GB its DRIVER3.IMG ill show you what I see when I put the Driver3 PS2 DVD into my PC



the below pic is whats in the modules folder


if these images take up too much bandwidth 
I can replace them with just the URLs.
## Post #29
- Username: gamehead
- Rank: advanced
- Number of posts: 48
- Joined date: Sat Nov 17, 2007 4:11 am
- Post datetime: 2009-12-02T21:43:17+00:00
- Post Title: Driv3r pc

Here is another shot of the IRX file folder in a different view if that helps anything:
As you can see in the above pic theres another IMG file in there, IOPRP280.IMG. Im hoping this is like a reference or binary file that tells the PS2 where the resources are in the DRIVER3.IMG file.
I can email this file to someone to take a look at maybe someone knows what this is and if it has any relations to the DRIVER3.IMG file. all I need is an email address to send to. I dont know how else to send the larger img file and filecutter isnt working for me for some reason.
## Post #30
- Username: gamehead
- Rank: advanced
- Number of posts: 48
- Joined date: Sat Nov 17, 2007 4:11 am
- Post datetime: 2009-12-07T03:24:40+00:00
- Post Title: Driv3r pc

So has anyone else got any ideas on how to open this DRIVER3.IMG file? just checking in to see if there is any progress. i cant get FileCutter to work does anyone know why? if anyone can get the game on PS2 or an image of the game its the DRIVER3.IMG file. thats what im trying to open. so just checking in. Laterz.
## Post #31
- Username: gamehead
- Rank: advanced
- Number of posts: 48
- Joined date: Sat Nov 17, 2007 4:11 am
- Post datetime: 2009-12-11T17:46:48+00:00
- Post Title: Re: Driv3r

> Reply from Mr.Mouse
>
> If you can use a filecutter to have us take a look at pieces of those large files, that would help. Check http://www.xentax.com for the tools pack that includes the FileCutter.

Mr. Mouse.
FileCutter doesnt work for me so I took drastic measures, I had to upload the driver3.img file on a file hosting site in 4 parts so you can take a look at it. you might be able to just DL the first part but be warned that each part is 1GB in size. Please let me know if you are OK with DLing this file then ill post the link(s) on here if that is OK. I have the other 4 parts all 1GB except the last one which is about 800 MB. 
Also I hope this whole thing isnt against the rules b/c all i'm trying to do is send you a piece of the file to analyze.
