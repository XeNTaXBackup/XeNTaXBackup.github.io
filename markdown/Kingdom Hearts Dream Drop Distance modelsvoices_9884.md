## Post #1
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2012-11-18T18:28:19+00:00
- Post Title: Kingdom Hearts Dream Drop Distance models/voices

Has someone attempted to get the resources from the 3ds game of Kingdom HEarts?
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-11-19T02:28:37+00:00
- Post Title: Kingdom Hearts Dream Drop Distance models/voices

its not possible to extract 3ds games.
## Post #3
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2012-11-19T07:40:27+00:00
- Post Title: Kingdom Hearts Dream Drop Distance models/voices

> Reply from chrrox
>
> its not possible to extract 3ds games.
aw. why?
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-11-19T11:43:57+00:00
- Post Title: Kingdom Hearts Dream Drop Distance models/voices

they are encrypted and the system is not hacked to dump the decryption keys.
## Post #5
- Username: SoftIce
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Jan 23, 2011 12:31 pm
- Post datetime: 2014-06-12T00:35:22+00:00
- Post Title: Kingdom Hearts Dream Drop Distance models/voices

Well... bummer. I was hoping someone here might have ripped them from the Dream Drop game. I wanted to look at them up close. Ah well.
## Post #6
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2014-06-12T01:26:45+00:00
- Post Title: Kingdom Hearts Dream Drop Distance models/voices

People are able to dump the RAM of 3DS games, but they need a Gateway in order to do so. So it's not impossible.
## Post #7
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-06-12T03:37:21+00:00
- Post Title: Kingdom Hearts Dream Drop Distance models/voices

It was impossible when the question was asked.
## Post #8
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2014-06-12T03:49:29+00:00
- Post Title: Kingdom Hearts Dream Drop Distance models/voices

> Reply from chrrox
>
> It was impossible when the question was asked.Derp, for some reason I didn't realize this topic was from 2012. That's what I get for living under a rock for the past few months.

Still, the possibility exists now, you'd just need to get in contact with someone capable of doing so... or wait until someone inevitably releases information how to decrypt the ROMs.
## Post #9
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2014-06-17T12:33:30+00:00
- Post Title: Kingdom Hearts Dream Drop Distance models/voices

it0s taking a lot tho. I wonder why, DS was much faster.
## Post #10
- Username: GovanifY
- Rank: advanced
- Number of posts: 59
- Joined date: Thu Apr 17, 2014 4:25 am
- Post datetime: 2014-06-28T01:29:25+00:00
- Post Title: Kingdom Hearts Dream Drop Distance models/voices

