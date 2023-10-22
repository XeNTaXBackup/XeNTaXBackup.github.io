## Post #1
- Username: bAstimc
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Jan 23, 2007 4:33 am
- Post datetime: 2007-01-22T20:44:57+00:00
- Post Title: Tony Hawk's American Wasteland + Project 8

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Silver
- Rank: veteran
- Number of posts: 80
- Joined date: Sat Apr 30, 2005 8:25 pm
- Post datetime: 2007-01-24T08:35:51+00:00
- Post Title: Tony Hawk's American Wasteland + Project 8

Umm I'm confused.  You want to extract out of these archives or you already have the ability of doing so? What about the compression issue?

As far as the extensions you have... I have no idea 

Example: qb.pak.xbx (xbox) -> qb.pab.xbx (xbox)

qb.pak.wpc (PC) -> qb.pab.wpc (PC)

You will find these files related,  all qb.pak actually lookup files in qb.pab

Each listing in these files  (qb.pak.(extension pc or xbox))  is limited to 192 bytes per file. The end of these files are padded with 32bytes and contains one final entry @ 32 bytes Each goes something like this:

[4] Bytes - Some type of ID (you will find this constant in the qb files) (C405F5A7) it is more than likely what file to seek with directory: like THPS\DATA\qb.pab crc'd or something
[4] Bytes - This is a bit tricky to explain, we'll just call this offset for now *see below
[4] Bytes - File size
[4] Bytes -  CRC 32 (Complement 1s) of string (see below)
[4] Bytes -  Always Null?
[4] Bytes -  Another Type of CRC?
[4] Bytes -  Always Null?
[4] Bytes -  File Type? 
[chars] - String Null terminated
File is then just padded with null bytes.

*File Offset the first time it is listed this is the first offset. You can also do a number of files check like this: ((First Offset -64) / 192 ) You will find the first offset is the same size as the qb.pak.(extension pc or xbox) file size. 
It is really (file size + current offset) So the second offset is really (offset - file size) The final entry seemingly points to nowhere but it is the last  official file and contains no strings and is only 32 bytes.

*CRC in the qb files it will use the entire string above to crc. I've found the other non-qb ones (if large enough) only take the first extension like
worlds\worldzones\z_at\z_at_sfx_dat_xbx.qb.xbx
only worlds\worldzones\z_at\z_at_sfx_dat_xbx.qb is crc'd

Please note the non-qb files have a pattern that I have not guessed to how many files it lists before the string, some list multiples.

The data itself for the most part looks compressed, looks light like LZ77 or something like that. example : assume CH is given to start

4348FF4F4F534520414E207F4143434F554E54      |     CH.OOSE AN .ACCOUNT

CH (FF copy next 8 ) OOSE AN 7F (01111111) etc...

Not all of the text is compressed. I only looked briefly so sorry if I couldn't be much help
## Post #3
- Username: Silver
- Rank: veteran
- Number of posts: 80
- Joined date: Sat Apr 30, 2005 8:25 pm
- Post datetime: 2007-01-24T08:36:25+00:00
- Post Title: Tony Hawk's American Wasteland + Project 8

err double post
## Post #4
- Username: bAstimc
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Jan 23, 2007 4:33 am
- Post datetime: 2007-01-24T14:33:10+00:00
- Post Title: Tony Hawk's American Wasteland + Project 8

thx but better than nothing 
yea i havnt a ability of doing it
## Post #5
- Username: Silver
- Rank: veteran
- Number of posts: 80
- Joined date: Sat Apr 30, 2005 8:25 pm
- Post datetime: 2007-01-25T06:39:18+00:00
- Post Title: Tony Hawk's American Wasteland + Project 8

The contents of this post was deleted because of possible forum rules violation.
## Post #6
- Username: bAstimc
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Jan 23, 2007 4:33 am
- Post datetime: 2007-01-25T15:38:58+00:00
- Post Title: Tony Hawk's American Wasteland + Project 8

:O wow tuvm
how to dumb that shit 
i could do that for the levelfiles too 
but first i try to use those qbs as scripts ingame
## Post #7
- Username: Silver
- Rank: veteran
- Number of posts: 80
- Joined date: Sat Apr 30, 2005 8:25 pm
- Post datetime: 2007-01-26T21:37:59+00:00
- Post Title: Tony Hawk's American Wasteland + Project 8

> Reply from bAstimc
>
> :O wow tuvm
how to dumb that shit 
i could do that for the levelfiles too 
but first i try to use those qbs as scripts ingame

