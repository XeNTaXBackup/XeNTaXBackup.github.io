## Post #1
- Username: Teryal5532
- Rank: beginner
- Number of posts: 27
- Joined date: Wed May 11, 2011 7:10 am
- Post datetime: 2011-09-08T01:21:59+00:00
- Post Title: /PC/ Hard Reset (DEMO) files

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2011-09-08T08:02:44+00:00
- Post Title: /PC/ Hard Reset (DEMO) files

simply unpack, bin = zip
## Post #3
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2011-09-08T09:26:49+00:00
- Post Title: /PC/ Hard Reset (DEMO) files

they're password protected
## Post #4
- Username: rengareng
- Rank: veteran
- Number of posts: 131
- Joined date: Fri Feb 18, 2011 5:23 pm
- Post datetime: 2011-09-08T16:50:39+00:00
- Post Title: /PC/ Hard Reset (DEMO) files

The contents of this post was deleted because of possible forum rules violation.
## Post #5
- Username: Falo
- Rank: advanced
- Number of posts: 78
- Joined date: Fri Oct 23, 2009 8:29 pm
- Post datetime: 2011-09-08T17:12:15+00:00
- Post Title: /PC/ Hard Reset (DEMO) files

the steam demo version pw is "rNPXgxj12A#Ian@!K5qt%JSNx2I"
## Post #6
- Username: tsl16b
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Dec 27, 2010 8:16 pm
- Post datetime: 2011-09-09T14:54:53+00:00
- Post Title: /PC/ Hard Reset (DEMO) files

> Reply from Falo
>
> the steam demo version pw is "rNPXgxj12A#Ian@!K5qt%JSNx2I"
Thank you, Falo. PW is correct, and it's working with the standalone demo too.
## Post #7
- Username: DarkAngel
- Rank: n00b
- Number of posts: 19
- Joined date: Sun Jan 23, 2011 12:12 pm
- Post datetime: 2011-09-14T02:13:58+00:00
- Post Title: /PC/ Hard Reset (DEMO) files

Help to find the password for full version games Files: [http://www.multiupload.com/27DDRLMHOF](http://www.multiupload.com/27DDRLMHOF)
## Post #8
- Username: DarkAngel
- Rank: n00b
- Number of posts: 19
- Joined date: Sun Jan 23, 2011 12:12 pm
- Post datetime: 2011-09-14T06:08:43+00:00
- Post Title: /PC/ Hard Reset (DEMO) files

password for full version "9dU36jSJ@h265^k0b1!jrx*945F1"
## Post #9
- Username: lezek
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Mar 27, 2009 2:36 am
- Post datetime: 2011-09-16T17:57:39+00:00
- Post Title: /PC/ Hard Reset (DEMO) files

Can you tell me how you got the password?
## Post #10
- Username: rengareng
- Rank: veteran
- Number of posts: 131
- Joined date: Fri Feb 18, 2011 5:23 pm
- Post datetime: 2011-09-17T09:07:08+00:00
- Post Title: /PC/ Hard Reset (DEMO) files

generally password is found from exe of game. search for that in it you will see it is in same place for demo and full. You can get also by dissamblying game exe and finding password insertion command.
## Post #11
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-04-06T16:46:13+00:00
- Post Title: /PC/ Hard Reset (DEMO) files

To update this, can anyone get the password from the new Hard Reset: Extended Edition?
* snip *
Thanks!
## Post #12
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-04-06T19:27:41+00:00
- Post Title: /PC/ Hard Reset (DEMO) files

> Reply from AlphaTwentyThree
>
> To update this, can anyone get the password from the new Hard Reset: Extended Edition?
* snip
Thanks!

PWD: 9dU36jSJ@h265^k0b1!jrx*945F1
## Post #13
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-04-06T19:42:25+00:00
- Post Title: /PC/ Hard Reset (DEMO) files

lol, thanks.
## Post #14
- Username: tsl16b
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Dec 27, 2010 8:16 pm
- Post datetime: 2012-05-16T09:46:29+00:00
- Post Title: /PC/ Hard Reset (DEMO) files

Retro Sprint (no head bobbing)
A do-it-yourself minimod for the game Hard Reset (all versions)
No Squirrel bytecode decompilation required


1. Extract file data\scriptsbin\gameplay\base_templates\models\m_camera.nut
- This compiled Squirrel script file can be found in data_10_scripts.bin, which is a password encrypted ZIP file. Look for ZIP password of your game version here in this thread.

2. Hex edit file
- Find string sprint (case sensitive), and then find the second occurence of it. For Hard Reset Demo version it will be at 071F.
- Replace sprint to run. This will cause the file size to be 3 bytes less. Seems unbelievable, but the file will remain to be a working script after that.
- Position your cursor on the letter r of run and step 4 bytes left, there's a 06 byte value. Replace this to 03. (String length of sprint was 6 bytes, we need to update this to 3 since run is shorter.)
- Save the file and quit hex editor.

3. Put edited m_camera.nut file into data\scriptsbin\gameplay\base_templates\models folder of your installed game
- Game will find and use this file instead of its original packed in data_10_scripts.bin.
## Post #15
- Username: theBloodone
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Jun 10, 2012 8:22 pm
- Post datetime: 2012-06-17T10:39:24+00:00
- Post Title: /PC/ Hard Reset (DEMO) files

Anyone know if there is a way to open the game's archives or it's impossible?
## Post #16
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-06-17T15:02:24+00:00
- Post Title: Re: /PC/ Hard Reset (DEMO) files

they have already told that they are zip files, about what other archives you are referring?
