## Post #1
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2013-01-05T03:12:23+00:00
- Post Title: Stargaze Framework Pack

Hi everyone!

If you download games frequently from Alawar, you'll notice that a good number of recent games feature a SFP format. In the game credits, they all state they were made using the Stargaze Framework (a fact that I've only caught on to after the third SF game I played). I made a quick extractor for the format, and with it I found a copy of the real deal embedded within the data of the latest game released on Alawar's site. Anyway, I've figured out enough of the format to extract the pack, there are still a few fields that I don't know, and I want to know what they do. Any chance anyone can take a look?

Attached are some random files packed together with the pack tool.
Link to pack tool: [blog/?p=683](http://forum.xentax.com/blog/?p=683)

What I know so far:

```
char idstr[4];
int file_count;
int pack_len;
sf_entry entries[];
};

struct sf_entry {
String<char, 112> filename;
int len;
int offset;
};

struct BaseString {
unsigned short size;
unsigned short max_size;
short hash;
short __padding__;
};
```


The ID is currently "SFP\x01", though it seems an earlier version that can be extracted the same way has an ID of "SFGP".

Output from tool when building, if it's of any consequence:

```
Directory and files lookup, open handles...
Ordering files in directories...
Merging single-page directories...
Placing files in gamepack...
Writing gamepack data...
        Total files in gamepack: 21.
        Target system alignment: 4.
        Target system page: 32768.
        Gamepack size: 294912.
        Total files files: 188603
        Space wasted for alignment and pages: 103609
        Percentage of wasted space for original size: 54.93
Success: gamepack 'stuff.pack' created.
```


Update: I generated a few more packs and looked at them, and figured out what the first two unknown fields are. As far as I can guess the third is some sort of hash, maybe for the file name.

Also, there is an int with the file size before the data of each file. Not sure what they use it for.

Update 2: It so happens that I found a demo version of the Stargaze Framework SDK, and they actually write the raw string object as the file name. I was right that the third field was a hash, though it was a short instead of an int. The file name is a String<char, 112>, which means it's ASCII, and up to 112-1 chars long (accounting for null terminator).
[stuff.zip](https://xentaxbackup.github.io/file/6113_stuff.zip)
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2013-01-05T19:59:01+00:00
- Post Title: Stargaze Framework Pack

Somehow, the file is not there at the blog. Are you sure it was uploaded? Also, do you know if there are any specific copyrights on it?
## Post #3
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2013-01-06T00:49:48+00:00
- Post Title: Stargaze Framework Pack

> Reply from Mr.Mouse
>
> Somehow, the file is not there at the blog. Are you sure it was uploaded? Also, do you know if there are any specific copyrights on it?

This attachment contains the sourcecode to the tool he mentions - but packed in the format he is describing! Very amusing!

edit wait, you found their packing tool? it should be easy to reverse the method
## Post #4
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2013-01-06T04:26:20+00:00
- Post Title: Stargaze Framework Pack

> Reply from Mr.Mouse
>
> Somehow, the file is not there at the blog. Are you sure it was uploaded? Also, do you know if there are any specific copyrights on it?

Interesting. I never put it in a ZIP file, though. I have no idea about the copyrights on it. Doesn't say anything in the output.
Update: re-uploaded it.
## Post #5
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2013-01-06T04:28:51+00:00
- Post Title: Stargaze Framework Pack

> Reply from WRS
>
> Mr.Mouse wrote:Somehow, the file is not there at the blog. Are you sure it was uploaded? Also, do you know if there are any specific copyrights on it?

This attachment contains the sourcecode to the tool he mentions - but packed in the format he is describing! Very amusing!

edit wait, you found their packing tool? it should be easy to reverse the method

The stuff in the archive is the version I made. I didn't take too long thinking about what files I would stuff in there. I tried looking at their packing tool, though the last field that I want to know about isn't very obvious to find. It's somewhere in that field of expanded mod operations or something.
## Post #6
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2013-01-06T09:01:59+00:00
- Post Title: Stargaze Framework Pack

that last unknown is just an extra field left untouched by the developer. it exists because the memory allocated for the file structure was not nulled when it was allocated from the heap, but it could equally be there for future usage. and bms is perfect for extracting such a format:

```
idstring "SFP"
get ver byte

if ver != 1
  print "Expected version 1, got %ver%"
  cleanexit
endif

get fcount long
get fsize long
get size asize

if fsize != size
  print "Expected size %size%, got %fsize%"
  cleanexit
endif

for i = 1 to fcount
  get ignore1 long
  get ignore2 long
  getdstring fname 112
  get fsize long
  get foffset long
  math fsize -= 4
  math foffset += 4
  log fname fsize foffset
next i

```
## Post #7
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2013-01-08T15:35:17+00:00
- Post Title: Stargaze Framework Pack

In the BMS I don't think the file name size should be skipped, because it's possible for a really long/nested file name to use more than the default allotted space.
