## Post #1
- Username: Frozik
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Jun 22, 2010 1:27 am
- Post datetime: 2011-12-04T14:42:36+00:00
- Post Title: Assassins Creed: Revelations

Any ideas how to unpack 3d models and textures from *.forge?
## Post #2
- Username: JPulowski
- Rank: beginner
- Number of posts: 30
- Joined date: Sun Aug 29, 2010 5:39 am
- Post datetime: 2011-12-06T17:09:57+00:00
- Post Title: Assassins Creed: Revelations

You may use Forgeview that is posted on another thread.

[viewtopic.php?f=10&t=3005&start=120](http://forum.xentax.com/viewtopic.php?f=10&t=3005&start=120)

> Reply from DerPlaya
>
> Hi all,

I did some research on ACB's forge files, here's the result.

It's an unfinished tool (and will probably stay unfinished).

What it can do:
- view/export textures as DDS/PNG
- view/export LocalizationPackage files as *.txt
- view most Models - very simple viewer using WPF, no proper texture support (uses first texture which has 'Diffuse' in its name...)
- view/export data of unknown types as hex/binary

What it can't do:
- no Model export, no import...

some facts:
- most id type fields (EntryId, ...) are CRC32 hashes
- lots of data is stored as duplicate in the same forge (probably console specific optimization)
- I started to decode some other types: Skeleton, Material, MaterialTemplate, ... see source code.

The tool needs .net 4 (client profile) and should be compilable with VC# Express 2010

If you want to use some of the code in your own tool/program go ahead...

I won't give any support or can be held responsible for damage - USE AT OWN RISK

[url=[/url]

Uploaded with [url=
## Post #3
- Username: milance941
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Sep 06, 2011 1:00 am
- Post datetime: 2011-12-07T20:56:22+00:00
- Post Title: Assassins Creed: Revelations

3D Ripper DX won't work either:(
## Post #4
- Username: Sidus
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Dec 09, 2011 1:56 am
- Post datetime: 2011-12-08T18:14:16+00:00
- Post Title: Assassins Creed: Revelations

> Reply from JPulowski
>
> You may use Forgeview that is posted on another thread.

viewtopic.php?f=10&t=3005&start=120
DerPlaya wrote:Hi all,

I did some research on ACB's forge files, here's the result.

It's an unfinished tool (and will probably stay unfinished).

What it can do:
- view/export textures as DDS/PNG
- view/export LocalizationPackage files as *.txt
- view most Models - very simple viewer using WPF, no proper texture support (uses first texture which has 'Diffuse' in its name...)
- view/export data of unknown types as hex/binary

What it can't do:
- no Model export, no import...

some facts:
- most id type fields (EntryId, ...) are CRC32 hashes
- lots of data is stored as duplicate in the same forge (probably console specific optimization)
- I started to decode some other types: Skeleton, Material, MaterialTemplate, ... see source code.

The tool needs .net 4 (client profile) and should be compilable with VC# Express 2010

If you want to use some of the code in your own tool/program go ahead...

I won't give any support or can be held responsible for damage - USE AT OWN RISK

[url=[/url]

Uploaded with [url=

Trying to view a mesh with forgeview 0.0.0.1, what you will get is:

```
expected 0x92b95f74 got 0xb95f7400
```
