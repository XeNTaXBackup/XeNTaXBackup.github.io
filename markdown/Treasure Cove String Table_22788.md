## Post #1
- Username: DosGuy362
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Dec 31, 2019 6:03 am
- Post datetime: 2020-10-07T17:05:26+00:00
- Post Title: Treasure Cove String Table

Hi. I have tried to look into where the sprites are stored for Treasure Cove (Which is a DOS game, though, the computer seems to run it just fine on a Windows 7 Virtual Machine), and, at the moment, I have some leads. However, I decided to extract the Strings Table to see if there's anything interesting, and, to my surprise, there is. I just need some help in interpreting the Text File that's enclosed in the attachment (The Forum won't allow Text Files) in this post, as well as knowing how to proceed with this information. What's most interesting is the following: BNDL, FFNT, PMAP, SSND, and OTHR. Now, I think BNDL is a reference to a bundle (I could be wrong), FFNT refers to... a font, PMAP, SSND refers to sounds, and OTHR refers to other resources? Other interesting finds are RRGB, and a reference to WING32.DLL. Please correct me if I am wrong in any aspect of my analysis. I just need help in figuring out where the sprites are stored, and how to interpret the data that is presented in the output file. If it helps, I used [Executable's strings lister and replacer 0.2.3a](http://aluigi.altervista.org/mytoolz/exestringz.zip) to generate the Text File.

Thanks in advance, and I look forward to extract the sprites with your help.
[Treasure Cove Text.zip](https://xentaxbackup.github.io/file/18803_Treasure Cove Text.zip)
## Post #2
- Username: DosDude
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-10-07T21:59:14+00:00
- Post Title: Treasure Cove String Table

I guess that sprites are probably in those DAT files [https://imgur.com/a/piWQ7wG](https://imgur.com/a/piWQ7wG)
But you need to reverse engineer DAT file format first to get sprites.
## Post #3
- Username: DosGuy362
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Dec 31, 2019 6:03 am
- Post datetime: 2020-10-08T00:38:02+00:00
- Post Title: Treasure Cove String Table

Hm. That's probable. However, in Versions 1 and 2, the only DAT file is users.dat, and there's slight differences. For example, the screenshot you uploaded shows me that the version you looked at is the original one (the dead giveaway is the DAT files, and the TCV.BAT file in the screenshot). I noticed a difference in how the different versions are launched. The DOS or original (whichever term you want to use) uses COVE.EXE, file size: 153 kilobytes. Version 1 has Tcvwin32.exe, size 192 kilobytes, and Version 2 has the same executable name, size: 195 kilobytes. The differing file sizes tell me that something is up.

Versions 1 and 2 must have a different way to store sprite data, probably partially within the executable in the later two versions, since there's no TLD, DAT, or DLL files other than users.dat (I suspect the TLD to be a similar type of file to DLL files, since they appear to serve the same purpose). The executable is suspected to store sprite data, since there's an executable called TCVWIN32.EXE in Versions 1.1 and 2, and the primary reason I believe the executable to be holding the sprite data is due to the file size. On the CD roms of each Version (1.1 and 2), there's TCVWIN.EXE, and TCVWIN32.EXE. For Version 1.1, you can notice that there's a folder called TCVWINCD, which sounds like a starting point for that particular version, because it contains DLL files. For Version 2, there's a folder called DATA, which contains TLD files. I am going to enclose some download links, so you can see which versions have which structure, and I hope to rip the sprites from each version, if possible. Now, your DAT file theory still sounds plausible, since from what I can tell, DAT files are basically data files, if I am correct? If that's the case, data can probably include sprite data. What's your suggested plan of action to reverse engineer DAT files?

In the meantime, I will try my best to understand how sprites were stored in those days, and it's possible they partially stored the sprites and background information in the executables. If that's the case, how do I confirm this, or did I already confirm it? Just wondering. Thanks for having replied. Not too many people have replied to my inquiries on doing this.

Download links
[Version 1 link](http://www.sonamyfan362.com/TC.ISO), [Version 2 link](https://archive.org/download/treasure-cove-v2/Treasure%20Cove%21%20v2.0%20%281997%29%28TLC%29%5BPC-Mac%5D.iso).
## Post #4
- Username: DosGuy362
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-10-08T11:02:42+00:00
- Post Title: Treasure Cove String Table

Yeah, I was using other version, but now I have reverse engineered TLD archives from Treasure Cove 2.0
Here are tool and documentation
[https://github.com/bartlomiejduda/Tools ... ure%20Cove](https://github.com/bartlomiejduda/Tools/tree/master/NEW%20Tools/Treasure%20Cove)
It will allow you to extract data and analyze it.

For now I was only able to see font in Tile Molester [https://imgur.com/a/p5d9xdB](https://imgur.com/a/p5d9xdB)
It is view of one of the extracted files from TCV.TLD archive.


> the only DAT file is users.dat
I believe it is only save file as it appears only when you launch the game and 
it stores your profile name on the beginning [https://imgur.com/a/pYVQYV7](https://imgur.com/a/pYVQYV7)
I called my user "Lel" [https://imgur.com/a/DVrKmWT](https://imgur.com/a/DVrKmWT)

> DAT files are basically data files, if I am correct?
Yeah, probably.

> What's your suggested plan of action to reverse engineer DAT files?
I think that there are two possible way to proceed. First is to open files in hex editor or any graphics tools [viewtopic.php?f=33&t=15540](https://forum.xentax.com/viewtopic.php?f=33&t=15540)
and try to find image data manually.
Second is to open executable in dissasembler and try to understand source code.
You can use tools like IDA Pro, x32dbg, Sysinternal's ProcessMonitor etc.

You can also read some tutorials  how to do it here [viewtopic.php?f=29&t=22266](https://forum.xentax.com/viewtopic.php?f=29&t=22266)
(Expecially see "DOS Tutorials" section there)
## Post #5
- Username: DosGuy362
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Dec 31, 2019 6:03 am
- Post datetime: 2020-10-08T14:15:54+00:00
- Post Title: Treasure Cove String Table

Cool stuff! So far, such a great start! I want to try out your Python Script, but, I need to know how to operate it. Like, does it run straight from CMD, or does it require to be run through a Python Commandline?
## Post #6
- Username: DosGuy362
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Dec 31, 2019 6:03 am
- Post datetime: 2020-10-08T14:41:36+00:00
- Post Title: Treasure Cove String Table

There’s a strong chance that the sprites are in the BNDL files. I did a rapid Google Search, and although there’s nothing that I can find in regards to BNDL files in those days, the results suggest that they are bundle files. Sounds like another highly obvious place to search. I think that Version 1.1 refers to the BNDL files, and there seems to be a great amount of them. If I am wrong about this theory, what do bundle files contain?
## Post #7
- Username: DosGuy362
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-10-08T17:10:42+00:00
- Post Title: Treasure Cove String Table

> I want to try out your Python Script, but, I need to know how to operate it. Like, does it run straight from CMD, or does it require to be run through a Python Commandline?

You can just follow these steps to run it:
1. Download and install Python 3
2. (optionally) Download and install Wing IDE Personal Edition
3. Change paths at the end of the script
4. Run script in Python (cmd) or in Wing IDE if you like.

You can see some tuts here [https://www.google.com/search?client=fi ... hon+script](https://www.google.com/search?client=firefox-b-d&q=how+to+run+python+script)

> There’s a strong chance that the sprites are in the BNDL files.
After extracting files using my script you will see files with extension .ssnd, .lips, .ffnt etc.
Those are resource types defined at the beginning of TLD archives.
My guess would be that sprites are stored in .othr or .ao files, but I can't be sure, because
those files seems to be compressed.

> what do bundle files contain?
Structure of BNDL files is very simple.
I have added this file on github to help you understand file format
[https://github.com/bartlomiejduda/Tools ... format.txt](https://github.com/bartlomiejduda/Tools/blob/master/NEW%20Tools/Treasure%20Cove/BNDL%20file%20format.txt)

In my opinion, game reads those BNDL files to match file entries to some objects, levels etc.
## Post #8
- Username: DosGuy362
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Dec 31, 2019 6:03 am
- Post datetime: 2020-10-08T17:47:06+00:00
- Post Title: Treasure Cove String Table

I will try out the script, shortly. Thanks for letting me know how to run it. When I try out the script, I will try to read the OTHR files. I get the feeling that they are compressed, as I think it would make the game much larger than needed.
## Post #9
- Username: DosGuy362
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-10-09T13:20:12+00:00
- Post Title: Treasure Cove String Table

I have just discovered quickbms script for Treasure series made by aluigi
[http://aluigi.zenhax.com/bms/treasure_series.bms](http://aluigi.zenhax.com/bms/treasure_series.bms)
It should work with DAT files from Treasure Cove 1.0
and with few other games from The Learning company.
## Post #10
- Username: DosGuy362
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Dec 31, 2019 6:03 am
- Post datetime: 2020-10-09T23:33:32+00:00
- Post Title: Treasure Cove String Table

Thanks! Problem is, it spits out a lot of DAT files.
## Post #11
- Username: DosGuy362
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-10-10T08:46:12+00:00
- Post Title: Treasure Cove String Table

Yeah, it's common when file format is unknown.
But at least some graphics may be viewed [https://imgur.com/a/9WkIzMp](https://imgur.com/a/9WkIzMp)
## Post #12
- Username: DosGuy362
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Dec 31, 2019 6:03 am
- Post datetime: 2020-10-10T14:31:06+00:00
- Post Title: Treasure Cove String Table

That is so cool. How do you change the palette?
## Post #13
- Username: DosGuy362
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-10-10T14:35:58+00:00
- Post Title: Treasure Cove String Table

First you need to find the palette   

In TC 2.0 I would suggest to look in .rrgb files first,
but in TC 1.0 I have no idea where it could be stored.
## Post #14
- Username: DosGuy362
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Dec 31, 2019 6:03 am
- Post datetime: 2020-10-26T16:39:28+00:00
- Post Title: Treasure Cove String Table

Hi. It's been a while. Sorry to have taken so long to get back to you.

So, I ran the script last night, and, wow, oh wow. That's a lot of files to examine. But, I'll try to do what I can. One thing I noticed is that there is a LOT of .SSND files, and I highly doubt that all those files represent a sound effect. However, it's still probable that a few of them do contain some in-game sounds. (Just felt like bringing up something that's between a minor and major note.)

Now, as far as the .OTHR and .AO files are concerned, how do we know for certain that they are compressed, and how do we decompress them?
## Post #15
- Username: DosGuy362
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-10-26T17:55:55+00:00
- Post Title: Treasure Cove String Table

> Now, as far as the .OTHR and .AO files are concerned, how do we know for certain that they are compressed, and how do we decompress them?
I don't know this compression, but you can try to use com type scanner
[https://zenhax.com/viewtopic.php?t=23](https://zenhax.com/viewtopic.php?t=23)
## Post #16
- Username: DosGuy362
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Dec 31, 2019 6:03 am
- Post datetime: 2020-10-26T20:48:21+00:00
- Post Title: Re: Treasure Cove String Table

I think there's going to be a lot of investigation as to which DMP file is the correct one. Is there something that can help me rapidly narrow down which file may be the right one?
## Post #17
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-10-27T08:02:18+00:00
- Post Title: Re: Treasure Cove String Table

There is a method to sort dmp files from largest to smallest and check them in that order.
## Post #18
- Username: DosGuy362
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Dec 31, 2019 6:03 am
- Post datetime: 2020-10-27T13:22:01+00:00
- Post Title: Re: Treasure Cove String Table

Roger that. I also use PSPad Editor to do a search for Bitmap Signatures, as well.
## Post #19
- Username: DosGuy362
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Dec 31, 2019 6:03 am
- Post datetime: 2020-11-10T00:09:59+00:00
- Post Title: Re: Treasure Cove String Table

I find that it is taking a long time. Is there anything that we can do to speed up the process?
## Post #20
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-11-10T08:14:10+00:00
- Post Title: Re: Treasure Cove String Table

Don't know. Have you found anything interesting so far?
## Post #21
- Username: DosGuy362
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Dec 31, 2019 6:03 am
- Post datetime: 2020-11-10T16:09:09+00:00
- Post Title: Re: Treasure Cove String Table

Not much. I'll try to get a list ready of the stuff that I did find unusual.
