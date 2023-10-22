## Post #1
- Username: Denis
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Oct 03, 2009 10:15 pm
- Post datetime: 2011-06-01T20:44:15+00:00
- Post Title: Insane 2 pak files

Help me unpack archives from Insane 2 game.
I think they myst be the same as in Clutch (Armageddon Riders) [http://aluigi.org/papers/bms/clutch.bms](http://aluigi.org/papers/bms/clutch.bms)

Here the sample file from Insane 2 [https://rapidshare.com/files/2259931768/gamedata.rar](https://rapidshare.com/files/2259931768/gamedata.rar)
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-06-04T14:51:56+00:00
- Post Title: Insane 2 pak files

I have updated the script for supporting both the games
## Post #3
- Username: Denis
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Oct 03, 2009 10:15 pm
- Post datetime: 2011-06-05T06:18:22+00:00
- Post Title: Insane 2 pak files

Thanks
## Post #4
- Username: mambox
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Wed Mar 24, 2004 9:06 pm
- Post datetime: 2011-11-06T15:59:53+00:00
- Post Title: Insane 2 pak files

hi,

i just play with insane 2 and as usual i'm looking deeper inside.

i've seen that the excellent aluigi updated the script,i've tested it onto my gamedata but it give:

quickbms.exe clutch.bms gamedata.pak

result:

QuickBMS generic files extractor and reimporter 0.5.3
by Luigi Auriemma
e-mail: [aluigi@autistici.org](mailto:aluigi@autistici.org)
web:    aluigi.org

- open input file gamedata.pak
- open script clutch.bms

  offset   filesize   filename
------------------------------

Error: the requested amount of bytes to allocate is negative (-17)

Note that if both the scripts and your files are correct then it's possible
that the script needs a newer version of QuickBMS, in which case download it:

[http://aluigi.org/quickbms](http://aluigi.org/quickbms)


what's wrong?
thanks!
## Post #5
- Username: delutto
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Apr 16, 2011 12:20 pm
- Post datetime: 2011-11-07T02:15:47+00:00
- Post Title: Insane 2 pak files

Here gave the same error.
I uploaded the file gamedata.pak for analysis.
http://www.mediafire.com/?rv1cdux4r8wmbm0
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-11-07T13:42:07+00:00
- Post Title: Insane 2 pak files

script updated to version 0.2.1:
[http://aluigi.org/papers/bms/clutch.bms](http://aluigi.org/papers/bms/clutch.bms)
## Post #7
- Username: mambox
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Wed Mar 24, 2004 9:06 pm
- Post datetime: 2011-11-07T17:18:33+00:00
- Post Title: Insane 2 pak files

Respect to you!!!

work fine.

if my old brain could like your knowledge
## Post #8
- Username: delutto
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Apr 16, 2011 12:20 pm
- Post datetime: 2011-11-09T01:44:31+00:00
- Post Title: Insane 2 pak files

Another problem aluigi.
Extracting the packages, some files are larger than packaged.
For example the file "loadtips_strings.txt" extracted from the file ui.pak which I uploaded for analysis.
http://www.mediafire.com/?cgn8wrs410gdnf2
## Post #9
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-11-12T16:44:42+00:00
- Post Title: Insane 2 pak files

if you refer to problems during the reinjection I can do nothing because the injectable data (compressed or plain-text file) must be minor-equal than the original one.

so if the archive uses compression and your file is smaller than the original one it could be invalid because when compressed it's larger than the original compressed data
## Post #10
- Username: delutto
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Apr 16, 2011 12:20 pm
- Post datetime: 2011-11-13T23:04:51+00:00
- Post Title: Insane 2 pak files

> Reply from aluigi
>
> if you refer to problems during the reinjection I can do nothing because the injectable data (compressed or plain-text file) must be minor-equal than the original one.

so if the archive uses compression and your file is smaller than the original one it could be invalid because when compressed it's larger than the original compressed data
But the error message appears even without edit the files. It would be a problem to decompress them from the pack?
I tested using both x86 and x64 versions and the error persists.
Even so, thanks. I'll have to reduce the size of files even before you edit them.
## Post #11
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-11-14T16:10:17+00:00
- Post Title: Insane 2 pak files

yes it's perfectly possible because the same algorithm is not really identical so some of them pack better of others or pack some types of data better than others.
quickbms uses zlib for this type of data and it's not that good for compression ratio.
quickbms implements also the deflate algorithm used in 7zip which works very well, I don't remember what of these two is used in this script in reimport mode.
## Post #12
- Username: delutto
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Apr 16, 2011 12:20 pm
- Post datetime: 2011-11-18T18:56:50+00:00
- Post Title: Insane 2 pak files

> Reply from aluigi
>
> yes it's perfectly possible because the same algorithm is not really identical so some of them pack better of others or pack some types of data better than others.
quickbms uses zlib for this type of data and it's not that good for compression ratio.
quickbms implements also the deflate algorithm used in 7zip which works very well, I don't remember what of these two is used in this script in reimport mode.
One last observation:  
Some textures are in error, EOF error, it was also because of the decompression?
And it would update the script to use 7zip compression?
Thank you again aluigi.

Example:
