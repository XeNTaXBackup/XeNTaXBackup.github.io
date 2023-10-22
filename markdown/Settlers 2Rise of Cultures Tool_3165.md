## Post #1
- Username: streem
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-09-24T17:22:06+00:00
- Post Title: Settlers 2:Rise of Cultures Tool

Ok I created a new thread for the tool to keep it clean.
Discussion about the format etc. can be found in [viewtopic.php?f=21&t=3142](http://forum.xentax.com/viewtopic.php?f=21&t=3142)

Current version: v1.11 BETA
CHANGES:
v1.11
- FIXED: compression bug

v1.10
- FIXED: compression should now work properly

v1.01
- FIXED: decryption failed when filename contained capital letters
- FIXED: you can drag&drop files now

v1.0
- supports 10th Anniversary files as well
- supports encryption

Both tools can decrypt 10th Anniversary and Rise of Cultures files, but while AdKEd encrypts normal files to RoC files, DnGEd converts them to 10th A. ones.

Compression doesn't work properly yet, in fact files get bigger.


OH AND CAUTION, THE TOOL OVERWRITES THE INPUT FILE, SO ALWAYS COPY THE FILES YOU WANT TO DECRYPT INTO A WORKING FOLDER.

EDIT: If you want to decrypt a whole directory, you can use a batch script like the following for the moment:

```
FOR %%i IN (*.*) DO AdKEd %%i
```

You just need to put this into a text file, rename it "go.bat" and run it. 
[S2Editors.rar](https://xentaxbackup.github.io/file/1771_S2Editors.rar)
## Post #2
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-09-25T13:29:57+00:00
- Post Title: Settlers 2:Rise of Cultures Tool

Ok here is a preliminary encrypter. It is a hacked version of the encrypter for S2:DNG.
Just in case I don't have the time to finish my own 

EDIT: In case of virus messages: I couldn't find anything bad in there, AntiVir & Co. normally cry wolf cause the exe is packed.
[AdKEnc.rar](https://xentaxbackup.github.io/file/1656_AdKEnc.rar)
## Post #3
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-12-02T22:18:41+00:00
- Post Title: Settlers 2:Rise of Cultures Tool

updated to v1.0
## Post #4
- Username: hunpatrik
- Rank: veteran
- Number of posts: 101
- Joined date: Tue Jan 05, 2010 4:21 am
- Post datetime: 2010-01-05T16:50:20+00:00
- Post Title: Settlers 2:Rise of Cultures Tool

Hello!
Now i use this tools and i make the hungarian translation for the game. I started with the ui.txt.
In most of the document i can use éáűúőóüöí characters, but some place i can't.
for example: line 169:
I can't write:
!Castle_tip_kurz   A főhadiszállás minden település szíve.
Only:
!Castle_tip_kurz   A fohadiszallas minden telepules szive.

other problem some place i can't modify or delete dthe german text like:
line 161:
!Cancel Tutorial    Abbrechen
if i edit/replace Abbrechen the file will corrupt.
or at line 139:
!CONNECTION_LOST  A kapcsolat megszakadt verloren
if i delet the verloren world the file will corrupt.

Can anyone give me some help, how can i solve the problem?
## Post #5
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2010-01-05T18:02:33+00:00
- Post Title: Settlers 2:Rise of Cultures Tool

First problem might be caused by using the wrong encoding.
Second one, no clue atm.
## Post #6
- Username: hunpatrik
- Rank: veteran
- Number of posts: 101
- Joined date: Tue Jan 05, 2010 4:21 am
- Post datetime: 2010-01-05T21:05:46+00:00
- Post Title: Settlers 2:Rise of Cultures Tool

thanks anyway
## Post #7
- Username: Servismann
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Jul 17, 2010 8:14 pm
- Post datetime: 2010-07-19T18:48:30+00:00
- Post Title: Settlers 2:Rise of Cultures Tool

Hi,

changes in encryption file size of 3 bits. Please advice how to solve this problem

using tools from the forum without coding into the Czech language
## Post #8
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2010-07-19T19:59:13+00:00
- Post Title: Settlers 2:Rise of Cultures Tool

don't understand what you mean.
strangely I can't even find the original source code anymore.
## Post #9
- Username: Servismann
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Jul 17, 2010 8:14 pm
- Post datetime: 2010-07-20T17:32:58+00:00
- Post Title: Settlers 2:Rise of Cultures Tool

Use the tools if you have recommended to transfer back the resulting file has the same size as the original.

is only seen - "!Single Player" translation is "JEDEN HRAC"



Thank you for your help
## Post #10
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2010-07-20T18:36:14+00:00
- Post Title: Settlers 2:Rise of Cultures Tool

sry, I don't understand.
So you tried decrypting a file, translating it and then re-encrypted it, right?
What went wrong, any error messages?
## Post #11
- Username: Servismann
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Jul 17, 2010 8:14 pm
- Post datetime: 2010-07-20T18:57:04+00:00
- Post Title: Settlers 2:Rise of Cultures Tool

yes exactly

original file size after translation of 4039b and 4042b encrypted file size

change only the name "SINGLE" (6  letters and spaces) to "JEDEN " (6  letters and spaces)

no error message is not shown only the correct text  

correct text "JEDEN" wrong text "!Single"  WHY?

thanks
## Post #12
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2010-07-20T19:24:46+00:00
- Post Title: Settlers 2:Rise of Cultures Tool

Please post your files so I can try to reproduce it.
## Post #13
- Username: Servismann
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Jul 17, 2010 8:14 pm
- Post datetime: 2010-07-20T19:37:11+00:00
- Post Title: Settlers 2:Rise of Cultures Tool

I have the files you have you translated into English from German

 from this set, I tried to create a Czech translation
## Post #14
- Username: Simon
- Rank: mega-veteran
- Number of posts: 180
- Joined date: Mon Sep 21, 2009 12:41 am
- Post datetime: 2010-07-20T19:39:42+00:00
- Post Title: Settlers 2:Rise of Cultures Tool

Sorry for Off Topic. but JEDEN is not the German word for SINGLE 

You can translate it with ANY or better EVERY
## Post #15
- Username: Servismann
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Jul 17, 2010 8:14 pm
- Post datetime: 2010-07-20T19:42:07+00:00
- Post Title: Settlers 2:Rise of Cultures Tool

"JEDEN" is not German word but it's the Czech word for one player
## Post #16
- Username: Simon
- Rank: mega-veteran
- Number of posts: 180
- Joined date: Mon Sep 21, 2009 12:41 am
- Post datetime: 2010-07-20T19:45:13+00:00
- Post Title: Re: Settlers 2:Rise of Cultures Tool

Oh great one word means different things
## Post #17
- Username: Servismann
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Jul 17, 2010 8:14 pm
- Post datetime: 2010-07-20T19:57:00+00:00
- Post Title: Re: Settlers 2:Rise of Cultures Tool

I used these files

if the title is in English "Single Player" in Czech and it is "JEDEN HRAC"

disagrees only the number of letters instead of letters may be empty character?
[file.zip](https://xentaxbackup.github.io/file/3256_file.zip)
## Post #18
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2010-07-20T20:05:50+00:00
- Post Title: Re: Settlers 2:Rise of Cultures Tool

> Reply from Servismann
>
> change only the name "SINGLE" (6  letters and spaces) to "JEDEN " (6  letters and spaces)
it needs to be !SINGLE PLAYER	JEDEN HRAC
the first half with the ! must always be as it is.

!READY_CHECK_TOOLTIP	Bereit zum Starten
==>
!READY_CHECK_TOOLTIP	Ready to start
## Post #19
- Username: Servismann
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Jul 17, 2010 8:14 pm
- Post datetime: 2010-07-20T20:23:13+00:00
- Post Title: Re: Settlers 2:Rise of Cultures Tool

Thanks for the advice. I tried now. it works.
## Post #20
- Username: doki
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Dec 02, 2010 10:01 am
- Post datetime: 2011-08-12T08:11:25+00:00
- Post Title: Re: Settlers 2:Rise of Cultures Tool

I am unable to download the S2Editors.rar file in the first post (some issue with the server it says). Could you reupload it when possible please? I am unable to find the tool anywhere else ><
## Post #21
- Username: kokosak
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Aug 14, 2011 2:05 am
- Post datetime: 2011-08-13T18:38:32+00:00
- Post Title: Re: Settlers 2:Rise of Cultures Tool

AdKed.exe - Generic4_c.DWH
And the mew runtime compression is also suspissious ( hiding another virus? )
## Post #22
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2011-08-18T20:28:01+00:00
- Post Title: Re: Settlers 2:Rise of Cultures Tool

The "Generic" already says it: It's only compressed, no need to shit one's pants.
The tool works flawlessly.

Sorry but I'm kinda sick of that. MEW is a very simple compressor to reduce size and easy to unpack, there even is a ready-to-use decompressor tool: [http://www.cdw.de.vu/](http://www.cdw.de.vu/)
## Post #23
- Username: doki
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Dec 02, 2010 10:01 am
- Post datetime: 2011-08-19T18:34:39+00:00
- Post Title: Re: Settlers 2:Rise of Cultures Tool

Think I wasnt clear in my post, what I meant is : Whenever I try to download the tools (namely : S2Editors.rar) there is a problem with the download link (error varies from broswer used, for example chrome gets stuck at 122/129 kb, firefox simply states file link unexistant).

I was hoping I could have a mirror link so I could download the tools, or alternatively some help on why Im having trouble downloading (I have tried other files in xentax.com and no problem, and yes I have cleared my browser cache etc...)

Thanks for any help!
## Post #24
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2011-08-20T11:57:53+00:00
- Post Title: Re: Settlers 2:Rise of Cultures Tool

The contents of this post was deleted because of possible forum rules violation.
## Post #25
- Username: Fenris
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Mar 13, 2013 3:35 am
- Post datetime: 2013-03-13T01:06:12+00:00
- Post Title: Re: Settlers 2:Rise of Cultures Tool

EDIT : ok, i get it. I didnt encrypt with the already good filename.
For example, i used to encrypt my translated file like "info - translation.txt", then rename it to "info.txt".
The filename must be the correct one BEFORE encrypting it.

Thanks to you work !
_________

Hello,

I just used your tool to decrypt/encrypt some text files for the french translation of the S 10th anniversary.

I started to translate the info.txt, tested it and it worked well.
Then, with no particular reason, the game wont be able to launch anymore, and i had to replace the original files.

I carefully looked at my file, and saw nothing about missing characters, tabulations or returns...

DId you know a possible solution, or a tip i didnt tried ?
Is some special characters (like !?/ and other specila punctuation) messing the whole thing ?

FUrthermore, do you know how to change or gain access to the fonts of the game ? I tried to translate the intro.txt text, and it seems to not have the accentuated characters, so wont start the game...
The "controls.txt" file seems not be able to get the accents either, but can't tell accurately because of the previous mess with the info.txt file...

thanks for your help !
## Post #26
- Username: migglesnz1
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Sep 04, 2013 2:58 pm
- Post datetime: 2013-09-10T07:28:23+00:00
- Post Title: Re: Settlers 2:Rise of Cultures Tool

hey this may seem a stupid question but I would like to translate some more of the game so I can play it in English. so my question is how do I use/run the editor ?
