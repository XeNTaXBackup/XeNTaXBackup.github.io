## Post #1
- Username: invisible
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Jul 10, 2005 4:45 am
- Post datetime: 2005-07-09T20:51:53+00:00
- Post Title: BAG file in Brian Lara International Cricket 2005

Can anyone tell how to edit the *.BAG files in brian lara International cricket 2005 demo?
I tried to open the *.bag files using game extractor,total commander,multiex commander etc.. but none of them were able to read the *.bag files.SO kindly help how to extract the files from the *.bag archive.

Link for the game ->

[http://www.codemasters.co.uk/brianlara/index.php](http://www.codemasters.co.uk/brianlara/index.php)
## Post #2
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-07-09T22:27:13+00:00
- Post Title: BAG file in Brian Lara International Cricket 2005

You can attach small example archive ?
Thanks
## Post #3
- Username: invisible
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Jul 10, 2005 4:45 am
- Post datetime: 2005-07-09T22:42:47+00:00
- Post Title: BAG file in Brian Lara International Cricket 2005

The contents of this post was deleted because of possible forum rules violation.
## Post #4
- Username: invisible
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Jul 10, 2005 4:45 am
- Post datetime: 2005-07-09T23:39:10+00:00
- Post Title: BAG file in Brian Lara International Cricket 2005

this is what i get in Game extractor


Replace.bag is  105MB

So kindly help
## Post #5
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-07-10T02:01:28+00:00
- Post Title: BAG file in Brian Lara International Cricket 2005

Your version Game Extractor 1.52 .... Now version Game Extractor 1.5201
Download Update ->>> [http://gameextractor.sf.net/update15/upd15201.jar](http://gameextractor.sf.net/update15/upd15201.jar)
## Post #6
- Username: invisible
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Jul 10, 2005 4:45 am
- Post datetime: 2005-07-10T17:50:35+00:00
- Post Title: BAG file in Brian Lara International Cricket 2005

> Reply from KorNet
>
> Your version Game Extractor 1.52 .... Now version Game Extractor 1.5201
Download Update ->>> http://gameextractor.sf.net/update15/upd15201.jar
its not able to open bag files(even after update)
## Post #7
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-07-10T19:22:29+00:00
- Post Title: BAG file in Brian Lara International Cricket 2005

[http://www.watto.org/extract/download.html#updates](http://www.watto.org/extract/download.html#updates)
look this
## Post #8
- Username: invisible
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Jul 10, 2005 4:45 am
- Post datetime: 2005-07-10T21:03:14+00:00
- Post Title: BAG file in Brian Lara International Cricket 2005

> Reply from KorNet
>
> http://www.watto.org/extract/download.html#updates
look this
yes man i updated it.But still its not able to open those bag files
can anyone open those bag files?
I will be very thankful for your effort as im looking to mod this game
## Post #9
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-07-11T01:38:43+00:00
- Post Title: BAG file in Brian Lara International Cricket 2005

Hi mate,

Yeah game extractor obviously can't open the archive - as is indicative of the funny filenames. However we can try to add the support if we can get a look at the archive.

As the archive is quite large, you can use one of our file cutter tools to give us the information we need. Mr Mouse's tool can be found in his signature, or you can use mine from [http://www.watto.org/extract/download/cutter.zip](http://www.watto.org/extract/download/cutter.zip) . Both programs do the same thing - they just take a piece of the archive and then zip it up for us - then all you need to do is post it here on the forums and we will take a look at it.

Thanks mate.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #10
- Username: invisible
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Jul 10, 2005 4:45 am
- Post datetime: 2005-07-11T02:06:31+00:00
- Post Title: BAG file in Brian Lara International Cricket 2005

I submitted two files ( around 1MB) check my previous posts.(my second post)

and im attaching one more file created with file splitter

Hope u can do it soon
[GameData.bag.zip](https://xentaxbackup.github.io/file/348_GameData.bag.zip)
## Post #11
- Username: invisible
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Jul 10, 2005 4:45 am
- Post datetime: 2005-07-11T13:50:30+00:00
- Post Title: BAG file in Brian Lara International Cricket 2005

Sorry i came up this when searching in google and any progress?

BAG ARCHIVE FILE FORMAT V1.1
by Jeff Connelly

The main goal of bag archives is to provide a simple and efficant way to
combine many files into one.  For that reason, it is extreamly simple.

The header is at the beginning of the file:
OFFSET             Count TYPE   Description
0000h                  3 char   ID='BAG'
0003h                  2 char   Version, ID='11'

There is one file block for each file:
OFFSET             Count TYPE   Description
0000h                  1 dword  File length in bytes
0004h                  1 byte   Filename length
????h                  ? char   Filename
????h                  ? char   File contents

At the very end of the file is:
OFFSET             Count TYPE   Description
0000h                  1 char   EOF marker, ID=1A

A file length of zero in a file block indicates a special file that will be
used as a description.  Directorys are also stored in the filename field:
    Filename='> dirname' means change current directory to 'dirname'.
For example,
Filename='> JEFF'
Filename='> COMPUTER'
Filename='> BAG'
Would make the directory be JEFF\COMPUTER\BAG.  Files are put in the current
directory.

The files contents is not always raw data, it can be compressed.  A
four-byte
signature can specifiy the compression scheme:
---- Compression ----
LZW     LZW encoded (note extra space at end)
RLEn    RLE method N (1 to 4) encoded
HUFF    Huffman encoded
LZHF    LZHUF encoded (LZSS + Arithmetic) (Note - the authors of LZHUF to
        not allow using is for any commicial purpose)
LZAR    LZARI encoded (LZSS + Huffman)
WCOD    Word coded -- text only
If no signature is found it is assumed to be raw data.

The word coding compression is as follows:
* Initalize dictionary (max. size FFFF)
* Loop until end-of-file
  * Read a space-delimited word from the input stream
  * Search for the word in the dictionary
    * If it is not there, add it to the first free space and output location
      of where in the dictionary the word was added as a 16-bit integer.
    * If it is there, output the location of where it is as a 16-bit
integer.
* Write dictionary at end of file.  Each word is null-terminated, whole
  dictionary is double-null terminated.
This means that each word will be encoded as 2 bytes.

The last character is an end-of-file character to insure the whole file was
recived when transfering this archive.
## Post #12
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-07-12T14:51:02+00:00
- Post Title: BAG file in Brian Lara International Cricket 2005

Just removing a duplicated post - not sure why its here twice. See the next post.
## Post #13
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-07-12T14:51:49+00:00
- Post Title: BAG file in Brian Lara International Cricket 2005

Hmm nah unfortunately most game archives are different - the specs you posted are not correct for this game.

Anyway attached is a plugin for Game Extractor to open the *.bag archives, but I think it only opens some of them. Just unzip the attachment into your plugins/ directory.

Good luck!

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
[Plugin_BAG.zip](https://xentaxbackup.github.io/file/354_Plugin_BAG.zip)
## Post #14
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-07-12T15:07:36+00:00
- Post Title: BAG file in Brian Lara International Cricket 2005

Mr Mouse,

Here is a script I wrote that works fully for the format, however the offsets are wrong. This is because the offsets start from the end of the directory + padding, so somehow this needs to be calculated before doing the FOR loop. However, I am not sure whether you have a modulous operator in MexScript because you need to calculate the size of the padding between the directory and the first file. So please correct this before using this script, if it is at all possible. See the wiki for better details.

```
Goto 4 0 ;
Get FNum Long 0 ;
Set CalcFour Long FNum ;
Math CalcFour *= 4 ;
Set LenDirOff Long CalcFour ;
Math LenDirOff += 8 ;
Set NameDirOff Long LenDirOff ;
Math NameDirOff += CalcFour ;
Set OffDirOff Long FNum ;
Math OffDirOff *= 64 ;
Math OffDirOff += NameDirOff ;
For n = 1 to FNum ;
Goto LenDirOff 0 ;
SavePos FSO 0 ;
Get FS Long 0 ;
Math LenDirOff += 4 ;
Goto NameDirOff 0 ;
Get FN String 0 ;
Math NameDirOff += 64 ;
Goto OffDirOff 0 ;
SavePos FOO 0 ;
Get FO Long 0 ;
Math OffDirOff += 4 ;
Log FN FO FS FOO FSO ;
Next n ;

```


WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #15
- Username: invisible
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Jul 10, 2005 4:45 am
- Post datetime: 2005-07-12T18:33:13+00:00
- Post Title: BAG file in Brian Lara International Cricket 2005

Yes the given plugin is not working with this game
## Post #16
- Username: invisible
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Jul 10, 2005 4:45 am
- Post datetime: 2005-07-15T15:02:07+00:00
- Post Title: 

After a lot of waiting i couldn't resist myself in making my own BAG viewer.ANd thanks to all those who replied.I appreciate it.
If anyone wants the BAG viewer which supports only uncompressed bag files, I will post it
## Post #17
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-07-15T17:02:17+00:00
- Post Title: 

You waited 6 days

That's not a real lot, is it. We do have jobs to do, families to be with, other stuff to program and organize, friends to see and relax. 

But it's good that you wrote your own extractor though!  

Why not put it up the wiki as a Game Specific Tool?

[http://wiki.xentax.com/](http://wiki.xentax.com/) , much appreciated.
## Post #18
- Username: invisible
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Jul 10, 2005 4:45 am
- Post datetime: 2005-07-15T17:24:07+00:00
- Post Title: 

Currently the viewer supports only uncompressed bag files. I hope either me or someone can fix this soon.

Here it is BAG viewer
[http://rapidshare.de/files/3082466/BLIC ... r.exe.html](http://rapidshare.de/files/3082466/BLIC_BagViewer.exe.html)

To view the .dds files in Photoshop you will need a plugin. More information about this plug-in can be viewed at [http://developer.nvidia.com/object/phot ... ugins.html](http://developer.nvidia.com/object/photoshop_dds_plugins.html)
(direct download link)

[http://download.nvidia.com/developer/NV ... 9.1500.exe](http://download.nvidia.com/developer/NVTextureSuite/Photoshop_Plugins_7.83.0629.1500.exe)
