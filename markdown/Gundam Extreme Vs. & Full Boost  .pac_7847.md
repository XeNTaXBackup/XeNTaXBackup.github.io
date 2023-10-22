## Post #1
- Username: Nigoli
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Mar 29, 2011 2:23 pm
- Post datetime: 2011-12-12T02:25:07+00:00
- Post Title: Gundam Extreme Vs. & Full Boost | *.pac

I currently have these files using a proper dump from my game. I was able to successfully unpack the PSARC files. But now I'm having trouble with certain things like PAC files. One for the EXVS.PSARC which unpacked is DATA00.PAC, and some of the bigger PAC files in stream.PSARC.

Thanks in Advance!
## Post #2
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2011-12-13T03:39:30+00:00
- Post Title: Gundam Extreme Vs. & Full Boost | *.pac

similar to Xbox360 Naruto Shippuden:Ultimate Ninja Storm 2
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-12-13T03:46:46+00:00
- Post Title: Gundam Extreme Vs. & Full Boost | *.pac

namco uses a near identical format in all thier games.
sc4 tekken idolmaster dbz naruto gundam time crisis they all use slight variations of the exact same format.
## Post #4
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2011-12-13T03:49:20+00:00
- Post Title: Gundam Extreme Vs. & Full Boost | *.pac

here is stream.PSARC's DATA.TBL file
## Post #5
- Username: stephanehl
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Dec 20, 2008 2:25 am
- Post datetime: 2011-12-14T19:26:06+00:00
- Post Title: Gundam Extreme Vs. & Full Boost | *.pac

Anyone can rip the music from this game....

Please any help....
## Post #6
- Username: alientech
- Rank: n00b
- Number of posts: 19
- Joined date: Sat Apr 03, 2010 8:23 pm
- Post datetime: 2013-04-04T09:15:04+00:00
- Post Title: Gundam Extreme Vs. & Full Boost | *.pac

How can I extract the EXVS.psarc ?
## Post #7
- Username: Nigoli
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Mar 29, 2011 2:23 pm
- Post datetime: 2014-02-06T12:01:48+00:00
- Post Title: Gundam Extreme Vs. & Full Boost | *.pac

Full Boost recently came out. And it seems to still use PAC files in stream.psarc. EXFB.psarc extracts a large file bigger than itself as DATA00.PAC.

I still can't figure out how to extract those .pac files.
## Post #8
- Username: Nigoli
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Mar 29, 2011 2:23 pm
- Post datetime: 2014-02-13T03:57:28+00:00
- Post Title: Gundam Extreme Vs. & Full Boost | *.pac

