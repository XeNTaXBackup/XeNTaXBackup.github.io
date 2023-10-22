## Post #1
- Username: ReedSteed
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Sep 25, 2017 9:14 am
- Post datetime: 2017-09-30T07:29:32+00:00
- Post Title: Unreadable Game Data XMLs

I have a list of XML files that i want to edit from WADs I've extracted from the game called Wizard101 (GameBryo Engine if that helps).

I believe these XML's contain the game code for their respective areas (example: extracting MB_Arena.wad gives me the textures, the model and these XML's).

My only issue is upon opening these XML's in Notepad, WordPad etc.. I am greeted with strange characters that I cannot understand (let alone make edits to).

My goal is to edit the areas code so that teleporting to the area as a spectator would teleport my character on the battle circle and not in the spectator area (maybe with triggers.xml so that it adds me into battle always, or spawndata.xml to spawn my character onto the battle circle.. (as colliding with the circle joins you into battle automatically).

Can anyone translate the code in these XML's or help me read it? (Note: I believe the mechanics were written mainly in C/C++)

EXAMPLE XML'S + OTHER DATA FROM MB_ARENA.WAD HERE:

[http://www.mediafire.com/file/99ore2ia8 ... +Arena.rar](http://www.mediafire.com/file/99ore2ia8fmhml2/Marlybone+Arena.rar)
[Snipped.JPG](https://xentaxbackup.github.io/file/13360_Snipped.JPG)
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2017-09-30T09:23:19+00:00
- Post Title: Unreadable Game Data XMLs

These are "binary" xml files - xml files packed into data.

Interestingly portals.xml is actual xml
## Post #3
- Username: ReedSteed
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Sep 25, 2017 9:14 am
- Post datetime: 2017-09-30T10:50:08+00:00
- Post Title: Unreadable Game Data XMLs

> Reply from WRS
>
> These are "binary" xml files - xml files packed into data.

Is there any way I can open/edit these binaries properly?
## Post #4
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2017-09-30T12:45:50+00:00
- Post Title: Unreadable Game Data XMLs

What tools did you use to unpack the 'WAD's? I'm thinking there may be other tools like XML converting for this engine? Some of these other files like NIF are graphics files which would need converting to read..

Otherwise we can look at examining it
## Post #5
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2017-09-30T13:33:36+00:00
- Post Title: Unreadable Game Data XMLs

Here, I've written a script which can parse all files. Not sure how to reconstruct them to xml yet! Check back later

```
// wrs

/////////////////////////////////
typedef uint uint_p2 <read=ReadUIntP2>;

uint unpackLen(uint len)
{
  // len is is bits (x8 larger than it need be)
  // odd values are restored

  local int b = (len>>3);// + (len&0x7);
  //Printf("%u ==> %u (%u)**\n", len, b, (len&0x7));

if( (len&0x7) == 1 ){ b++; }

  return b - 4;//sizeof(uint);
}

// 010ed magic
string ReadUIntP2( uint_p2 b ) {
  string s;   
  SPrintf( s, "%u", unpackLen(b) );
  return s;
}
/////////////////////////////////
struct
{
  char Magic[4];
  Assert(Magic=="BINd");

  uint Version;
  Assert(Version==7);

} BINdHeader;
/////////////////////////////////
struct str(int size)
{
  byte len;

  if(size!=-1)
  Assert((len/2)==size);
  //Printf("Expected: %u\n",size);
  //Printf("Read:     %u\n",len/2);

  char cstr[len/2];

  Printf("%s\n", cstr);
};
/////////////////////////////////
struct ChunkBit
{
  uint_p2 len;
union{
  byte bits[unpackLen(len)];
  struct {
    uint tag <format=hex>;
    if( (tag &0xFF) == 0x10 ) {
      str astr(-1);
    }
  } s;
} u;
};
/////////////////////////////////

union un
{
  byte a[8];

  struct
  {
    byte a, b, c, d;
    uint_p2 len;
  } b;
};

/////////////////////////////////
struct
{
  byte flags[4];
  uint_p2 len_first; // from this offset -> eof


  // first chunk
  uint_p2 len; // from this offset -> eof 
  byte unknown[4];
  byte cnt_2;

  local uint cnt = cnt_2/2;
  if( cnt > 0 ) {
    struct {
       un hdr;
       local uint max = unpackLen(hdr.b.len);
       local uint size = 0;
      struct {
         while(size<max) {
         ChunkBit cs;
         size += sizeof(cs);
         }
      } data;
      
    } chunk[cnt] <optimize=false>;
  }

} data;

/////////////////////////////////

Assert(FEof());

/////////////////////////////////

```
## Post #6
- Username: ReedSteed
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Sep 25, 2017 9:14 am
- Post datetime: 2017-09-30T23:03:53+00:00
- Post Title: Unreadable Game Data XMLs

> Reply from WRS
>
> What tools did you use to unpack the 'WAD's?

QuickBMS, using scripts I've found on this forum. I repack WAD's using a python shell written specifically for this game. 


> Reply from WRS
>
> Some of these other files like NIF are graphics files which would need converting to read..

I have opened the NIF's with NifSkope and it opens older versions just fine, but making any edits to the NIF either in hex or in NifSkope causes a game client crash upon entering the Marlybone Arena. (that post here: [viewtopic.php?f=16&t=17074](http://forum.xentax.com/viewtopic.php?f=16&t=17074))

> Reply from WRS
>
> Here, I've written a script which can parse all files. 


Executing the script on the XML's provide me with data I still can't exactly understand! Can we define what each of these do so I can edit accordingly?
[Snipped.JPG](https://xentaxbackup.github.io/file/13364_Snipped.JPG)
## Post #7
- Username: Belloq
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Mar 25, 2018 3:04 pm
- Post datetime: 2018-03-25T07:09:47+00:00
- Post Title: Unreadable Game Data XMLs

> Reply from WRS
>
> Here, I've written a script which can parse all files. Not sure how to reconstruct them to xml yet! Check back later

Hi. Is there any chance you'd be so kind as to finish this? It would be really helpful for me and OP.
Thanks