No you can't try them in game yet, was really just tossing them up to see if someone could easily spot the compression scheme.
## Post #8
- Username: bAstimc
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Jan 23, 2007 4:33 am
- Post datetime: 2007-01-26T22:02:42+00:00
- Post Title: Tony Hawk's American Wasteland + Project 8

mh yea i need to decompress them to use them ingame 
it works on the scheme like the previous games do
there exists instead of the pak file a compressed pre file which contains the qbs 
 mh i hope there will be someone who will be able to write such working pak-(de)compressor  it would be awesome
## Post #9
- Username: bAstimc
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Jan 23, 2007 4:33 am
- Post datetime: 2007-02-08T15:27:25+00:00
- Post Title: Tony Hawk's American Wasteland + Project 8

thats not easy
## Post #10
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2007-02-17T02:38:01+00:00
- Post Title: Tony Hawk's American Wasteland + Project 8

None of these files are compressed.

the qb files contains for me currently unknown data.
the WPC files seems to contain DDS texture data without headers.

and one of the WPC files also contains a bunch of WAVE files.
## Post #11
- Username: Silver
- Rank: veteran
- Number of posts: 80
- Joined date: Sat Apr 30, 2005 8:25 pm
- Post datetime: 2007-02-17T08:02:56+00:00
- Post Title: Tony Hawk's American Wasteland + Project 8

> Reply from Strobe
>
> None of these files are compressed.

the qb files contains for me currently unknown data.
the WPC files seems to contain DDS texture data without headers.

and one of the WPC files also contains a bunch of WAVE files.

Errm I said : "Not all of the text is compressed"

There is a bit of compression going on, this is throughout the archive though. Check qb.pab.wpc at around 0xFD1F8 or so.

As for the scripts... I haven't really tried anything else on them :\

Edit: here are a few of the compressed scripts.
[Compressedqb.pak.wpc(THAW).zip](https://xentaxbackup.github.io/file/1061_Compressedqb.pak.wpc(THAW).zip)
## Post #12
- Username: bAstimc
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Jan 23, 2007 4:33 am
- Post datetime: 2007-02-17T18:16:37+00:00
- Post Title: Tony Hawk's American Wasteland + Project 8

i also have from previous games the qbfiles ... from so called pre files .. it works the same way ..but the compression mode is just different

the script folders size is 11 mb with 224 files ... and the compressed qb_script file is like 1.3 mb
[exampleofthug2.zip](https://xentaxbackup.github.io/file/1062_exampleofthug2.zip)
## Post #13
- Username: bAstimc
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Jan 23, 2007 4:33 am
- Post datetime: 2007-04-08T19:28:58+00:00
- Post Title: Tony Hawk's American Wasteland + Project 8

> Reply from Blindreaper666
>
> A couple months after THAW came out I made a program to extract the pak files, and didn't wanna release it because of the threat of cheaters. I'm gonna release it publicly now, you can see what's inside of your pak files and learn how they work but I warn you, you won't be doing any cheating or even modding with this tool because the qb files are in a much more secure, and frustrating format. I'm releasing this in hopes of increasing interest so somebody can get working on THAW, I and most of the old modders no longer have any interest (Though I have something HUGE planned for thug2 in the near future, don't ask) and this program is about as far as the modding community got with THAW. This program will NOT rebuild pak files and will NOT decrypt the qb files, you'll have to figure that out on your own. There's no reason to keep it secret anymore and there's no danger in releasing this so.. have fun (yea right)

The build of the program in the archive only extracts to C:\, if you need it to go to a different directory then rebuild the provided source code or hax it up with a hex editor. It also only extracts the qb files to avoid confusion (If you see it say "Warning, unnamed file...", that's a non-qb file that it skipped), if you want img, mdl, etc there's more than enough info in the source code for an experienced C programmer to do that. There's source code for a THP8 pak extractor as well, though I haven't personally tested it. The source code was written for GCC based compilers, specifically MinGW, but should work in any C compiler on any operating system. I release this under the GPL license so do whatever you want with the source code, not that I could stop you from doing so anyway.

READ THIS BEFORE ASKING ANY QUESTIONS! : It only accepts single pak files, for some archives there's both a pak file and a pab file and to extract those open both in a hex editor, copy the entire contents of the pab, paste to the end of the pak file and save it as a single file and it will work fine. With this release I also provide a pre-made single pak of qb.pak/qb.pab for the people who can't figure it out so don't ask me a million times how to do it, please!

Here ya go: http://www.reap.hyptonicfilms.com/pakreaper.rar

Now he released his Unpacker ..Thank you Reaper
and yes the files are still a bit compressed  
maybe someone of you will know how to pack them back etc
