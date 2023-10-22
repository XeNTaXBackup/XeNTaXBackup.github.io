## Post #1
- Username: innocentius92
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Dec 16, 2017 4:10 pm
- Post datetime: 2017-12-16T09:30:33+00:00
- Post Title: Okami HD PC - Texts files

hi guys, I'm new here, sorry if this does not go in this section, but someone could help me find the texts and how unpack the files of the game? it's for a language translation. Some help?
## Post #2
- Username: ffgriever
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Dec 16, 2017 12:21 am
- Post datetime: 2017-12-16T12:26:40+00:00
- Post Title: Okami HD PC - Texts files

The first thing you need to realize is that Okami was initially a Wii (and then PS2) game. This means very strict memory and computing power constraints. That's one of many reasons why every format was developed to need the least possible memory footprint and the least possible processing. An XML parser or some other text parser could add a hundred or even few hundreds kB to the application size, then it would require a lot of memory for intermediate buffers before it's processed to the form that can be displayed directly. With small and simple games that's not an issue, but becomes one once you do something as big as one of the AAA games. That's why most games of that era (and before) opted mostly for relative pointers (which sometimes would be changed on the fly to absolute memory addresses), character substitution (containing only the used character glyphs and assigning them numbers in order of appearance in font table or font image), bitmap fonts, etc. That meant you had to place a file in memory only once, sometimes do some minimal processing (like pointer recalculation) and then use the values as they are, without any intermediates.

"Take a value CHAR from text file, take values from font description file at position CHAR*DESC_SIZE, use the values to determine X, Y, W, H coordinates of the glyphs to display, print a glyph from the font texture with given coordinates". That's very simplistic description of what usually happens in PSX/PS2 games (was a little different in nes/snes era, due to tiles, memory addressing, etc.).

With that mindset it will be much easier to take on the Okami file formats.

Anyway, to the point. ~90% of text in Okami is contained within MSD files, which in turn are contained in binary containers alongside many other files. The binary containers are usually one per location/menu/etc. For example st1/r120.bin is an intro stage. You know, "A long time ago in a galaxy far, far away..." or something along the lines, it's been a while. The file formats are VERY straightforward, probably among the most simple ones I've ever found in a game.

