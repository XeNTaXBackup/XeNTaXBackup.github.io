## Post #1
- Username: DarkBolo
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Nov 23, 2010 3:00 am
- Post datetime: 2010-11-23T17:32:18+00:00
- Post Title: The Saboteur

Hi, I also tried to extract music from The Saboteur, but without any resoults.
If you have the music from alarm,sneak etc(not the ones in the car radio)

I am stuck at the moment when I unpacked .PCK files.
I am trying to convert extracted files with ww2ogg09 but I am getting
1 KB .OGG files always.
## Post #2
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2010-11-23T19:17:49+00:00
- Post Title: The Saboteur

Try this

```
ww2ogg input.wav --inline-codebooks --full-setup
```
## Post #3
- Username: DarkBolo
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Nov 23, 2010 3:00 am
- Post datetime: 2010-11-24T09:37:46+00:00
- Post Title: The Saboteur

But where should I tyoe this line?
I am  n00b at those extracting/converting stuff
## Post #4
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2010-11-25T15:57:00+00:00
- Post Title: The Saboteur

I wrote this up a little while ago, maybe it will help:

1. extract the ww2ogg.exe file (copy out of the ww2ogg09.zip)
2. right click the .exe, select Create Shortcut
3. right click the "Shortcut to ww2ogg.exe" file that's created, select Properties
4. Add --full-setup to the end of the Target field. For example, if it was originally:
"C:\Documents and Settings\Bozo\Desktop\ww2ogg.exe"
change it to:
"C:\Documents and Settings\Bozo\Desktop\ww2ogg.exe" --full-setup
5. Click OK to save the changes
6. Drag a wav onto the shortcut
## Post #5
- Username: DarkBolo
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Nov 23, 2010 3:00 am
- Post datetime: 2010-11-27T14:56:54+00:00
- Post Title: The Saboteur

OMG! It's working!
Thanks a lot man!
Is there a way to convert those files all at once?
## Post #6
- Username: Cryptonia
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Aug 20, 2009 12:11 am
- Post datetime: 2010-11-28T14:59:16+00:00
- Post Title: The Saboteur

> Reply from DarkBolo
>
> OMG! It's working!
Thanks a lot man!
Is there a way to convert those files all at once?

for in in bat

or u make a list with dir /b /s *.* >>file.bat

and u can edit the file with any editor and repleace the path with ur comand
## Post #7
- Username: DarkBolo
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Nov 23, 2010 3:00 am
- Post datetime: 2010-11-28T16:20:34+00:00
- Post Title: The Saboteur

Can you explain it more simple?

here are paths to files

F:\MSIc28ba.tmp\Sound       //////////////////////////////////////// -those wave files


C:\Users\Bolo\Desktop\ww2ogg09         ////////////////////////////////////////////   -ww2ogg
## Post #8
- Username: Cryptonia
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Aug 20, 2009 12:11 am
- Post datetime: 2010-11-29T02:43:39+00:00
- Post Title: The Saboteur

start
run
cmd
now u did the folow cd "path to dir"
now u tip in dir /b /s *.wav >>wavco.bat
and enter it


now u have in the dir a file called wavco.bat its include files after the folow example


path/audio.wav
path/audio2.wav

now u can go to find and repleace and repleace the path/ by ur comand from ww2ogg so thaht its looks for example


ww2ogg --fullsetup audio.wav
ww2ogg --fullsetup audio2.wav

u save the file and run it also the bat
## Post #9
- Username: DarkBolo
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Nov 23, 2010 3:00 am
- Post datetime: 2010-11-29T09:41:16+00:00
- Post Title: The Saboteur

Sorry, I don't get it...
It's very difficult. Maybe you can make screenshot guide?
## Post #10
- Username: DarkBolo
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Nov 23, 2010 3:00 am
- Post datetime: 2010-12-04T10:02:52+00:00
- Post Title: The Saboteur

Can anyone?
## Post #11
- Username: mauzerX
- Rank: advanced
- Number of posts: 57
- Joined date: Thu Jul 01, 2010 8:48 pm
- Post datetime: 2010-12-04T11:18:25+00:00
- Post Title: The Saboteur

It's simple,copy all files(ww2ogg.exe,*.RIFX,packed_codebooks.bin,RIFX.bat) in one dir
RIFX.bat(batch(txt) file) with code:
for %%a in (*.RIFX) do ww2ogg.exe "%%a" --full-setup
*.RIFX - files from *.pck packs.
Run RIFX.bat,it will convert *.RIFX files all at once.
## Post #12
- Username: DarkBolo
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Nov 23, 2010 3:00 am
- Post datetime: 2010-12-07T12:44:38+00:00
- Post Title: The Saboteur

I need to convert those freaky WAVE format to OGG.
Can you make a tutorial with screenshots? PLS
## Post #13
- Username: deathkitten
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Jun 24, 2012 12:32 pm
- Post datetime: 2012-06-27T05:52:49+00:00
- Post Title: The Saboteur

For me it works, but only without the --full-setup for some reason. I don't know why, I definitely have all my ww2ogg.exe,WAVs,packed_codebooks.bin,and the WAV.bat I made in the same folder... Weird. But yeah, it works without the --full-setup.

(This was with fresh install of ww2ogg from [hcs64](http://hcs64.com/vgm_ripping.html))
