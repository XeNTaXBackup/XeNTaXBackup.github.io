## Post #1
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2012-09-29T04:25:03+00:00
- Post Title: X360 Love Tore Sweet

Hi, guys
I would be able to browse models, but most do not have such knowledge.
.bin (meshes)
.dds (textures)
I will send you PM with sample.
Any help would be greatly appreciated. 

Thanks,
## Post #2
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-09-29T17:48:44+00:00
- Post Title: X360 Love Tore Sweet

This one is easy as pie. Don't have time for it though. If someone else wants to learn this stuff this is a game to do it.
## Post #3
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-09-29T17:52:12+00:00
- Post Title: X360 Love Tore Sweet

> This one is easy as pie. Don't have time for it though. If someone else wants to learn this stuff this is a game to do it.

Hum great !!

I will enjoy to have some models of this one, and will enjoy to learn how to get better at reversing 3d.
Wait the sample :p
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-09-29T20:58:13+00:00
- Post Title: X360 Love Tore Sweet

> Reply from howfie
>
> This one is easy as pie. Don't have time for it though. If someone else wants to learn this stuff this is a game to do it.

Anything in particular to watch out for?
## Post #5
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-09-30T02:35:04+00:00
- Post Title: X360 Love Tore Sweet

nope. vertex and index buffers are in plain site. textures are already in DDS files; no need to extract textures lol.
## Post #6
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-09-30T02:36:40+00:00
- Post Title: X360 Love Tore Sweet

> nope. vertex and index buffers are in plain site. textures are already in DDS files; no need to extract textures lol.

GOOD !  I really want to pick a try.

PS: And by the way, nice HTML5 game :p
## Post #7
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-09-30T02:55:42+00:00
- Post Title: X360 Love Tore Sweet

thanks. i would have made it fancier, but Namco goes after people if you get too close lol. go ahead and give Love * Sweet a try. what language are you going to use? if you need help just ask on here.
## Post #8
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-09-30T03:09:45+00:00
- Post Title: X360 Love Tore Sweet

> Namco goes after people if you get too close lol
Wow !! I didn't know that lol.

> go ahead and give Love * Sweet a try. what language are you going to use? if you need help just ask on here.

I will just read the files with a Hexadecimal, then try to "store" the data in a txt file.
Then I will see if I will use python or maybe PHP.....

The thing is I have a project, re-create all (or at least what I love) console games on PC using HTML5 technology, so using PHP for converting to .JSON will be good case for me :p
## Post #9
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-10-01T05:50:56+00:00
- Post Title: X360 Love Tore Sweet

Does someone can provide me a sample ?
## Post #10
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-10-14T15:44:11+00:00
- Post Title: X360 Love Tore Sweet

```
you have 4 bytes for a tag like
AGHX
SCEN
IMGH
then each tag has 12 bytes following it
6 shorts.
This is what tells you the xml structure
its slightly complex in that the numbers can mean a few different things based on the tag.
in a lot of the tags the 2nd short means the number of child elements.
for example
GEOM 00 00 00 02 00 10 00 00 00 00 00 00
this means there are 2 sub nodes under geom
so here is an example
==GEOM 00 00 00 02 00 10 00 00 00 00 00 00 - 2 TRLS sub nodes
====TRLS 00 00 00 01 00 10 00 00 00 00 00 00 - in this case the 1 means it has 1 data element
======VELM 00 00 00 07 00 10 00 00 00 00 00 00 - in this case the 7 means it has 7 data elements 
======INDX 00 00 06 06 00 10 00 02 00 00 00 00 - in this case the 0606 means it has that many face indecies
======VERT 00 00 16 1E 00 10 00 00 00 00 00 00 - in this case 16 1E * 4 is the size of the vertex buffer
======BUND 00 00 00 01 00 10 00 01 00 00 00 00 - in this case the 1 means it has 1 data element 
====TRLS 00 00 00 01 00 10 00 00 00 00 00 00
======VELM 00 00 00 07 00 10 00 00 00 00 00 00
======INDX 00 00 03 0C 00 10 00 02 00 00 00 00
======VERT 00 00 0A 64 00 10 00 00 00 00 00 00
======BUND 00 00 00 01 00 10 00 01 00 00 00 00

The VELEm tells how to read the vertex points
Vert Element start , type , count
00000000 504F5349 00000003 POSI - 3 floats for verts
0000000C 4E4F524D 00000003 NORM - 3 floats for normals
00000018 54414E47 00000003 TANG - 3 floats for gangents
00000024 42494E4F 00000003 BINO - 3 floats for binormals
00000030 54455843 00000002 TEXC - 2 flaots for tex coords
00000038 424C5745 00000004 BLWE - 4 floats for bone weights
00000048 424C494E 00000001 BLIN - 4 bytes for bone indecies


```
## Post #11
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-10-15T03:39:27+00:00
- Post Title: X360 Love Tore Sweet

Ok I should have this done tomorrow just need to finish a few more things but its getting late.
## Post #12
- Username: protosk8
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-10-16T03:46:29+00:00
- Post Title: X360 Love Tore Sweet

here is a beta script it loads everything you need to get the models out with normals and uv's.
each model has only 2 or 3 textures so they are fairly easy to assign.
[fmt_tls_bin_001.zip](https://xentaxbackup.github.io/file/5902_fmt_tls_bin_001.zip)
## Post #13
- Username: HatsuneMiku15
- Rank: n00b
- Number of posts: 10
- Joined date: Mon May 07, 2012 7:13 pm
- Post datetime: 2012-10-19T11:09:24+00:00
- Post Title: X360 Love Tore Sweet

Could I have the samples please??
## Post #14
- Username: anime663
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Jun 04, 2012 8:45 am
- Post datetime: 2012-12-30T01:04:20+00:00
- Post Title: X360 Love Tore Sweet

I cant seem to find where the .bin files are. Where did u find them?
## Post #15
- Username: mikulover39
- Rank: advanced
- Number of posts: 61
- Joined date: Tue Nov 22, 2011 5:55 pm
- Post datetime: 2013-01-02T19:47:47+00:00
- Post Title: X360 Love Tore Sweet

Cool script thanks chrrox although one model had a UV error but that was easily fixed in a hex editor
## Post #16
- Username: anime663
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Jun 04, 2012 8:45 am
- Post datetime: 2013-01-11T20:59:08+00:00
- Post Title: Re: X360 Love Tore Sweet

> Reply from chrrox
>
> here is a beta script it loads everything you need to get the models out with normals and uv's.
each model has only 2 or 3 textures so they are fairly easy to assign.

When I convert the Gabriel/Gabrielle's Uniform outfit it has a UV issue on the shirt. I don't understand hex editor so is there any else to fix it without UV mapping?
Or can you fix it possibly?
