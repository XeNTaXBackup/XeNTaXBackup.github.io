## Post #1
- Username: Cloud452
- Rank: veteran
- Number of posts: 91
- Joined date: Sat Oct 23, 2010 9:50 pm
- Post datetime: 2012-07-20T07:21:29+00:00
- Post Title: Digimon World Re:Digitize

999 files located in the "INSDIR", sample file: [00000001.BIN](http://www.mediafire.com/?ufwaxw3fg45iacq)
## Post #2
- Username: Falo
- Rank: advanced
- Number of posts: 78
- Joined date: Fri Oct 23, 2009 8:29 pm
- Post datetime: 2012-07-20T13:35:28+00:00
- Post Title: Digimon World Re:Digitize

This is the wrong file ^^
the INSDIR is for data installation, you need to extract the decrypt key from EBOOT.BIN and decrypt all files with JPCSP Connector.

The real bigfile is ARCV0.BIN + file table -> ARCVINFO.BIN it contains all files unencrypted with real filename + path.

I already finished an extracting tool, and i'm working on a text translation tool

tool + source (.NET): [http://www.mediafire.com/download.php?sb74rim5hj38oa7](http://www.mediafire.com/download.php?sb74rim5hj38oa7)

here the ARCVINFO.BIN format: (some structs are incomplete, but you can extract all files with it)

```
//--- 010 Editor v3.2.1 Binary Template
//
// File:
// Author:
// Revision:
// Purpose:
//--------------------------------------
struct{
    char magic[4];
    int unk1;
    int numFiles;
    int szSector;
    int szFile;
    int unk4;
    int unk5;
    int unk6;
    struct{
        struct ENTRY entry[numFiles]<optimize=false>;
    }Files;
}VCRA;

struct ENTRY{
    local int fTemp;
    int Size;
    int unk1;
    int ofsFileName;
    int Offset; // sector
    int ofsMARV;
    int ofsData;
    fTemp = FTell();

    FSeek(ofsFileName);
    char Filename[];

    if (ofsMARV)
    {
        FSeek(ofsMARV);
        struct MARV marv;
    }

    if (ofsData)
    {
        FSeek(ofsData);
        struct DATA data;
    }

    Printf("%d;%d;%s\n",Offset*0x800,Size,Filename);
    FSeek(fTemp); // go back to filetable
};

struct MARV{
    char magic[4];
    int unk1;
    int unk2;
    int unk3;
    int unk4;
    int unk5;
    int unk6;
    int unk7;
};

struct DATA{ // not finished
    int unk1;
};
```
## Post #3
- Username: StorMyu
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Sep 21, 2011 6:35 pm
- Post datetime: 2012-07-20T15:46:24+00:00
- Post Title: Digimon World Re:Digitize

Omg guys, the game just came out yesterday and my pre-order still isn't here, what the fuck ?

[irony]Oh yes piracy... my bad[/irony]

And just in case, please don't do a menu patch, it's really horrendous !
## Post #4
- Username: Falo
- Rank: advanced
- Number of posts: 78
- Joined date: Fri Oct 23, 2009 8:29 pm
- Post datetime: 2012-07-20T16:10:45+00:00
- Post Title: Digimon World Re:Digitize

> Reply from StorMyu
>
> And just in case, please don't do a menu patch, it's really horrendous !
Why not ?

My text editor is nearly finished, only saving edited text makes problems (game uses some text length based padding...)
But i can export every text in the game as csv and edit it with excel.

map\text\*text.pack = all story/npc text
Keep\LanguageKeep_jp.res = all menu, item, ... text


here the text file structure:
works with all *text.pack files, only LanguageKeep_jp.res has an extra Pack Header, remove it and it should work too...

```
//--- 010 Editor v3.2.1 Binary Template
//
// File:
// Author:
// Revision:
// Purpose:
//--------------------------------------
local int i;
struct KCAP pack;

struct KCAP{ // PACK Header, LanguageKeep_jp has 2 Pack header
    char magic[4];
    int unk1;
    int szPack;
    int unk2;
    int numFiles;
    int unk3;
    int ofsFT;
    int unk4;

    FSeek(ofsFT);
    struct ENTRY entry[numFiles]<optimize=false>;
};

struct ENTRY{
    local int fTemp;
    int Offset;
    int Size;
    fTemp = FTell();
    FSeek(Offset);
    struct ChunkHeader chunk_header;
    FSeek(fTemp);
};

struct ChunkHeader{
    char magic1[4];

    if( magic1 == "BTX ") // only LanguageKeep_jp
    {
        struct BTX1 btx1;
    }
    else // all other *text.pack files have 4 Byte Size and then the magic
    {
        char magic2[4];
        if( magic2 == "BTX ")
        {
            struct BTX2 btx2;
        }
    }
};

struct BTX1{
    int unk1;
    int unk2;
    int unk3;
    int unk4; // only LanguageKeep_jp
    int numText;
    struct TEXT_HEADER text_head[numText]<optimize=false>;
};

struct BTX2{
    int unk1;
    int unk2;
    int unk3;
    int numText;
    struct TEXT_HEADER text_head[numText]<optimize=false>;

    // not in  LanguageKeep_jp
    // after the text comes 28 Byte of data, don't know what it does
};

struct TEXT_HEADER{
    local int iStart,iLen,fTemp;
    iStart = FTell();
    int ID;
    int Start;
    fTemp = FTell();
    FSeek(iStart + Start);

    wchar_t text[]; // text is common Unicode Little Endian text

    iLen = Strlen(text) *2;
    if(iLen % 4 > 0) byte padding[iLen % 4];

    FSeek(fTemp);
};
```
## Post #5
- Username: StorMyu
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Sep 21, 2011 6:35 pm
- Post datetime: 2012-07-20T17:24:51+00:00
- Post Title: Digimon World Re:Digitize

Why not ? Well most of the time you have a menu patch => Fame level +10 => Stop working on it => Project fail.
I just think it's better to give a 100% operational (by that I mean bug free) version fully translated.
But good job working on it.  

Btw I'll be happy to look at the game once it'll arrived.
Also, try replacing with ASCII, see if there's a variable-width font and not just a fucked up Fixed-width one.
Because any translation with this will be horrible =/
## Post #6
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-07-20T19:58:46+00:00
- Post Title: Digimon World Re:Digitize

Who cares whether it looks bad or not. If it looks bad then just leave the source files and have someone else continue it. Better than having to figure out how to do everything from scratch.

And much better than not bothering to develop tools because "fame +10 => project fail"
A lot of groups feel that if you're going to do something, you better do it 100% and even provide bug support. No, I think someone should provide the tools and some samples and if people don't like it they can take the tool and make a better one.

People will complain about anything anyways even if they can't do anything so there's no pleasing them.
## Post #7
- Username: StorMyu
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Sep 21, 2011 6:35 pm
- Post datetime: 2012-07-20T22:11:24+00:00
- Post Title: Digimon World Re:Digitize

> Reply from finale00
>
> Who cares whether it looks bad or not. If it looks bad then just leave the source files and have someone else continue it. Better than having to figure out how to do everything from scratch.
I never said something like that, and yeah having something like that is grantly appreciated. But seriously... if you don't care that it looks "bad", you really should peek at most of the difference in quality when you have something serious and just attempt to "do" something.
The first Digimon game on Psx was really a good game which this one tries to "return to THIS basic" so it looks freakin awesome to me, and thus I was asking if they really try to do a translation, to do it right. no more/no less.

> Reply from finale00
>
> No, I think someone should provide the tools and some samples and if people don't like it they can take the tool and make a better one.
That's exactly why translation project fail...
Bare minimum is: One hacker / one translator
if there is no connection between them it's messy, and the hacker can (if possible) do something to fix some troubles the translator can have (by that I mean Assembly hacking of course, because it's not just about the files...)

> Reply from finale00
>
> People will complain about anything anyways even if they can't do anything so there's no pleasing them.
When I'm doing a translation project, I'm mostly doing it for me, I'm not trying to please anyone. That's what I was talking about people who were happy to release a patch full of bug with 1% of the game translated just because they want to "please" the public which is... not a good idea.

imho a good project is a project release day one   

None of this is mean btw finale00, I was just giving my opinion on that ^^
## Post #8
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-07-20T22:19:25+00:00
- Post Title: Digimon World Re:Digitize

Hmm ya I haven't really seen any really "nice" translation projects where the translators are off doing their own thing and can do all of the art and magic that they would like.

Maybe in the future there will be more advancements in the translation scene.
## Post #9
- Username: Falo
- Rank: advanced
- Number of posts: 78
- Joined date: Fri Oct 23, 2009 8:29 pm
- Post datetime: 2012-07-20T23:50:41+00:00
- Post Title: Digimon World Re:Digitize

To make this clear, i'm not going to translate this game, i know 0 about japanese, i'm just making the tools to do it...
And i finished the tool, translation works perfectly:

[](http://www.imagebanana.com/view/jba3h4z2/TranslationTest001.png)

No text limit and it should support all unicode characters.
## Post #10
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-07-21T00:31:19+00:00
- Post Title: Digimon World Re:Digitize

Looks pretty nice, but then again I'm not a hardcore gamer so I don't know what to look for.

How easy is it to use the tool?
## Post #11
- Username: Falo
- Rank: advanced
- Number of posts: 78
- Joined date: Fri Oct 23, 2009 8:29 pm
- Post datetime: 2012-07-21T00:42:44+00:00
- Post Title: Digimon World Re:Digitize

For all *text.pack files, just open it, select what file to edit, select what text to edit and then edit it ^^
for LanguageKeep_jp.res, cut of the first 48 Byte (the first Pack Header), then translate it, re-add that 48 byte header, fix sizes.

I should make a repacker tool, i manually repacked ARCV0.BIN for this small test.
But it's very easy to use, you can export all text from one file to csv, edit it with excel/google/whatever and then reimport it and save as text.pack.

[http://www.imagebanana.com/view/sotrvcp ... est002.jpg](http://www.imagebanana.com/view/sotrvcp5/TranslationTest002.jpg)
## Post #12
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-07-21T00:57:15+00:00
- Post Title: Digimon World Re:Digitize

Is there a way to automatically calculate the sizes of the new data and do that 48-byte header process?
## Post #13
- Username: Forte
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Aug 07, 2007 4:51 am
- Post datetime: 2012-07-21T08:51:17+00:00
- Post Title: Digimon World Re:Digitize

Man, KCAP is wild. Depending on what's in the 4th int (the one you have as unk2), it's possible that there is no file table at all (example: the msh files) and of course, as the language keep file demonstrates, a KCAP can be a container for other KCAPs.

Also, both BTX are the same file format, unk2 tells you how much management info there is (if you leave out the magic number like you did, it's basically the offset of numText)

By the way, any clue how the ARCVINFO.BIN is structured? I get that the table has an entry for each file (20 bytes), but what about the part after that, the "MARV" stuff?  Looks like a file table entry can have a pointer to an entry in the MARV table but doesn't have to. I'm equally clueless what the table after MARV is supposed to be. (hashes?)
I guess it doesn't matter since the edited text works anyway, but I'm just curious.

> Is there a way to automatically calculate the sizes of the new data and do that 48-byte header process?

It is, but what you'll be doing is basically saying "if file == the language keep one: add extra header", but I guess that's still better than having the user do it.

> (by that I mean Assembly hacking of course, because it's not just about the files...)

It's not? What part of the game would you say requires assembly hacking in this game?
There are no font related issues since they used a nice library (and even then: just edit the library). I guess some of the boxes could use some resizing, but I wouldn't anticipate an official, paid localization to even do that (similar to DW1)
## Post #14
- Username: eycaramba
- Rank: veteran
- Number of posts: 86
- Joined date: Wed Sep 02, 2009 8:52 pm
- Post datetime: 2012-07-21T13:38:28+00:00
- Post Title: Digimon World Re:Digitize

Great to hear that you have nearly finished the text tools, Falo 
Can't wait to play around a little. Have been a big fan of Digimon when I was younger ^.^
## Post #15
- Username: Falo
- Rank: advanced
- Number of posts: 78
- Joined date: Fri Oct 23, 2009 8:29 pm
- Post datetime: 2012-07-21T17:55:14+00:00
- Post Title: Digimon World Re:Digitize

> Reply from Forte
>
> By the way, any clue how the ARCVINFO.BIN is structured? I get that the table has an entry for each file (20 bytes), but what about the part after that, the "MARV" stuff?  Looks like a file table entry can have a pointer to an entry in the MARV table but doesn't have to. I'm equally clueless what the table after MARV is supposed to be. (hashes?)
I guess it doesn't matter since the edited text works anyway, but I'm just curious.

I think it has to do with how the psp handle's it's VRAM (VRAM = reversed MARV), but i can't tell what info it has, some values matches the size, but not always...

My text tool can now detect the extra pack header and writes it by saving, so only a repacking tool and it's finished.
But now that i know MARV contains size data, this could be a problem.
## Post #16
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2012-07-21T23:24:33+00:00
- Post Title: Re: Digimon World Re:Digitize

I noticed that when searching for the following hex string in the digi.res files:
54 54 50 4F 05 00 00 00 00 30 00 00 00 03

That this will take you to where the subsections that have vertexes are located.
There are two types of subsections which each type alternating somehow.

Type one subsections are sets of 8Byte arrays, that I do not know what they do.
Type two subsections are sets of 14Byte arrays that have the following structure:
{8ByteUnknowns, 2ByteSignedIntegerVertexes(X,Y,Z)}
I think there are tristrips because I see no face indexes.
## Post #17
- Username: Falo
- Rank: advanced
- Number of posts: 78
- Joined date: Fri Oct 23, 2009 8:29 pm
- Post datetime: 2012-07-22T13:14:04+00:00
- Post Title: Re: Digimon World Re:Digitize

Ok i know most of whats going on,
MARV = extra header for KCAP, it contains some extra info, example:

BattleEvent\battleTutorial.img
the KCAP header contains no file info, except that 7 files are inside, 
the szPack contains only the header size, but the MARV contains both, header size and image size.

The info in MARV depends on the KCAP header and file format.

Now the Data part, it contains PGD decryption keys, every file in INSDIR has it's own key, 
but i don't know why the ID's doesn't match the bin filename.

Data can be ignored (if you play from iso, you don't need to install any data...) but MARV, 
i may try later to remove it, lets see what happens. ^^

here the Text Editor + Source:
[http://www.mediafire.com/download.php?14ai4ua4i8ep45c](http://www.mediafire.com/download.php?14ai4ua4i8ep45c)
## Post #18
- Username: DarianLoL
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jul 23, 2012 5:54 am
- Post datetime: 2012-07-22T21:58:35+00:00
- Post Title: Re: Digimon World Re:Digitize

> Reply from Falo
>
> 
here the Text Editor + Source:
http://www.mediafire.com/download.php?14ai4ua4i8ep45c

Can you get it to work with [https://docs.google.com/spreadsheet/ccc ... bGc#gid=18](https://docs.google.com/spreadsheet/ccc?key=0AgZckeipWJ6bdFZtckpYNk9WbjJhRHFiZEd6ZUQxbGc#gid=18)?

Would make this easier and faster
## Post #19
- Username: MrShyCity
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Jul 17, 2012 6:48 am
- Post datetime: 2012-07-23T13:56:24+00:00
- Post Title: Re: Digimon World Re:Digitize

@DarianLOL
that would be nice to but as far as i can tell there is no easy way when it come to translating
"just saying"

on topic - thanks for the tools falo cant wait for the rebuilder/repacker tool
## Post #20
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-07-23T18:59:03+00:00
- Post Title: Re: Digimon World Re:Digitize

> Reply from DarianLoL
>
> Falo wrote:
here the Text Editor + Source:
http://www.mediafire.com/download.php?14ai4ua4i8ep45c

Can you get it to work with https://docs.google.com/spreadsheet/ccc ... bGc#gid=18?

Would make this easier and faster

Or maybe change the format of that spreadsheet to something simple?
## Post #21
- Username: Plop23
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Apr 05, 2011 2:14 am
- Post datetime: 2012-07-26T08:09:10+00:00
- Post Title: Re: Digimon World Re:Digitize

this may be off topic but, how can I change the font of the game?
I found this file, but I can not change it, yet I'm sure this is the file that contains the font:
[http://www.mediafire.com/?1ji340g6qrna7gg](http://www.mediafire.com/?1ji340g6qrna7gg)
Thanks in advance.
## Post #22
- Username: StorMyu
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Sep 21, 2011 6:35 pm
- Post datetime: 2012-07-26T18:39:17+00:00
- Post Title: Re: Digimon World Re:Digitize

> Reply from Plop23
>
> this may be off topic but, how can I change the font of the game?
I found this file, but I can not change it, yet I'm sure this is the file that contains the font:
http://www.mediafire.com/?1ji340g6qrna7gg
Thanks in advance.
looks like one of those Pack archive the game uses, + it really looks like a font (can't find the right mode used though)
You can clearly see a map for the letters (you can think of it as a tilemap) at the beginning of the file (just change everything to "a" for example and try to see if everything changes ^^) and after that I could have a glance at the font:

The said map =>


The said font (yeah Random palette, don't expect something sexy) =>


Probably everything is here so : Easy
I'm just tired right now, I'll take a better look at it tomorrow (just done that in 5min for you plop ^^)
## Post #23
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2012-07-26T23:49:42+00:00
- Post Title: Re: Digimon World Re:Digitize

Can i have a model sample o.o?
## Post #24
- Username: Romored
- Rank: beginner
- Number of posts: 20
- Joined date: Fri May 14, 2010 7:52 pm
- Post datetime: 2012-07-30T10:06:52+00:00
- Post Title: Re: Digimon World Re:Digitize

Epic topic! I'm really looking forward to this!

I'm waiting for the repacker, I'd really like to make an Italian patch for the game, once the English one is completed.

Keep up the good work!
## Post #25
- Username: StorMyu
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Sep 21, 2011 6:35 pm
- Post datetime: 2012-07-30T17:23:52+00:00
- Post Title: Re: Digimon World Re:Digitize

Tada:
## Post #26
- Username: Falo
- Rank: advanced
- Number of posts: 78
- Joined date: Fri Oct 23, 2009 8:29 pm
- Post datetime: 2012-07-31T11:36:03+00:00
- Post Title: Re: Digimon World Re:Digitize

> Reply from FurryFan
>
> I noticed that when searching for the following hex string in the digi.res files:
54 54 50 4F 05 00 00 00 00 30 00 00 00 03

That this will take you to where the subsections that have vertexes are located.
There are two types of subsections which each type alternating somehow.

Type one subsections are sets of 8Byte arrays, that I do not know what they do.
Type two subsections are sets of 14Byte arrays that have the following structure:
{8ByteUnknowns, 2ByteSignedIntegerVertexes(X,Y,Z)}
I think there are tristrips because I see no face indexes.

54 54 50 4F 05 00 00 00 00 30 00 00 00 03
Is the TTPO header (the palette header), it's part of the GMIO structure, the Texture/Image Header.

I got a more or less working model out of Digi1.res:
[](http://www.imagebanana.com/view/2aauponh/digi1.jpg)

I think we have to parse every sub-pack file to find out where the model info is,
here the code to read "\Digimon\Partner\digi1.res" model data:

```
//--- 010 Editor v4.0.2 Binary Template
//--------------------------------------

struct{
    local int iStart,iEnd;

    FSeek(0xC480);
    struct VERTEX vert1[264]<optimize=false>;
    Printf("g StaticModel1 \n");
    iStart = 0;
    iEnd = 264;
    MakeTriStrips(iStart,iEnd);

    FSeek(0xD100);
    struct VERTEX vert2[582]<optimize=false>;
    Printf("g StaticModel2 \n");
    iStart += 264;
    iEnd += 582;
    MakeTriStrips(iStart,iEnd);

    FSeek(0xEC80);
    struct DYNAMIC_VERTEX vert3[228]<optimize=false>;
    Printf("g DynamicModel1 \n");
    iStart += 582;
    iEnd += 228;
    MakeTriStrips(iStart,iEnd);

    FSeek(0xF900);
    struct DYNAMIC_VERTEX vert4[63]<optimize=false>;
    Printf("g DynamicModel2 \n");
    iStart += 228;
    iEnd += 63;
    MakeTriStrips(iStart,iEnd);

    FSeek(0xFC80);
    struct DYNAMIC_VERTEX vert5[63]<optimize=false>;
    Printf("g DynamicModel3 \n");
    iStart += 63;
    iEnd += 63;
    MakeTriStrips(iStart,iEnd);

}Header;

struct VERTEX{
    short unk1;
    short unk2;
    short unk3;
    short x;
    short y;
    short z;
    Printf("v %d %d %d\n",x,y,z);
};

struct DYNAMIC_VERTEX{
    short unk1;
    short unk2;
    short unk3;
    short unk4;
    short x;
    short y;
    short z;
    Printf("v %d %d %d\n",x,y,z);
};

void MakeTriStrips(int start, int end)
{
    local int i;
    for(i=start;i<end;i+=3)
    {
        Printf("f %d %d %d\n",i+1,i+2,i+3);
    }
};

```


@StorMyu
Thanks for the info, i did know it was swizzled/tiled, but there are more formats, here a unszwizzled texture:
[](http://www.imagebanana.com/view/sykxssim/digi1_texture.jpg)
the full image format is in the GMIO structure.

//edit:
updated script, now fully reads all models, 5 total and a perfect digimon comes out of it (no normals, no uv):
[](http://www.imagebanana.com/view/gj51tr0w/digi1_2.jpg)
## Post #27
- Username: Romored
- Rank: beginner
- Number of posts: 20
- Joined date: Fri May 14, 2010 7:52 pm
- Post datetime: 2012-08-01T11:37:23+00:00
- Post Title: Re: Digimon World Re:Digitize

Falo, how did you repack the ARCV0.BIN file? I'd like to test some of the translations I did directly on the console, but I don't know how to repack that file. Can you tell me, please?
## Post #28
- Username: Romsstar
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Aug 03, 2012 6:30 pm
- Post datetime: 2012-08-03T11:49:13+00:00
- Post Title: Re: Digimon World Re:Digitize

Awesome work with the Models Falo. Seems you figured it out.
So can we expect a Model Ripper?

By the way I know this is off topic but:
Could I ask you to look into the 3D Model Data of Digimon World 1 for PSX?
I would really appreciate that.

Here is a sample of Phoenixmon 
[https://rapidshare.com/files/37321962/HOUO.MMD](https://rapidshare.com/files/37321962/HOUO.MMD)
## Post #29
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-03T19:40:48+00:00
- Post Title: Re: Digimon World Re:Digitize

Just start a new topic if you want to request a new game.
## Post #30
- Username: Romsstar
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Aug 03, 2012 6:30 pm
- Post datetime: 2012-08-10T12:18:32+00:00
- Post Title: Re: Digimon World Re:Digitize

Issue: Game hangs up by loading any map with anything story related translated.

@Falo: Help? Why could this be? Everything translated in our Languagekeep works fine. But the files in map/text don't work.
Translated it with the TextEditor 1.1.

Plus: Really need a Image Editor and a more handy Repacker.
## Post #31
- Username: Romsstar
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Aug 03, 2012 6:30 pm
- Post datetime: 2012-08-12T12:36:24+00:00
- Post Title: Re: Digimon World Re:Digitize

bumping this, Falo can you make the Editor work with the story related files please?
## Post #32
- Username: Jecht
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Jan 26, 2012 9:32 am
- Post datetime: 2012-10-04T03:21:43+00:00
- Post Title: Re: Digimon World Re:Digitize

I plenty know that this's Necro-post , but its more easy ask my question here than make a new topic.




So here goes:

I've get this game early, for heard that it have one Model that its not the DMO one. I know that model its on the Data Squad and Digimon World 4, but for weird it sound any time i try to take the texture they don't capture the ones of the Digimon models, actually they take of the environmental.


I've read and try to make this to, and funny part that a part of the text part, i get other folders were it goes the "Dgimon" word i though it could be of models, but when i open it there were of RES extension, and weird was of the size:



Its... to tiny our maybe the RES comprise it?
For start i don't know many of RES format, but what i know its change depend of the game.


Now here goes my question:
Does those really were are the models? they're just data of were it suppose to go the models?

Because a part of that, its the only that have a more huge size on whole disc.



PS: Sorry if someone confuse on it, as the image can say, english its not my first language
PS2: And its just for ask. if this don't work the last option its the Digimon 4... but to know if it would capture the texture this time...
## Post #33
- Username: AvengerSeraphim
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jan 29, 2011 3:15 am
- Post datetime: 2012-10-07T23:32:32+00:00
- Post Title: Re: Digimon World Re:Digitize

I can't wait for the translation.... Do we have any news for the models?

PS: I know it's not the right place to ask, but how can I rip the music from the game? There isnt any BGM folder like the Naruto games...Thanks in advance guys!