These are very similar to PS2 files, with one exception being that at pointer-0x20 location there is a metric with file type and stage name which wasn't present in PS2 version. Which in turn makes all the actuall file sizes next_pointer-previous_pointer-0x20 (except for the very last one, which just spans to the end). From the game perspective it doesn't matter at all (remember, it just loads it and uses the data, it doesn't dissect it into files).

So the file starts with 32bit number of files within container. Then a 32bit pointers to all the files, followed by 32bit magic strings describing file formats. What's interesting for you is the MSD file (or files).

As above, it starts with number of dialogs within a file (doesn't mean number of windows, but full dialogs, sometimes with multiple characters). Then come pointers. Each pointer is either 64bit or 32bit followed by an unknown/reseved 32bit value (I don't recall ever seeing it used). Then at each pointer relative to file start a dialog starts. Each character (or command value) consists of 16bit (two bytes). You'll need to assign characters to the values, but eg. 0xA301 (or 0x01 0xA3) is an action of waiting for gamepad/keyboard entry to move the dialog forward, 0xA101 is a "clearscreen" command, etc.

If you're about to edit Japanese files, please note, that there are also special commands to enable furigana and the text will be intertwined with furigana text. In Japanese version there will also be a lot more images in the files. That's because main Japanese font contains only numbers, romaji, kanas, few hundred most popular kanjis and some other characters. If a particular stage file uses kanjis/other characters not present in the main font file, the font pages are added to the stage file and accessed through special character range, which essentially means that for different stages a particular 16bit value may actually mean other characters. There are few cases when this is used for English version, too.

Some text is contained within other binary files with other formats, on PS2 a few labels were also hardcoded into executable, but the MSD files are a good start.

In the nearest week or two, considering I'll have enough time, I'll port all my PS2 tools to work properly with PC version. If you still need them by then, I'll try to post a package here, but it's always more fun if you do it on your own. At least that's how it works for me.
## Post #3
- Username: innocentius92
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Dec 16, 2017 4:10 pm
- Post datetime: 2017-12-16T12:33:17+00:00
- Post Title: Okami HD PC - Texts files

> Reply from ffgriever
>
> The first thing you need to realize is that Okami was initially a Wii (and then PS2) game. This means very strict memory and computing power constraints. That's one of many reasons why every format was developed to need the least possible memory footprint and the least possible processing. An XML parser or some other text parser could add a hundred or even few hundreds kB to the application size, then it would require a lot of memory for intermediate buffers before it's processed to the form that can be displayed directly. With small and simple games that's not an issue, but becomes one once you do something as big as one of the AAA games. That's why most games of that era (and before) opted mostly for relative pointers (which sometimes would be changed on the fly to absolute memory addresses), character substitution (containing only the used character glyphs and assigning them numbers in order of appearance in font table or font image), bitmap fonts, etc. That meant you had to place a file in memory only once, sometimes do some minimal processing (like pointer recalculation) and then use the values as they are, without any intermediates.

"Take a value CHAR from text file, take values from font description file at position CHAR*DESC_SIZE, use the values to determine X, Y, W, H coordinates of the glyphs to display, print a glyph from the font texture with given coordinates". That's very simplistic description of what usually happens in PSX/PS2 games (was a little different in nes/snes era, due to tiles, memory addressing, etc.).

With that mindset it will be much easier to take on the Okami file formats.

Anyway, to the point. ~90% of text in Okami is contained within MSD files, which in turn are contained in binary containers alongside many other files. The binary containers are usually one per location/menu/etc. For example st1/r120.bin is an intro stage. You know, "A long time ago in a galaxy far, far away..." or something along the lines, it's been a while. The file formats are VERY straightforward, probably among the most simple ones I've ever found in a game.

These are very similar to PS2 files, with one exception being that at pointer-0x20 location there is a metric with file type and stage name which wasn't present in PS2 version. Which in turn makes all the actuall file sizes next_pointer-previous_pointer-0x20 (except for the very last one, which just spans to the end). From the game perspective it doesn't matter at all (remember, it just loads it and uses the data, it doesn't dissect it into files).

So the file starts with 32bit number of files within container. Then a 32bit pointers to all the files, followed by 32bit magic strings describing file formats. What's interesting for you is the MSD file (or files).

As above, it starts with number of dialogs within a file (doesn't mean number of windows, but full dialogs, sometimes with multiple characters). Then come pointers. Each pointer is either 64bit or 32bit followed by an unknown/reseved 32bit value (I don't recall ever seeing it used). Then at each pointer relative to file start a dialog starts. Each character (or command value) consists of 16bit (two bytes). You'll need to assign characters to the values, but eg. 0xA301 (or 0x01 0xA3) is an action of waiting for gamepad/keyboard entry to move the dialog forward, 0xA101 is a "clearscreen" command, etc.

If you're about to edit Japanese files, please note, that there are also special commands to enable furigana and the text will be intertwined with furigana text. In Japanese version there will also be a lot more images in the files. That's because main Japanese font contains only numbers, romaji, kanas, few hundred most popular kanjis and some other characters. If a particular stage file uses kanjis/other characters not present in the main font file, the font pages are added to the stage file and accessed through special character range, which essentially means that for different stages a particular 16bit value may actually mean other characters. There are few cases when this is used for English version, too.

Some text is contained within other binary files with other formats, on PS2 a few labels were also hardcoded into executable, but the MSD files are a good start.

In the nearest week or two, considering I'll have enough time, I'll port all my PS2 tools to work properly with PC version. If you still need them by then, I'll try to post a package here, but it's always more fun if you do it on your own. At least that's how it works for me.
Ok, i will wait. But please, dont forget me. I really need this.
## Post #4
- Username: Zolodei
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Jun 19, 2017 2:15 am
- Post datetime: 2017-12-18T20:57:04+00:00
- Post Title: Okami HD PC - Texts files

Could, check your program can pull out the text, PC version?
[https://cloud.mail.ru/public/6ecc/QZ42MTxh5](https://cloud.mail.ru/public/6ecc/QZ42MTxh5)
## Post #5
- Username: innocentius92
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Dec 16, 2017 4:10 pm
- Post datetime: 2017-12-19T08:46:52+00:00
- Post Title: Okami HD PC - Texts files

> Reply from Zolodei
>
> Could, check your program can pull out the text, PC version?
https://cloud.mail.ru/public/6ecc/QZ42MTxh5

Yes, PC version.
I managed to visualize texts of the game using a thingy table, from your file Core_20_dec_0.rar, that could be modified with TranslHextion.
How could I correctly extract the files from Core_20.bin? There is text within the MSD file that could be modified for translation.


Now I am downloading Okami HD PS3 version to compare the files.
## Post #6
- Username: innocentius92
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Dec 16, 2017 4:10 pm
- Post datetime: 2017-12-19T10:11:43+00:00
- Post Title: Okami HD PC - Texts files

I am thinking of some tool that facilitates the reading of the MSD files.
## Post #7
- Username: Zolodei
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Jun 19, 2017 2:15 am
- Post datetime: 2017-12-19T14:32:17+00:00
- Post Title: Okami HD PC - Texts files

innocentius92, give the table for MSD to write a program, and you know the structure of the MSA file?
## Post #8
- Username: innocentius92
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Dec 16, 2017 4:10 pm
- Post datetime: 2017-12-19T14:49:21+00:00
- Post Title: Okami HD PC - Texts files

> Reply from Zolodei
>
> innocentius92, give the table for MSD to write a program, and you know the structure of the MSA file?
I don't know much about this, but, I give you the table, i need learn more about this. And now I will patiently wait for your results. You have helped me a lot.

Okami tbl
[https://mega.nz/#!pgATlIrY!CA_D_8uWDZhE ... Jv2DZIcd7I](https://mega.nz/#!pgATlIrY!CA_D_8uWDZhEsL-08hAmJd7XYOYNvRJIHJv2DZIcd7I)

keep me informed please.
## Post #9
- Username: Zolodei
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Jun 19, 2017 2:15 am
- Post datetime: 2017-12-19T17:20:49+00:00
- Post Title: Okami HD PC - Texts files

Sample text [https://cloud.mail.ru/public/HQSw/UzfjgP956](https://cloud.mail.ru/public/HQSw/UzfjgP956)

innocentius92, ffgriever can share the file structure  *.MSA, or describe the algorithm?
## Post #10
- Username: innocentius92
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Dec 16, 2017 4:10 pm
- Post datetime: 2017-12-19T18:25:13+00:00
- Post Title: Okami HD PC - Texts files

Zolodei Can you say me how can I extract MSD and MSA from Core_20.bin please?
## Post #11
- Username: Zolodei
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Jun 19, 2017 2:15 am
- Post datetime: 2017-12-19T23:05:09+00:00
- Post Title: Okami HD PC - Texts files

On writing a program to extract, but it is not ready yet, can not package files.
I want to add support for text and font.
## Post #12
- Username: ffgriever
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Dec 16, 2017 12:21 am
- Post datetime: 2017-12-21T10:31:12+00:00
- Post Title: Okami HD PC - Texts files

Quick update. I've written a simple unpacker/repacker. It can handle most of the binary containers, while repacking it also handles 64bit runtime offset file if it's present (it essentially contains the same pointers that at the beginning, only 64bit length and it's overwritten in memory to actual runtime offsets).

I've also fixed the descriptions in decrypter/crypter to match their real function.

Here's the link: [http://ff12.pl/down/okami-tools-20171221.zip](http://ff12.pl/down/okami-tools-20171221.zip)

I've tried it with few files edited and it seems to be working, but I did not do any extensive tests. Note, that it might produce smaller files (original files seem to have some additional 16byte padding here and there, but it's not needed as long as the files start at 16byte boundary).

Initially I was going to rewrite my PS2 multi tool/editor/viewer, but that's just too much hassle. It's much faster to just take care of the files with CLI. GUI was useful for the original translation, but is a waste of time for porting.



As for MSA files. I should have my notes about it somewhere. I've never written any tool for that as I just had to add ęóąśłżźćńĘÓĄŚŁŻŹĆŃ and for that I could just copy both the glyphs (edit them a little) as well as their font table data (with some minor changes to improve kerning - there is no true kerning possible though, just some basics). I'll post the notes if I'm able to find them... Or reverse the format again. I guess you can't avoid editing it properly for a completely different script (Cyrillic in your case).

As for MSD extractor/repacker, I should be able to handle that on Saturday. The PS2 code should be fully reusable.
## Post #13
- Username: innocentius92
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Dec 16, 2017 4:10 pm
- Post datetime: 2017-12-21T14:23:46+00:00
- Post Title: Okami HD PC - Texts files

ffgriever Can you share with us the tool you use in your screenshot?
## Post #14
- Username: makcar
- Rank: veteran
- Number of posts: 154
- Joined date: Tue May 13, 2014 5:41 am
- Post datetime: 2017-12-21T15:01:02+00:00
- Post Title: Okami HD PC - Texts files

Maybe filelist_dat.lst, filelist_bin.lst etc to packing all?


```
for /R %%a in (*.ddp;*.tbl;*.emd;*.eff;*.tbl;*.scp;*.akt;*.cmp;*.pac;*.idd;*.bin;*.dat) do okami-pack.exe -p "%%a" "%%~dpna"
```

How about .emd and this archive [https://mega.nz/#!4a5mCA5S!KlCTKDh3i3QG ... m1fB3mr2ec](https://mega.nz/#!4a5mCA5S!KlCTKDh3i3QGycenyEJxjUS_uOev9Xp5Km1fB3mr2ec)?
You have src?
## Post #15
- Username: innocentius92
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Dec 16, 2017 4:10 pm
- Post datetime: 2017-12-23T02:20:17+00:00
- Post Title: Okami HD PC - Texts files

ffgriever Initially I was going to rewrite my PS2 multi tool/editor/viewer, but that's just too much hassle. It's much faster to just take care of the files with CLI. GUI was useful for the original translation, but is a waste of time for porting.

Can you share with me your Translation Tool and PS2 multi tool/editor/viewer, I need to do some tests with the original PS2 iso and its MSD files. I would really appreciate it. I love this game very much and I would like to be able to do something to bring the PC port in Spanish to the community.
## Post #16
- Username: prime
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Dec 26, 2017 8:23 pm
- Post datetime: 2017-12-26T15:44:39+00:00
- Post Title: Re: Okami HD PC - Texts files

Hello, I'm new here. Please excuse me for my poor English.
I want to be of little help to you.

(This is just my test resut. If there are any wrong information, Please correct me.)


Thanks for ffgriever, I've unpacked ENG font file PC and PS3 version.
(PS3: through QuickBMS script I've made. that is imperfect version)

Here's link of unpacked ENG font file I've unpacked.(core_20.bin(PC), core.bin(PS3))
[https://mega.nz/#!iR9nlayT!_2EjmaB-ZNrz ... 3aThWo9OB8](https://mega.nz/#!iR9nlayT!_2EjmaB-ZNrzozuun85KVztUV6IvQ1WCT3aThWo9OB8)


I think the MSA file is associated with font table.

For example, in core_20.bin, there are many files and you can find MessCore.DDS and MessCore.MSA file. This is same on PS3 version too.

------------------------------------------------------------------

1. DDS file.
In both MessCore.DDS, you can figure out some properties.

PC(DX10):   number of letter: 213 /  image size: 2400x2400 
PS3(DXT5): number of letter: 212 /  image size: 1200x1200 

With this file, you can make your own OKAMI HD table.

DDS Viewer: Noesis(v4.296) 
([http://richwhitehouse.com/index.php?con ... sv4296.zip](http://richwhitehouse.com/index.php?content=inc_projects.php&filemirror=noesisv4296.zip))

DDS Edit: Intel® Texture Works Plugin for Photoshop
([https://software.intel.com/en-us/articl ... rks-plugin](https://software.intel.com/en-us/articles/intel-texture-works-plugin))
(Requirements of this plugin is Photoshop CS6, but it also works on my Photoshop CS5)

----------------------------------------------------------------------

2. MSA file
Open two MessCore.MSA through HEX editor. You can figure out some similarities on structure.

*Note: PC version uses little endian, and PS3 version uses big endian.(the little endian data must be read backward)

MessCore.MSA(PC, little endian)

```
01 03 67 8C 01 01 B3 80 01 02 63 80 01 C3 72 94 
01 C2 72 90 01 02 C3 54 01 C0 92 80 01 01 83 4C 
01 02 43 4C 00 03 93 90 00 01 73 90 00 41 D3 80 
00 81 73 80 00 81 B3 80 00 41 B3 80 00 81 D3 84 
00 81 B3 80 00 41 B3 80 00 81 A3 80 00 41 C3 80 
00 81 C3 84 00 01 E3 84 00 03 E3 80 00 01 D3 80

```


MessCore.MSA(PS3, big endian)

```
01 0D C1 A3 01 04 C2 E0 01 08 C1 A0 01 0C B1 E5 
01 08 B1 E4 01 08 C3 15 01 00 B2 60 01 04 C2 13 
01 08 C1 13 00 0C C2 64 00 04 C1 E4 00 04 D3 60 
00 04 E1 E0 00 04 E2 E0 00 04 D2 E0 00 04 E3 61 
00 04 E2 E0 00 04 D2 E0 00 04 E2 A0 00 04 D3 20 
00 04 E3 21 00 04 C3 A1 00 0C C3 A0 00 04 C3 60

```

in PC version
1st 2 byte: 0x00D5(HEX)=213 -> number of CHAR on font table(see MessCORE.DDS)
2nd 2 byte: 0x0258(HEX)=600(DEC) -> width/4(width of MessCore.DDS: 2400)
3rd 2 byte: 0x0258(HEX)=600(DEC) -> height/4(height of MessCore.DDS: 2400)
4th 2 byte: 0x28(HEX)=40(DEC) ->  width_each_letter/4, height_each_letter/4


in PS3 version
1st 2 byte: 0x00D4(HEX)=212 -> number of letter on font table(see MessCORE.DDS)
2nd 2 byte: 0x0258(HEX)=600(DEC) -> width/2(width of MessCore.DDS: 1200)
3rd 2 byte: 0x0258(HEX)=600(DEC) -> height/2(height of MessCore.DDS: 1200)
4th 2 byte: 0x28(HEX)=40(DEC) ->  width_each_letter/2, height_each_letter/2


After 8h, there are lots of data.
they are located per 4 byte, 212 times.
(4 x 212 + 8 = 856(DEC) =0x358(HEX)
 -> the data of MessCore.MSA file ends on 358h.

So I think it means MSA file is associated with font table, and each of 4 byte data in MSA file might be linked to letter each other(After 8h)

For example, on PS3 version, I've changed some value of MSA file.
(Actually, I've changed value in unpacked wolves.cpk, on core.bin area....)
0xFC~0xFF: 00 09 34 20  -> 00 09 32 10

Then width of the letter 'm' was cut. it looks like 'n'.
It means 6-7th value in 4 byte are width of letter on text screen.

But I cannot figure out the role of other data and I want to figure it out later.


Though my words are frantic article, I hope it will be helpful to you.


p.s-In MSD file, You can find many text with using font table. 

But As ffgriever says, there are lots of command HEX code between the sentences.

ex) 80 01 - end of dialog / 31 35 - issun says / B9 02 xx xx - gamepad button (on the sentence "press the A button")

This HEX code must be figured out what codes are doing.
I'm trying to figure the role of codes, but it will take a long time.
## Post #17
- Username: innocentius92
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Dec 16, 2017 4:10 pm
- Post datetime: 2017-12-27T04:18:33+00:00
- Post Title: Re: Okami HD PC - Texts files

prime I'm trying to figure the role of codes, but it will take a long time
Thanks a lot *u* I will wait for any tool that helps translate this game for people who speak other languages. In my case, Spanish.
## Post #18
- Username: prime
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Dec 26, 2017 8:23 pm
- Post datetime: 2017-12-27T05:04:37+00:00
- Post Title: Re: Okami HD PC - Texts files

> Reply from innocentius92
>
> prime I'm trying to figure the role of codes, but it will take a long time
Thanks a lot *u* I will wait for any tool that helps translate this game for people who speak other languages. In my case, Spanish.

innocent92 I've seen Spanish patches for PS2 and Wii version before.

here's the link
[http://okami.romhackhispano.org/](http://okami.romhackhispano.org/)

I think there are user translated text in there. 

Could you patch it to PS2 or Wii version and extract MSD FILE?

If the text contents and commands are not much different between PC and PS2, you can compare structure of some MSD file and test to copy-paste it.
(before paste, consider little endian and big endian type)

If it succeed, what you need to prepare is spanish font graphic.

Or contact to the spanish translate team. It could be helpful somehow.
## Post #19
- Username: innocentius92
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Dec 16, 2017 4:10 pm
- Post datetime: 2017-12-27T23:20:54+00:00
- Post Title: Re: Okami HD PC - Texts files

prime Yes, i know the translations for ps2 and wii and I have both. but now i want to work on PC version, the real HD.
## Post #20
- Username: ffgriever
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Dec 16, 2017 12:21 am
- Post datetime: 2018-01-05T13:44:58+00:00
- Post Title: Re: Okami HD PC - Texts files

Here's a simple tool to unpack/repack MSD files. It lacks some stuff like speaker codes (like hmff is narrator, etc. - I've got all of them from PS2 version, so no problem here) and some special codes are not recognized (it's fine, actual 16bit short values are inserted into the file). I might add these later, but it won't break compatibility.

[http://ff12.pl/down/okami-tools-20180105.zip](http://ff12.pl/down/okami-tools-20180105.zip)
## Post #21
- Username: makcar
- Rank: veteran
- Number of posts: 154
- Joined date: Tue May 13, 2014 5:41 am
- Post datetime: 2018-01-06T01:27:22+00:00
- Post Title: Re: Okami HD PC - Texts files

Thanks!
## Post #22
- Username: ffgriever
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Dec 16, 2017 12:21 am
- Post datetime: 2018-01-06T16:06:19+00:00
- Post Title: Re: Okami HD PC - Texts files

There is an issue with the MSD unpacker/repacker. The very first value (number of dialogs) is not u32 but u16 folowed by another u16. Trivial to fix, but the tool will crash on some of the files. Unfortunately I won't have access to the source code until Monday (I've been working on it during my lunch break and left the drive at work, it's also why this bug happened as I had only three files to test on). You can zero the second value out and the restore it after repack if you're in a hurry.
## Post #23
- Username: makcar
- Rank: veteran
- Number of posts: 154
- Joined date: Tue May 13, 2014 5:41 am
- Post datetime: 2018-01-06T19:34:40+00:00
- Post Title: Re: Okami HD PC - Texts files

@ffgriever
405 files: [https://zenhax.com/download/file.php?id=3808](https://zenhax.com/download/file.php?id=3808)
## Post #24
- Username: Zolodei
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Jun 19, 2017 2:15 am
- Post datetime: 2018-01-06T20:16:54+00:00
- Post Title: Re: Okami HD PC - Texts files

ffgriever, there are files with the order of bytes big-endian, this is the folder st0 and std.
makcar, dismantled the MSA archive or rebuilt the image?
## Post #25
- Username: innocentius92
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Dec 16, 2017 4:10 pm
- Post datetime: 2018-01-07T09:46:13+00:00
- Post Title: Re: Okami HD PC - Texts files

> Reply from ffgriever
>
> There is an issue with the MSD unpacker/repacker. The very first value (number of dialogs) is not u32 but u16 folowed by another u16. Trivial to fix, but the tool will crash on some of the files. Unfortunately I won't have access to the source code until Monday (I've been working on it during my lunch break and left the drive at work, it's also why this bug happened as I had only three files to test on). You can zero the second value out and the restore it after repack if you're in a hurry.

The okami-msd tool don't recongnize ñ á é í ó ú ¿ ¡ and other spanish characters, can you fix it, my friend?
## Post #26
- Username: ffgriever
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Dec 16, 2017 12:21 am
- Post datetime: 2018-01-07T13:03:35+00:00
- Post Title: Re: Okami HD PC - Texts files

It does. Just make sure the text is utf8 encoded.
## Post #27
- Username: innocentius92
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Dec 16, 2017 4:10 pm
- Post datetime: 2018-01-07T14:51:03+00:00
- Post Title: Re: Okami HD PC - Texts files

> Reply from ffgriever
>
> It does. Just make sure the text is utf8 encoded.

I converted it and coded it in UTF-8 and when I applied the SMD tool I got this message. And then when you apply it in core_20.bin, encrypt it and start the game, the game crashes.
## Post #28
- Username: ffgriever
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Dec 16, 2017 12:21 am
- Post datetime: 2018-01-07T16:13:23+00:00
- Post Title: Re: Okami HD PC - Texts files

Remove the BOM (which doesn't have any sense anyway as utf8 has no byte order, you always read 8 consecutive bits at once, so no marker is necessary, they really should call it utf8 header or something). The tool is unaware of any BOM value at the beginning and it might cause these issues. As I wrote, it supports properly all the characters you've quoted above.

It expects "^\{Dialogs: *([0-9]+)\}$" and the bom makes it "^0xEF 0xBB 0xBF \{Dialogs: *([0-9]+)\}$". The regular expression just doesn't find a match then.
## Post #29
- Username: makcar
- Rank: veteran
- Number of posts: 154
- Joined date: Tue May 13, 2014 5:41 am
- Post datetime: 2018-01-07T23:51:09+00:00
- Post Title: Re: Okami HD PC - Texts files

> Reply from Zolodei
>
> makcar, dismantled the MSA archive or rebuilt the image?
I used Photoshop to edit dds.
## Post #30
- Username: innocentius92
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Dec 16, 2017 4:10 pm
- Post datetime: 2018-01-08T02:36:14+00:00
- Post Title: Re: Okami HD PC - Texts files

> Reply from makcar
>
> Zolodei wrote:makcar, dismantled the MSA archive or rebuilt the image?
I used Photoshop to edit dds.

How did you do it? Photoshop does not recognize the DDS file extension.

¿Can you help me, please?
## Post #31
- Username: ffgriever
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Dec 16, 2017 12:21 am
- Post datetime: 2018-01-08T12:02:15+00:00
- Post Title: Re: Okami HD PC - Texts files

Here is an updated msd tool that handles both u16 values properly. Now it also takes care of utf8 bom/signature.

[http://ff12.pl/down/okami-tools-20180108.zip](http://ff12.pl/down/okami-tools-20180108.zip)

Remember, though, the tool writes proper utf8 and expect utf8 but in fact is unaware of the encoding whatsoever. It's lazy but it works.

@innocentius92
You shouldn't need to modify MSA file for Spanish font. AFAIK all the characters used in Spanish are already there. Unless you mean the ñ character, that has some weird space on the right.

Photoshop needs a plugin to support DDS. I'm using paint.NET, though (it's free) with a "DDS Plus" plugin:
[https://github.com/0xC0000054/pdn-ddsfi ... s/releases](https://github.com/0xC0000054/pdn-ddsfiletype-plus/releases)
## Post #32
- Username: star19990
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jan 07, 2018 4:59 pm
- Post datetime: 2018-01-09T11:41:19+00:00
- Post Title: Re: Okami HD PC - Texts files

> Reply from ffgriever
>
> Here is an updated msd tool that handles both u16 values properly. Now it also takes care of utf8 bom/signature.

http://ff12.pl/down/okami-tools-20180108.zip

Remember, though, the tool writes proper utf8 and expect utf8 but in fact is unaware of the encoding whatsoever. It's lazy but it works.

@innocentius92
You shouldn't need to modify MSA file for Spanish font. AFAIK all the characters used in Spanish are already there. Unless you mean the ñ character, that has some weird space on the right.

Photoshop needs a plugin to support DDS. I'm using paint.NET, though (it's free) with a "DDS Plus" plugin:
https://github.com/0xC0000054/pdn-ddsfi ... s/releases

this tool support 2-byte? (ex : korean)
## Post #33
- Username: ffgriever
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Dec 16, 2017 12:21 am
- Post datetime: 2018-01-09T12:39:52+00:00
- Post Title: Re: Okami HD PC - Texts files

It doesn't support any language in particular. It supports the glyphs supported by the game and present in character replacement table (hardcoded in executable for now). It so happens I encoded the table as utf8. The tool should work (provided you'll use proper replacement table) on any encoding that doesn't use 0x00 values anywhere (it's read in text mode).

I'll add support for external table at some point. I don't need it (I have another version with hardcoded Polish diacritic characters), but it might make things easier for some people.

But... The game itself doesn't support combining jamos into full syllables, so it means you'd have to create a font with ~12k glyphs (containing all combinations) and create a table for these as well. Main font can't accommodate that much, but there is a system for Japanese version, that uses font pages (separate images) for each stage file. There can be many of such pages in each stage, but you have to add pages with all used glyphs to each stage.

For Japanese it was solved by adding kanas, romaji and some most common kanji to the main font and then adding font pages to each stage (so the font was basically different in each stage and the values of characters in one MSD file meant different glyphs than in another MSD file, in other words, the values are pointing at a particular glyph in a particualr font page, not at a particular character). But with Japanese it was easy, as there was only ~3k characters used in total, with only a small subset per stage. For Korean it actually gets more complicated. This writing system is simple and works great on paper, but becomes nightmare when there is no combining support available. Good riddance hanja are scarcely used in Korean nowadays, as that would complicate things even further .
## Post #34
- Username: prime
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Dec 26, 2017 8:23 pm
- Post datetime: 2018-01-09T14:03:10+00:00
- Post Title: Re: Okami HD PC - Texts files

> Reply from innocentius92
>
> makcar wrote:Zolodei wrote:makcar, dismantled the MSA archive or rebuilt the image?
I used Photoshop to edit dds.

How did you do it? Photoshop does not recognize the DDS file extension.

¿Can you help me, please?
innocentius92, As I said before, You have to install DDS plug-in file to photoshop.

Please refer to this site: [http://gametechdev.github.io/Intel-Text ... ks-Plugin/](http://gametechdev.github.io/Intel-Texture-Works-Plugin/)
(intel texture works plugin)

And if you want to edit MessCore.dds file, you have to edit both RGB and alpha channel.
## Post #35
- Username: ffgriever
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Dec 16, 2017 12:21 am
- Post datetime: 2018-01-11T12:57:17+00:00
- Post Title: Re: Okami HD PC - Texts files

An updated version of tools:

[http://ff12.pl/down/okami-tools-20180111v2.zip](http://ff12.pl/down/okami-tools-20180111v2.zip)

I've added support for PS2 binaries in okami-pack (via -ups2 and -pps2 switches).

I've added support for external character replacement table to okami-msd (via -t=table_file). I've included default table (it's not necessary as it contains exactly the hardcoded table) and Polish table I use for translation. Each line holds one entry in format

```
u16_hex_value=replacement
```


The table supports utf8 (including bom). Malformed lines will be skipped (eg. value greater than u16, no 0x prefix, empty string, etc.). If a particular character is not found, tool will fall back to the hardcoded table. So only entries that have changed (or completely new entries) are required. The "replacement" part doesn't have to be one character. For example:

```
0xb902={button}
```


is a valid entry and will be properly handled by both unpacker and packer. Newline at the end of file is optional.

The normal steps would probably be to export English (or other language) with default table (not specifying it at all is always a bit faster). Then translate in your native language and import with table containing all the glyphs you've used. You don't need to change parts of control/special values, because even if you've replaced it in table, it will still fallback to default table and be resolved properly.

Finally, I've fixed a stupid bug that could cause the tool to end export early or read past the end of file in very specific situations :/. Thanks to @makcar for the heads up.
## Post #36
- Username: faqy
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Jun 16, 2009 5:30 pm
- Post datetime: 2018-01-17T19:34:34+00:00
- Post Title: Re: Okami HD PC - Texts files

> Reply from ffgriever
>
> An updated version of tools:

http://ff12.pl/down/okami-tools-20180111v2.zip

I've added support for PS2 binaries in okami-pack (via -ups2 and -pps2 switches).
I found some files has messed in this version.
Like "data_pc\st0\r011.bin" will cause msd tool crash.
## Post #37
- Username: ffgriever
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Dec 16, 2017 12:21 am
- Post datetime: 2018-01-18T07:59:57+00:00
- Post Title: Re: Okami HD PC - Texts files

These files are not used. On PS2 these directories (AFAIR st0, std and one or two more) were empty.
## Post #38
- Username: MJay
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Aug 11, 2014 7:49 am
- Post datetime: 2018-02-03T14:11:14+00:00
- Post Title: Re: Okami HD PC - Texts files

Hi, can you update the tool to insert .pac files?

Thanks.
## Post #39
- Username: ffgriever
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Dec 16, 2017 12:21 am
- Post datetime: 2018-02-04T12:33:49+00:00
- Post Title: Re: Okami HD PC - Texts files

These files (like EmFileMes.pac or EmFileIcon.dat) have no structure at all. It's just one file appended to another and padded to the length of the largest file rounded up to the nearest 0x800. The padding is not stored within a file (probably in the executable itself), so you need to keep the offsets.

I'm attaching a quick app that works with pac files containing MSD (it won't work for dat files as you would have to check the sizes with dds headers instead of msd headers). You'll need the libraries from my previous tool pack (or mingw64 installed).

BTW. I'm done with the Polish translation and the project has been released.
[okami-mes.7z](https://xentaxbackup.github.io/file/13871_okami-mes.7z)
## Post #40
- Username: MJay
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Aug 11, 2014 7:49 am
- Post datetime: 2018-02-05T14:24:54+00:00
- Post Title: Re: Okami HD PC - Texts files

Thanks. Did you edited the IDDs files?
## Post #41
- Username: ffgriever
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Dec 16, 2017 12:21 am
- Post datetime: 2018-02-05T17:25:00+00:00
- Post Title: Re: Okami HD PC - Texts files

IDD files are handled by okami-pack tool just fine. Just as tbl, pac and many others. It's the structure that matters not the extension. The four applications in my toolset are all that's needed to do a full translation. I didn't have to use anything else.
## Post #42
- Username: SuHeAndZl
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jan 31, 2019 12:08 am
- Post datetime: 2019-02-01T16:32:49+00:00
- Post Title: Re: Okami HD PC - Texts files

> Reply from ffgriever
>
> IDD files are handled by okami-pack tool just fine. Just as tbl, pac and many others. It's the structure that matters not the extension. The four applications in my toolset are all that's needed to do a full translation. I didn't have to use anything else.
hello sorry my English is bad

i want your okami GUI tools please
## Post #43
- Username: weirdalsuperfan
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Apr 23, 2019 5:54 pm
- Post datetime: 2019-06-30T13:33:13+00:00
- Post Title: Re: Okami HD PC - Texts files

> Reply from ffgriever ↑Thu Jan 11, 2018 8:57 pm at Thu Jan 11, 2018 8:57 pm
>
> 
An updated version of tools:

http://ff12.pl/down/okami-tools-20180111v2.zip

I've added support for PS2 binaries in okami-pack (via -ups2 and -pps2 switches).

I have the Japanese PS2 version of the game, and I want to get at the Japanese script. Do you happen to have that? It sounds like you don't yet support custom tables...I also don't know what encoding Okami uses.
Unzipping the iso gives me files like r10b, r120, etc. (with no file extension), a bunch of .DAT files, .SES files, .AFD/.AFS files, some .tm2 files, etc., but nothing explicitly labeled as .MSD, etc.

I'm also not  sure how to run your program in bulk easily.

Details:
I tried running it on the r120 file of mine (and on the corresponding MessR120.MSD file I got from this thread), and while the latter worked well (and gave me English), the former gave me stuff like this, which I guess is because the encoding or this "table" is wrong and so it just spat out a bunch of bytes (I found a couple shift JIS tables, but it seems custom tables aren't supported soooo):
{DialogStart}
{0x0110} {0x0105}   {0x0118} {0x0106}   {0x011c} {0x0204}   {0x012c} {0x0304}   {0x013c} {0x0404}   {0x0180} 

Could you help me with a CLI command, or pointers to how to work with the files from the Japanese game?

I tried using okami-pack.exe but it gave me this
okami-pack.exe -u r120.bin
Number of files: 7
File 001 type MSD offset 00000040 size 10560
File 002 type MSA offset 000029a0 size 592
Error in main: Cannot create output file DATA0\r120.bin_dir\K.

and it only gave me a EFF.MST file because of this crash.
## Post #44
- Username: ffgriever
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Dec 16, 2017 12:21 am
- Post datetime: 2019-07-09T06:31:35+00:00
- Post Title: Re: Okami HD PC - Texts files

The problem with Japanese version is that there is one common font with kana and most commonly used kanji, but each msd file has its own supplementary font (or multiple of these). This means you'd need a separate character table for each location. Each supplementary font has from zero (mostly for menu files) up to over a thousand of characters. I needed Japanese files only for reading, so I didn't bother with that. Instead I just dumped the supplementary fonts into images and used in html. The interesting thing is that the game had furigana embedded. Here are the files I dumped from PS2 version in 2008/2009.

[https://okami.ffgriever.pl/down/jap_furi.7z](https://okami.ffgriever.pl/down/jap_furi.7z)
## Post #45
- Username: Snake128
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue May 12, 2020 11:26 pm
- Post datetime: 2020-06-15T10:46:30+00:00
- Post Title: Re: Okami HD PC - Texts files

> Reply from ffgriever ↑Tue Jul 09, 2019 2:31 pm at Tue Jul 09, 2019 2:31 pm
>
> 
The problem with Japanese version is that there is one common font with kana and most commonly used kanji, but each msd file has its own supplementary font (or multiple of these). This means you'd need a separate character table for each location. Each supplementary font has from zero (mostly for menu files) up to over a thousand of characters. I needed Japanese files only for reading, so I didn't bother with that. Instead I just dumped the supplementary fonts into images and used in html. The interesting thing is that the game had furigana embedded. Here are the files I dumped from PS2 version in 2008/2009.

https://okami.ffgriever.pl/down/jap_furi.7z

Hi ffgriever, I have some problems when I try to pack some folders, I lost file "runofs.ROF" when this has more than 1kb, and the switch version crash.

Have you any solution with this problem.

If we pack with ps2 version we doesn't lose runofs file but doesn't work with pc version pack.

Thanks
## Post #46
- Username: ffgriever
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Dec 16, 2017 12:21 am
- Post datetime: 2020-07-13T14:00:07+00:00
- Post Title: Re: Okami HD PC - Texts files

What do you mean you lost them? Did you try simply unpacking the original files again?

AFAIR, I tested it only on PC version, though, so there might be differences in switch.
## Post #47
- Username: Beridow
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Aug 03, 2020 6:33 pm
- Post datetime: 2020-08-03T11:53:49+00:00
- Post Title: Re: Okami HD PC - Texts files

Hi, can you update the tool to insert .pac files?
## Post #48
- Username: Snake128
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue May 12, 2020 11:26 pm
- Post datetime: 2020-08-14T16:42:52+00:00
- Post Title: Re: Okami HD PC - Texts files

> Reply from ffgriever ↑Mon Jul 13, 2020 10:00 pm at Mon Jul 13, 2020 10:00 pm
>
> 
What do you mean you lost them? Did you try simply unpacking the original files again?

AFAIR, I tested it only on PC version, though, so there might be differences in switch.

Hi, i have my okamihd spanish translation in advance.

Thanks a lot for your excelent work. 
I want to quote you in my work like a romhacking worker.

I use your name: ffgriever if you want.
## Post #49
- Username: Mstr Samuel
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Aug 18, 2023 2:27 am
- Post datetime: 2023-08-17T18:32:09+00:00
- Post Title: Re: Okami HD PC - Texts files

> Reply from ffgriever ↑Thu Jan 11, 2018 8:57 pm at Thu Jan 11, 2018 8:57 pm
>
> 

hi, it's look like the tool needs to get update, it's look like won't open in windows 10