IT IS possible to extract 3ds games. tutorial in 2 steps:
1) Use the AES Engine of the 3ds for decrypt the rom ([http://3dbrew.org/wiki/PSPXI:EncryptDecryptAes](http://3dbrew.org/wiki/PSPXI:EncryptDecryptAes))
2) The rom will be more likely compressed using a lz varient compression, use 3ds explorer, DSDecmp or shit like that for extract the game.

Not that hard as long as you have a hacked 3ds. If someone ever have one please pm me, I'll be interested to play around w/ kh3d!

Good luck, GovanifY

EDIT: I wonder why smealum wanted to keep his method secret cuz you can see that just before extracted pokemon he did some work w/ the AES engine on 3dbrew, so wasn't THAT hard to guess, as long as u search
## Post #11
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2014-06-28T08:17:31+00:00
- Post Title: Kingdom Hearts Dream Drop Distance models/voices

a hacked 3ds? how is that even possible?
## Post #12
- Username: GovanifY
- Rank: advanced
- Number of posts: 59
- Joined date: Thu Apr 17, 2014 4:25 am
- Post datetime: 2014-06-28T11:13:59+00:00
- Post Title: Kingdom Hearts Dream Drop Distance models/voices

As I said you need a 3ds who can launch or SSSpwn(private for now) or this one:

"     The following was fixed with 7.0.0-13, see here for details. Too long or corrupted strings (01Ah 2 Nickname length in characters 050h 2 Message length in characters) in the NVRAM DS user settings cause (System Settings->Other Settings->Profile->Nintendo DS Profile) to crash in 3DS-mode due to a stack-smash. The DSi is not vulnerable to this, DSi launcher(menu) and DSi System Settings will reset the NVRAM user-settings if the length field values are too long(same result as when the CRCs are invalid). "

With that you'll have to make a ROP exploit using this pattern: [http://3dbrew.org/wiki/PSPXI:EncryptDecryptAes](http://3dbrew.org/wiki/PSPXI:EncryptDecryptAes) then here ya go, decrypted 3ds rom
## Post #13
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2014-07-02T16:03:54+00:00
- Post Title: Kingdom Hearts Dream Drop Distance models/voices

hey i have a 3ds that has the gateway-3ds hack if you need any help with anything im willing to
## Post #14
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-07-02T20:31:49+00:00
- Post Title: Kingdom Hearts Dream Drop Distance models/voices

> Reply from lllccc
>
> hey i have a 3ds that has the gateway-3ds hack if you need any help with anything im willing to
just play your original cart till you get to where the model you want is then launch the ram dumper and send the ram dump to be looked at
## Post #15
- Username: GovanifY
- Rank: advanced
- Number of posts: 59
- Joined date: Thu Apr 17, 2014 4:25 am
- Post datetime: 2014-08-29T08:44:03+00:00
- Post Title: Kingdom Hearts Dream Drop Distance models/voices

As a part of VoiD we finally managed to make a public decryptor for anyone.

[http://govanify.x10host.com/_files/3DS_ ... ryptor.zip](http://govanify.x10host.com/_files/3DS_CTR_Decryptor.zip)

Read the NFO.

See you soon!

 -VoiD
## Post #16
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2014-08-31T07:08:45+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

holy crap! lemme see NOW!
Damn I need a hacked 3ds.. no emulator available now and besides, it wouldn't work...
## Post #17
- Username: MayBeePah
- Rank: advanced
- Number of posts: 44
- Joined date: Mon Oct 06, 2014 2:22 pm
- Post datetime: 2014-11-14T11:24:15+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

Is it alright if I can upload a few PMO (Model) files for people to try and reverse engineer, not all of them but just a few. Maybe other types of files as well? For people who can't decrypt 3ds games yet
## Post #18
- Username: Falo
- Rank: advanced
- Number of posts: 78
- Joined date: Fri Oct 23, 2009 8:29 pm
- Post datetime: 2014-11-15T08:13:14+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

> Reply from MayBeePah
>
> Is it alright if I can upload a few PMO (Model) files for people to try and reverse engineer, not all of them but just a few. Maybe other types of files as well? For people who can't decrypt 3ds games yet

Until someone figures out how to decompress them, it's pointless to post.

010 Editor *.rbin Template:

```
//--- 010 Editor v5.0.2 Binary Template
//
// File: Kingdom Hearts 3D *.rbin
// Author: Falo
//
//--------------------------------------
struct{
    char magic[4]; //"CRAR"
    ushort unk1; //version?
    ushort numFiles;
    uint szHeader; //or start of data
    uint reserved;
    char path[16]; //relative rbin source path

    struct ENTRY entry[numFiles]<optimize=false>;
}header;

struct ENTRY{
    local int FTemp, FTemp2;

    uint Hash; //should be filename hash
    FTemp2 = FTell(); //save name start pos
    int ofsName; 
    int Size:31;
    int IsCompressed:1;
    int Offset;

    FTemp = FTell(); //save file pos

    FSeek(FTemp2+ofsName); //goto name pos
    char Name[];

    FSeek(Offset); //goto data pos
    ubyte data[Size];

    FSeek(FTemp); //load file pos

    Printf("%s;0x%08X;%d;%d\n", Name, Offset, Size, IsCompressed);
};

```


As far as i can see, only *.l2d and *.pmo have the compression flag set.
The last 4 byte of compressed files is the decompressed size, like KH1/2 you need to read compressed files backwards.
It's not the same compression as KH1/2 but something similar.

Most of the game's files look like KHBBS, i guess every old BBS tool should work here.
## Post #19
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-11-15T13:00:43+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

Its LZOlv compression
[LZOvl.zip](https://xentaxbackup.github.io/file/8077_LZOvl.zip)
## Post #20
- Username: GovanifY
- Rank: advanced
- Number of posts: 59
- Joined date: Thu Apr 17, 2014 4:25 am
- Post datetime: 2014-11-15T18:12:11+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

Wow, new replies.
Yup, DDD is using obviously LZovl compression on all PMOs files afaik, and the format isn't exactly the same than BBS, some mods in there. Textures are CTT files afaik, might be wrong.
all rbin files contains different folders of the game, it's just packed, not even compressed. Square ftw.
## Post #21
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2014-11-15T18:17:37+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

Audio is using the bcstm format which can be played with vgmstream, so that's good. Voices are distorted though. The TXA files are just the same as in BBS I think, I managed to get some of Sora's facial expressions ripped from one with Yosh's BBS tools, but without the right palette and dimensions it was a little distorted.
## Post #22
- Username: GovanifY
- Rank: advanced
- Number of posts: 59
- Joined date: Thu Apr 17, 2014 4:25 am
- Post datetime: 2014-11-15T18:23:18+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

Optionally I documented BCSAR format a while ago on 3dbrew ([http://3dbrew.org/wiki/BCSAR](http://3dbrew.org/wiki/BCSAR)) and made a tool for it. It contains all battle grunts and shits.
## Post #23
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2014-11-15T18:37:18+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

With the latest vgmstream the cutscene voices are no longer distorted, I had an outdated version  

Do you mind posting your bcsr tool? I'm interested in hearing the grunts without sound effects and bgm
## Post #24
- Username: GovanifY
- Rank: advanced
- Number of posts: 59
- Joined date: Thu Apr 17, 2014 4:25 am
- Post datetime: 2014-11-15T18:44:50+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

Actually my HDD had some problems recently and I'm afraid that most of my DDD tools are losted for good :/(if you don't trust me watch my twitter) I'm repairing it atm, but no idea if I will ever be able to have it again. Anyways, documented a bit the format, so you should be able to make a lil' tool that will: parse STRG names, delete names present in the sound folder(contains a whole list, not only somnium.bcsar files) parse offset and size of file, extract.

EDIT: Devilot, if you're there, please post the outdated version I sended to you that can parse names.

EDIT2: Most of my DDD tools are definitely losted, you'll have to rely on Devilot for get the bcsar thingy, also it only parse names, I didn't implemented the extraction in this version. Sorry :/
## Post #25
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2014-11-16T09:43:16+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

Here it is|

[https://mega.co.nz/#!o4sQhSKZ!QpxvDEzma ... 9qcyauZT-E](https://mega.co.nz/#!o4sQhSKZ!QpxvDEzmaj6od9FR3wRDf7_FdjfXibFpW9qcyauZT-E)
## Post #26
- Username: GovanifY
- Rank: advanced
- Number of posts: 59
- Joined date: Thu Apr 17, 2014 4:25 am
- Post datetime: 2014-11-16T10:08:26+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

Yup, this is the first ever version of the BCSAR_TOOL I made that was able to parse names. You can get the source by using ILSpy.
As for others facts I may recreate some of my DDD tools, tho not now: don't really have that much time atm.

As for others things: BCSTM is just more or less a BCWAV file packed, which is REALLY similar to wave windows files. Think I can't send ya SDK tools or any other things tho the format is documented on 3dbrew: [http://3dbrew.org/wiki/BCWAV](http://3dbrew.org/wiki/BCWAV)

Also the DATA partition is in the same kind of windows wave files, so for make a tool: -> parse header, recreate wave header and parse DATA wave.

For the PMOs it's almost the same as BBS afaik w/ 2/3 things rearranged and 3ds texture format instead of TIM2(also, iirc, 8 or 16bpp direct color, got to check)
For CTD it's almost the same as BBS, you can hex edit them if you want to edit the text(YES, translations ARE possible)

For moflex files(pre-rendered videos) used in several 3ds games, those are mobiclip encoded videos, gl to everyone wanting to make a converter of this format.

That's more or less all I remember, don't have DDD on me so can't check further other formats. Just listed all I remembered about it.
Anyways gl for your lil' romhacking tests!
-GY
## Post #27
- Username: MayBeePah
- Rank: advanced
- Number of posts: 44
- Joined date: Mon Oct 06, 2014 2:22 pm
- Post datetime: 2014-11-18T10:46:09+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

Does anyone still want me to upload decompressed PMOs, or is that not allowed?
## Post #28
- Username: MayBeePah
- Rank: advanced
- Number of posts: 44
- Joined date: Mon Oct 06, 2014 2:22 pm
- Post datetime: 2014-11-24T07:28:31+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

This is the best I can do, I don't know how to get the right order of indices...
[blah.png](https://xentaxbackup.github.io/file/8135_blah.png)
## Post #29
- Username: MayBeePah
- Rank: advanced
- Number of posts: 44
- Joined date: Mon Oct 06, 2014 2:22 pm
- Post datetime: 2014-11-24T07:43:41+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

Another 
[neku.png](https://xentaxbackup.github.io/file/8137_neku.png)
## Post #30
- Username: Azurfan
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Jun 24, 2010 5:12 am
- Post datetime: 2014-11-25T07:56:20+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

> Reply from MayBeePah
>
> This is the best I can do, I don't know how to get the right order of indices...
This still looks very good though, maybe Falo can help.
## Post #31
- Username: GovanifY
- Rank: advanced
- Number of posts: 59
- Joined date: Thu Apr 17, 2014 4:25 am
- Post datetime: 2014-11-28T14:52:22+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

If you really want to know:
Bone format is the exact same.
Vertexes, meshes and UV are rearrenged and in a slightly different format iirc.
Texture format are in a 3ds custom format.

All I can say 'bout those DDD PMOs, never really worked on 'em tho tbh.
-GY
## Post #32
- Username: MayBeePah
- Rank: advanced
- Number of posts: 44
- Joined date: Mon Oct 06, 2014 2:22 pm
- Post datetime: 2014-11-29T01:39:06+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

I fixed it anyway, now for textures 
[mickey.png](https://xentaxbackup.github.io/file/8163_mickey.png)
## Post #33
- Username: MayBeePah
- Rank: advanced
- Number of posts: 44
- Joined date: Mon Oct 06, 2014 2:22 pm
- Post datetime: 2014-11-30T08:56:16+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

This scene was just 1 Pmo 
[khddd.png](https://xentaxbackup.github.io/file/8167_khddd.png)
## Post #34
- Username: GovanifY
- Rank: advanced
- Number of posts: 59
- Joined date: Thu Apr 17, 2014 4:25 am
- Post datetime: 2014-11-30T10:28:17+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

> Reply from MayBeePah
>
> This scene was just 1 Pmo
Not really surprising by knowing square...
## Post #35
- Username: jadentheman
- Rank: n00b
- Number of posts: 18
- Joined date: Fri Oct 24, 2014 7:21 am
- Post datetime: 2014-12-28T19:20:25+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

anything new on this front? It's been about a month
## Post #36
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2014-12-29T09:52:07+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

it's Christmas\New Year and I'm pretty sure Govani, the KH master, has been busy 
I myself am away from my system, so I can't really test\understand anything!
## Post #37
- Username: MayBeePah
- Rank: advanced
- Number of posts: 44
- Joined date: Mon Oct 06, 2014 2:22 pm
- Post datetime: 2015-01-12T09:43:32+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

Finished Christmas holidays  Today I finally decrypted the textures 
Here's Donalds...
[DonaldTexture.png](https://xentaxbackup.github.io/file/8469_DonaldTexture.png)
## Post #38
- Username: MayBeePah
- Rank: advanced
- Number of posts: 44
- Joined date: Mon Oct 06, 2014 2:22 pm
- Post datetime: 2015-01-13T08:28:43+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

With textures applied 
[donald&goofy.png](https://xentaxbackup.github.io/file/8470_donald&goofy.png)
## Post #39
- Username: MayBeePah
- Rank: advanced
- Number of posts: 44
- Joined date: Mon Oct 06, 2014 2:22 pm
- Post datetime: 2015-01-13T08:59:57+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

Some more...
[set.png](https://xentaxbackup.github.io/file/8471_set.png)
## Post #40
- Username: Azurfan
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Jun 24, 2010 5:12 am
- Post datetime: 2015-01-13T14:13:13+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

Great work, although there seems to be something wrong with the color depth as gradient should be more smooth and not change that abruptly.
## Post #41
- Username: MayBeePah
- Rank: advanced
- Number of posts: 44
- Joined date: Mon Oct 06, 2014 2:22 pm
- Post datetime: 2015-01-13T22:06:54+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

Each texture comes with an alpha mask or something, I also noticed pixels appear where abrupt changes happen... Can anyone figure this out?
[donald.png](https://xentaxbackup.github.io/file/8475_donald.png)
## Post #42
- Username: jrush
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Oct 25, 2012 6:10 pm
- Post datetime: 2015-01-16T23:15:47+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

Dang dude. Great job man.
## Post #43
- Username: MayBeePah
- Rank: advanced
- Number of posts: 44
- Joined date: Mon Oct 06, 2014 2:22 pm
- Post datetime: 2015-01-17T21:15:35+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

Fixed the textures 

I need to fix some other small bugs first, then I'll release some models 
[pmo.png](https://xentaxbackup.github.io/file/8498_pmo.png)
## Post #44
- Username: MayBeePah
- Rank: advanced
- Number of posts: 44
- Joined date: Mon Oct 06, 2014 2:22 pm
- Post datetime: 2015-01-18T03:58:09+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

Here's a link to show you of all the characters I could convert 
[https://db.tt/UPgdTMlE](https://db.tt/UPgdTMlE)
## Post #45
- Username: MayBeePah
- Rank: advanced
- Number of posts: 44
- Joined date: Mon Oct 06, 2014 2:22 pm
- Post datetime: 2015-01-18T06:15:55+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

I've made a lot of progress today 
[group.jpg](https://xentaxbackup.github.io/file/8502_group.jpg)
## Post #46
- Username: MayBeePah
- Rank: advanced
- Number of posts: 44
- Joined date: Mon Oct 06, 2014 2:22 pm
- Post datetime: 2015-01-19T03:36:38+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

Here's Lea's keyblade, if anyone wanted to see it.
[lea.jpg](https://xentaxbackup.github.io/file/8517_lea.jpg)
## Post #47
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2015-01-19T10:36:46+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

all this awesome is killing me
## Post #48
- Username: GovanifY
- Rank: advanced
- Number of posts: 59
- Joined date: Thu Apr 17, 2014 4:25 am
- Post datetime: 2015-01-23T23:23:37+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

To answer to Devilot: Yeah I've been busy, a lot of HDD fials, KH2FM_Toolkit update, works everywhere and such.
About you MayBeePah: Wow! Pretty cool work! Would you wish to share iure shit) but always good to have some kind of viewer!ed textt? Not like it's really different from BBS (except for the textures shit)but always cool to have a viewer!

And errrr ya I got a shitload of stuff to do so I'm gettin' away like this, byyyye~~
-GY
## Post #49
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2015-01-23T23:31:34+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

> Reply from GovanifY
>
> To answer to Devilot: Yeah I've been busy, a lot of HDD fials, KH2FM_Toolkit update, works everywhere and such.
About you MayBeePah: Wow! Pretty cool work! Would you wish to share iure shit) but always good to have some kind of viewer!ed textt? Not like it's really different from BBS (except for the textures shit)but always cool to have a viewer!

And errrr ya I got a shitload of stuff to do so I'm gettin' away like this, byyyye~~
-GY

you do this too much lol
## Post #50
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2015-02-02T02:20:08+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

> Reply from MayBeePah
>
> Here's a link to show you of all the characters I could convert 
https://db.tt/UPgdTMlE
Woah dude, great job! I don't see Rinzler, Groucho Sora, Black Guard, Chernabog, Magic Brooms, Monstro, Cleo, Moogle, Dream Eaters, Pluto, Diablo, or Ursula on that list though.
Will they get ripped for the first release?
And is it just me, or does Pinocchio have a mustache in those renders?
## Post #51
- Username: Azurfan
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Jun 24, 2010 5:12 am
- Post datetime: 2015-02-23T15:01:09+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

Everything looked so promising but I guess MayBeePah doesn't come back. I wish I understood how the texture works.
## Post #52
- Username: Truthkey
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Jul 24, 2010 5:39 am
- Post datetime: 2015-02-26T03:21:29+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

> Reply from Azurfan
>
> Everything looked so promising but I guess MayBeePah doesn't come back. I wish I understood how the texture works.

Yeah, I wish I could understand the format too. It must be using some sort of encryption or compression method. D:
## Post #53
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2015-03-05T13:10:53+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

> Reply from Devilot
>
> Here it is|

https://mega.co.nz/#!o4sQhSKZ!QpxvDEzma ... 9qcyauZT-E

Is there a version of the bcsar-tool that can extract and possibly repack .bcsar-files?
A QuickBMS-Script would be okay, too.
## Post #54
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2015-03-05T13:25:20+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

> Reply from ChrisX930
>
> Devilot wrote:Here it is|

https://mega.co.nz/#!o4sQhSKZ!QpxvDEzma ... 9qcyauZT-E

Is there a version of the bcsar-tool that can extract and possibly repack .bcsar-files?
A QuickBMS-Script would be okay, too.

unfortunately, there is not as you specify...
## Post #55
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2015-03-05T13:35:00+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

> Reply from Devilot
>
> ChrisX930 wrote:Devilot wrote:Here it is|

https://mega.co.nz/#!o4sQhSKZ!QpxvDEzma ... 9qcyauZT-E

Is there a version of the bcsar-tool that can extract and possibly repack .bcsar-files?
A QuickBMS-Script would be okay, too.

unfortunately, there is not as you specify...

But is there a way to "extract" music with a quickBMS Script?
I thought there was a tool that is able to do something (but it was deleted or something?).
If someone could write a QuickBMS Script to extract files from bcsar, there's a way to replace files inside of the bcsar.
## Post #56
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2015-03-05T17:18:20+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

> Reply from ChrisX930
>
> But is there a way to "extract" music with a quickBMS Script?
I thought there was a tool that is able to do something (but it was deleted or something?).
If someone could write a QuickBMS Script to extract files from bcsar, there's a way to replace files inside of the bcsar.

extract yes, Govan knows it because he's amazing 
files extracted are without any name however.
## Post #57
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2015-03-05T17:28:24+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

> Reply from Devilot
>
> ChrisX930 wrote:But is there a way to "extract" music with a quickBMS Script?
I thought there was a tool that is able to do something (but it was deleted or something?).
If someone could write a QuickBMS Script to extract files from bcsar, there's a way to replace files inside of the bcsar.

extract yes, Govan knows it because he's amazing 
files extracted are without any name however.

That's weird because with the old bcsar-tool it's possible to parse the names D:
I had a bms.-script that was able to extract all files from a .dat file from a online-game (300 Heroes).
With this Script, Files got extracted with correct filenames.
[https://hackpad.com/QuickBMS-300-IdX43K0vtwZ](https://hackpad.com/QuickBMS-300-IdX43K0vtwZ)

Not sure if a quickbms-script would work with bcsar-files, but I think it should.
The problem is: I don't know how to create scripts that works with specific files like this^^'
Would be cool if someone could make a quickbms-script for a bcsar-file because you can Extract AND Reimport modified files with it.
## Post #58
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2015-03-05T17:48:25+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

again, GovanifY knows, because he's amazing. he's just super, super busy.
## Post #59
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2015-03-05T17:58:02+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

> Reply from Devilot
>
> again, GovanifY knows, because he's amazing. he's just super, super busy.

hahaha, that could be true^^' 
I think I'll ask him to help me. 
It's amazing that I can almost change everything in the game with a quickbms-script for bcsar-files and .arc (darc) files.
The reason is: all scripts are in PlainText and probably I could write a very own game that works like a legit 3DS Game.
## Post #60
- Username: Farlavor
- Rank: beginner
- Number of posts: 24
- Joined date: Tue Apr 10, 2012 7:02 pm
- Post datetime: 2015-03-14T01:37:32+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

Why MayBeePah???... Why????
I mean... WHY the heck you disappeared just when you made such a great progress????

I waited years for this... Entire years for the Dream eater models... and all you've got to rip are just plain human NPCs... Not a bad idea at all, becuz I'm interested on some of them... (A few of them)... But my interests focuses entirely on the dreameaters themselves... You started a project like this on both model resources and here... and now, you disappear mysteriously, like you were dead or kidnapped by the Yihadists...    

Why should I be too unlucky just like this?. Who will be able to rip all those models if you aren't here? Who will help me to do that???... I cannot try something I never known to rip aside from Wii's BRRES and SZS or anything that Noesis could convert. So, BCSAR or wathever the file that contains the models is just a format that I am unable to convert or rip... and even if I can... I don't have the script to properly convert it to DAE for Cinema 4D, or even import it to 3DS Max... and I only have 2009 version... I may download any version but I must need what version is compatible with the script (Just in case is already available in public).

It's the eternal losing fight of my life...   

I hate people who never finish succesfully what they started... I would rip everything from KHDDD (Dreameaters, NPCS, Maps, Sounds, Voices, Music and even if I'd had the tools to do so... I would fan-translated the game in Spanish.    )... So... That kind of laziness just when we were having wet dreams about your ripped NPCs... and the 99% guarantee that Dreameaters will be next to be ripped... Absolutely disgusts me    .

Sorry for my rudeness... I'm so desperated... Yeah... Desperated. and even my mobile is mysteriously broken.
Ergo my rage increased up to astronomic levels... If I would be a kind of Saiyan... today I would be already on my first time becoming a supersaiyan 100000.
## Post #61
- Username: myrzavkin
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Jun 26, 2012 9:53 pm
- Post datetime: 2015-03-18T18:17:29+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

It seems MayBeePah really dissapeared.
Is here anyone who can help with .pmo .pam and .txa formats?
if somebody interested but lazy:
you can find decrypted game on youtube just enter "Fully Decrypted 3DS Games Links" in search 
then extract .rbin files with this tool [http://www.mediafire.com/download/7lmjj ... _v0.01.rar](http://www.mediafire.com/download/7lmjjlbkpyzkpib/KingdomHeartsDDD_Toolset_by_Vash_v0.01.rar)
there will be 
.pmo (model) 
.pam (animation)
.txa (textures ?)
also .ctd (text)

if somebody manage to reverse engineer (or teach me how ) them ,that would be awesome
## Post #62
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2015-03-19T12:05:00+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

That sounds like a reasonable course of action, as long as downloading the "Fully Decrypted 3DS Games Links" is legal for people who actually own the game.
Except MayBeePah hasn't disappeared. According to his profile, he logs into XeNTaX at least once a week, sometimes once a day. In fact, he was last online just a few hours ago.
## Post #63
- Username: flarespire
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Jul 24, 2011 7:30 am
- Post datetime: 2015-03-20T02:13:41+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

> Reply from Mirrorman95
>
> That sounds like a reasonable course of action, as long as downloading the "Fully Decrypted 3DS Games Links" is legal for people who actually own the game.

Well technically the "Fully Decrypted 3DS Games Links" still fall under the category of a ROM as this version is how the 3DS system would be reading it, so basing on that I think the rules for any other ROM apply here aswell.

> Reply from myrzavkin
>
>  Is here anyone who can help with .pmo .pam and .txa formats?

Hmm, depending on how much the formats may have been altered, can we not use the information we have on the versions of these formats that KH:BBS had as a base? I believe that is how the content on the last couple of pages was achieved (could be wrong though....)
## Post #64
- Username: Sorakairi
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Aug 21, 2011 4:35 pm
- Post datetime: 2015-03-22T19:19:49+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

> Reply from Farlavor
>
> Why MayBeePah???... Why????
I mean... WHY the heck you disappeared just when you made such a great progress????

I waited years for this... Entire years for the Dream eater models... and all you've got to rip are just plain human NPCs... Not a bad idea at all, becuz I'm interested on some of them... (A few of them)... But my interests focuses entirely on the dreameaters themselves... You started a project like this on both model resources and here... and now, you disappear mysteriously, like you were dead or kidnapped by the Yihadists...    

Why should I be too unlucky just like this?. Who will be able to rip all those models if you aren't here? Who will help me to do that???... I cannot try something I never known to rip aside from Wii's BRRES and SZS or anything that Noesis could convert. So, BCSAR or wathever the file that contains the models is just a format that I am unable to convert or rip... and even if I can... I don't have the script to properly convert it to DAE for Cinema 4D, or even import it to 3DS Max... and I only have 2009 version... I may download any version but I must need what version is compatible with the script (Just in case is already available in public).

It's the eternal losing fight of my life...   


I hate people who never finish succesfully what they started... I would rip everything from KHDDD (Dreameaters, NPCS, Maps, Sounds, Voices, Music and even if I'd had the tools to do so... I would fan-translated the game in Spanish.    )... So... That kind of laziness just when we were having wet dreams about your ripped NPCs... and the 99% guarantee that Dreameaters will be next to be ripped... Absolutely disgusts me    .

Sorry for my rudeness... I'm so desperated... Yeah... Desperated. and even my mobile is mysteriously broken.
Ergo my rage increased up to astronomic levels... If I would be a kind of Saiyan... today I would be already on my first time becoming a supersaiyan 100000.

You can actually translate this game in spanish (and other languages, too... I'm working on the italian patch, we're almost done), there's already a patch in the works, so you may help them. 
I coded all the tools to extract textures and texts. Don't ask me to work on 3D models, cause I have no time and I don't have much knowledge about 3D modeling.

Here's my blog to see some screenshots :

[http://adf.ly/1CU2ac](http://adf.ly/1CU2ac)

See ya!
## Post #65
- Username: Truthkey
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Jul 24, 2010 5:39 am
- Post datetime: 2015-03-23T05:07:29+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

> Reply from Sorakairi
>
> Farlavor wrote:Why MayBeePah???... Why????
I mean... WHY the heck you disappeared just when you made such a great progress????

I waited years for this... Entire years for the Dream eater models... and all you've got to rip are just plain human NPCs... Not a bad idea at all, becuz I'm interested on some of them... (A few of them)... But my interests focuses entirely on the dreameaters themselves... You started a project like this on both model resources and here... and now, you disappear mysteriously, like you were dead or kidnapped by the Yihadists...    

Why should I be too unlucky just like this?. Who will be able to rip all those models if you aren't here? Who will help me to do that???... I cannot try something I never known to rip aside from Wii's BRRES and SZS or anything that Noesis could convert. So, BCSAR or wathever the file that contains the models is just a format that I am unable to convert or rip... and even if I can... I don't have the script to properly convert it to DAE for Cinema 4D, or even import it to 3DS Max... and I only have 2009 version... I may download any version but I must need what version is compatible with the script (Just in case is already available in public).

It's the eternal losing fight of my life...   


I hate people who never finish succesfully what they started... I would rip everything from KHDDD (Dreameaters, NPCS, Maps, Sounds, Voices, Music and even if I'd had the tools to do so... I would fan-translated the game in Spanish.    )... So... That kind of laziness just when we were having wet dreams about your ripped NPCs... and the 99% guarantee that Dreameaters will be next to be ripped... Absolutely disgusts me    .

Sorry for my rudeness... I'm so desperated... Yeah... Desperated. and even my mobile is mysteriously broken.
Ergo my rage increased up to astronomic levels... If I would be a kind of Saiyan... today I would be already on my first time becoming a supersaiyan 100000.

You can actually translate this game in spanish (and other languages, too... I'm working on the italian patch, we're almost done), there's already a patch in the works, so you may help them. 
I coded all the tools to extract textures and texts. Don't ask me to work on 3D models, cause I have no time and I don't have much knowledge about 3D modeling.

Here's my blog to see some screenshots :

https://deepdivetranslations.wordpress.com

See ya!

Would you mind sharing your tools? Or at least please tell me what format textures are in. I've tried parsing the data as indexed pixels but all I get is junky pictures that barely ressemble the original and I can't seem to find the palette anywhere in the texture. Are they compressed or encrypted in some way. Please enlighten me. xD
## Post #66
- Username: Sorakairi
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Aug 21, 2011 4:35 pm
- Post datetime: 2015-03-23T07:01:47+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

I can't share my tools yet, cause the italian and spanish translations have not been released.
There's no palette, the textures are direct colors and they are even tiled. You won't see anything until you deswizzle them, they actually don't follow a standard algorithm, but a variant one, and there are different pixel formats, so the only deswizzling doesn't solve everything.
## Post #67
- Username: KiRAfromYouTube
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Sep 03, 2010 9:53 pm
- Post datetime: 2015-03-24T08:21:41+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

myrzavkin, I downloaded the tool you provided but as I try to run the program, this error message pops-up that says,

"KingdomHeartsDDD_Toolset.exe is not a valid Win32 application."

I also try to run a command prompt but it gives me the same message as well. Is there any way for me to fix this or is there another KH3D toolset? BTW, I'm running an old operating system Windows XP SP1.
[win32.png](https://xentaxbackup.github.io/file/8872_win32.png)
## Post #68
- Username: flarespire
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Jul 24, 2011 7:30 am
- Post datetime: 2015-03-24T15:20:33+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

> Reply from KiRAfromYouTube
>
> myrzavkin, I downloaded the tool you provided but as I try to run the program, this error message pops-up that says,

"KingdomHeartsDDD_Toolset.exe is not a valid Win32 application."

I also try to run a command prompt but it gives me the same message as well. Is there any way for me to fix this or is there another KH3D toolset? BTW, I'm running an old operating system Windows XP SP1.

That might be because the toolset was written for a x64 environment, If that isnt the case, maybe your system is lacking some of the required runtimes or is just that little bit too old to actually run it. I'd suggest installing windows XP Service Pack 2 and Service Pack 3 and if it still gives this message try getting the latest C++ runtime library update. If it persists after doing all that then it may be that as i said it was written for a 64bit (x64) system, or your OS is still just that little bit outdated for it to work.
## Post #69
- Username: KiRAfromYouTube
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Sep 03, 2010 9:53 pm
- Post datetime: 2015-03-24T18:13:59+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

flarespire:- Okay, I'll try to upgrade my operating system and see if it works. Also, what's your operating system?
## Post #70
- Username: flarespire
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Jul 24, 2011 7:30 am
- Post datetime: 2015-03-24T18:26:06+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

> Reply from KiRAfromYouTube
>
> flarespire:- Okay, I'll try to upgrade my operating system and see if it works. Also, what's your operating system?
 I'm running Windows 7 64bit and I have not had a problem with the program.
## Post #71
- Username: Sorakairi
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Aug 21, 2011 4:35 pm
- Post datetime: 2015-03-25T07:15:59+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

Don't update your system if you don't want. I'll extract my code for the unpacker and repacker from my tool and release it as a stand alone program tomorrow or in the next days. I can't give you yet all the other things I've coded so far, though.
## Post #72
- Username: KiRAfromYouTube
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Sep 03, 2010 9:53 pm
- Post datetime: 2015-03-25T16:53:25+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

Sorakairi:-Okay, noted. Also, I just mess around with the .bcstm files and I have this program which can play these files and convert it .WAV files. I think everyone knows what program that could play .bcstm files.
## Post #73
- Username: Sorakairi
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Aug 21, 2011 4:35 pm
- Post datetime: 2015-03-26T19:56:35+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

Hi guys, this is the small part of my tool that I was talking about.
As a small "gift" I've added the unpacking/repacking for ARC files, too.
It's a drag & drop tool, so just take your file and drop it into my .exe, it will open and show you a menu.
The rest is self-explanatory. 
As for the repacking, just drag & drop the same file that you used during the unpacking.

[http://adf.ly/1CU6ZI](http://adf.ly/1CU6ZI)

P.S : Since this is not the complete tool anyone who wants to translate the game into his own language can contact me.

See ya!
## Post #74
- Username: KiRAfromYouTube
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Sep 03, 2010 9:53 pm
- Post datetime: 2015-03-27T15:32:47+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

Sorakairi:- Thanks for sharing your tool. I'll try this one out and will update this post if I extract anything. Thanks again.
## Post #75
- Username: flarespire
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Jul 24, 2011 7:30 am
- Post datetime: 2015-03-28T17:16:51+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

So does anyone actually have any documentation on how formats like .pmo have changed in KH3D since their use in KHBBS? Might bring us a step closer to getting them viewable in a program like Noesis.
## Post #76
- Username: KiRAfromYouTube
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Sep 03, 2010 9:53 pm
- Post datetime: 2015-03-28T18:38:11+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

> Reply from flarespire
>
> So does anyone actually have any documentation on how formats like .pmo have changed in KH3D since their use in KHBBS? Might bring us a step closer to getting them viewable in a program like Noesis.

I'm onto that at the moment. However, I do want to say that they've changed a lot and some of the extensions I've never seen before. Truth is, my knowledge about formats is really low, but right now, I'm trying to list all the formats from each of the folder and will post it here once I'm done.

EDIT:- I've done listing all the formats on each of the folder. Here you go:-

```
.rgr

cam.rbin:-
.exa
.mcv

chara_boss:-
.abc
.bcd
.ccd
.ead
.fsm
.gpl
.pam
.pmo
.seb
.tcd
.txa

chara_d_obj:-
.abc
.bcd
.ccd
.pam
.pmo
.tcd
.txa

chara_e_obj:-
.abc
.ccd
.ctt
.ead
.pam
.pmo
.seb
.tcd

chara_enemy:-
.abc
.ccd
.ead
.fsm
.gpl
.lub
.pam
.pmo
.seb
.tcd
.txa

chara_f_obj:-
.bcd
.ccd
.ead
.pam
.pmo
.tcd
.txa

chara_gim:-
.abc
.bcd
.ccd
.ead
.fsm
.gpl
.mcv
.pam
.pld
.pmo
.seb
.tcd
.txa

chara_high:-
.ead
.pam
.pmo
.txa

chara_npc:-
.abc
.ead
.pam
.pmo
.seb
.tcd (only 1 file)
.txa

chara_pc:-
.abc
.ccd
.ead
.mcv
.pam
.pmo
.seb
.tcd
.txa

chara_wep:-
.ead
.pam
.pmo
.seb

effect:-
.ese
.fep
.frr

event:-
.ctt
.exa

font:-
.bcfnt
.ctt

game:-
.abc
.bin
.dbg
.lub

item:-
.cct
.itb
.ite

map:-
.bcd
.mcv
.ctt
.mss
.ngd
.pmp
.pvd
.txa

menu:-
.bin
.ctt
.l2d

message:-
.ctd
.bin

minigame:-
.bin
.gpl
.olo

mission:-
.bin
.cir
.cle
.evf
.exa
.gpl
.lki
.lpm
.lps
.mcv
.mis
.mon
.olo

romarc:-
[it looks like a text file with folder names in it]

setdata:-
.bin
.dbg
.olo
```


This MAY NOT be the ones you're looking for, but by looking at the extensions, I assume you'll get the idea on how these formats worked.

Unfortunately, .PMO files does NOT WORK with Noesis as I've tried it earlier. However, MayBeePah have successfully extracting the models and the weapons all by himself. As for the other formats, it looks very different from what I know so far.

Also, sorry if my knowledge for these formats are very low as I'm still new to these kind of things.
## Post #77
- Username: Sorakairi
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Aug 21, 2011 4:35 pm
- Post datetime: 2015-03-30T16:43:38+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

- .ctd, these are the text files and they use an UTF-16 encoding.
- .ctt, these are textures, they are actually swizzled and they don't have the same pixel formats.
- .l2d, these are archives for textures and animations, they are compressed with LZOvl.
- .ead, .seb, .pmo, .txa, .abc, are used in 3D Modeling.
- .bcfnt, it is actually the 3DS font standard file. There are 4/5 fonts in the game, I don't recall now.
- .bin, these are generic binary files, they can hold rarc archives that you can unpack/repack with my tool.
- .lub, these are the game's lua scripts. They can't be disassembled without an effort, though.
- .olo, they are used to set an event, like number of enemies, characters and such.
- .exa, they are animation files, cutscenes.
- .moflex, they are actually the 3DS standard videos.
- .bcstm, 3DS audio files.
- .bcsar, an easy 3DS sounds archive.
- .pmp, they are actually map files.

Here's just a start.
## Post #78
- Username: flarespire
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Jul 24, 2011 7:30 am
- Post datetime: 2015-03-30T17:17:56+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

Well its good to know the formats the game uses and what they are. Now has anyone tried to compare the files from this game to their counterparts in KH: Birth By Sleep to see what the difference in structure is?
## Post #79
- Username: Farlavor
- Rank: beginner
- Number of posts: 24
- Joined date: Tue Apr 10, 2012 7:02 pm
- Post datetime: 2015-03-31T17:18:37+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

> Reply from Sorakairi
>
> Farlavor wrote:Why MayBeePah???... Why????
I mean... WHY the heck you disappeared just when you made such a great progress????

I waited years for this... Entire years for the Dream eater models... and all you've got to rip are just plain human NPCs... Not a bad idea at all, becuz I'm interested on some of them... (A few of them)... But my interests focuses entirely on the dreameaters themselves... You started a project like this on both model resources and here... and now, you disappear mysteriously, like you were dead or kidnapped by the Yihadists...    

Why should I be too unlucky just like this?. Who will be able to rip all those models if you aren't here? Who will help me to do that???... I cannot try something I never known to rip aside from Wii's BRRES and SZS or anything that Noesis could convert. So, BCSAR or wathever the file that contains the models is just a format that I am unable to convert or rip... and even if I can... I don't have the script to properly convert it to DAE for Cinema 4D, or even import it to 3DS Max... and I only have 2009 version... I may download any version but I must need what version is compatible with the script (Just in case is already available in public).

It's the eternal losing fight of my life...   


I hate people who never finish succesfully what they started... I would rip everything from KHDDD (Dreameaters, NPCS, Maps, Sounds, Voices, Music and even if I'd had the tools to do so... I would fan-translated the game in Spanish.    )... So... That kind of laziness just when we were having wet dreams about your ripped NPCs... and the 99% guarantee that Dreameaters will be next to be ripped... Absolutely disgusts me    .

Sorry for my rudeness... I'm so desperated... Yeah... Desperated. and even my mobile is mysteriously broken.
Ergo my rage increased up to astronomic levels... If I would be a kind of Saiyan... today I would be already on my first time becoming a supersaiyan 100000.

You can actually translate this game in spanish (and other languages, too... I'm working on the italian patch, we're almost done), there's already a patch in the works, so you may help them. 
I coded all the tools to extract textures and texts. Don't ask me to work on 3D models, cause I have no time and I don't have much knowledge about 3D modeling.

Here's my blog to see some screenshots :

http://adf.ly/1CU2ac

See ya!

Sorry... When I said I would translated the game itself in spanish... I mean when I have the tools to do so, since I have NO KNOWLEDGE of how to understand formats and stuff like that... you at least managed to know the PMO formats, and even others knows about EAD and other formats as well... but you tell me about those formats and I the only thing I can say is "No idea"...
but when comes to using programs that KNOWS and UNDERSTANDS how to change voices/text... I mean like that spanish team managed to create an Spanish rom of TWEWY for DS (With spanish voices as well)... Then probably after some months, you would already see my translated rom uploaded on MEGA or Mediafire. 

Sadly. I only can see a few fandubs in spanish... but it would be great if I would contribute with that rom, if I had the tools to do so... Anyway. I was far more interested on the models... and translating may be possible in the future, when godess fate gives me the tools needed for that and more importantly, that it should be easy that even a 5 year old nOOb child can make a good translating/fandub by just a few clicks and plenty of writing, you know.
Sorry if it sounded rude... but I wanted to clarify, I don't have the programming skills needed to modify stuff on the rom itself, it may be a pain for me if I have to keep fixing error codes everytime like always happens when I do something like this... Anyway. I never expected that translating was EVEN possible... I said that with irony and even some little sarcasm, it doesn't mean I wouldn't translate... but it doesn't mean I would translate... just I would if it were easy doing that by myself. if I were MayBeePah... I wouldn't QUIT like he did... I would keep ripping all files, Not just a few damn NPCs, but also ALL dreameaters, all models, all scenarios, EVERYTHING in-game... and most importantly... I would already uploaded all those models... since he couldn't... All I can say to him is...

"GTFO! you loser"

Leaving us with our dreams crumbled by just a few JPG pictures of several T posed NPCs and a keyblade that only appeared in a cutscene and neither we know it's true power in-game.

PS: At least... I saw further progresses on all of your work... maybe we can reach this goal... I will do my work on Models Resource as well. if I ever get to the models or not... I will let you know here as well. and even I will provide you the files I manage to rip... Good luck everyone.
specially me, Becuz I need really more than you expected... this is my FIRST time ever ripping stuff from a 3DS rom. and my chances to fail is almost 99.9999%
## Post #80
- Username: Sorakairi
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Aug 21, 2011 4:35 pm
- Post datetime: 2015-03-31T18:07:13+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

Err... I guess you didn't get what I meant. XD
I was asking you to translate it into spanish with the aid of MY tools.
There's already a spanish team working on it with my programs and they need help.
So... let me know if you want to do it. 
Anyway, I don't find it nice that you accuse that guy in that horrible way. LOL
He isn't obliged to share something. He may have had some problems, who knows.
## Post #81
- Username: KiRAfromYouTube
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Sep 03, 2010 9:53 pm
- Post datetime: 2015-03-31T21:05:45+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

I agree with Sorakairi regarding accusing MayBeePah.

Farlavor, this is not the place for your "inner rage" just because he can pull all those models out by himself. We're here to learn on how these formats worked and perhaps some of the members here are working on tools/programs to be able to read these formats.

So, instead of you writing a long post and going ape-rage about one particular thing, how about if you help us with these formats?
## Post #82
- Username: MayBeePah
- Rank: advanced
- Number of posts: 44
- Joined date: Mon Oct 06, 2014 2:22 pm
- Post datetime: 2015-04-01T04:32:06+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

Because Farlavor is being impatient, I'll may as well say that I'm actually working on a big surprise for everyone...
But don't want to say yet, I still need time.

I've tried avoiding contact with everyone because I though you all could wait.

Sorry, Bye
## Post #83
- Username: KiRAfromYouTube
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Sep 03, 2010 9:53 pm
- Post datetime: 2015-04-01T06:39:27+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

MayBeePah:- No worries, just take your time. I'm looking forward for what you can come up with.
## Post #84
- Username: Sorakairi
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Aug 21, 2011 4:35 pm
- Post datetime: 2015-04-02T14:10:48+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

Some people asked me to share the full pack of KH3D's textures for HUD, Menus, Maps, etc...
Here's a link to download them :

[http://adf.ly/1CrCEz](http://adf.ly/1CrCEz)

Bye!

~Sorakairi
## Post #85
- Username: Farlavor
- Rank: beginner
- Number of posts: 24
- Joined date: Tue Apr 10, 2012 7:02 pm
- Post datetime: 2015-04-02T20:16:07+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

> Reply from MayBeePah
>
> Because Farlavor is being impatient, I'll may as well say that I'm actually working on a big surprise for everyone...
But don't want to say yet, I still need time.

I've tried avoiding contact with everyone because I though you all could wait.

Sorry, Bye

Ok, ok... I got it... but I think that confusing my despair with inpatientness is also being rude... becuz, at least that's masking the truth.   

Just I believed you were gone, since I had no news about you on both Models resource and here, even an user was doing some kind of campaign to get ppl to help him on ripping the models in your place. I forgot his nickname, but I think his posts lies somewhere here and Models resource post.

also. I didn't meant to be rude with SoraKairi... I wasn't meant to take the translation so seriously... I would just take an example of what I would do if I were you, MayBeePah.
besides on the time I posted that, I didn't knew it was already possible to translate the game on any language possible. I discovered that when I saw the page of SoraKairi... 

SoraKairi, My apologies if you were offended with that explanation...   
But Hey... at first I was saying that sarcastically... but after some thinking. I think I will do it... but not today. I will take some time before doing that.   

As I said before... I was really desperated... oh gosh, you were gone for over two months, and still had the guts to say that?   ... if it would happen on 1st of april... I would be fallen on Fools day. but since it happened on day 2... at least I know it's not a joke.   
Sorry for being rude about saying "Having guts"... but I wanted to just spit that out, before exploding in anger.
I really loved your project, you cannot simply quit like making the MOST EPIC YAOMING MEME EVER.

if that so, Instead of making a Yaoming meme... You would turned it into just this meme.



I saw plenty of projects being cancelled, 

(Flash videos)
Eevee Party 3, Warrior Cats, Super Mario Bros Z. (And others)

(Videogames, Fan games)
MKF, Cube World. (and some more)

(Spanish Loquendo Youtubers)
Winnieco, Taroken, KrzKreations. (And others)

(Program/tools updates)
Noesis, 3D Ripper DX. (And a few others)

That's why, I believed you cancelled the project as well... so sorry.   
Maybe if you would at least leave you a signal of life posting something and not just some logins here or there.   

Why everything I loved so much, no matter what it is, ends cancelled like all of stuffs I mentioned above?   
Sorry for what I had caused. I always hated this page since a few months ago for the following reasons.

1- Since the forum staff had changed the rules, now I cannot clarify if I can upload model data or not, since you said everything copyrighted cannot be uploaded here.
2- before the change of rules, on main page, I could see weekly news about ripping data, meaning you can see details of progressions so perfectly, that way I could get the Noesis plugin to import Enchanted arms models.   
3- MR. Adults has quit from updating his Noesis... and from now on, There will be no further updates on it's plugins, and out there are NIF formats that needs support for Noesis... like Shin Megami Tensei Imagine, or Atlantica Online models. 
and just don't forget GTA V models (Like animals, NPCs or vehicles), or even the models I was about to send here before the change of rules... A model from a PSP game called Toriko Gourmet Survival 1... or even the sequel if you wish too. 

that's why I preferred Models Resource over here... but I came to see progress from you MayBeePah... so sorry for everything.
## Post #86
- Username: GovanifY
- Rank: advanced
- Number of posts: 59
- Joined date: Thu Apr 17, 2014 4:25 am
- Post datetime: 2015-05-11T19:06:27+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

Wow lots of new stuff there!
Welp yeah, I actually am super busy(sorry T_T) and am only discussing at my free time on skype w/ few peoples(ChrisX930 pops in my mind atm)
I'm amazed of all the work that has been done ever since romhack has been possible, and yeah all that has been done is awesome.
As I said to SoraKairi if I ever get to have enough time I'll release my tool(YES THERE WILL  BE A DDD_TOOLKIT W/ PATCH SYSTEM) but again I'm more than supa busy atm ;_;
For exemple my RECOM_Toolkit is almost finished, I did it in like a week a while ago, but I NEVER HAD A CHANCE TO FIX THE FEW BUGS THAT ARE STILL THERE.
Needless to say guys are asking me for my CFW *cough* I'm not pointing to anyone *cough* wants me to create tools and so....

Gimme a break life ;_;

So yeah can't do that much, just thank this awesome community that is around this serie of games, love y'all!

And again I don't mind if you want to contact me on skype, just know I'm KIND OF BUSY.

And so gj to SoraKairi, MayBeePah, and as always old ones, such as Azurfan or Falo(saw one profile pic' here, can't say which)
So bye, and good luck!

-GY
## Post #87
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2015-05-12T03:06:44+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

GovanifY, is this bye for good, or are you going to make new KH tools sometime in the future? I always love downloading your latest code and programs for meddling with the Kingdom Hearts games. And with MayBeePah going months without posting so much as a WIP of his next big thing, it would be a shame to lose you too.
## Post #88
- Username: GovanifY
- Rank: advanced
- Number of posts: 59
- Joined date: Thu Apr 17, 2014 4:25 am
- Post datetime: 2015-05-12T16:11:27+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

Temporary, just need time!
As for an ETA:
KH1FM_Toolkit: Released(have to work on it one day but...meh)
KH2FM_Toolkit: Released
RECOM_Toolkit: In dev(need time to finish it; will be open source)
BBSFM_Toolkit: Same as before
KHDDD_Toolkit: Same as before

For tools most of my tools(Eventviewer_Editor, MDLX_TEST, CTT_Editor and so are on my comp' and almost finished, just need to finish 'em(as advanced as RECOM_Toolkit for most, aka almost finished and usable yet not featuring all I want to))

So yeah only temporary until life gives me more time ;_;


(for 358 or re:coded or com don't even think about a toolkit or tools)
## Post #89
- Username: MayBeePah
- Rank: advanced
- Number of posts: 44
- Joined date: Mon Oct 06, 2014 2:22 pm
- Post datetime: 2015-05-18T05:19:54+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

I thought I'd tell everyone what I've been working on for the past months...

I'm learning how to read Assembly Language and for a while now I've been reversing the Binary of Kingdom Hearts 3D, this I what I'm working towards :
- Every format will be reverse engineered
- Data as Xml files eg. stats, events...
- All models with animations
- Attack/Magic/Keyblade effects animated
- Music, sound effects
- World Models with collisions
- Cutscene Animations

Each model comes with a Dae and Obj format
Each world & cutscene can be imported straight into Blender or Unity

This has been my first ever try on reverse engineering and I've learnt a lot.
I have been working hard on this for a while now, but I also have to work on other things, so I don't know If I'll finish this project soon...

This will give everyone the base for creating mods, cutscene editing, etc... You could end up recreating the whole game If you wanted.

I'm trying to make this the most comprehensive Kingdom Hearts Reversing Project, and I hope you all will be happy with what I've achieved.
I may or may not be finished this year, but It'll be worth the wait
## Post #90
- Username: GovanifY
- Rank: advanced
- Number of posts: 59
- Joined date: Thu Apr 17, 2014 4:25 am
- Post datetime: 2015-05-18T15:15:35+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

Well MayBeePah this is a really good idea but, trust me, you won't finish it before a while.
A while ago I did the same for KH2FM, and trust me, even if it is a lot harder than DDD to understand/mod( in fact EVERYTHING is custom) I was never able to finish it.
I made html pages for almost all format, listed all files I could, tried to do the most I could on events and tool creating and....as you see it never ended.

I wish you good luck but I don't think you will finish this soon(unless you have a shitload of free time and if you do I'll have to say to you something: lucky bastard ;3)

But yeah, that's my thougts on this.
-GY
## Post #91
- Username: jadentheman
- Rank: n00b
- Number of posts: 18
- Joined date: Fri Oct 24, 2014 7:21 am
- Post datetime: 2015-05-18T21:33:36+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

Reversing everything is a hard task, but there's far more documentation on ARM assembly than MIPS I think. That and the fact that the engine is the same one used for BBS so the file research done for BBS will help MayBeePah a bit more than just figuring stuff from nothing like you had to with KH2FM.

A handheld game hopefully isn't as complex as a console game
## Post #92
- Username: MayBeePah
- Rank: advanced
- Number of posts: 44
- Joined date: Mon Oct 06, 2014 2:22 pm
- Post datetime: 2015-05-19T01:56:56+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

I'm also making my own Arm disassembler specific for 3Ds games with the ctr SDK functions included, I'm not using IDA Pro... plus doing it all myself makes everything easier to understand.
I'm not someone who gives up, before I started this project I knew nothing about everything I've done so far.

when I first started extracting Kingdom Hearts 3D I made all my own tools. 
I figured out how to hex edit, 3d modelling (Vertices, UV maps, Normals, TriangleStrips),  learnt about 3 different compression techniques for textures, now I'm making my own program to automatically identify where the Arm binary accesses files. I very hopeful I will finish this project because of how much I've learnt 

I expect It'll take a while, but I expect to Finish...
## Post #93
- Username: GovanifY
- Rank: advanced
- Number of posts: 59
- Joined date: Thu Apr 17, 2014 4:25 am
- Post datetime: 2015-05-19T13:36:07+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

Trust me, you won't finish this quickly, even if I hope you do.
Having created your own disasm is, though, impressive since having one as easy to use as IDA Pro's kind of hard.
Really glwt but trust me, it's a hard task(actually it is SO EASY compared to KH2FM since basically it's the same engine(and file formats most likely) than BBS but hey)
and it'll take a while but it is possible.

I cannot give you any help for now(busy w/ a lot of shits atm) but if you ever need help later I'd be glad to help ya(even if I know that working in solo is easier most of the time(at least it is for me))
## Post #94
- Username: Farlavor
- Rank: beginner
- Number of posts: 24
- Joined date: Tue Apr 10, 2012 7:02 pm
- Post datetime: 2015-05-24T14:44:49+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

> Reply from MayBeePah
>
> I'm also making my own Arm disassembler specific for 3Ds games with the ctr SDK functions included, I'm not using IDA Pro... plus doing it all myself makes everything easier to understand.
I'm not someone who gives up, before I started this project I knew nothing about everything I've done so far.

when I first started extracting Kingdom Hearts 3D I made all my own tools. 
I figured out how to hex edit, 3d modelling (Vertices, UV maps, Normals, TriangleStrips),  learnt about 3 different compression techniques for textures, now I'm making my own program to automatically identify where the Arm binary accesses files. I very hopeful I will finish this project because of how much I've learnt 

I expect It'll take a while, but I expect to Finish...

Okay... At least you made it this far... And I had readed your previous post telling us your plans on KHDDD models... Anyway I wonder, how could you make the magic animations to be reproduced on 3d programs?... I mean you may rip the models, but some spark effects looks kinda 2D and somehow requires of complex methods to make those visuals in a 3d environment... I saw those effects on other kh games but it was possible with the proper gaming engine... And normally ripped models of any animated character cannot reproduce those effects, like Axel's fire chakrams for example. Anyway... It is just curiosity, I am much more interested on the dream eaters models.   

At least I had seen progressions and of course you did not left this topic dying... Cuz of course would be really annoying having to bump/necropost...   

Ok... Gotta wait more...
## Post #95
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2015-05-24T17:33:52+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

MayBeePah, it's great that you're working on a full disassembly of the game. However, as it will admittedly take years to complete the work, it would be nice to see screenshots of your progress every now and again, just so that people don't lose interest and necro this thread. I'm still really interested in the model exporter and I wonder when it will be able to output all the character meshes in the game. I'm also curious to see if any models that didn't make the final cut are still in the game's files. I hope one day I will be able to get my hands on all the handy tools you are developing from scratch for KH3D.
## Post #96
- Username: GovanifY
- Rank: advanced
- Number of posts: 59
- Joined date: Thu Apr 17, 2014 4:25 am
- Post datetime: 2015-05-24T21:27:38+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

You mean such as the letters in the ending? If so watch this: [https://www.youtube.com/watch?v=gV7XL4_a4dg](https://www.youtube.com/watch?v=gV7XL4_a4dg) (sorry for the sound D:) 
Ofc letters and some other models are still in game
## Post #97
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2015-05-25T05:09:29+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

Still haven't figured out the sound problems with that video?
## Post #98
- Username: MayBeePah
- Rank: advanced
- Number of posts: 44
- Joined date: Mon Oct 06, 2014 2:22 pm
- Post datetime: 2015-05-28T11:55:21+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

Another little surprise for you all -> [https://db.tt/PwemlYKM](https://db.tt/PwemlYKM)

Tell me if anything went wrong
## Post #99
- Username: mysis
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Aug 14, 2014 6:45 pm
- Post datetime: 2015-05-28T14:53:11+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

UVs need to be flipped when viewing in noesis
## Post #100
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2015-05-28T15:57:59+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

Holy Guacamole, MayBeePah made a Noesis plugin for KH3D models and just released all the Dream Eaters!
## Post #101
- Username: MayBeePah
- Rank: advanced
- Number of posts: 44
- Joined date: Mon Oct 06, 2014 2:22 pm
- Post datetime: 2015-05-28T21:06:36+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

The grey textures ending in _g0 are for changing the colour of the dream eater so you should set them to overlay and set what ever colour you want
The textures ending in _E are emission textures for the eyes

I couldn't see any UV problems in Unity, Blender or Photoshop so It doesn't really matter
## Post #102
- Username: MayBeePah
- Rank: advanced
- Number of posts: 44
- Joined date: Mon Oct 06, 2014 2:22 pm
- Post datetime: 2015-05-28T22:15:22+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

More coming soon...
[island.jpg](https://xentaxbackup.github.io/file/9240_island.jpg)
## Post #103
- Username: MayBeePah
- Rank: advanced
- Number of posts: 44
- Joined date: Mon Oct 06, 2014 2:22 pm
- Post datetime: 2015-05-31T04:00:33+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

maps.png (124.12 KiB) Viewed 121 times

 Maps can be exported now
## Post #104
- Username: MayBeePah
- Rank: advanced
- Number of posts: 44
- Joined date: Mon Oct 06, 2014 2:22 pm
- Post datetime: 2015-05-31T04:46:36+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

[nd.png](https://xentaxbackup.github.io/file/9247_nd.png)
## Post #105
- Username: Azurfan
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Jun 24, 2010 5:12 am
- Post datetime: 2015-05-31T12:47:23+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

Wow, this is great MayBeePah. Also thanks for the Dream Eaters, do you know how the disposition (eye color) change works model-wise though? Is it just a texture replacement or something else?
## Post #106
- Username: MayBeePah
- Rank: advanced
- Number of posts: 44
- Joined date: Mon Oct 06, 2014 2:22 pm
- Post datetime: 2015-05-31T13:16:07+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

You could just change the diffuse colour or change the textures, doesn't matter 
You can make new shapes and mix other dream eater textures together too, if you change the textures.
[eyes.png](https://xentaxbackup.github.io/file/9249_eyes.png)
## Post #107
- Username: Azurfan
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Jun 24, 2010 5:12 am
- Post datetime: 2015-06-04T14:59:30+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

I know and that's totally a cool thing to do.   It's just that not only is the pupil's color changing but also its shape and these shapes are different for (almost) every Dream Eater (at least I think they are). I just wondered how the game does that since often they are part of the texture.

Edit: After checking every model it seems that the eye texture is often stored separately, would you mind uploading the rest too?
[Disposition.jpg](https://xentaxbackup.github.io/file/9259_Disposition.jpg)
## Post #108
- Username: Disgustor1
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jun 13, 2015 3:04 pm
- Post datetime: 2015-06-13T07:11:07+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

Would somebody mind updating the link to the models? It 404'd. I've been waiting a long time to get these models! Thank you very much for your hard work as well MayBeePah.
## Post #109
- Username: Dorigon
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Jan 02, 2012 3:04 am
- Post datetime: 2015-06-14T18:16:00+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

Hi, can someone explain me how to edit the .CTD files?

I tried with CTD_Editor but no way, I just get an error
## Post #110
- Username: Farlavor
- Rank: beginner
- Number of posts: 24
- Joined date: Tue Apr 10, 2012 7:02 pm
- Post datetime: 2015-06-19T00:56:52+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

dear MayBeePah.

The link you provided to dl the Dreameaters along with the plugin is broken, it leads me to a 404 error... 

ah, I almost forgot to mention the guy who was behind of my worryness... if you just told me I was impatient... you maybe forgot the one who has got the golden trophy of the impatientness...

EVERYONE HAIL TO... myrzavkin...   

Anyway... it's not a reason to blame HIM or me for this... you went MIA for over 3 months... and since those damned rules called "NO NECROPOSTING ALLOWED" or "NO BUMPING ALLOWED" ever existed... Anyone had to take charge... and honestly... I wouldn't figured out anything. since I have no idea of format compressions shenanigams, so I just would copy/paste all the stuff figured out so far by others... 

In other words... I SUCK!...    
unlike you my fella...   

It's not meant to steal you any credit... it's just simply we didn't want your project to die... you know?   

The only thing I only suggest you is to reupload the files please. becuz it seems those are gone for good. or at least... share them to models resource too... we waited for over half a year for this.
and I want to grab those dream eaters and test with the texture overlays... to find out the possible variations of color I may get, specially for making some custom dream eaters. maybe even with a few little modifications I may create Heartless/Nobody versions too...   
I will wait for your reupload... thanks and sorry for all the trouble... I only wanted the dream eaters... the human characters are just the lowest priority models... 
as well as keyblades, (Maybe the only keyblades I want are the Lea's, Master Xehanort's/Terranort's and Young Xehanort's (The one with the ability to control time) keyblades). So... Just with only the Dream Eaters I will be nore than satisfied...   

so once again... Thanks a lot...  

PS2: I didn't knew the Dream Eaters eyes were separated from the original files... it seems your ripping almost got 100% or just didn't noticed that... Not just like I would care... but I think I know why you deleted the uploading file. Was because you forgot the textures for the eyes (Like the ones from Meow wow) isn't it?.
If that's so... I wouldn't give a *censored* to those eyes... but maybe in the future. I may need them. so okay... more reasons for waiting...
## Post #111
- Username: MayBeePah
- Rank: advanced
- Number of posts: 44
- Joined date: Mon Oct 06, 2014 2:22 pm
- Post datetime: 2015-06-19T01:08:36+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

The link still works for me? [https://db.tt/PwemlYKM](https://db.tt/PwemlYKM)
Don't know what happened...
## Post #112
- Username: Farlavor
- Rank: beginner
- Number of posts: 24
- Joined date: Tue Apr 10, 2012 7:02 pm
- Post datetime: 2015-06-19T01:14:50+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

> Reply from MayBeePah
>
> The link still works for me? https://db.tt/PwemlYKM
Don't know what happened...

ok... It seems your link was right...
maybe it was just an error when posting it.

Thanks.   


PS: too strange... This is the 3rd time I got a quickest response in a random forum on this year... normally it takes up to 24 hours for a reply...  (Did everyone woke up tonight???)
## Post #113
- Username: MayBeePah
- Rank: advanced
- Number of posts: 44
- Joined date: Mon Oct 06, 2014 2:22 pm
- Post datetime: 2015-06-19T01:18:28+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

These are only test models though, so they have bugs. I used an old exporter for them.
My new one will come with animations and everything else including effects
## Post #114
- Username: Farlavor
- Rank: beginner
- Number of posts: 24
- Joined date: Tue Apr 10, 2012 7:02 pm
- Post datetime: 2015-06-19T01:55:12+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

> Reply from MayBeePah
>
> These are only test models though, so they have bugs. I used an old exporter for them.
My new one will come with animations and everything else including effects

Ok... I will try something with these for now.  

Anyway it seems I have no idea of how to do the colouring... I know something about textures (Diffuse, Specular, Luminance, Etc), but I dunno about overlays... I am using Cinema 4D but I can use 3DS Max too... if you know how can I do the colourings in textures, please send me a tutorial on PM or a videotutorial for 3DS Max if there's one on Youtube, and I will try it... besides. Considering that my best choice for vertex wielding and subdivision is using 3DS Max (As well as basic rigging), then I will use it.
(I did managed to do it on C4D but I dunno if I can do it on 3DS Max, for now, see "edit2")

Thanks in advance.  

if some of these bugs does affect some dream eaters disallowing me to do the colouring... (I tested Meow wow), then... it's okay... By testing I did managed to make a demonic kind of Meow Wow... MWAHAHAHAHAAAAA....   
and I think I'm gonna play with it a little...  

Edit: Oh wait... I think I remembered something I did with a model I was making days ago with multiple textures... let's see if I can do the Overlay by myself on Cinema 4D. 

Edit2: Oh yeah... It seems that Meow Wow is bugged (On Cinema 4D) I did noticed the G0 has no Alpha channel so I had to add it manually. and now it became the Overlay by placing it properly... AWESOME... I have my first unrigged and fully colourable Meow Wow... now it's my turn to rig it.
## Post #115
- Username: Truthkey
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Jul 24, 2010 5:39 am
- Post datetime: 2015-06-21T01:53:29+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

> Reply from Mirrorman95
>
> Holy Guacamole, MayBeePah made a Noesis plugin for KH3D models and just released all the Dream Eaters!

Where's the plugin? D:
## Post #116
- Username: myrzavkin
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Jun 26, 2012 9:53 pm
- Post datetime: 2015-06-21T20:29:08+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

> Reply from Farlavor
>
> dear MayBeePah.

The link you provided to dl the Dreameaters along with the plugin is broken, it leads me to a 404 error... 

ah, I almost forgot to mention the guy who was behind of my worryness... if you just told me I was impatient... you maybe forgot the one who has got the golden trophy of the impatientness...

EVERYONE HAIL TO... myrzavkin...   

Anyway... it's not a reason to blame HIM or me for this... you went MIA for over 3 months... and since those damned rules called "NO NECROPOSTING ALLOWED" or "NO BUMPING ALLOWED" ever existed... Anyone had to take charge... and honestly... I wouldn't figured out anything. since I have no idea of format compressions shenanigams, so I just would copy/paste all the stuff figured out so far by others... 

In other words... I SUCK!...    
unlike you my fella...   

It's not meant to steal you any credit... it's just simply we didn't want your project to die... you know?

Your wall of text... Again... talk less... Nobody fucking cares tbh...
You could end on "it leads me to 404 error"
Anyway im not impatient i just wanted to bump this thread
And im glad maybee has returned with good news.
## Post #117
- Username: Farlavor
- Rank: beginner
- Number of posts: 24
- Joined date: Tue Apr 10, 2012 7:02 pm
- Post datetime: 2015-06-23T02:27:56+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

Hey you... I don't fucking care you don't like my wall of texts... I just say the damn TRUTH... you were the impatient one and made me become desperate to do that kind of stuff while I was the ONLY ONE who was being really patient... making kinds of misunderstanding... even you posted the same cr@p on Models Resource... so Deal With it my fella.

To all the people who needs explanations I cannot resume this. I WAS DESPERATED... NOT IMPATIENT... and that was thanks to you!.

stop saying that kind of stuff right now... it only shows me how right I am.
And I have no time to waste on fools, I am here for those damn models.
6 months of waiting must worth it, since Mr Adults stopped adding support to newer formats on Noesis, This page has lost all my interests and they didn't posted weekly news about ripping and making rules that simply says it's forbidden uploading ANY MODELS (Since every videogame model has Copyright), and Noesis was by far the best model ripping tool than anything else.  so
## Post #118
- Username: MayBeePah
- Rank: advanced
- Number of posts: 44
- Joined date: Mon Oct 06, 2014 2:22 pm
- Post datetime: 2015-06-23T04:06:06+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

Can we end all of these pointless arguments please
## Post #119
- Username: white emperor
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jun 24, 2015 10:56 pm
- Post datetime: 2015-06-24T15:04:23+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

hey good work for this project  however can you put link for the map?
## Post #120
- Username: white emperor
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jun 24, 2015 10:56 pm
- Post datetime: 2015-06-26T00:03:46+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

or the texture of the map?
## Post #121
- Username: MayBeePah
- Rank: advanced
- Number of posts: 44
- Joined date: Mon Oct 06, 2014 2:22 pm
- Post datetime: 2015-06-26T01:36:45+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

Maps won't be released for a while because I haven't finished my exporter yet. Sorry I'm too busy with work...
## Post #122
- Username: KiRAfromYouTube
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Sep 03, 2010 9:53 pm
- Post datetime: 2015-06-26T13:14:07+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

You did an amazing job! I haven't checked the Dream Eater models yet, but I'm looking forward for more work that you've done.
Keep us posted!
## Post #123
- Username: Farlavor
- Rank: beginner
- Number of posts: 24
- Joined date: Tue Apr 10, 2012 7:02 pm
- Post datetime: 2015-06-29T16:57:12+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

> Reply from MayBeePah
>
> Maps won't be released for a while because I haven't finished my exporter yet. Sorry I'm too busy with work...

Ok... No worries. on my opinion, I am not interested on maps or scenario models. I only want rigged models of the dream eaters, some characters and a few Keyblades... Anything else is redundant for me.   

of course if I would need maps, If you hadn't finished your exporter yet, What's the point in rushing... it's not like you will be AFK for another 6 months.

PS: Even if it will take over that time... I still have the dream eaters you shared. I know those are unrigged... but, I will rig them by myself... and use them temporarily until the day the rigged models are uploaded... 
(And yet I only had tested Meow Wow, becuz it was my top priority model   )
## Post #124
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2015-06-29T23:36:30+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

> Reply from Farlavor
>
> MayBeePah wrote:Maps won't be released for a while because I haven't finished my exporter yet. Sorry I'm too busy with work...

Ok... No worries. on my opinion, I am not interested on maps or scenario models. I only want rigged models of the dream eaters, some characters and a few Keyblades... Anything else is redundant for me.   

of course if I would need maps, If you hadn't finished your exporter yet, What's the point in rushing... it's not like you will be AFK for another 6 months.

PS: Even if it will take over that time... I still have the dream eaters you shared. I know those are unrigged... but, I will rig them by myself... and use them temporarily until the day the rigged models are uploaded... 
(And yet I only had tested Meow Wow, becuz it was my top priority model   )
If you do manage to rig all the Dream Eater models before MayBeePah does, could you upload them when you do?
## Post #125
- Username: Truthkey
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Jul 24, 2010 5:39 am
- Post datetime: 2015-07-03T18:03:22+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

> Reply from MayBeePah
>
> Maps won't be released for a while because I haven't finished my exporter yet. Sorry I'm too busy with work...

I know it may sound rude to ask you out of nowhere, but would it be possible to get Young Xehanort's HQ model even if it's without bones? (not the one with the Org coat, the one with regular clothing)
It would solve me a lot of problems and I would be grateful to you forever. xD
## Post #126
- Username: MayBeePah
- Rank: advanced
- Number of posts: 44
- Joined date: Mon Oct 06, 2014 2:22 pm
- Post datetime: 2015-07-31T11:59:04+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

Sorry I'm late, I have a lot of work going on at the moment.
But I hope everyone will be happy with this : 
[https://db.tt/fo89x5VL](https://db.tt/fo89x5VL)
[https://db.tt/yuDMt3fD](https://db.tt/yuDMt3fD)
## Post #127
- Username: Pleasance13
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jun 20, 2015 10:59 pm
- Post datetime: 2015-07-31T14:32:10+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

> Reply from MayBeePah
>
> Sorry I'm late, I have a lot of work going on at the moment.
But I hope everyone will be happy with this : 
https://db.tt/fo89x5VL
https://db.tt/yuDMt3fD

Oh man, this is magnificent! Thanks a lot MayBeePah, this helps me out a lot. I'll make sure to credit you for ripping these models in any projects I use them in.
## Post #128
- Username: kinlyki
- Rank: advanced
- Number of posts: 40
- Joined date: Sun Jun 21, 2015 12:36 am
- Post datetime: 2015-08-01T01:30:10+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

I can't find Armored Ventus Nightmare, is it not in there?
## Post #129
- Username: MayBeePah
- Rank: advanced
- Number of posts: 44
- Joined date: Mon Oct 06, 2014 2:22 pm
- Post datetime: 2015-08-01T01:57:53+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

Bosses have a different kind of PMO format. Just wait a bit
## Post #130
- Username: MayBeePah
- Rank: advanced
- Number of posts: 44
- Joined date: Mon Oct 06, 2014 2:22 pm
- Post datetime: 2015-08-01T03:11:00+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

Fixed  here are the Bosses : [https://db.tt/e7hwybRr](https://db.tt/e7hwybRr)
## Post #131
- Username: Azurfan
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Jun 24, 2010 5:12 am
- Post datetime: 2015-08-02T09:06:08+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

Thanks for all the models MayBeePah, you the real MVP.
## Post #132
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2015-08-02T17:28:09+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

Thanks  Any chance of getting these with their skeleton data intact?

Weird, some textured have been resized to 512x512. Looks like the just used photoshop to resize them, the quality has decreased on some of them. It's nice to see a model of Xion, too 

Also playable Sora and Riku aren't included in the pack.
## Post #133
- Username: MayBeePah
- Rank: advanced
- Number of posts: 44
- Joined date: Mon Oct 06, 2014 2:22 pm
- Post datetime: 2015-08-02T21:13:38+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

Which models have textures resized, I might be a bug but I could check.
## Post #134
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2015-08-02T21:19:52+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

H_DI020 - KH2 Kairi
H_EH010 - Vanitas
H_EH120 - Ansem SoD

They may have just nerfed some quality when they ported them to 3ds. There's new Terra textures at 512x512 as well. H_EX160.
## Post #135
- Username: kinlyki
- Rank: advanced
- Number of posts: 40
- Joined date: Sun Jun 21, 2015 12:36 am
- Post datetime: 2015-08-09T03:34:21+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

I can't actually find Armored Ventus Nightmare's Keyblade texture.
## Post #136
- Username: Truthkey
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Jul 24, 2010 5:39 am
- Post datetime: 2015-08-11T10:39:32+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

Thank you very much, MayBeePah!! You saved me a lot of work.
## Post #137
- Username: KiRAfromYouTube
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Sep 03, 2010 9:53 pm
- Post datetime: 2015-08-12T13:02:22+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

These are amazing work you have done. Thank you so much! 
However, would it be possible if you can export the models with bones in it?
## Post #138
- Username: MayBeePah
- Rank: advanced
- Number of posts: 44
- Joined date: Mon Oct 06, 2014 2:22 pm
- Post datetime: 2015-08-12T14:19:49+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

I can export them with bone structures, but there just vertex points with no connections.
Because Obj doesn't support bones...

I'm working on a Dae exporter with bone weights, vertex colours, etc though I haven't found the time to finish yet. Sorry.
## Post #139
- Username: KiRAfromYouTube
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Sep 03, 2010 9:53 pm
- Post datetime: 2015-08-12T23:31:42+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

That's alright, friend. Just take your time.
## Post #140
- Username: Farlavor
- Rank: beginner
- Number of posts: 24
- Joined date: Tue Apr 10, 2012 7:02 pm
- Post datetime: 2015-08-16T06:30:22+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

> Reply from MayBeePah
>
> I can export them with bone structures, but there just vertex points with no connections.
Because Obj doesn't support bones...

I'm working on a Dae exporter with bone weights, vertex colours, etc though I haven't found the time to finish yet. Sorry.

Indeed that's quite reasonable. 
You got a point about the OBJ not being able to support bones.
I think you've done the most difficult part when converting the raw model files into OBJ.
It's just the same thing but instead of OBJ, just exporting to DAE.

I don't know really how hard is the reverse engineering to convert a model into specific formats, specially with bones, but it's okay... I will wait wathever it takes. 
and this time... is seriously.
## Post #141
- Username: KiRAfromYouTube
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Sep 03, 2010 9:53 pm
- Post datetime: 2015-08-16T14:47:10+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

> Reply from Farlavor
>
> Indeed that's quite reasonable. 
You got a point about the OBJ not being able to support bones.
I think you've done the most difficult part when converting the raw model files into OBJ.
It's just the same thing but instead of OBJ, just exporting to DAE.

I don't know really how hard is the reverse engineering to convert a model into specific formats, specially with bones, but it's okay... I will wait wathever it takes.
and this time... is seriously.

What I know so far about these 3D formats is that .OBJ and .3DS (not to be confused with dumped .3DS roms) are both static objects, which means you can't put any skeleton or bones data information in it, just a simple geometry mesh data.

As for .DAE (Collada), .SMD (Valve), .FBX (Autodesk), .MDL (Quake) are the formats that's enable you to insert the skeletal data information, thus enables you to export the model with skeletons in it.

I may not as much know about reverse engineering and such, but if MayBeePah could figure out these formats, I think he's the first user who's able to pull this off alone and I'm very thankful to him for doing this for us.
## Post #142
- Username: Azurfan
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Jun 24, 2010 5:12 am
- Post datetime: 2015-08-19T06:53:16+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

> Reply from kinlyki
>
> I can't actually find Armored Ventus Nightmare's Keyblade texture.
At least for me it was in the folder of the Keyblade or do you mean something different? It's basically a black re-skin of the Kingdom Key.
## Post #143
- Username: kinlyki
- Rank: advanced
- Number of posts: 40
- Joined date: Sun Jun 21, 2015 12:36 am
- Post datetime: 2015-08-20T01:23:40+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

> Reply from Azurfan
>
> kinlyki wrote:I can't actually find Armored Ventus Nightmare's Keyblade texture.
At least for me it was in the folder of the Keyblade or do you mean something different? It's basically a black re-skin of the Kingdom Key.
That Keyblade looks more like it is for Anti-Sora then Ventus Nightmare. I checked the video footage of the final battle of KH3D, Ventus Nightmare's Keyblade doesn't have a blue tint.
## Post #144
- Username: Azurfan
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Jun 24, 2010 5:12 am
- Post datetime: 2015-08-21T17:59:32+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

> Reply from kinlyki
>
> Azurfan wrote:kinlyki wrote:I can't actually find Armored Ventus Nightmare's Keyblade texture.
At least for me it was in the folder of the Keyblade or do you mean something different? It's basically a black re-skin of the Kingdom Key.
That Keyblade looks more like it is for Anti-Sora then Ventus Nightmare. I checked the video footage of the final battle of KH3D, Ventus Nightmare's Keyblade doesn't have a blue tint.
Hmm, I never noticed that the Anti-Soras from the dive segment also have Keyblades. Still, I watched some footage by Everglow and Cyberman65 and can't make out a difference between these two, even though I admit that the coloring is extremly similiar to the AntiSora Keyblade of the original Kingdom Hearts.
If there is indeed another dark Keyblade available there should also be another model not just another texture, hopefully MayBeePah can confirm or deny this.
## Post #145
- Username: MayBeePah
- Rank: advanced
- Number of posts: 44
- Joined date: Mon Oct 06, 2014 2:22 pm
- Post datetime: 2015-08-22T06:15:06+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

I've checked every PMO in the game, I couldn't find any more keyblades.
But the FEP (Effect) files contain more models, they also may contain unused models and other things as I found a cinderella texture in one of them from bbs.

I'm still looking though...
## Post #146
- Username: kinlyki
- Rank: advanced
- Number of posts: 40
- Joined date: Sun Jun 21, 2015 12:36 am
- Post datetime: 2015-08-24T07:35:10+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

Wish you the best of luck
## Post #147
- Username: Farlavor
- Rank: beginner
- Number of posts: 24
- Joined date: Tue Apr 10, 2012 7:02 pm
- Post datetime: 2015-09-16T19:14:50+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

> Reply from MayBeePah
>
> I've checked every PMO in the game, I couldn't find any more keyblades.
But the FEP (Effect) files contain more models, they also may contain unused models and other things as I found a cinderella texture in one of them from bbs.

I'm still looking though...

Okay, No problem.

it seems like you have done with every PMO files available. 
I dunno if you can find any secret models on FEP files.

it's good to know that tidbit.
## Post #148
- Username: raulr
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Oct 25, 2014 11:23 pm
- Post datetime: 2016-02-06T08:51:32+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

Hi there.
I want to extract the video files, can someone help me?
I think they are .moflex files.
## Post #149
- Username: Farlavor
- Rank: beginner
- Number of posts: 24
- Joined date: Tue Apr 10, 2012 7:02 pm
- Post datetime: 2016-02-12T05:00:27+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

huh? is that all?

Sorry for bumping. but I thought it has some progression since the big surprise from MayBeePah.

Goddamn, it seems that the peoples memory is as dead as this comunity.

Neither they were able to crack J Star Victory VS contents and get the models.

#No-more-unrippable-games
## Post #150
- Username: KiRAfromYouTube
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Sep 03, 2010 9:53 pm
- Post datetime: 2016-02-25T22:02:55+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

To be fair, reverse engineering could take more than a year (if not months) to create. Like I mention before, I may not know much about reverse engineering, but it's not as easy as you think. MayBeePah's probably busy with his time, so please understand his situation.

As for all that, I'll be sitting here waiting for his next announcement.
## Post #151
- Username: MayBeePah
- Rank: advanced
- Number of posts: 44
- Joined date: Mon Oct 06, 2014 2:22 pm
- Post datetime: 2016-02-26T03:29:36+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

I'm very busy at the moment but, if you really want to know my progress...

I've built a game engine (based on Unreal Engine Source, using their core and shaders) for KHDDD, 
right now It supports
: animations and cutscenes with sound
: particle effects 
and reads
: state machine files (what sounds play when attacks are finished, boss attack sequences)
: save data
: meta data (where treasure chests are and what's in them, motion paths, enemy stats etc...)

I've made a debugger for citra, it creates structures related to files by finding where memory read/write's occurred...
Code that hasn't been reversed yet, I let citra handle it and return the results to my engine

When I think it's publicly usable it will be open source on github (requires you to have a uncompressed/decrypted RomFS & ExeFS of KHDDD to run it though) 
The main goal of this is to allow people to create mods or custom games based on kingdom hearts gameplay, no original source of KHDDD will be used.

I'll show a video soon and please be patient, I may release it at the end of this year or sooner depending on how much time I have.
## Post #152
- Username: Azurfan
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Jun 24, 2010 5:12 am
- Post datetime: 2016-02-26T09:19:52+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

That's really impressive, so you're (re-)building kind of a Kingdom Hearts engine that can be used to make your own adventures? Fantastic.
## Post #153
- Username: MayBeePah
- Rank: advanced
- Number of posts: 44
- Joined date: Mon Oct 06, 2014 2:22 pm
- Post datetime: 2016-02-26T10:34:43+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

To clarify:

Because all the code is my own everyone can use the engine for commercial purposes, no original code used from Kingdom Hearts just based on it...
And the engine is built from scratch using Unreal Engine source as inspiration, not copy and paste. So you don't have to have an Unreal Engine license.

If you want to play KHDDD you have to uncompress and decrypt Rom/ExeFS first (no instructions will be given), and all the files will be converted to my own formats for use in the engine.
But you can definitely create your own game with it. The engine won't be related to Kingdom Hearts, just an engine to has all the gameplay elements included.
## Post #154
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-02-26T17:08:17+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

> Reply from MayBeePah
>
> 
I've made a debugger for citra, it creates structures related to files by finding where memory read/write's occurred...
Code that hasn't been reversed yet, I let citra handle it and return the results to my engine

Neat! Will this technique be compatible with other games? Are you able to release info on that?
## Post #155
- Username: MayBeePah
- Rank: advanced
- Number of posts: 44
- Joined date: Mon Oct 06, 2014 2:22 pm
- Post datetime: 2016-02-28T06:53:12+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

Yes structures can be created for any 3ds game.

You make a breakpoint on what you want to find like "PMO" with khddd models.
When Citra accesses memory it'll find the first occurrence then a struct will be created based on how the memory was accessed and what type of Arm instruction was executed:

0x504D4F00 == "PMO"

struct S0 {
     int V0_int; //cmp 0x504D4F00 to Mem[0x10AB900] = 0x504D4F00
     char V1_char; //cmp 0x1 to Mem[0x10AB904] = 0x1
     char V2_char; //R0 = Mem[0x10AB905] = 0x1
     short V3_ short; //cmp 0x4 to Mem[0x10AB906] = 0x4
     char V4_char; //R3 = Mem[0x10AB908] = 0x1
     ...etc
}

You still need to make sense of the data yourself, but at least you can confirm the structure of it
## Post #156
- Username: KeybladeCrafter
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu May 26, 2016 12:52 pm
- Post datetime: 2016-06-01T04:51:10+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

I'm seeing a problem with the keyblades in Noesis. Some of the faces on the models are using the same texture for both sides of the face. The only way I've been able to make it go away is by looking at the original .obj in Noesis and flipping the Global UVs, but when I try to export (either from the preview or not), I still get the same problem. 

The only reason I'm trying to export is so I can rotate the keyblades to standing up. 

Before face cull toggle: [http://i.imgur.com/c8qoZp9.png](http://i.imgur.com/c8qoZp9.png)

After: [http://i.imgur.com/GE4CQ7A.png](http://i.imgur.com/GE4CQ7A.png)

also, as far as I know, it only does it on the hat of All for One (w_so30), the keychain of Ferris Gear (w_so50), and the gargoyle of Guardian Bell (w_so70), and only after rotating and exporting through blender. They look fine if I just flip the UV's in Noesis, but I need them rotated to stand up.
## Post #157
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2017-01-31T05:57:24+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

So uh...it's been a while...what's the status of this project? I've been wanting to extract the model of Clopin (the Jester from Hunchback of Notre Dame) for a friend of mine for ages, but uh...I can't seem to find a means to...
## Post #158
- Username: Sora6645
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Oct 24, 2014 4:16 am
- Post datetime: 2017-02-28T02:02:00+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

is there anyone who can do a bscar tool?
## Post #159
- Username: kinlyki
- Rank: advanced
- Number of posts: 40
- Joined date: Sun Jun 21, 2015 12:36 am
- Post datetime: 2018-07-11T03:17:21+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

Does anyone have the Noesis plugin Maybeepah once posted? Cuz all of his dropbox links have been dead for quite some time.
## Post #160
- Username: kinlyki
- Rank: advanced
- Number of posts: 40
- Joined date: Sun Jun 21, 2015 12:36 am
- Post datetime: 2018-07-30T16:15:24+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

So I used GL Intercept on Citra in the final boss battle and managed to get the REAL textures to Armored Ventus Nightmare's Keyblade.
[http://www.mediafire.com/file/vmldi5ds2b...s.zip/file](http://www.mediafire.com/file/vmldi5ds2b...s.zip/file)
## Post #161
- Username: DaniKH
- Rank: n00b
- Number of posts: 18
- Joined date: Thu Oct 11, 2018 5:15 am
- Post datetime: 2020-03-24T01:11:27+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

I know Im necroposting but I really need ask this; someone still have the plugin for noesis?
## Post #162
- Username: ElmerMouseFan34
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Dec 04, 2020 5:52 pm
- Post datetime: 2020-12-04T09:56:53+00:00
- Post Title: Re: Kingdom Hearts Dream Drop Distance models/voices

> Reply from MayBeePah ↑Wed Aug 12, 2015 10:19 pm at Wed Aug 12, 2015 10:19 pm
>
> 
I can export them with bone structures, but there just vertex points with no connections.
Because Obj doesn't support bones...

I'm working on a Dae exporter with bone weights, vertex colours, etc though I haven't found the time to finish yet. Sorry.

Hello,
Sorry to bump this, but I wanted to know if there's any progress on the DAE exporter.
