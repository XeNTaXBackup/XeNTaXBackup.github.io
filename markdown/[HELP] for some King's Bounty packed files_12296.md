## Post #1
- Username: vallex
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Oct 07, 2014 4:55 am
- Post datetime: 2014-11-30T17:56:03+00:00
- Post Title: [HELP] for some King's Bounty packed files

I want to extract (decompile) some strg(slcb) files from  King's Bounty map editor

The size of the files is very small like this one:

```
slcb?...7.. xЪcb``а.вЧ€x_WF.„™Ђ$ойг`b. .ЙМIЌOО/Н+r ЧTO
```


Decompiled looks something like this:

```
........TILES........tile_count....
```


I'm trying to find the algorithm of the compression. If someone want to help me with this I would be very grateful and I am ready to pay

Here is some strg files ..and extracted / decompiled files, taken from RAM memory with Hex editor when editor.exe is started   :


 strg-slcb.rar
(17.4 KiB) Downloaded 20 times
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2014-11-30T22:09:17+00:00
- Post Title: [HELP] for some King's Bounty packed files

its a very common delate algorithm

```
get size long
get zsize long
clog "strg_decompiled" 12 zsize size

```
## Post #3
- Username: vallex
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Oct 07, 2014 4:55 am
- Post datetime: 2014-11-30T22:57:19+00:00
- Post Title: [HELP] for some King's Bounty packed files

Wow - very fast answer!
It works!!!!!! Thanks a lot!

I try to use the algorithm in maxscript. Do you help me with this?

```
idstring = readlong file
size = readlong file
zsize = readlong file
...........???........
fclose f

```


I don't understand how to use [ CLog <filename> <offset> <compressed_size> <uncompressed_size>  ] in my script
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-11-30T22:59:11+00:00
- Post Title: [HELP] for some King's Bounty packed files

its zlib compression.
you will have to make a .net import in your script to extract a zlib file.
you are better off using quickbms 
then use max on the already decompressed file.
## Post #5
- Username: vallex
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Oct 07, 2014 4:55 am
- Post datetime: 2014-11-30T23:26:00+00:00
- Post Title: [HELP] for some King's Bounty packed files

Yep!
it works with quickbms command line and HiddenDOSCommand !!!!!!!
Thanks so so much!
## Post #6
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2014-11-30T23:50:32+00:00
- Post Title: [HELP] for some King's Bounty packed files

as a bonus, the text stuff is xml.

here is a basic parser for it (for 010 editor):

```

struct Node;
struct Attrib;

enum TypeInfo
{
  NODE_1 = 1,
  NODE_2,
  ATTRIB_3,
  ATTRIB_4,
  ATTRIB_5,
};

struct Node
{
  TypeInfo Info;
  str Name(plen32);
  uint Items;
  TypeInfo InfoHint[Items];
  
  local uint i;
  for(i=0;i<Items;i++)
  {
    switch(InfoHint[i])
    {
      case NODE_1:
      case NODE_2:
        Node child;
        break;
      case ATTRIB_3: // may be different types (int, string, et)
      case ATTRIB_4:
      case ATTRIB_5:
        Attrib attrib;
        break;
      default:
        Exit(-1);
    }
  }
};

struct Attrib
{
  str Key(plen32);
  uint Value;
};

Node root;

```


prelen.bt from here: [https://gist.github.com/x1nixmzeng/3805536](https://gist.github.com/x1nixmzeng/3805536)
## Post #7
- Username: vallex
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Oct 07, 2014 4:55 am
- Post datetime: 2014-12-01T00:11:27+00:00
- Post Title: [HELP] for some King's Bounty packed files

You are great!!!!
Thanks again!
I will take advantage of this

I use the editor for easy creation of terrains and landscapes and it's will be very helpful!
The rest of the resources are not compressed and are easy to use. Only this strg file impeded me and had to move texture info by hand in max

PP. Sorry for my bad english
