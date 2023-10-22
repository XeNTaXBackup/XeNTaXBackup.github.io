## Post #1
- Username: KFUPM
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Nov 11, 2014 1:33 pm
- Post datetime: 2015-01-08T15:06:16+00:00
- Post Title: The Last Ranker Null char

Hello everyone.

I am working on translating the Last Ranker, a PSP game. The game text is already translated by "Englishsubs4all", and I already found and extracted the text files and manually translated the intro and the tutorial. Now I am planning on writing a tool for the translation, but I am having trouble with the null character. The files are in utf-8 format and as with most PSP games, all strings are tailed by a null character. My problem is that when I shift the null character to make a string shorter while the adjacent string longer - the file size stay the same- the game does not allow that and it crashes when the length modified string is reached  to be displayed.

Is there a way to shift the null character to lengthen a string size that needs more space by reducing the other that doesn't? I can continue writing a tool that deals with constant size strings, but that would be a pain to change the translation just because the string is too small.
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2015-01-08T19:26:43+00:00
- Post Title: The Last Ranker Null char

good question - and it depends how the game deals with the null-terminator strings

usually

the format will include offsets and/or string lengths (and perhaps even some kind of checksum) that need modifying when you make a change, OR
the game will read the strings in sequence - ie:
s t r \0 s t r \0 s t r \0

str
str
str

which can be bypassed by shifting the entire texts across - ie:
s t r \0 a \0 s t r \0 \0 \0

str
a
str

can you see what i did there?
## Post #3
- Username: KFUPM
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Nov 11, 2014 1:33 pm
- Post datetime: 2015-01-08T21:25:19+00:00
- Post Title: The Last Ranker Null char

> the format will include offsets and/or string lengths (and perhaps even some kind of checksum) that need modifying when you make a change

That's what I figured since I can do anything with the strings except removing the null locations I can add nulls without problems though. It cannot be checksum since I can change the string content.

I did some tests, and It appears to work by offset, see the next part.

> the game will read the strings in sequence

I wish it did, but it does not. when I add a null in the middle of the string, the game display the first half the string, then jumps to the next string skipping the other half without crashing which rules out both using string length and sequential, unless I'm missing something. I need to find where the offsets are stored or just suck it and work with constant lengths
## Post #4
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2015-01-08T22:19:46+00:00
- Post Title: The Last Ranker Null char

is there any other data in the file other than strings? offsets and string lenghts are pretty easy to spot - post a cut of it here if you can
## Post #5
- Username: KFUPM
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Nov 11, 2014 1:33 pm
- Post datetime: 2015-01-08T23:34:35+00:00
- Post Title: The Last Ranker Null char

Here you go. This is the original extracted file. Some of the Japanese text is just code comments. Main dialogue is at 000E9680.

