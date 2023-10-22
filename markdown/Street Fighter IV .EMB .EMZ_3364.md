## Post #1
- Username: Itze
- Rank: veteran
- Number of posts: 81
- Joined date: Sat Mar 15, 2008 11:43 pm
- Post datetime: 2009-02-21T11:59:52+00:00
- Post Title: Street Fighter IV .EMB .EMZ

I tried editing the files of the xbox360 version, but since the pc version is coming out next month this should be a nice headstart 

The .emb files are simple container files which are mostly used for the unlockable gallery images and menu backgrounds etc.

They contain standart .dds files that can be extracted using the usual tools...

And then there the .EMZ files which are the interesting ones

They are used for the character models, textures and all other interesting files... they are either just compressed or encoded, i couldn't make much sense from the hex :/

I have uploaded one emb and one emz file so you guys can check it out and maybe tell me how i can extract stuff from the emz file

[http://www.yourfilelink.com/get.php?fid=487148](http://www.yourfilelink.com/get.php?fid=487148)
## Post #2
- Username: Crypton
- Rank: advanced
- Number of posts: 60
- Joined date: Sat Aug 09, 2008 6:19 pm
- Post datetime: 2009-03-06T10:23:00+00:00
- Post Title: Street Fighter IV .EMB .EMZ

Always remember to upload 2 files for every format you want to extract, from one file its hard to find a format structure...
## Post #3
- Username: cTWOpLaY
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Mar 06, 2009 5:13 am
- Post datetime: 2009-03-06T19:38:33+00:00
- Post Title: Street Fighter IV .EMB .EMZ

so how did you extract the .emb's? and the .dds's? not to sure what the usual tools are as i've never seen these file formats before and they aren't typical archives..

sry for being so full of questions
## Post #4
- Username: Itze
- Rank: veteran
- Number of posts: 81
- Joined date: Sat Mar 15, 2008 11:43 pm
- Post datetime: 2009-07-05T04:00:13+00:00
- Post Title: Street Fighter IV .EMB .EMZ

i recently got the pc version of sf iv and now we got some files to compare 

i've uploaded an archive with various files from the pc and xbox360 version:
[http://www.yourfilelink.com/get.php?fid=500636](http://www.yourfilelink.com/get.php?fid=500636)

i found some UNCOMPRESSED files in the 360 version that are compressed in the pc version 

And as i thought .EMB files are just simple containers:
[](http://img127.imagevenue.com/img.php?image=66165_emb_container_122_259lo.jpg)

here's the main menu background which i've successfully extracted:
[](http://img212.imagevenue.com/img.php?image=66290_bg_main_122_80lo.jpg)

.EMB's can also contain other EMB's and EMZ's

the .EMZ files are definately compressed... maybe Z for zlib or zipped? :X

Please help me figuring out the EMZ format, i really want to edit this game
## Post #5
- Username: Itze
- Rank: veteran
- Number of posts: 81
- Joined date: Sat Mar 15, 2008 11:43 pm
- Post datetime: 2009-07-05T04:16:55+00:00
- Post Title: Street Fighter IV .EMB .EMZ

OH MY GOD!!!
I'm so good! 

i played around a bit with Luigis offzip and with the following commandline i was able to extract this mofo 

offzip.exe -m 16 -a -z -15 bg_main.emz blah 0

```
 -z -15 bg_main.emz blah 0

Offset file unzipper 0.3.3
by Luigi Auriemma
e-mail: aluigi@autistici.org
web:    aluigi.org

- open input file:    bg_main.emz
- enter in directory: blah
- zip data to check:  16 bytes
- zip windowBits:     -15
- seek offset:        0x00000000  (0)

+------------+-------------+-------------------------+
| hex_offset | blocks_dots | zip_size --> unzip_size |
+------------+-------------+-------------------------+
  0x00000010 ...................................................................
................................................................. 268466 --> 460
992


- 1 valid zip blocks found

```

[](http://img107.imagevenue.com/img.php?image=68013_bytes_122_587lo.jpg)
the byte order seems to be swapped between the xbox and pc version but apart from that my extracted pc "emb" is exactly the same as the one that came with the xbox360 version   

gotta play some more now... the first step is done 

EDIT:
[](http://img237.imagevenue.com/img.php?image=68690_00000000015infuser364_122_392lo.jpg)

YAY seems to work with all EMZ's so far  

from ryu's common file:
RYU.skl.emo
RYU.skl.emm
RYU.obj.ema
RYU.fce.ema
RYU.cam.ema
RYU.bac
RYU.bcm

Model extraction might be possible
## Post #6
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-07-05T04:44:36+00:00
- Post Title: Street Fighter IV .EMB .EMZ

here is a quickbms script
Ill update the file name soon.

```
get unkown long
get SIZE long
set NAME fname.emb
get ZSIZE asize
math ZSIZE -= 0x10
goto 0x10
savepos OFFSET
comtype inflate
clog NAME OFFSET ZSIZE SIZE
```
## Post #7
- Username: Itze
- Rank: veteran
- Number of posts: 81
- Joined date: Sat Mar 15, 2008 11:43 pm
- Post datetime: 2009-07-05T04:59:22+00:00
- Post Title: Street Fighter IV .EMB .EMZ

nice!

is it possible to recompress with quickbms so i can try inserting modified files again(first only textures)?
## Post #8
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-07-05T05:08:31+00:00
- Post Title: Street Fighter IV .EMB .EMZ

```
idstring "#EMZ"
get unkown long
get SIZE long
get NAME filename
set EXT string .emb
string NAME -= .emz
string NAME += EXT
get ZSIZE asize
math ZSIZE -= 0x10
goto 0x10
savepos OFFSET
comtype inflate
clog NAME OFFSET ZSIZE SIZE
```


It is not possible with quickbms but it is just using the inflate compression so another program should do that no problem
have you tried just removing the .emz and see if it loads the emb?
## Post #9
- Username: Itze
- Rank: veteran
- Number of posts: 81
- Joined date: Sat Mar 15, 2008 11:43 pm
- Post datetime: 2009-07-05T05:48:31+00:00
- Post Title: Street Fighter IV .EMB .EMZ

Yeah, it just gets stuck on "Now Loading" forever :/

What program could i use to recompress the emb so it looks exactly like the extracted one before decompression?

EDIT:
OWNED!

[](http://img176.imagevenue.com/img.php?image=81987_yay_122_118lo.jpg)

No need to recompress the files... just rename the extracted .emb to .emz and the game will load them 

You can make texture mods with my infusion program:
[viewtopic.php?f=13&t=3363](http://forum.xentax.com/viewtopic.php?f=13&t=3363)
## Post #10
- Username: Itze
- Rank: veteran
- Number of posts: 81
- Joined date: Sat Mar 15, 2008 11:43 pm
- Post datetime: 2009-07-05T14:16:49+00:00
- Post Title: Street Fighter IV .EMB .EMZ

I'm working on the models now...

[](http://img101.imagevenue.com/img.php?image=03250_wrong_122_7lo.jpg)

Model editing gone wrong... looks like ryu's fireball melted half her face off  :uglyeye: 

I also broke her skeleton somehow... as you can see by the hanging arms
## Post #11
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2009-07-08T09:24:37+00:00
- Post Title: Street Fighter IV .EMB .EMZ

Is there a viewer for the model files?
## Post #12
- Username: NGboo
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jul 08, 2009 8:59 pm
- Post datetime: 2009-07-08T13:46:21+00:00
- Post Title: Street Fighter IV .EMB .EMZ

> Reply from Itze
>
> 
No need to recompress the files... just rename the extracted .emb to .emz and the game will load them

I tried that, but the game crashes.
## Post #13
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2009-07-08T18:55:20+00:00
- Post Title: Street Fighter IV .EMB .EMZ

Nice one!   the compression used it's gzip, lol
## Post #14
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2009-07-10T13:40:04+00:00
- Post Title: Street Fighter IV .EMB .EMZ

Texture editing does work quite well, thanks to the programs posted here. A model viewer would really help in doing texture mods so that the game doesnt have to be started to view texture changes. This is my basic Zangief mod:
## Post #15
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-07-11T14:14:07+00:00
- Post Title: Street Fighter IV .EMB .EMZ

Excellent work done here!
## Post #16
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-07-11T14:32:44+00:00
- Post Title: Re: Street Fighter IV .EMB .EMZ

3dripperdx works fine so you can capture a character and mod the textures in max so you can see the changes in real time.
if you need a t-posed character just look for the bone names in the decompressed files and fill them with 00 in hex and the character will t-pose.
## Post #17
- Username: Endragor
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Jul 09, 2009 3:38 pm
- Post datetime: 2009-07-15T14:56:10+00:00
- Post Title: Re: Street Fighter IV .EMB .EMZ

Thanks, I use your bms-script and infusion program to make translation of the game.
But there is a problem: there are "comment_???.emb" files in "Battle\Hud" directory that contain 41 .emz files each. And that .emz-files contain 1 dds inside. It's not so difficult to extract them but is there any way to put them back together so the game will read them?
Here is an archive with 2 emb-files of that kind:
[http://www.yourfilelink.com/get.php?fid=501561](http://www.yourfilelink.com/get.php?fid=501561)
Many thanks.
## Post #18
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2009-07-16T06:19:14+00:00
- Post Title: Re: Street Fighter IV .EMB .EMZ

> Reply from Endragor
>
> Thanks, I use your bms-script and infusion program to make translation of the game.
But there is a problem: there are "comment_???.emb" files in "Battle\Hud" directory that contain 41 .emz files each. And that .emz-files contain 1 dds inside. It's not so difficult to extract them but is there any way to put them back together so the game will read them?
Here is an archive with 2 emb-files of that kind:
http://www.yourfilelink.com/get.php?fid=501561
Many thanks.

Use dragon unpacker to  extract the files and use infuser to place modded files inside the emb. 

Has anybody figured out how to recompress the modded file bak into an emz. I want to mod the xbox version but in order to replace a file, the new file must be the same size as the original?
## Post #19
- Username: Endragor
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Jul 09, 2009 3:38 pm
- Post datetime: 2009-07-16T07:37:33+00:00
- Post Title: Re: Street Fighter IV .EMB .EMZ

> Reply from plodtrew
>
> Use dragon unpacker to  extract the files and use infuser to place modded files inside the emb.
Looks like you haven't read my post heedfully. I know how to extract and bring back files from simple emb-s. But that ones contain .emz-files inside. Dragon Unpacker doesn't know emz-format as well as Infuser. And there is no way to put dds-files back to emz (now, at least).
## Post #20
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2009-07-16T07:52:58+00:00
- Post Title: Re: Street Fighter IV .EMB .EMZ

Yeah, this "emz inside the emb" is very annoying thing.
As I heard, the emz compressed with gzip. I tried to recompress an emb file, but the game always crashed. Although I change the header of the new file from the old one.
## Post #21
- Username: LouNGeR
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Jul 06, 2009 6:58 am
- Post datetime: 2009-07-16T13:31:11+00:00
- Post Title: Re: Street Fighter IV .EMB .EMZ

Hey there, I was following this topic since the beginning, but something went wrong with the activation of my account.

About the EMZ, I'm very close to recreate an EMZ file with the same size.
It seems that I need to move some data (checksum?) from the end of the new file, to the begin of the file.

EDIT:
MD5's

```
d5bfeeacff8f7fd7b2888aa228d066ce *AGL.tex.emb.NEW.emz

530128879a1ef3dbb8290f394ef83fb4 *CNL_01_01.col.emz
530128879a1ef3dbb8290f394ef83fb4 *CNL_01_01.col.emb.NEW.emz
```


Here's a modified self-created EMZ file, this one didn't end up being the same size as the original somehow.
Wait, that's obvious right? The texture was changed so the compression will be different.
Oh well, it works in-game though 

[http://ifile.it/xfaldps](http://ifile.it/xfaldps)
## Post #22
- Username: Endragor
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Jul 09, 2009 3:38 pm
- Post datetime: 2009-07-17T15:21:17+00:00
- Post Title: Re: Street Fighter IV .EMB .EMZ

LouNGeR
Superb. And... so did you write a program or something to pack emb-s back?
## Post #23
- Username: LouNGeR
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Jul 06, 2009 6:58 am
- Post datetime: 2009-07-17T21:36:54+00:00
- Post Title: Re: Street Fighter IV .EMB .EMZ

Yes I did, but a personal tool that is not to be released, because:

1) It's not finished and requires manual EMZ inspection for every file.
2) I do most of my own tools in PHP, it may be called [insert_flame_here], but it works for me and it's also easy and versatile.

I'm planning to make some tools in AutoIt, which is also versatile, but IMHO a bit harder to program.

I like AutoIt because:

Programs usually have very good compatibility with a lot of Windows versions
Compiling is the easiest ever
Can compile for x86 and x86-64, without the need to worry about x64 code.
Very simple and easy to understand documentation
## Post #24
- Username: sophist
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jul 18, 2009 4:05 am
- Post datetime: 2009-07-18T02:08:29+00:00
- Post Title: Re: Street Fighter IV .EMB .EMZ

I tried to make each character to pose t-pose by hex-coding each bonename contained in decompressed files with filling 00. But it gives me crash when I try to select the applied character. I think I might have missed some other parts. Will somebody tell me what that is???

What I did so far is;

changing bonename to look like Rarm. ---> 0000.
                                          Rarm. --->    .....(which is 00 in hex code.)
                                          Rarm ----> 00000
## Post #25
- Username: LouNGeR
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Jul 06, 2009 6:58 am
- Post datetime: 2009-07-18T14:36:25+00:00
- Post Title: Re: Street Fighter IV .EMB .EMZ

Since many ppl were interested, here's the code that I use for EMZ creation.
I'm pretty sure it's not complete nor correct, it works though, on everything I've tried thus far.

```

// Hex To Binary
function h2b($h) {
	return pack("H*", $h);
}

$emb = file_get_contents($in);
$gz = gzencode($emb, 9);
$checksum = substr($gz, -8);	// IS IT the checksum? who knows...

//$head1 = h2b("23454D5A");
$head = "#EMZ" . $checksum . h2b("10000000");

$body = substr($gz, 10, -8);

$foot = "";
//$foot = h2b("000000");	// Some files end with 000...Some don't

$new_emz = $head . $body . $foot;
file_put_contents($in . ".NEW.emz", $new_emz);
```


Have fun 


EDIT: btw, it's PHP code
## Post #26
- Username: LouNGeR
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Jul 06, 2009 6:58 am
- Post datetime: 2009-07-19T05:20:20+00:00
- Post Title: Re: Street Fighter IV .EMB .EMZ

Tool for modifying Object States from Stages or Characters



__dev_20090719071201.png (16.68 KiB) Viewed 1831 times



Almost ready for a test release
## Post #27
- Username: Itze
- Rank: veteran
- Number of posts: 81
- Joined date: Sat Mar 15, 2008 11:43 pm
- Post datetime: 2009-07-19T06:46:00+00:00
- Post Title: Re: Street Fighter IV .EMB .EMZ

nice what does it do?

what i'd like to change is the specular etc of the textures but no matter what i change in the costume file i can't edit it properly
## Post #28
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-07-19T12:33:03+00:00
- Post Title: Re: Street Fighter IV .EMB .EMZ

what effect do you want to achieve i can try to help if you give me an example.
## Post #29
- Username: Itze
- Rank: veteran
- Number of posts: 81
- Joined date: Sat Mar 15, 2008 11:43 pm
- Post datetime: 2009-07-19T15:05:54+00:00
- Post Title: Re: Street Fighter IV .EMB .EMZ

for example cammys leotard has different specular / ambient light colors than the rest of her skin... so you can't make her arms / legs blend properly with the body cause its always lighter  or darker depending on the stage

also sakuras underwear somehow tints the texture you paint on it... even if you paint it white its still slightly red (i mean the underwear under her white blouse, you can remove it with a hexeditor)
## Post #30
- Username: LouNGeR
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Jul 06, 2009 6:58 am
- Post datetime: 2009-07-19T16:17:40+00:00
- Post Title: Re: Street Fighter IV .EMB .EMZ

> Reply from Itze
>
> nice what does it do?

what i'd like to change is the specular etc of the textures but no matter what i change in the costume file i can't edit it properly
For now it's just for enabling/disabling objects in Character or Stage files, manual or batch.
Some objects have a "spawn flag" of 02 or 03, I dunno what those values do yet, but we can probably find out.

I'll have a look into the specular data to see why it's so hard to remove it
## Post #31
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2009-07-20T05:47:28+00:00
- Post Title: Re: Street Fighter IV .EMB .EMZ

Hm, I would be very interested in an emb editor. Am I to understand that this may actually come to be?

I look forward to the day that I don't have to hex-edit in a few things that aren't textures. Added, I haven't figured out editing voices and move sets.
## Post #32
- Username: LouNGeR
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Jul 06, 2009 6:58 am
- Post datetime: 2009-07-20T09:14:02+00:00
- Post Title: Re: Street Fighter IV .EMB .EMZ

Yes there will be an EMB editor, without a doubt.
EMB's are very plain files, I might create an editor myself 

So, what we want is a combination of HyperRipper (modified to recognize tags in SF4 files) and Infuser...
## Post #33
- Username: Itze
- Rank: veteran
- Number of posts: 81
- Joined date: Sat Mar 15, 2008 11:43 pm
- Post datetime: 2009-07-20T09:18:18+00:00
- Post Title: Re: Street Fighter IV .EMB .EMZ

should that be a wink in my direction?

tell me how i should split the files and i'll try to code it... integrating infusion is no problem since its only made up of one simple function
## Post #34
- Username: LouNGeR
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Jul 06, 2009 6:58 am
- Post datetime: 2009-07-20T09:39:58+00:00
- Post Title: Re: Street Fighter IV .EMB .EMZ

> Reply from Itze
>
> should that be a wink in my direction?

tell me how i should split the files and i'll try to code it... integrating infusion is no problem since its only made up of one simple function
haha, yes, a little  

You know the EMB format, no?

EMB header, then every file is jus pasted after it with it's own header like #EMB, #EMG, #BSR, there are some more there....
The EMB foot just contains the filenames, although these doesn't always seem correct in relation to the EMB contents.

I'm not an expert programmer or anything, so don't expect ground-breaking C++ or Assembler tools from me
## Post #35
- Username: Itze
- Rank: veteran
- Number of posts: 81
- Joined date: Sat Mar 15, 2008 11:43 pm
- Post datetime: 2009-07-20T09:55:35+00:00
- Post Title: Re: Street Fighter IV .EMB .EMZ

well you mentioned something about a checksum?

also i don't really know how the emb is build up... i just know enough to unpack and extract/inject files from/to it 

does it contain a header with the amount of sections / files?
how does the footer work?
etc. i dunno... maybe Mr.Mouse or chrrox can help :X
## Post #36
- Username: LouNGeR
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Jul 06, 2009 6:58 am
- Post datetime: 2009-07-20T10:40:13+00:00
- Post Title: Re: Street Fighter IV .EMB .EMZ

No the checksum thing was about EMZ.
## Post #37
- Username: Endragor
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Jul 09, 2009 3:38 pm
- Post datetime: 2009-07-20T11:41:13+00:00
- Post Title: Re: Street Fighter IV .EMB .EMZ

> Reply from Itze
>
> does it contain a header with the amount of sections / files?
how does the footer work?
Here is my quickbms-script for extracting the EMBs:

```
idstring "#EMB"
get UNK1 long
get UNK2 long
get FILES long
set FILENAME long FILES
math FILENAME *= 8
math FILENAME += 0x20
goto 0x20
get OFFSET long
math OFFSET += 0x20
get SIZE long
savepos NEXTFILE
set SIZECHECK long SIZE
math SIZECHECK += OFFSET
goto SIZECHECK
Do
get CHK byte
math SIZE += 0x1
While CHK == 0x00
math SIZE -= 0x1
goto FILENAME
get NAMEPOS long
savepos FILENAME
goto NAMEPOS
getdstring k 0x1
set NAME string k
Do
savepos CHECK
getdstring k 0x1
goto CHECK
get HM byte 
string NAME += k
While HM != 0x0
log NAME OFFSET SIZE
for i = 1 < FILES
goto NEXTFILE
math OFFSET += SIZE
get UNK long
get SIZE long
savepos NEXTFILE
set SIZECHECK long SIZE
math SIZECHECK += OFFSET
goto SIZECHECK
Do
get CHK byte
math SIZE += 0x01
While CHK == 0x00
math SIZE -= 0x1
goto FILENAME
get NAMEPOS long
savepos FILENAME
goto NAMEPOS
getdstring k 0x1
set NAME string k
Do
savepos CHECK
getdstring k 0x1
goto CHECK
get HM byte
string NAME += k
While HM != 0x0
log NAME OFFSET SIZE
next i
```

Well, maybe it's a bit long but works for any emb (that contains filename info inside and begins with "#EMB") with any file-format inside saving filename of any length 
Combining this script and chrrox's one you can extract almost any resource from Street Fighter 4.
But still... It would be great if someone would make a tool for packing files back into emz-format based on LouNGeR's PHP-program.

EDIT:
I've found some EMBs without filenames in the foot that contain DDS inside. Are there any EMBs that contain some other formats (not DDS) inside and have no filename info in the foot at the same time? Give some examples please (i need just paths, not files themselves).
I'll update my script when I find out.
## Post #38
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2009-07-20T13:59:46+00:00
- Post Title: Re: Street Fighter IV .EMB .EMZ

Well, the decompressed EMB file can be loaded by SF4 by changing the extension to EMZ right? What are the advantages of re compressing back to EMZ? Just curious is all.
## Post #39
- Username: Endragor
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Jul 09, 2009 3:38 pm
- Post datetime: 2009-07-20T14:09:20+00:00
- Post Title: Re: Street Fighter IV .EMB .EMZ

> Reply from Darkfox
>
> Well, the decompressed EMB file can be loaded by SF4 by changing the extension to EMZ right? What are the advantages of re compressing back to EMZ? Just curious is all.
The advantage is file size. My translation is 500 MB now without compression. That is not OK.
EDIT:
Besides, there are some EMBs with the EMZs inside. So in this case we need first to pack EMZs and then to put them into EMB.
## Post #40
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2009-07-20T14:20:11+00:00
- Post Title: Re: Street Fighter IV .EMB .EMZ

Hm, this is true, and the game is pretty darn big too. Around 4.30GBs?

Just imagine all that data decompressed... alright, point taken.
## Post #41
- Username: LouNGeR
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Jul 06, 2009 6:58 am
- Post datetime: 2009-07-20T15:02:08+00:00
- Post Title: Re: Street Fighter IV .EMB .EMZ

@Endragor
Awesome!! I hope it works as expected!
Will try it right away!

This means doing everything without a gui from now on....

BTW, is it easy to reverse the process (combine files to EMB) without having to look at the initial EMB ?

EDIT
At first, it works great.
Unpacking "CNL_01.cos.emb" gives me 4 files.
1 EMB: CNL_01.nml.emb
This EMB does not have file names in it, but does contain DDS files.

Also: is it possible to make your script Infuser compatible? (or is there another way to smash the EMB back together?)

EDIT
Trying STG_RVR.emb....

```
------------------------------
.....
.....
  000031c0 0          RVR_CUBE.emb
  000031c0 524672     RVR_CUBE.emb
- the file "RVR_CUBE.emb" already exists
  do you want to overwrite it (y/N/all)?
```
## Post #42
- Username: Endragor
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Jul 09, 2009 3:38 pm
- Post datetime: 2009-07-20T18:13:48+00:00
- Post Title: Re: Street Fighter IV .EMB .EMZ

So here is updated version of the script:

```
idstring "#EMB"
get UNK1 long
get UNK2 long
get FILES long
set FILENAME long FILES
math FILENAME *= 8
math FILENAME += 0x20
goto 0x20
get OFFSET long
math OFFSET += 0x20
get SIZE long
savepos NEXTFILE
set NEXTOFF long SIZE
math NEXTOFF += OFFSET
goto NEXTOFF
Do
get CHK byte
math NEXTOFF += 0x1
While CHK == 0x00
math NEXTOFF -= 0x01
goto FILENAME
getdstring CHKEX 0x01
If CHKEX == D
set NAME string DDS0.dds
set EXNAME byte 0x00
else
set EXNAME byte 0x01
goto FILENAME
get NAMEPOS long
savepos FILENAME
goto NAMEPOS
getdstring k 0x1
goto NAMEPOS
get HM byte
set NAME string k
If HM != 0x0
Do
savepos CHECK
getdstring k 0x1
goto CHECK
get HM byte
string NAME += k
While HM != 0x0
endif
endif
log NAME OFFSET SIZE
math FILES -= 0x01
for i = 1 to FILES
goto NEXTFILE
set OFFSET long NEXTOFF
get UNK long
get SIZE long
savepos NEXTFILE
If i != FILES
set NEXTOFF long SIZE
math NEXTOFF += OFFSET
goto NEXTOFF
Do
get CHK byte
math NEXTOFF += 0x1
While CHK == 0x00
math NEXTOFF -= 0x01
endif
If EXNAME != 0x00
goto FILENAME
get NAMEPOS long
savepos FILENAME
goto NAMEPOS
getdstring k 0x1
goto NAMEPOS
get HM byte
set NAME string k
If HM != 0x0
Do
savepos CHECK
getdstring k 0x1
goto CHECK
get HM byte
string NAME += k
While HM != 0x0
endif
else
set NAME string DDS
string NAME += i
string NAME += .dds
endif
log NAME OFFSET SIZE
next i
```

Changelog:
1. Now it can extract DDSes from EMBs that don't have filename info (it just simply gives them names like DDS0.dds, DDS1.dds, etc.).
2. It doesn't save  unnecessary nulls in files's endings.
3. Some other little mistakes are corrected.
4. Empty files will be now extracted properly.

> Reply from LouNGeR
>
> Also: is it possible to make your script Infuser compatible? (or is there another way to smash the EMB back together?)
Well, If Itze would replace '#' symbol in infuser identifier with some other i would try, but now i can't because that symbol used in quickbms as comment-beginning mark so i can't put it into string variable.

> Reply from LouNGeR
>
> Trying STG_RVR.emb....
I have no idea why it happens so yet. But I'll try to figure out. And anyway the previous file was 0 bytes in size so you'll lose nothing overwriting it.
For now countinue testing the script on different EMBs 

EDIT:
The problem solved. The script updated.
## Post #43
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2009-07-22T06:43:41+00:00
- Post Title: Re: Street Fighter IV .EMB .EMZ

> Reply from Darkfox
>
> Well, the decompressed EMB file can be loaded by SF4 by changing the extension to EMZ right? What are the advantages of re compressing back to EMZ? Just curious is all.

The xbox 360 version needs to have emz files with exactly the same filesize as the originals to be injected. Compressing back into emz would may it possible to mod the xbox version also.
## Post #44
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2009-07-22T07:06:32+00:00
- Post Title: Re: Street Fighter IV .EMB .EMZ

Ah, true... though wouldn't modding the XBox version require burning a new DVD for each modification?
## Post #45
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2009-07-22T09:22:44+00:00
- Post Title: Re: Street Fighter IV .EMB .EMZ

> Reply from Darkfox
>
> Ah, true... though wouldn't modding the XBox version require burning a new DVD for each modification?

Unfortunately yes. Although rewritables may be an option.
## Post #46
- Username: LouNGeR
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Jul 06, 2009 6:58 am
- Post datetime: 2009-07-22T12:51:20+00:00
- Post Title: Re: Street Fighter IV .EMB .EMZ

Does that Samsung drive which supports DVD-5 also support DVD-RW ?
BTW, I think it's kind of hard to get the same sized EMZ, if someone can prove me wrong, please do so.
## Post #47
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-07-22T16:54:22+00:00
- Post Title: Re: Street Fighter IV .EMB .EMZ

I know we could get the game to load the modified files but the problem is the mods would most likely get you kicked off of xbox live as they could detect the disc was tampered with.
## Post #48
- Username: LouNGeR
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Jul 06, 2009 6:58 am
- Post datetime: 2009-07-22T22:33:12+00:00
- Post Title: Re: Street Fighter IV .EMB .EMZ

I'm pretty certain that it actually IS possible to edit a 360 game, burn it and make it show up as valid.

Funny enough, I actually own such a disc.
It's DoA Extreme 2, full nude mod, iXtreme/Stealth check pass.
## Post #49
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-07-22T23:34:11+00:00
- Post Title: Re: Street Fighter IV .EMB .EMZ

I am not saying you can not burn a game and have it show up as valid to the xbox but if you connect to live servers they can check your files and ban you from live if you fail the check.
## Post #50
- Username: LouNGeR
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Jul 06, 2009 6:58 am
- Post datetime: 2009-07-22T23:56:32+00:00
- Post Title: Re: Street Fighter IV .EMB .EMZ

OK, that may be true.
I was speaking in general, Connecting to Live is fine.
I guess you are talking about joining servers?
## Post #51
- Username: LouNGeR
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Jul 06, 2009 6:58 am
- Post datetime: 2009-07-25T17:16:25+00:00
- Post Title: Re: Street Fighter IV .EMB .EMZ

I have some questions about other SF4 file formats.
Mostly working on Models and Shaders/Materials/Filters at the moment.

Here's a list of types/tags that I could find.
These are only the "EM" tags, there are some others too.

```
EMB		"Bundle"? Archive
EME		Effects
EMG		Geometries?
EMM		Material/Shader/Light Definitions???
EMO		Objects Archive (contains EMGs)
EMZ		(G)Zipped EMB Archive
```


All archives look very similar to EMB when I do a quick look.
Isn't there any way to extract for example, EMO files with some BMS script?

Also: What's this "EM"?
## Post #52
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-07-25T18:57:17+00:00
- Post Title: Re: Street Fighter IV .EMB .EMZ

post 2 different emo files and I bet someone can make a bms script.
## Post #53
- Username: LouNGeR
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Jul 06, 2009 6:58 am
- Post datetime: 2009-07-25T22:21:15+00:00
- Post Title: Re: Street Fighter IV .EMB .EMZ

Sure thing! 

There are multiple types in this archive, I think they all differ from each other but not much.
They all look like pretty straightforward archives, that I can see 

Included file types: BAC, BCM, BSR, EMA, EMM, EMO

Mirror 1: [http://ifile.it/k1g45l8](http://ifile.it/k1g45l8)
Mirror 2: [http://www.megaupload.com/?d=7YQTQBFB](http://www.megaupload.com/?d=7YQTQBFB)
## Post #54
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2009-07-27T08:29:05+00:00
- Post Title: Re: Street Fighter IV .EMB .EMZ

> Reply from LouNGeR
>
> I'm pretty certain that it actually IS possible to edit a 360 game, burn it and make it show up as valid.

Funny enough, I actually own such a disc.
It's DoA Extreme 2, full nude mod, iXtreme/Stealth check pass.

I've done my own modding on some xbox games and the game boots fine. I replace files using xbox backup creator but the files have to be the exact same size as the original. You cant play on live though as you risk being banned.
## Post #55
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2009-07-28T13:37:22+00:00
- Post Title: Re: Street Fighter IV .EMB .EMZ

Silly question, but where might the movesets be stored in the character files? And what effects to use in said moves?
## Post #56
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2009-07-28T13:52:08+00:00
- Post Title: Re: Street Fighter IV .EMB .EMZ

does someone know where i can find the background img's ? ( and with wut i can get them   )
## Post #57
- Username: LouNGeR
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Jul 06, 2009 6:58 am
- Post datetime: 2009-07-28T14:22:58+00:00
- Post Title: Re: Street Fighter IV .EMB .EMZ

> Reply from CMihai
>
> does someone know where i can find the background img's ? ( and with wut i can get them   )
They are in
".....\Game\MainMenu\bg_*.emz"
And you can extract them by unpacking the EMZ with Offzip or QuickBMS, then openinging the extracted file with Dragon Unpacker to grab the background DDS image.
## Post #58
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2009-07-28T16:29:25+00:00
- Post Title: Re: Street Fighter IV .EMB .EMZ

.......

np works now  ty
## Post #59
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2009-07-30T19:53:09+00:00
- Post Title: Re: Street Fighter IV .EMB .EMZ

Question: Where are the character moves stored.
## Post #60
- Username: LouNGeR
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Jul 06, 2009 6:58 am
- Post datetime: 2009-07-30T20:45:49+00:00
- Post Title: Re: Street Fighter IV .EMB .EMZ

> Reply from Darkfox
>
> Question: Where are the character moves stored.
Character Animations:
...\Chara\CHR\CHR.cmn.emz\CHR.fce.ema
...\Chara\CHR\CHR.cmn.emz\CHR.obj.ema



> Reply from Endragor
>
> LouNGeR wrote:Also: is it possible to make your script Infuser compatible? (or is there another way to smash the EMB back together?)
Well, If Itze would replace '#' symbol in infuser identifier with some other i would try, but now i can't because that symbol used in quickbms as comment-beginning mark so i can't put it into string variable.
How about just using some other symbol?
I'm only using BMS scripts in tools anyway at the moment, these could rename for me.

EDIT: Nvm, I'm adding Infuser naming (and probably infusing) support to my own tool atm.
## Post #61
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2009-07-31T02:27:20+00:00
- Post Title: Re: Street Fighter IV .EMB .EMZ

Oh? So these are the movesets they swap in the videos on YT?
## Post #62
- Username: Endragor
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Jul 09, 2009 3:38 pm
- Post datetime: 2009-07-31T04:57:02+00:00
- Post Title: Re: Street Fighter IV .EMB .EMZ

Infuser compatible version of emb-extracting bms-script:

```
idstring "#EMB"
get UNK1 long
get UNK2 long
get FILES long
set FILENAME long FILES
math FILENAME *= 8
math FILENAME += 0x20
goto 0x20
get OFFSET long
math OFFSET += 0x20
get SIZE long
savepos NEXTFILE
set NEXTOFF long SIZE
math NEXTOFF += OFFSET
goto NEXTOFF
Do
get CHK byte
math NEXTOFF += 0x1
While CHK == 0x00
math NEXTOFF -= 0x1
set SYM string $#
string SYM -= $
goto OFFSET
getdstring EXT 0x3
If EXT != DDS
goto OFFSET
getdstring EXT 0x1
getdstring EXT 0x3
endif
set DECOFF 0
math DECOFF += OFFSET
set NAME string 1
string NAME += SYM
string NAME += infuser
string NAME += SYM
string NAME += DECOFF
string NAME += .
string NAME += EXT
log NAME OFFSET SIZE
math FILES -= 0x01
for i = 1 to FILES
goto NEXTFILE
set OFFSET long NEXTOFF
get UNK long
get SIZE long
savepos NEXTFILE
If i != FILES
set NEXTOFF long SIZE
math NEXTOFF += OFFSET
goto NEXTOFF
Do
get CHK byte
math NEXTOFF += 0x1
While CHK == 0x00
math NEXTOFF -= 0x01
endif
goto OFFSET
getdstring EXT 0x3
If EXT != DDS
goto OFFSET
getdstring EXT 0x1
getdstring EXT 0x3
endif
set DECOFF 0
math DECOFF += OFFSET
set NUM 0
math NUM += i
math NUM += 1
set NAME string NUM
string NAME += SYM
string NAME += infuser
string NAME += SYM
string NAME += DECOFF
string NAME += .
string NAME += EXT
log NAME OFFSET SIZE
next i
```
## Post #63
- Username: LouNGeR
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Jul 06, 2009 6:58 am
- Post datetime: 2009-07-31T05:00:46+00:00
- Post Title: Re: Street Fighter IV .EMB .EMZ

Awesome!
Will try it out, Thanks!
## Post #64
- Username: Noire
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Sep 01, 2009 3:01 pm
- Post datetime: 2009-09-01T07:30:52+00:00
- Post Title: Re: Street Fighter IV .EMB .EMZ

Hi, first I'm sorry for my poor english.
I want to ask about Offzip, can this tools extract subtitles files in Street Fighter IV?

I'm using this command line: offzip.exe -m 16 -a -z -15 AGL.emz blah 0
The result is file "00000010.dat" with size 2.62MB.

Is there something wrong? Also I'm trying to open Gallery artwork, the result is the same, the output is a dat file.
Is there a way to open dat file? Considering in the first page you can extract some image file.

Thanks for your help.
## Post #65
- Username: LouNGeR
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Jul 06, 2009 6:58 am
- Post datetime: 2009-09-01T21:23:16+00:00
- Post Title: Re: Street Fighter IV .EMB .EMZ

When you unpack an EMZ file with OffZip, the output DAT file is likely to be an EMB file.
So, you can open the EMB with Dragon Unpacker, Assets Explorer or some Hex Editor if you want to Hex edit something.

Just forget OffZip all together, it's confusing for newbies.
Grab Assets Explorer by Piecemontee, it can also unpack EMZ to EMB.
## Post #66
- Username: Noire
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Sep 01, 2009 3:01 pm
- Post datetime: 2009-09-02T03:27:56+00:00
- Post Title: Re: Street Fighter IV .EMB .EMZ

> Reply from LouNGeR
>
> When you unpack an EMZ file with OffZip, the output DAT file is likely to be an EMB file.
So, you can open the EMB with Dragon Unpacker, Assets Explorer or some Hex Editor if you want to Hex edit something.

Just forget OffZip all together, it's confusing for newbies.
Grab Assets Explorer by Piecemontee, it can also unpack EMZ to EMB.

Wow! It really does work and quite simple, I'm using Assets Explorer along with DDS Converter.
Thanks for your help.
## Post #67
- Username: LouNGeR
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Jul 06, 2009 6:58 am
- Post datetime: 2009-09-02T14:20:38+00:00
- Post Title: Re: Street Fighter IV .EMB .EMZ

DDS Convertor, what? why?
## Post #68
- Username: Itze
- Rank: veteran
- Number of posts: 81
- Joined date: Sat Mar 15, 2008 11:43 pm
- Post datetime: 2009-09-22T05:41:28+00:00
- Post Title: Re: Street Fighter IV .EMB .EMZ

Could anyone do me a favor and rip Bisons ENGLISH Vocals for me?

Especially the Psychocrusher vocal   

 I don't have SF4 installed at the moment so i can't do it myself 

Thanks in advance
## Post #69
- Username: govern
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jul 20, 2010 10:05 am
- Post datetime: 2010-07-20T23:07:02+00:00
- Post Title: Re: Street Fighter IV .EMB .EMZ

I want to be the best street fighter in the whole world. How I wish.
