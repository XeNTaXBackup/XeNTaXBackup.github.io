## Post #1
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2010-11-26T20:55:35+00:00
- Post Title: A New Beginning VIS/VC???/VS???

Until the Wiki is up and running again, I thought I'd share some bits of information for A New Beginning here.


I. General information

[A New Beginning](http://www.anewbeginning-game.com/) is an adventure game based on the [Visionaire engine](http://www.visionaire-studio.net/). Luigi Auriemma already has a BMS to handle the basic format, as can be seen in [this thread](http://forum.xentax.com/viewtopic.php?f=10&t=4407). However, there is still some interesting information to be retrieved by taking a closer look.


II. Relevant files

The interesting game files, which all share the same VIS format (despite their extensions) are these:
data.vis (the main archive)
characters\character.vc???
scenes\scene.vs???

Additionally, there are cutscene videos in videos\video.vv???, but these are just renamed OGV files.


III. File naming

The directory of the VIS archive format does not support storing the names of the files contained within the archive. However, the main archive data.vis contains exactly one file in XML format (type identifier 3), which servers as an entry point for the Visionaire engine. Beside other information, it contains the actual names of the files found in the VIS archives. The file names are always followed by a plaintext indicator telling the engine in which archive the file is located:

```
path\filename.ext#x#nnn#kkkkk#
```
 In this pattern, "x" is a single character that identifies the logical archive type. It is usually also found in the extension of the archive: "c" stands for "characters\character.vc???", "s" for "scenes\scene.vs???". The number "nnn" identifies the actual archive number ("???" in the previous examples), "kkkkk" is the running number within the archive structure.

Example:

```
speech\de\standards\bent\Strd_Bent_22.ogg#c#068#00020#
```
 The file "speech\de\standards\bent\Strd_Bent_22.ogg" is the 20th entry in the archive "characters\character.vc068".

There is one exception: The logical archive type "m" does not refer to an archive, but to one of the renamed videos:

```
cutscenes\01-05\cutscene_01-05_02-02.ogv#m#026#00000#
```
 The video "cutscenes\01-05\cutscene_01-05_02-02.ogv" can be found under the name "videos\video.vv026".


IV. Encryption

Aside from the encryption of the directory information in the VIS archives, an additional encryption is applied to the content of PNG files: The width and height information (8 successive bytes) in the IHDR structure are XOR-encrypted using a lower-case hexadecimal character string. The key is derived from the MD5 hash of the file name (without path and extension) in UTF-16 format.

Example: The image dimensions of the file "Chars\tuersteher\5004_Ohr_Knopf\Ohr_09.png" have been encrypted. The key are the first 8 characters of MD5(UTF-16("Ohr_09")) = 1a7d8961481e341504f3efB6e7f6231d, i.e. 1a7d8961.

(The correctness of the key can be verified by checking the CRC32 of the IHDR chunk after decryption. If everything else fails, it can also be brute-forced via the CRC in reasonable time using some sensible assumptions.)


V. Tools

A proof-of-concept unpacker/extractor for the VIS archives as found in A New Beginning (possibly also other games built with the Visionaire engine?), which considers the above points is my [VISExt](http://oezmen.eu/gameresources/) command-line application.


Best wishes,
Deniz
## Post #2
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-11-27T07:25:43+00:00
- Post Title: A New Beginning VIS/VC???/VS???

Nice work, Deniz!
I especially liked your brilliant, png brute-force cracking idea!
## Post #3
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2010-11-27T18:19:52+00:00
- Post Title: A New Beginning VIS/VC???/VS???

Thanks, bacter. However, most of the credit goes to Luigi, since he had already published most of the VIS format description including the basic encryption algorithm. I just filled in the details mentioned above.

The brute-force method was originally necessary when I didn't yet know how the key for each file was generated. It should hopefully be obsolete by now. I wonder if the engine makers decided to implement this small "mangling" in order to thwart usage of generalized ripper programs ...
## Post #4
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2010-11-28T02:45:53+00:00
- Post Title: A New Beginning VIS/VC???/VS???

Can i ask a question? How to rip the subtitle files from the game?
And is there  anyway to repack it back?
## Post #5
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-11-28T04:45:47+00:00
- Post Title: A New Beginning VIS/VC???/VS???

The game texts are also stored inside that one huuuuuuge XML file inside the data.vis file.
The .XML reinserting to the .VIS is easy, but the tricky way is to edit that big (50 megabyte or so) file.
## Post #6
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2010-11-28T11:07:10+00:00
- Post Title: A New Beginning VIS/VC???/VS???

I was told that you could run the game from the extracted XML file as well, so repacking might not even be necessary. Try and edit config.ini in the game installation directory and have the "FILE" parameter point to your edited XML file instead of "data.vis".

I haven't tried this myself, so I'm not sure whether all the other resources have to be unpacked as well. If yes, you might have to edit the XML file to remove the archive designators (i.e. that "#x#nnn#kkkkk#" stuff).

Unfortunately for us, all identifiers in the XML file have been replaced by generic names (e.g. "T700", "T15", ...) during the compilation process, such that the Visionaire Editor will not load the file. Otherwise, one could use the Editor to modify the game.
## Post #7
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2010-11-28T13:38:15+00:00
- Post Title: A New Beginning VIS/VC???/VS???

I have another question.

For example: 

in the xml the file name is
T257="speech\de\scenes\ch3\3012\3012_03_20_01.ogg#s#035#00016#"

The file extracted by VISExt.exe is:
\speech\de\scenes\ch3\3012\3012_03_20_01#s#035#00016#.ogg

if i want to run the game from the extracted XML file,
what i need to do is 

1.edit the config.ini as you said.
2.edit the T257="speech\de\scenes\ch3\3012\3012_03_20_01.ogg#s#035#00016#"
  to T257="speech\de\scenes\ch3\3012\3012_03_20_01.ogg"
3.rename the file \speech\de\scenes\ch3\3012\3012_03_20_01#s#035#00016#.ogg
  to \speech\de\scenes\ch3\3012\3012_03_20_01.ogg

That's right?
## Post #8
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2010-11-28T19:24:14+00:00
- Post Title: A New Beginning VIS/VC???/VS???

In theory, yes. As I said, I didn't test it yet, but got this information from somebody else. 

Note: I changed the VISExt application a bit, so that it extracts the files without the identifier by default, i.e. "speech\de\scenes\ch3\3012\3012_03_20_01.ogg" in the example above. If you want to recreate the old behaviour, use the switch "/unique".
## Post #9
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2010-11-28T23:54:57+00:00
- Post Title: A New Beginning VIS/VC???/VS???

> Reply from Deniz Oezmen
>
> In theory, yes. As I said, I didn't test it yet, but got this information from somebody else. 

Note: I changed the VISExt application a bit, so that it extracts the files without the identifier by default, i.e. "speech\de\scenes\ch3\3012\3012_03_20_01.ogg" in the example above. If you want to recreate the old behaviour, use the switch "/unique".

OK, thank you very much, i will take a try.
## Post #10
- Username: matingsm
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Oct 30, 2010 6:55 pm
- Post datetime: 2011-01-26T09:47:19+00:00
- Post Title: A New Beginning VIS/VC???/VS???

hi friends
One is the process for me to fully explain
thanks.very very thanks
## Post #11
- Username: strizek
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Apr 07, 2012 2:34 am
- Post datetime: 2012-06-12T19:09:32+00:00
- Post Title: A New Beginning VIS/VC???/VS???

Hello friends,

  Have you a deal with font ? I need to replace some characters, but i find only some font characters in XML file (when i change them, then game has error)

Thanks
## Post #12
- Username: strizek
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Apr 07, 2012 2:34 am
- Post datetime: 2012-06-12T19:43:55+00:00
- Post Title: A New Beginning VIS/VC???/VS???

in data.vis in xls file are theese parts:

<T141 T12="Kaffeesatz" T13="8" T14="0" T249="!"#$%&&apos;()*+,-./0123456789:;<=>?@ABCDEFGHIJKLMNOPQRSTUVWXYZ[\]^_`abcdefghijklmnopqrstuvwxyz{|}~€µÜÄÖüäößŠŽšž©™°ÀÁÂÆÇÈÉÊËÎÏÔŒÙÛŸàáâæçèéêëîïôœùûÿÌÍÒÓÚÑìíòóúñ«»¡¿юабцдефгхийклмнопярстужвьызшэщчъЮАБЦДЕФГХИЙКЛМНОПЯРСТУЖВЬЫЗШЭЩЧЪёЁĄĆĘŁŃÓŚŹŻąćęłńóśźż" T540="0" T250="-3" T634="T" T623="10" T635="500">
			<T248 T12="" T32="-1" T7="Interface\fonts\interface.png#v#-01#02027#" T50="2">

From czech special characters working only ŠŽšž as seen in second line.... When i try to change it, game not working...

i look on bottom line: Interface\fonts\interface.png#v#-01#02027#"   then file will be in DATA.VIS and will be   00002027.PNG ????

When i try to calc MD5 utf-16 checksum (word is interface) - then C9AF27F7 is on start. BUT PNG not working, after putting theese characters after IHDR word... Where i have problem ?

Thank you

Filip
[00002027.png](https://xentaxbackup.github.io/file/5492_00002027.png)
## Post #13
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2012-07-13T22:57:08+00:00
- Post Title: A New Beginning VIS/VC???/VS???

I haven't done modifications to the game myself, so I probably can't help you there.

Regarding the encryption, however: You got the MD5 for this particular PNG file correctly. Now convert it to lower-case, i.e. to "c9af27f7". This is the key to encrypt or decrypt the 8 bytes after the IHDR marker. So you don't put it there all by itself, but you apply an XOR between each character of the key and the corresponding byte in the PNG header structure.

During unpacking, VISExt does the decryption for you. When unpacked, I would assume that it is not necessary to apply the encryption scheme to your modified PNG files, but I could be wrong there.
