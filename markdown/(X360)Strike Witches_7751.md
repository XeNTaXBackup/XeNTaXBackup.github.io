## Post #1
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2011-11-26T06:26:17+00:00
- Post Title: (X360)Strike Witches

Hello!
I used "ggxdiv.exe" to unpacked bin[GGXArchiver1.00] files in Strike Witches Xbox360.
*.GMA \?
*.GMM \?
*.GMO \model?
*.DDS  \texture
*.XMA  \sound

I want to converter GMO to obj, please. 
Here is sample files:
[delete](delete)

Thanks in advance!
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-11-26T06:59:00+00:00
- Post Title: (X360)Strike Witches

Everything is encrypted
## Post #3
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-11-26T14:35:40+00:00
- Post Title: (X360)Strike Witches

I dont think its encrypted i think the extractor he used is wrong
if you look at the original bin file there are readable strings in the file sections
so just need to get what type of compression they used.
## Post #4
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2011-11-26T14:49:25+00:00
- Post Title: (X360)Strike Witches

here are original bin files & xex file
[delete](delete)
## Post #5
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-11-26T18:14:48+00:00
- Post Title: (X360)Strike Witches

Quickbms script


> getdstring MAGIC 0x10
>
> get FILES long
>
> goto 0x20
>
> comtype BPE
>
> for i = 0 < files
>
> getdstring NAME 0x20
>
> putarray 0 i NAME
>
> next i
>
> savepos baseoff
>
> set tmp files
>
> math tmp * 0x18
>
> math baseoff + tmp
>
> for i = 0 < files
>
> get NID long
>
> get ONE long
>
> get size long
>
> get zsize long
>
> get COMP long
>
> get offset long
>
> math offset + baseoff
>
> getarray NAME 0 NID
>
> if COMP == 1
>
> clog name offset zsize size
>
> else
>
> log name offset size
>
> endif
>
> next i
## Post #6
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-11-27T20:32:04+00:00
- Post Title: (X360)Strike Witches

How did you figure out the compression type?

@OP, I'm guessing you deleted the file because all you needed was the decryption script?
## Post #7
- Username: Acewell
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-11-28T01:25:07+00:00
- Post Title: (X360)Strike Witches

its super easy with luigi's compscan and bms script.
all you need is the raw file part with the uncompressed size and it will try every compression quickbms knows for you.
then you just look at the output files to see what one decompressed correctly.
i chose a dds file because i know what that should look like.
## Post #8
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2011-11-28T03:43:45+00:00
- Post Title: (X360)Strike Witches

chrrox//
I've said it before and I'll say it again, thanks for all your help.

finale00//
replace links
## Post #9
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-11-28T04:52:03+00:00
- Post Title: (X360)Strike Witches

tutorial for noesis here on this format
[viewtopic.php?f=29&t=7760](http://forum.xentax.com/viewtopic.php?f=29&t=7760)
## Post #10
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-12-10T23:05:27+00:00
- Post Title: (X360)Strike Witches

to anyone interested in the comscan method:
[http://aluigi.org/quickbms/comtype_scan.htm](http://aluigi.org/quickbms/comtype_scan.htm)
