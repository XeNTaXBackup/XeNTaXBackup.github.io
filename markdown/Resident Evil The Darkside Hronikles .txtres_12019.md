## Post #1
- Username: Kaltan
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Jan 04, 2011 12:14 am
- Post datetime: 2014-09-27T18:17:04+00:00
- Post Title: Resident Evil: The Darkside Hronikles .txtres

Help to write a script BMS for packing and unpacking of the text in the game Resident Evil - The Darkside Hronikles.
[http://rghost.ru/58227121](http://rghost.ru/58227121)
Thank you very much.
## Post #2
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2014-09-28T01:47:06+00:00
- Post Title: Resident Evil: The Darkside Hronikles .txtres

The format seems straightforward enough...

```
{
    char magic[4] = "TRES";
    int version;
    int entryCount;
    int unknown; // 16
};

struct entry
{
    int messageIndex;
    int keyTextOffset;
    int type;
    int valueTextOffset;
    int reserved1; // always 0?
    int reserved2; // always 0?
};

struct main
{
	header h;
	int entryPointers[h.entryCount]; // offset to entries
	entry entries[h.entryCount];
	// null terminated string array
};
```
## Post #3
- Username: Kaltan
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Jan 04, 2011 12:14 am
- Post datetime: 2014-09-28T04:06:56+00:00
- Post Title: Resident Evil: The Darkside Hronikles .txtres

And you can write the script BMS?
## Post #4
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2014-09-28T20:38:57+00:00
- Post Title: Resident Evil: The Darkside Hronikles .txtres

The file isn't exactly an archive; it's a collection of strings with a bit of metadata. QuickBMS can probably do operations to dump everything to text, but you're really better off finding a more general purpose scripting language to use for exporting and importing.
## Post #5
- Username: Kaltan
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Jan 04, 2011 12:14 am
- Post datetime: 2014-09-29T07:56:43+00:00
- Post Title: Resident Evil: The Darkside Hronikles .txtres

> Reply from GMMan
>
> The file isn't exactly an archive; it's a collection of strings with a bit of metadata. QuickBMS can probably do operations to dump everything to text, but you're really better off finding a more general purpose scripting language to use for exporting and importing.
I need to extract the text in TXT, translated into Russian and back pack in .txtres. In general, I want to make a translation of the game on the Russian language.
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-09-29T16:55:00+00:00
- Post Title: Resident Evil: The Darkside Hronikles .txtres

try this txtres recreator:

[http://www.uploadmb.com/dw.php?id=1412009522](http://www.uploadmb.com/dw.php?id=1412009522)
## Post #7
- Username: Kaltan
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Jan 04, 2011 12:14 am
- Post datetime: 2014-09-29T17:30:59+00:00
- Post Title: Resident Evil: The Darkside Hronikles .txtres

> Reply from shakotay2
>
> try this txtres recreator:

http://www.uploadmb.com/dw.php?id=1412009522
Thank you very much, works great.
## Post #8
- Username: krzys837
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Aug 10, 2014 5:21 pm
- Post datetime: 2014-09-30T13:10:13+00:00
- Post Title: Resident Evil: The Darkside Hronikles .txtres

Very thank you for text tool Shakotay. I want make Polish translation, but i need help with fonts(.BRFNT file)

utf8_J.brfnt:
[http://pl.rghost.net/58281608](http://pl.rghost.net/58281608)
utf8_E.brfnt:
[http://pl.rghost.net/58281609](http://pl.rghost.net/58281609)
## Post #9
- Username: izunaa
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Sep 18, 2023 12:09 pm
- Post datetime: 2023-09-18T04:11:33+00:00
- Post Title: Resident Evil: The Darkside Hronikles .txtres

> Reply from shakotay2 ↑Tue Sep 30, 2014 12:55 am at Tue Sep 30, 2014 12:55 am
>
> 
try this txtres recreator:

http://www.uploadmb.com/dw.php?id=1412009522

link Broken ... i need this script please Fix
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-09-18T16:45:54+00:00
- Post Title: Resident Evil: The Darkside Hronikles .txtres

9 years later?   I'm sorry, but you're too late. (I don't even know what that script or app did exactly.)
## Post #11
- Username: krzys837
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Aug 10, 2014 5:21 pm
- Post datetime: 2023-09-24T16:09:41+00:00
- Post Title: Resident Evil: The Darkside Hronikles .txtres

Hello. I kept it for 9 years. It works nice. Thanks shakotay.
[( uploadMB.com ) RE-txtRes.zip](https://xentaxbackup.github.io/file/24377_( uploadMB.com ) RE-txtRes.zip)