[http://wikisend.com/download/169400/MAP_T_KAN_00](http://wikisend.com/download/169400/MAP_T_KAN_00)
## Post #6
- Username: KFUPM
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Nov 11, 2014 1:33 pm
- Post datetime: 2015-01-10T13:32:02+00:00
- Post Title: The Last Ranker Null char

Well, if no one can help me with this, then I guess I will proceed with constant strings then. This is gonna suck  :(
## Post #7
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2015-01-10T17:53:38+00:00
- Post Title: The Last Ranker Null char

do you have the other fan translation for comparison?
## Post #8
- Username: KFUPM
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Nov 11, 2014 1:33 pm
- Post datetime: 2015-01-10T18:23:41+00:00
- Post Title: The Last Ranker Null char

There is no other translation, the translation I mentioned was just the text:

[https://gbatemp.net/threads/last-ranker ... gh.361585/](https://gbatemp.net/threads/last-ranker-fully-translated-playthrough.361585/)


He pretty much translated everything, and I am trying to put it in the game.

There was a guy with much more experience than me who attempted it, but failed to find a way other than working with constant length, and he abandoned the project IIRC. He didn't do much, so nothing useful came from his attempt as far as I know.
## Post #9
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2015-01-10T19:20:46+00:00
- Post Title: The Last Ranker Null char

not to worry - i've got a bit stuck too.

the problem with this particular file is it contains so much redundant data for our purposes. any string changes may change pointers anywhere else- unfortunately the strings aren't very self-contained.

```
//--- 010 Editor v6.0 Binary Template
//--------------------------------------
#include "prelen.bt"

struct HEADER
{
    char chunkName[4];

    // scmp seems generic
    Assert(chunkName == "SCMP");

    // these are all pointers to other chunks:
    // a == SCCR
    // b == FRES
    // c == bscr
    // d == SCMP ?
    // e == SCMP ?

    uint a, b, c, d, e;

} hdr;

FSeek(hdr.a);
str sccr(pnt);

FSeek(hdr.c);
str bscr(4);
ushort hmm;

// watch this! it's incorrect:
struct
{
    str _string(pnt);
    FSkip(13);
} original_name;

Printf("Current file: %s\n", original_name._string.val);

struct
{
    uint a;
    uint count;
    uint c, d, e, f, g;
} items;

struct pairs
{
  uint unknown;
  uint index;
};

enum <ushort> unknown_types
{
    eUnknownE0= 0xe0,
    eUnknownE1= 0xe1,
    eUnknownE2= 0xe2,
    eUnknownE3= 0xe3,
    eUnknownE4= 0xe4,
    eUnknownE5= 0xe5,
    eUnknownE6= 0xe6,
    eUnknownE7= 0xe7,
    eUnknownE8= 0xe8,
};

struct
{
    struct
    {
        ushort size; // including self
        unknown_types t;
        str fn(32);
        uint a, b;

        if( b != 0 ) {
            pairs p[b];
        }

        //Printf("%s\n", fn.val);

    } i [items.count] <optimize=false>;
} INFO;

// some stings follow, but still unknown
str locString1(pnt); Printf("%u\n", locString1.len);
str locString2(pnt); Printf("%u\n", locString2.len);
str locString3(pnt); Printf("%u\n", locString3.len);

// not sure if this is a complete pool of strings
// some of the L00000000 strings may be placeholders

```


as the psp can be emulated - perhaps look into debugging the load
## Post #10
- Username: KFUPM
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Nov 11, 2014 1:33 pm
- Post datetime: 2015-01-10T20:39:22+00:00
- Post Title: The Last Ranker Null char

Thanks, I'll look into that as soon as I can.
## Post #11
- Username: flamethrower
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Apr 11, 2016 5:40 am
- Post datetime: 2016-05-31T23:56:12+00:00
- Post Title: The Last Ranker Null char

I made a menu patch you can get at GBAtemp: [http://gbatemp.net/threads/last-ranker- ... st-6403324](http://gbatemp.net/threads/last-ranker-translation-patch.343425/page-3#post-6403324)

I'm interested in this now. The compression is a zlib variant, that's all I know.
I tried replacing the 02 03 bytes with the 78 9C magic header and some others too. The one that worked best was 78 01 but it still didn't decompress the file correctly. It almost did though - you could see some plaintext in the result.
Did anyone try QuickBMS compression searcher yet? Is there any way to quickly try every known zlib variant? The string of compressed data starts at 0xA in the file; I gathered this by debugging.

This game uses zlib, DEFLATE, whatever you want to call it. The zlib routine is decompressing this data too. zlib is a bitwise compression I think. Lots of bit manipulations being done in the decompress routine. It's beyond my skills to debug. 

There is this file Z0.NPK. It is a bunch of zlib compressed files (standard). It says in the memory when the game is running. This data is for the menu screens. When one of the files is needed is it decompressed.

Regarding the decompressed files. Have you considered that it might just be strings separated by nulls?
At 0x58 there's a pointer to the SCMP header, that's at 0xE4870. The bscr under here is really a separate file, all the offsets in here is given against 0xE48A0.
--------------------------
within bscr:
0x24: How big is this file (word) - offset from bscr header to EOF (these are all referenced from bscr header)
0x34: Where is start of the string table 
0x3C: Where is start of the next data chunk (not sure what this data is) - useful because it's the end of the string table
------------------------------

Programmers of this game LOVE strings separated by nulls. Strings are not stored any other way that I can find. In this file it's a bit different than the others but still strings separated by nulls.

Originally posted files have been removed. Here they are again if you're taking a look: [http://www.mediafire.com/download/qb18k ... _KAN_00.7z](http://www.mediafire.com/download/qb18k61s6axaj82/MAP_T_KAN_00.7z)
Decompressed version was gotten by breakpointing where the first byte is written, then using the "step out" function, then dumping that range of memory.
---------
edit: Read on wikipedia: [https://en.wikipedia.org/wiki/Gzip](https://en.wikipedia.org/wiki/Gzip)
That 1f 8b is a standard gzip header. So I need to look into that.
## Post #12
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2016-06-01T20:36:35+00:00
- Post Title: The Last Ranker Null char

> Reply from flamethrower
>
> I'm interested in this now. The compression is a zlib variant, that's all I know.

Did anyone try QuickBMS compression searcher yet? Is there any way to quickly try every known zlib variant?

hey, your edit discovered this - but its just standard gzip - and the com_scan confirms this - COMP_GZIP is what returns valid data.

curiously - your sample MAP_T_KAN_00.BIN.unc is different to the decompressed output of MAP_T_KAN_00.BIN. is that intentional? they are different files!

the BIN begins with a valid SCMP block (of the right size!) but the BIN.UNC started with SSCR (of the right size!)

let me know any progress!
## Post #13
- Username: flamethrower
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Apr 11, 2016 5:40 am
- Post datetime: 2016-06-02T12:09:34+00:00
- Post Title: The Last Ranker Null char

All of my ideas above are correct.

Check this out: [https://youtu.be/oleWWxBuZUQ](https://youtu.be/oleWWxBuZUQ)

How to get things working:
Here is a link to my Google Sheet: [https://docs.google.com/spreadsheets/d/ ... =261413784](https://docs.google.com/spreadsheets/d/1H_noLOY4p2d3VgoZsVluCMWEKF31C2udZS-dtD2Lfso/edit#gid=261413784)
You also need my Google Sheets TSV export code: [http://pastebin.com/Aw4r0bkW](http://pastebin.com/Aw4r0bkW)
1. Make a copy of my sheet.
2. Export the MAP_T_KAN_00 sheet. You need to paste the Google Sheets TSV export code into your sheet using the script editor and then reload the sheet.
3. Here's my program. Python 3.50. [http://pastebin.com/MyPyfKEd](http://pastebin.com/MyPyfKEd)
3A. You need MAP_T_KAN_00.BIN and MAP_T_KAN_00.tsv in the same folder. Then, it will insert them and give you a new MAP_T_KAN_00.BIN, the uncompressed data is retained in MAP_T_KAN_00.orig.

Here is my script dumper but I don't know if it will work for files besides MAP_T_KAN_00: [http://pastebin.com/TiV2apKe](http://pastebin.com/TiV2apKe)

The "script table" (???) is pointed to at offset 0x3C from bscr. That was key to solving this.

Pseudo-code
1. Find the offset of each string in the string table
2. Go through the script table. Find offsets and the string index that's being pointed to by looking it up in the offset table from (1) for all string pointers.
3. Replace the string table.
4. Find the offset of each string in the string table
5. Go through the script table and update each pointer with the new offset of that string, using string index data from (2) and string offset data from (4)

Need help solving those length limits. There's plenty of space on screen - something is limiting the length. It affects other areas of the game, too.
## Post #14
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2016-06-02T22:08:46+00:00
- Post Title: The Last Ranker Null char

> Reply from flamethrower
>
> Need help solving those length limits. There's plenty of space on screen - something is limiting the length. It affects other areas of the game, too.

from your video, the subtitles look like they have precalculated positions on screen. if you can, compare the widths they take with the original japanese text. i have never played this game  

i'll have a proper look at the weekend
## Post #15
- Username: flamethrower
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Apr 11, 2016 5:40 am
- Post datetime: 2016-06-04T11:54:22+00:00
- Post Title: The Last Ranker Null char

Did some experimenting.

For the "subtitle portion" the operation is as follows:
The first 24 characters will print normally.
For longer than 24 and less than 50, the 25th character is replaced with a line break character. Then printing continues on the next line with the other characters.
Characters past position 50 won't render at all (also does not crash game).

The text boxes (dialogue bubble) are dynamically sized. I tried changing parameters in the function parameter table (where the string offsets are) and it only changed the text box position, not the size.
I also put null byte to truncate some strings and the text box appeared smaller.

From stepping through the GE debugger I find this game draws one letter at a time.

The text boxes are dynamically sized. I tried changing parameters in the function parameter table (where the string offsets are) and it only changed the text box position, not the size.
I also put null byte to truncate some strings and the text box appeared smaller (in width). From the video you can see they are dynamically sized vertically too.

The actual rendering routine is at 0x08821738
I looked a couple levels up from that (the call stack for this game is really deep for whatever reason)
It looks like it's loading some kind of vertical text position parameter at 0x08866738. 
It loaded 0xF7 (the PSP screen is 0x110 pixels tall), this parameter corresponds to the position of the top of the text line currently being drawn.
I didn't debug further than that.

To help you get started faster, here's a patch that corresponds to the demo version you saw in the video.
Link: [http://www.mediafire.com/download/vd928 ... _v1.xdelta](http://www.mediafire.com/download/vd9289xgoc7o8z5/LR_test_v1.xdelta)
------------------------
Solved it, if not fully then at least mostly.

0x8865DC0
Parameter for "subtitle-type"
Change to li a0, 0x30

0x8839758
Parameter for "explanation box-type"
Change to li a0, 0x30

0x886F6D8
Parameter for "dialogue bubble-type"
Change to li a0, 0x30

New video: [https://youtu.be/gaCwVH59i8c](https://youtu.be/gaCwVH59i8c)
--------------------
There's a lot of repeated strings in here, and also a lot of strings we don't need to translate.
I excluded the func strings from the dump. I made a back-reference to strings that are repeats, but we could still have different strings if we want.
Here's the dump: [https://docs.google.com/spreadsheets/d/ ... 1812741808](https://docs.google.com/spreadsheets/d/1OfOiXeVGDCUnFoJY_R5TvmkhsLfyyq9WsxiLdADb55g/edit#gid=1812741808)
The X in that column is the PTT mark (end of dialogue page)
