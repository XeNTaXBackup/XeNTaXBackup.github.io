## Post #1
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-01-18T06:46:15+00:00
- Post Title: Dead Space 3 Demo X360

Hi all,

I wrote script for loc purposes and all works ok, how ever after i make a bigger text file game is crashing. I have notice that in VIV files got some kind of CRC, could this have something to do with crashing? Please anyone can help ?

Here is script for VIV file:

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

idstring BIGH
get VIV_SIZE long
endian big
get FILES long
get HEADER_SIZE long
for i = 0 < FILES
    get OFFSET long
    get SIZE long
    get NAME_CRC long //THIS IS SOMETHING IM NOT SURE OF
    log i OFFSET SIZE
next i
```


And also with slo3 files inside the VIV file. It is pretty tricky but i manage to do repacker as well how ever not sure why game is crashing. There must be something i missing....


This is my original file:

```
http://warimagehost.net/files/output.bin
```


This is my bigger mod file :

```
http://warimagehost.net/files/final.bin
```
## Post #2
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-01-18T21:17:26+00:00
- Post Title: Dead Space 3 Demo X360

ok sorted
## Post #3
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2013-01-18T22:59:23+00:00
- Post Title: Dead Space 3 Demo X360

can you post the "sorted" script   hmm i just wanted to make sure does this repack?

(hmm it seems like the files arnt extracting right there all .file and none o the files have the right names for the files i hope someone can find this out)
## Post #4
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-01-19T00:44:58+00:00
- Post Title: Dead Space 3 Demo X360

script is correct no names just iD's
## Post #5
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2013-01-19T03:37:44+00:00
- Post Title: Dead Space 3 Demo X360

are they all .files thought? just asking because usually there's an xml txt etc not all 1 format
## Post #6
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2013-01-19T10:09:01+00:00
- Post Title: Dead Space 3 Demo X360

I can't test it, but try to change

```

to

 log "" OFFSET SIZE
```
 Is there still only .file extension?
## Post #7
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-01-19T15:33:08+00:00
- Post Title: Dead Space 3 Demo X360

Can anyone provide small VIV archive ? I want check hash func.
## Post #8
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2013-01-19T16:24:39+00:00
- Post Title: Dead Space 3 Demo X360

yep here you go i will give u 3 parts out of the files i spilt

[http://www.mediafire.com/?roa6hle42f3loo9](http://www.mediafire.com/?roa6hle42f3loo9)
[http://www.mediafire.com/?iqkbokd6kda9qsx](http://www.mediafire.com/?iqkbokd6kda9qsx)
[http://www.mediafire.com/?439scgi78fsvh86](http://www.mediafire.com/?439scgi78fsvh86)
## Post #9
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-01-19T17:27:05+00:00
- Post Title: Dead Space 3 Demo X360

Download: [here](http://www.sendspace.com/file/ohnypo)

Btw: You can use Rick tools format is old from DS2. Have fun.
## Post #10
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2013-01-19T18:38:30+00:00
- Post Title: Dead Space 3 Demo X360

How do you find the hashes with the names?
## Post #11
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-01-19T18:45:21+00:00
- Post Title: Dead Space 3 Demo X360

If you have XBOX you can dump some memory regions with loaded filenames. In my case, I used filelists from DS2 Rick project.
For PC easier to find filenames. For these games, I am writing logger that captures loaded filenames that access the Hash func.
## Post #12
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2013-01-19T18:51:56+00:00
- Post Title: Dead Space 3 Demo X360

Ahh cool. Does the 360 need to be connected via sata from the disc drive to pc or can i use a XEX dumper? I am interested in getting audio files names from dante's inferno x360 version.

Also i can't seem to figure out how to unpack the files from your tool.

Thanks anyway.
## Post #13
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2013-01-19T18:52:30+00:00
- Post Title: Dead Space 3 Demo X360

nice this is a huge step up the 1 gb opens perfect and i see alot of audiostreams lol
## Post #14
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-01-19T19:02:20+00:00
- Post Title: Dead Space 3 Demo X360

> Reply from OrangeC
>
> Ahh cool. Does the 360 need to be connected via sata from the disc drive to pc or can i use a XEX dumper? I am interested in getting audio files names from dante's inferno x360 version.

Also i can't seem to figure out how to unpack the files from your tool.

Thanks anyway.
For unpack and pack files with extension STR try StrUnpack and StrPack from Rick tools. I do not know if it works but BIGViewer work perfect.
## Post #15
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-01-19T21:52:42+00:00
- Post Title: Dead Space 3 Demo X360

if anyone interest i can make decompressor for LZX chunks.... Viceral is really stupid system and using very strange methods of chunk compression
## Post #16
- Username: BANDIT
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Sep 13, 2011 4:19 am
- Post datetime: 2013-02-06T19:29:41+00:00
- Post Title: Re: Dead Space 3 Demo X360

Where i can find texts for translation?
## Post #17
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2013-02-07T17:49:24+00:00
- Post Title: Re: Dead Space 3 Demo X360

only list for big0 ? how extract next one
## Post #18
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-02-08T19:47:03+00:00
- Post Title: Re: Dead Space 3 Demo X360

Ok here my filelists for Rick Gibbed.Visceral tools and my unpacker

Gibbed.Visceral_Projects - Extract files in Gibbed.Visceral.r39\projects\ folder (in file Dead Space 3.xml set your installiation game path)

```
			<action type="path">C:\Games\Dead Space 3</action>
		</install_location>