[http://m.gamer.com.tw/forum/C.php?page= ... =&keyword=](http://m.gamer.com.tw/forum/C.php?page=2&bsn=00109&snA=46959&bpage=0&subbsn=0&pagekey=%3Cype=&keyword=)

It seems like it's possible to extract from the compressed pac files for this game. This how they were able to determine what DLC Suits would come when the game was released.

I've tried other pac tools without any luck for compressed PNGs.
## Post #9
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2014-02-13T22:30:08+00:00
- Post Title: Gundam Extreme Vs. & Full Boost | *.pac

I checked out the patch for this game and found NTXB files in the PAC files. Game uses same format as TTT2 and Tekken Revolution.
## Post #10
- Username: Nigoli
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Mar 29, 2011 2:23 pm
- Post datetime: 2014-02-13T22:57:29+00:00
- Post Title: Gundam Extreme Vs. & Full Boost | *.pac

> Reply from howfie
>
> I checked out the patch for this game and found NTXB files in the PAC files. Game uses same format as TTT2 and Tekken Revolution.I'm seeing those myself in a hex editor. Does this mean these files aren't dumpable with a common tool?

I'm under the impression that DATA00.PAC is compressed even outside of EXFB.psarc. While stream.psarc seemed like there was no compression dumping .at3 files. DATA00.PAC is the only thing that is giving any problems up to this point for compressed image files.
## Post #11
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2014-02-13T22:58:10+00:00
- Post Title: Gundam Extreme Vs. & Full Boost | *.pac

PAC files are also easy, it's just:

starting at 0x10:
number of files + list of offsets + list of filesizes + data

I don't have the game but in the patch there is an NTP3 file in the second pac file and those are texture files used in TTT2 and TR.
If you find NDXR files in your game, models use TTT2 format.
If you find NDP3 files in your game, models use TR format.
There are no models in the patch, so I cannot help anyone at the moment.
## Post #12
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2014-02-13T23:19:13+00:00
- Post Title: Gundam Extreme Vs. & Full Boost | *.pac

BTW, if all you are interested in is music files, TTT2 and TR both use NUS3 files. Look up NUS3 in your PAC files. If they are there, then scroll down a little, you will see RIFF WAV files.

More audio files were also in PAMF if I recall right. Videos not sure of.

Anyways, if you PM me a link to the important files I'll see what I can do.
## Post #13
- Username: Nigoli
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Mar 29, 2011 2:23 pm
- Post datetime: 2014-02-13T23:24:16+00:00
- Post Title: Gundam Extreme Vs. & Full Boost | *.pac

[viewtopic.php?f=10&t=6474](http://forum.xentax.com/viewtopic.php?f=10&t=6474)
[http://leoheart.blog43.fc2.com/blog-ent ... ew_comment](http://leoheart.blog43.fc2.com/blog-entry-617.html#view_comment)

I tried looking for other tools that could do this but I haven't any luck, and that "unpac" tool seems to be down in the MediaFire links. I've tried multiple bms scripts with QuickBMS with no luck at all.

I'm not too interested in the models, rather just the compressed PNGs any other assets besides models is all I really want out of that file.

> Reply from howfie
>
> BTW, if all you are interested in is music files, TTT2 and TR both use NUS3 files. Look up NUS3 in your PAC files. If they are there, then scroll down a little, you will see RIFF WAV files.

I'll send something over through PM.
## Post #14
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2014-02-14T02:33:19+00:00
- Post Title: Gundam Extreme Vs. & Full Boost | *.pac

lmao, exact same format as TTT2. i'll have that file parsed soon. only music, sound, and video files you are interested in again?
## Post #15
- Username: Nigoli
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Mar 29, 2011 2:23 pm
- Post datetime: 2014-02-14T04:22:18+00:00
- Post Title: Gundam Extreme Vs. & Full Boost | *.pac

Just the PNGs would do nicely, any images. I know there's one that are compressed that can't be extract normally.

Thanks a lot for this.
## Post #16
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2014-02-16T03:54:20+00:00
- Post Title: Re: Gundam Extreme Vs. & Full Boost | *.pac

instructions:
1. Create a fresh, empty directory somewhere.
2. Put DATA00.PAC and xentax.exe inside this directory (not in C:\, I said A FRESH NEW DIRECTORY).
3. Right-click on xentax.exe and Run As Administrator (temporary files, folders, etc. need to be created and removed).
4. Wait an hour.
5. Browse DATA00 folder for files. _t are pure texture directories. Other folders contain other stuff.
[xentax.7z](https://xentaxbackup.github.io/file/7019_xentax.7z)
## Post #17
- Username: Nigoli
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Mar 29, 2011 2:23 pm
- Post datetime: 2014-02-16T11:08:27+00:00
- Post Title: Re: Gundam Extreme Vs. & Full Boost | *.pac

This tool is worked wonders for me. I've found everything I've wanted so far.
I wouldn't be surprised if it worked with the previous game, and the upcoming third installment coming out in the future.

I am forever grateful.
## Post #18
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2014-02-17T23:53:55+00:00
- Post Title: Re: Gundam Extreme Vs. & Full Boost | *.pac

lol, eww, the models use some kind of cell-shading type of shader that is hard to duplicate in modelers... probably not even worth doing them. i think that even i can paint textures like this lmao! looks like they were drawn using MSPAINT HAHAHAHAHAHHA!
