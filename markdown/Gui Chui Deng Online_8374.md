## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-22T07:26:57+00:00
- Post Title: Gui Chui Deng Online

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-02-22T18:19:26+00:00
- Post Title: Gui Chui Deng Online

the names look boring to handle so the following script extract the files without names:

```
# script for QuickBMS http://quickbms.aluigi.org

idstring "SGDP Package File."
goto 0x20
get DUMMY long
get DUMMY long
get NAMES_OFF long
get INFO_OFF long
get CRC_OFF long
get FILES long
get CRC long
get DUMMY long
get DUMMY long
goto INFO_OFF
for i = 0 < FILES
    get OFFSET long
    get SIZE long
    math OFFSET += 4
    log "" OFFSET SIZE
next i
```
## Post #3
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-23T07:18:13+00:00
- Post Title: Gui Chui Deng Online

thanks a lot for script aluigi, we can't do nothing about file names?
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-23T07:42:56+00:00
- Post Title: Gui Chui Deng Online

If you can figure out how to collect parts of the filename together then it will be fine. You don't even need to know hex; just look at the strings and try to think about how they're put together.

I think the easiest to start with will be data3.spf, since there seems to be only 4 names...

Anyways it's a good thing the only thing you have to piece together are the filenames. You can start to see some patterns with the names.

Imagine if the file entry data was all scrambled in there.
## Post #5
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-23T07:53:31+00:00
- Post Title: Gui Chui Deng Online

umm well it sound good but my question is how we can modify script for get it :S, maybe you can give me a guide or something for begin read about make scripts in QuickBMS,etc grateful.
## Post #6
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-23T08:14:16+00:00
- Post Title: Gui Chui Deng Online

The contents of this post was deleted because of possible forum rules violation.
## Post #7
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-23T10:10:30+00:00
- Post Title: Gui Chui Deng Online

ouch, so really is to much work xX, thanks for your info finale00.
## Post #8
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-23T17:34:56+00:00
- Post Title: Gui Chui Deng Online

Not really. You just have to look at some strings and determine how they are pieces together.
It doesn't look like a simple double loop will work, but the integers might mean something.

You will notice that the names near the end of the filenames section will contain a bunch of extensions, while the ones near the top don't.
## Post #9
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2012-02-23T22:59:53+00:00
- Post Title: Gui Chui Deng Online

i tried to automate this a little w a little luck:

```
/npc_pk/npc_pk.kfm
/test_npc/daiji01.kf

```


after the 4 character bytes is an offset from the name pointer which continues the string - but these 8 byte structures are themselves in some sort of order

so yeah, recursion   

010 for kicks:

```
FSeek(0x20);
long DUMMY1;
long DUMMY2;
long NAMES_OFF;
long INFO_OFF;
long CRC_OFF;
long FILES;
long CRC;
long DUMMY3;
long DUMMY4;
FSeek( NAMES_OFF );

struct FNS
{
  char str[4];
  uint32 nxt;
};

void parseStr( uint offset );

void parseStr( uint offset )
{
  FSeek( NAMES_OFF + 4 + offset );
  FNS p_x;
  Printf("%s", p_x.str);
  if( p_x.str[0] != 0 && p_x.str[1] != 0 && p_x.str[2] != 0 && p_x.str[3] != 0 )
    parseStr( p_x.nxt );
}


struct FNREC
{
    FNS p1;

    local uint pos = FTell();
    Printf("%s", p1.str);
    parseStr( p1.nxt );
    Printf("\n");
    FSeek( pos );

};

struct FNREC_2
{
    long len;
    if( len > 0 )
    {
      FNREC j[ len ] <optimize=false>;
    }
};

FNREC_2 test;

```
## Post #10
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-23T23:17:05+00:00
- Post Title: Gui Chui Deng Online

The offsets seem ok.
But then there are times where you see another integer that appears to indicate the number of filenames are in the sequence.

Then there's the weird cases where you have reached the end of the filename, but the offset after has an FF in there.

So for example the file table starts with the number of entries, followed by that looping sequence with the 4-char + offset.
When you finish reading all of the names for those entries, you repeat again with another integer that gives you the number of entries, followed by the same pattern

EDIT: actually no that's not true. You can have new entries starting in between the ones you've already started reading.
LOL who came up with this.
## Post #11
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2012-02-26T01:12:12+00:00
- Post Title: Gui Chui Deng Online

the filenames are stored in a binary tree, which i didn't bother writing up for quickbms

instead i wrote up a c version, attached, which dumps with filenames    source included
[spfreader.zip](https://xentaxbackup.github.io/file/5108_spfreader.zip)
## Post #12
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-26T01:16:23+00:00
- Post Title: Gui Chui Deng Online

lol never would've thought of a binary tree.

As long as we can get the files with names
## Post #13
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-26T01:24:43+00:00
- Post Title: Gui Chui Deng Online

wow this is great news man, thanks a lot for support, really grateful for that.

Use Gamebryo File Format, Version 20.2.0.8 

PD: anyway is a 2D Game, some ugly shots.