```

VIVUnpacker_Projects - Extract files in Projects folder

See [below](http://forum.xentax.com/viewtopic.php?p=82942#p82942)
## Post #19
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-02-08T20:09:35+00:00
- Post Title: Re: Dead Space 3 Demo X360

Update for bigfile0 +56

See [below](http://forum.xentax.com/viewtopic.php?p=82942#p82942)
## Post #20
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-02-09T16:28:48+00:00
- Post Title: Re: Dead Space 3 Demo X360

Update 3 for bigfile0 (1241) +567

it is all the file names that I could find. Complement filelists if you can find new file names. GL. 
[DS3_Filelist_Projects.rar](https://xentaxbackup.github.io/file/6189_DS3_Filelist_Projects.rar)
## Post #21
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2013-02-11T18:47:02+00:00
- Post Title: Re: Dead Space 3 Demo X360

only one but this already nice job ! don't stop the move! 
and any idea for convert sound requiered for sure  lol
## Post #22
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-02-12T14:03:43+00:00
- Post Title: Re: Dead Space 3 Demo X360

Almost no one interested
## Post #23
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2013-02-12T22:18:51+00:00
- Post Title: Re: Dead Space 3 Demo X360

For the pc version towav should handle the exas.snu.
## Post #24
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-02-13T07:03:45+00:00
- Post Title: Re: Dead Space 3 Demo X360

> Reply from Ekey
>
> Almost no one interested

This is not like noone is interest, just if you know the structure i think it would be great to write also repacker and not just extractor.I'm not talking about this game but about others, most ppl looking for repack for localization and a small percent of ppl are Modelers or something where they want use it for they own projects. For me i'm doing both but if there is repacker for archives or texts its always perfect. This is how i see it. Rick always succeded with his projects because he always include repack function, this is making his work kind of special(my opinion). Dont take it wrong you doing excellent work for others and it is much appreciated, this was just a notice
## Post #25
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-02-13T12:59:15+00:00
- Post Title: Re: Dead Space 3 Demo X360

For repack BIG files use Rick tools. Dont work only STR unpacker and packer
## Post #26
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2013-02-13T16:06:00+00:00
- Post Title: Re: Dead Space 3 Demo X360

well seems they chsnged the format again. towav cant hanfle the files.
## Post #27
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2013-02-14T07:06:34+00:00
- Post Title: Re: Dead Space 3 Demo X360

Yes, PC version has the newer variant of the EA codec which is incompatible with the previous decoder so even header changing will not work. Best bet is work with the xbox360 files as xma can't change so radically luckily
## Post #28
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-02-14T09:11:17+00:00
- Post Title: Re: Dead Space 3 Demo X360

> Reply from Apollo
>
> Yes, PC version has the newer variant of the EA codec which is incompatible with the previous decoder so even header changing will not work. Best bet is work with the xbox360 files as xma can't change so radically luckily

Agrees do revering is always easy on x360 coz they dont have so much posibilites like on PC . Except 1 thing and that is M$ stupid lzx compression. My opinion
## Post #29
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2013-02-14T20:44:21+00:00
- Post Title: Re: Dead Space 3 Demo X360

i wonder if the unpacker can work with the 360 version somehow.
## Post #30
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-02-14T22:54:27+00:00
- Post Title: Re: Dead Space 3 Demo X360

> Reply from OrangeC
>
> i wonder if the unpacker can work with the 360 version somehow.

Ricks tool can handle it, but i guess Ekys tool as well since PC and X360 are same struct, except not sure about endianess
## Post #31
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2013-02-15T01:53:20+00:00
- Post Title: Re: Dead Space 3 Demo X360

Okay nice, Well maybe if someone can upload the 360 unpacked music files in xma i can download it. Im on a really shitty connection atm.
## Post #32
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2013-02-19T04:02:48+00:00
- Post Title: Re: Dead Space 3 Demo X360

Anyone try to find the missing names yet?

Also how to match the names from The toc/str files to the correct offsets/hashes?
## Post #33
- Username: Amon
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jan 03, 2011 5:52 am
- Post datetime: 2013-02-26T03:44:14+00:00
- Post Title: Re: Dead Space 3 Demo X360

Did the previous Dead Space games have better audio quality (Bit depth, sampling rate, etc.) on the PC versus X360,PS3 ? Or were they identical? Add me to the list looking for Dead Space 3 PC SNU conversion tool.
## Post #34
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2013-02-26T21:22:00+00:00
- Post Title: Re: Dead Space 3 Demo X360

I would like to take over the filename project so if someone can point me in the right direction?

thanks.
## Post #35
- Username: BANDIT
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Sep 13, 2011 4:19 am
- Post datetime: 2013-03-04T14:33:48+00:00
- Post Title: Re: Dead Space 3 Demo X360

Can anyone make new tg4d converter with export\import function?
## Post #36
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-03-25T16:00:14+00:00
- Post Title: Re: Dead Space 3 Demo X360

Almost all the missing filenames are found.
Here is the updated list for bigfile0.viv (1100+ new audio filenames)

[http://pastebin.com/k19eBdvk](http://pastebin.com/k19eBdvk)

How it was done:

- extract all .smb files from all .str files (about 270)
- extract sound filenames from .smb files
- duplicate removal 

.smb format was not analyzed completely, I needed just a number of sounds (at 0x10) and a following table of offsets, which points to structure with null-terminated strings

The sounds themselves can be converted using modified version of ealayer3
