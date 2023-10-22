## Post #1
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2011-03-27T14:20:22+00:00
- Post Title: Help with Mystery of Mortlake Mansion .pack file

Any one can help me with extracting .pack file of Mystery of Mortlake Mansion?
A small sample has been attached. Thanks.

the trial version is here
[http://www.bigfishgames.com/download-ga ... index.html](http://www.bigfishgames.com/download-games/10448/mystery-of-mortlake-mansion/index.html)
[sample.rar](https://xentaxbackup.github.io/file/4119_sample.rar)
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-03-27T17:04:04+00:00
- Post Title: Help with Mystery of Mortlake Mansion .pack file

unknown compression.
if someone is interested I have attached the script for the format but it will not work without the compression, so it's only for future usage
[test.zip](https://xentaxbackup.github.io/file/4120_test.zip)
## Post #3
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2011-03-27T23:59:01+00:00
- Post Title: Help with Mystery of Mortlake Mansion .pack file

Some addition infomation for this file,it used this library to compress it.

[http://www.icsharpcode.net/OpenSource/S ... fault.aspx](http://www.icsharpcode.net/OpenSource/SharpZipLib/Default.aspx) 
[http://sourceforge.net/projects/sharpde ... arpZipLib/](http://sourceforge.net/projects/sharpdevelop/files/SharpZipLib/)
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-03-28T10:49:41+00:00
- Post Title: Help with Mystery of Mortlake Mansion .pack file

it's not zlib otherwise was a joke to do it :)
I give you an example, the code first reads the 5 bytes at the beginning of each compressed block (no it's not lzma)
## Post #5
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2011-03-29T16:56:26+00:00
- Post Title: Help with Mystery of Mortlake Mansion .pack file

I think there is no compression (well maybe inside decrypted pack archive), but data are xored. But there is not easy to get xor table. For example bin\*.bin are obfuscated dll files. File name is obfuscated and content is xored based on xor table generated for every file using file name as key and some Mersenne Twister random values table. So imho the pack content is based on this too and it will take some time to break it.
## Post #6
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2011-03-30T19:13:34+00:00
- Post Title: Help with Mystery of Mortlake Mansion .pack file

LOL, it is so funny, password for decrypt pack file is:

```
erax_pass__защита_от_взлома__fuck_off__{0D6D6FA9-4CC4-47e2-BBC5-6461224D4E01}__ls_res_protection1982_жыли_были_дед_и_баба_ели_кашу_с_молоком_Дед_На_Бабу_Разсердился_И_По_Пузу_Кулаком
```


Well, I have decrypted file, but I have no extractor yet. And because I don't think I'm going to make one, here is decrypted file. You can make bms script for extracting. It uses LZMA compression if I remember.

```
http://www.filesonic.com/file/421851584/DataOut.rar
```
## Post #7
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2011-03-31T04:59:13+00:00
- Post Title: Help with Mystery of Mortlake Mansion .pack file

> Reply from XRaptor
>
> LOL, it is so funny, password for decrypt pack file is:
Code: Select allerax_pass__защита_от_взлома__fuck_off__{0D6D6FA9-4CC4-47e2-BBC5-6461224D4E01}__ls_res_protection1982_жыли_были_дед_и_баба_ели_кашу_с_молоком_Дед_На_Бабу_Разсердился_И_По_Пузу_Кулаком

Well, I have decrypted file, but I have no extractor yet. And because I don't think I'm going to make one, here is decrypted file. You can make bms script for extracting. It uses LZMA compression if I remember.
Code: Select allhttp://www.filesonic.com/file/421851584/DataOut.rar

Thank you very much.
## Post #8
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2011-04-04T02:17:31+00:00
- Post Title: Help with Mystery of Mortlake Mansion .pack file

I made a bms script of it,but can't decompress correctly.
Can anyone can tell the correct comtype of bms?

My script is here:

```
#filename       nbytes
#size   8bytes
#zsize  8bytes
#offset 8bytes
#flag   1bytes  folder:0  file:1

get FILES long
goto 9

for i = 0 < FILES
    get NAME_LEN1 byte
    get NAME_LEN byte
    getdstring FNAME NAME_LEN
    get SIZE longlong
    get ZSIZE longlong
    get OFFSET longlong
    get FLAG byte
    comtype lzma_compress
    clog FNAME OFFSET ZSIZE SIZE
next i

```
## Post #9
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2011-04-04T06:58:21+00:00
- Post Title: Help with Mystery of Mortlake Mansion .pack file

Well, maybe file is not completly decrypted, but it should be. Or maybe there is another encryption in data block. I can take a look on it again.
## Post #10
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2011-04-13T16:22:52+00:00
- Post Title: Help with Mystery of Mortlake Mansion .pack file

Funnily enough, I've been working on a extractor for it. It directly uses the game engine to extract the files. I'll upload ASAP.

@aluigi: It is lzma. It uses a 7zip implementation too.
@stevenx: Looks like the SharpZip lib is a decoy. It's not applicable to the .pack files.
## Post #11
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2011-04-13T18:27:09+00:00
- Post Title: Help with Mystery of Mortlake Mansion .pack file

The contents of this post has been restored from another site that mirrored this post, since I never got a response about getting the contents back. Third party download links have been stripped and replaced with link to forum thread.

If you have already deobfuscated all of the .bin files (see below), use LuckySoftUnpack.exe. Otherwise, drag the .bin file from the package into the bin folder of the game (..\MysteryOfMortlakeMansion\bin). Then open a command prompt, cd to the bin directory, and type "startup.bin luckysoftunpack" and your command line arguments.)

To use:
- Prepare your key. Find the decryption key, copy it into your favorite text editor, and save it as a Unicode text file.
- cd to the game directory
- Type "LuckySoftUnpack.exe /in Data.pack /keyfile keyfilepath /extract", where keyfilepath is the path to your key file, to extract all files into the directory Data_decrypted.pack in the working directory.
- Type "LuckySoftUnpack.exe /in Data.pack /keyfile keyfilepath" to only decrypt the file to a LzmaPack, named Data_decrypted.pack in the working directory.
- You can use the switch "/key" to specify the key on the command prompt (type it out).
- You can use the switch "/noencryption" if the file is not encrypted.
- You can use the switch "/out" to specify the output directory/file.
- Leave the arguments blank to see usage.
- If you are using the obfuscated version, type "Startup.bin LuckySoftUnpack" and your arguments instead, and adjust your paths accordingly.

Make your own obfuscated file: Run Startup.bin with the "--obf" switch and your unobfuscated filename. Then it will obfuscate your file properly. Since it does an XOR operation, this method was used in deobfuscating the obfuscated .bins once the filenames were deobfuscated.

See download on LuckySoft/Stella Games Utilities thread: [viewtopic.php?f=32&t=7838](http://forum.xentax.com/viewtopic.php?f=32&t=7838)

Update log:
12/04/2012 (1.1.0.0)
- Some code cleanup: now faster
- Linked with Secrets of Power: Alexander the Great
04/13/2011 (1.0.2.0)
- Added detection for having both key and "/noencryption" specified
- Removed commented out key from source
- Synchronized sources in both VS2008 and VS2005 directories
04/13/2011 (1.0.1.0)
- Initial release
## Post #12
- Username: gambit37
- Rank: n00b
- Number of posts: 17
- Joined date: Fri Nov 05, 2010 11:27 am
- Post datetime: 2011-04-14T14:58:48+00:00
- Post Title: Help with Mystery of Mortlake Mansion .pack file

Interesting stuff! But what does "Prepare your key. Find the decryption key" mean -- how do we do that?
## Post #13
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2011-04-14T16:23:23+00:00
- Post Title: Help with Mystery of Mortlake Mansion .pack file

> Reply from gambit37
>
> Interesting stuff! But what does "Prepare your key. Find the decryption key" mean -- how do we do that?

Well, I suppose you can find the key. It's a few posts above. Copy and paste it into a text editor, and save it as a Unicode text file. Then supply it to the unpacker.
## Post #14
- Username: gambit37
- Rank: n00b
- Number of posts: 17
- Joined date: Fri Nov 05, 2010 11:27 am
- Post datetime: 2011-04-14T17:01:42+00:00
- Post Title: Help with Mystery of Mortlake Mansion .pack file

Oh right *doh!* Thanks, I'm interested to try this out.
## Post #15
- Username: warwar
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Jun 04, 2011 3:36 pm
- Post datetime: 2011-06-04T08:03:55+00:00
- Post Title: Help with Mystery of Mortlake Mansion .pack file

i use tool unpack the .pack file,but i  find font define file is encryption , i can't read it

here is samples

can anyone help me?
[fonts.zip](https://xentaxbackup.github.io/file/4293_fonts.zip)
## Post #16
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2011-07-02T22:45:48+00:00
- Post Title: Re: Help with Mystery of Mortlake Mansion .pack file

> Reply from warwar
>
> i use tool unpack the .pack file,but i  find font define file is encryption , i can't read it
It's not encrypted, just serialized. I've made a serialization format converter (there are three types of serializations the game can read: binary, formatted, and compact), but I haven't packaged it (I need to make an installer with file extension registration). If I have a moment, I'll convert the files for you.

[s]BTW, what directory were those files from? I've been looking for the fonts too, but it's like finding a needle from a haystack. It was from Mortlake Mansion, I presume?[/s] Got it, it's in system.font.

Update: here's the formatted UData.

<link removed due forum rules violation>
## Post #17
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2011-07-04T04:53:38+00:00
- Post Title: Re: Help with Mystery of Mortlake Mansion .pack file

This post used to talk about Stella Games UData Binary/Udl Transcoder. No one seemed to have made a copy of this post, and I'm too lazy to reconstruct it. See LuckySoft/Stella Games Utilities thread for the tool that was originally linked here. [viewtopic.php?f=32&t=7838](http://forum.xentax.com/viewtopic.php?f=32&t=7838)
## Post #18
- Username: warwar
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Jun 04, 2011 3:36 pm
- Post datetime: 2011-07-13T00:33:09+00:00
- Post Title: Re: Help with Mystery of Mortlake Mansion .pack file

Thank you for your tool, it solves my problem, I can now start translating the game, and again salute you.
## Post #19
- Username: luluxiu
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jul 18, 2011 6:41 pm
- Post datetime: 2011-07-19T06:14:15+00:00
- Post Title: Re: Help with Mystery of Mortlake Mansion .pack file

The contents of the file name is confusing and different, or XOR tables for each key and produced some of Mason Twister random value table used in file names based on. So, IMHO, the contents of the package is on this basis will also need some time to break it.
[undecided.gif](https://xentaxbackup.github.io/file/4513_undecided.gif)
