## Post #1
- Username: joaofeu
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun May 27, 2012 12:54 am
- Post datetime: 2015-06-24T19:46:10+00:00
- Post Title: Old Disney games tool

Hi. I've searched everywhere and I can't find a tool to extract some Disney Interactive pkg files (one per game).
These are old games. Here are the ones whose files I want to extract:
102 Dalmatians: Puppies To The Rescue
Extremely Goofy Skateboarding

I don't know how to make a decompiler, I would like to.
If you can give me some help extracting these files and give me a good tutorial of how to make a decompiler I would appreciate.
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2015-08-08T22:31:29+00:00
- Post Title: Old Disney games tool

Then we need examples.
## Post #3
- Username: joaofeu
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun May 27, 2012 12:54 am
- Post datetime: 2016-01-09T12:08:59+00:00
- Post Title: Old Disney games tool

Here you have a file.
This is a 102 Dalmatians: Puppies To The Rescue's .PKG file.
[https://mega.nz/#!QwlT1CDT!1RhYXa4HFwcc ... Tod36-c81o](https://mega.nz/#!QwlT1CDT!1RhYXa4HFwcc6E14OuayFVWb2V9fx3jCCTod36-c81o)
## Post #4
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2016-01-10T20:55:54+00:00
- Post Title: Old Disney games tool

Stuff can be extracted quite simply, question remains: what kind of compression is used on some of the content.
## Post #5
- Username: joaofeu
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun May 27, 2012 12:54 am
- Post datetime: 2016-01-15T15:27:35+00:00
- Post Title: Old Disney games tool

I really don't know. 
Does anyone know how to help here?
Anyway can you show me the extracted files?
## Post #6
- Username: masterX244
- Rank: beginner
- Number of posts: 31
- Joined date: Tue Aug 17, 2010 12:48 am
- Post datetime: 2016-01-16T18:21:47+00:00
- Post Title: Old Disney games tool

Not sure if i checked the same game atm since in Germany it might be called a bit different but for me the *.ase files inside the PKG file look like Text based files for me. haven't found binary in weird formats while quickly scrolling over the files inside
## Post #7
- Username: joaofeu
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun May 27, 2012 12:54 am
- Post datetime: 2016-01-29T14:41:02+00:00
- Post Title: Old Disney games tool

Sorry, but I don't even know how to get the files inside the .PGK.
## Post #8
- Username: masterX244
- Rank: beginner
- Number of posts: 31
- Joined date: Tue Aug 17, 2010 12:48 am
- Post datetime: 2016-01-31T19:12:01+00:00
- Post Title: Old Disney games tool

> Reply from joaofeu
>
> Sorry, but I don't even know how to get the files inside the .PGK.
rename it to zip and the standard tools for those should work. the game is from the era where people were easily fooled by wrong extensions so hiding zips that way worked
## Post #9
- Username: joaofeu
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun May 27, 2012 12:54 am
- Post datetime: 2016-02-02T21:11:10+00:00
- Post Title: Old Disney games tool

> Reply from masterX244
>
> joaofeu wrote:Sorry, but I don't even know how to get the files inside the .PGK.
rename it to zip and the standard tools for those should work. the game is from the era where people were easily fooled by wrong extensions so hiding zips that way worked
Thank you, but, unfortunately, that didn't solve the problem
## Post #10
- Username: masterX244
- Rank: beginner
- Number of posts: 31
- Joined date: Tue Aug 17, 2010 12:48 am
- Post datetime: 2016-02-06T21:29:08+00:00
- Post Title: Old Disney games tool

> Reply from joaofeu
>
> masterX244 wrote:joaofeu wrote:Sorry, but I don't even know how to get the files inside the .PGK.
rename it to zip and the standard tools for those should work. the game is from the era where people were easily fooled by wrong extensions so hiding zips that way worked
Thank you, but, unfortunately, that didn't solve the problem
damn... smells like there might be different versions of the game around... you got a hex-editor or something where you can see the binary content of the file? seeing the beginning of the file could get me on track
## Post #11
- Username: joaofeu
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun May 27, 2012 12:54 am
- Post datetime: 2016-02-12T00:18:26+00:00
- Post Title: Old Disney games tool

Here's the beginning of the file I've got from opening it with an hex-editor:

00 08 00 00 DC 6C 06 00 00 78 06 00 40 16 00 00
00 90 06 00 E4 0B 00 00 00 A0 06 00 04 C0 12 00
00 68 19 00 04 C0 12 00 00 30 2C 00 04 C0 12 00
00 F8 3E 00 04 C0 12 00 00 C0 51 00 04 C0 12 00
00 88 64 00 04 C0 12 00 00 50 77 00 04 C0 12 00
00 18 8A 00 04 C0 12 00 00 E0 9C 00 04 C0 12 00
00 A8 AF 00 04 C0 12 00 00 70 C2 00 04 C0 12 00
00 38 D5 00 04 C0 12 00 00 00 E8 00 04 C0 12 00
00 C8 FA 00 04 C0 12 00 00 90 0D 01 04 C0 12 00
00 58 20 01 04 C0 12 00 00 20 33 01 04 C0 12 00

[](http://postimg.org/image/ofdmoscp3/)
## Post #12
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-02-12T02:26:25+00:00
- Post Title: Old Disney games tool

[http://zenhax.com/viewtopic.php?p=8666#p8666](http://zenhax.com/viewtopic.php?p=8666#p8666)

aluigi made a QuickBMS script for 102 Dalmatians pkg
## Post #13
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2016-02-12T21:37:07+00:00
- Post Title: Old Disney games tool

```

for
    get OFFSET long
    get SIZE long
    if OFFSET == 0
        break
    endif
    if OFFSET != 0xffffffff
        math OFFSET + 4 # useless TYPE
        math SIZE   - 4
        log "" OFFSET SIZE
    endif
next

```


Yes, that was the easy part. As I said: Stuff can be extracted quite simply, question remains: what kind of compression is used on some of the content. So the problem is the encryption/compression.
## Post #14
- Username: joaofeu
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun May 27, 2012 12:54 am
- Post datetime: 2016-02-20T13:38:00+00:00
- Post Title: Old Disney games tool

> Reply from AceWell
>
> http://zenhax.com/viewtopic.php?p=8666#p8666

aluigi made a QuickBMS script for 102 Dalmatians pkg

Thank you!! I didn't know about that forum. 

But now I can't read the files inside it. 

> Reply from Mr.Mouse
>
> :Yes, that was the easy part. As I said: Stuff can be extracted quite simply, question remains: what kind of compression is used on some of the content. So the problem is the encryption/compression.

Does anyone know how to help here?
