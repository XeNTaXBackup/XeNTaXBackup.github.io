## Post #1
- Username: HAIDER6222354
- Rank: beginner
- Number of posts: 27
- Joined date: Wed Jul 04, 2012 12:19 pm
- Post datetime: 2014-04-23T03:59:29+00:00
- Post Title: Splinter Cell Blacklist loc-int.umd (EPCK)

hi 

this file loc-int.umd for language in SC Blacklist i a try with iaa_unpacker but cant extract it

???

this loc-int.umd
[http://ps3gameroom.net/upme/uploads/1398225540561.zip](http://ps3gameroom.net/upme/uploads/1398225540561.zip)
## Post #2
- Username: swuforce
- Rank: veteran
- Number of posts: 121
- Joined date: Fri Nov 06, 2009 3:46 am
- Post datetime: 2014-04-24T16:39:01+00:00
- Post Title: Splinter Cell Blacklist loc-int.umd (EPCK)

There is a method, but only with size limit.
Unpack attached file to a folder and put the tools there: aluigi's [quickbms](http://aluigi.altervista.org/quickbms.htm) and [offzip](http://aluigi.altervista.org/mytoolz.htm#offzip), Gildor's [unumd](http://www.gildor.org/smf/index.php/topic,458.msg15196.html#msg15196).

For loc umd:
Drag it to !export_loc. Files unpacked to loc-... folder. Edit them, but size can't be bigger than original, or reimport not work.
Drag it to !import_loc for reimport.

For ingame text: (they are in ...strm_b.umd files)
Drag umd to !export_text. The xml files size can't be bigger than original, or reimport not work.
Drag umd to !import_text for reimport.
[scb_text.7z](https://xentaxbackup.github.io/file/7252_scb_text.7z)
## Post #3
- Username: HAIDER6222354
- Rank: beginner
- Number of posts: 27
- Joined date: Wed Jul 04, 2012 12:19 pm
- Post datetime: 2014-04-25T17:43:56+00:00
- Post Title: Splinter Cell Blacklist loc-int.umd (EPCK)

> Reply from swuforce
>
> There is a method, but only with size limit.
Unpack attached file to a folder and put the tools there: aluigi's quickbms and offzip, Gildor's unumd.

For loc umd:
Drag it to !export_loc. Files unpacked to loc-... folder. Edit them, but size can't be bigger than original, or reimport not work.
Drag it to !import_loc for reimport.

For ingame text: (they are in ...strm_b.umd files)
Drag umd to !export_text. The xml files size can't be bigger than original, or reimport not work.
Drag umd to !import_text for reimport.
thanks for this worked
## Post #4
- Username: HAIDER6222354
- Rank: beginner
- Number of posts: 27
- Joined date: Wed Jul 04, 2012 12:19 pm
- Post datetime: 2014-04-25T18:07:21+00:00
- Post Title: Splinter Cell Blacklist loc-int.umd (EPCK)

but how can i find font file or edit it

edit : I FIND gfxfontlib.gfx in dynamicxbox.umd but i cant unpack or repack
## Post #5
- Username: swuforce
- Rank: veteran
- Number of posts: 121
- Joined date: Fri Nov 06, 2009 3:46 am
- Post datetime: 2014-04-25T20:12:30+00:00
- Post Title: Splinter Cell Blacklist loc-int.umd (EPCK)

> Reply from HAIDER6222354
>
> but how can i find font file or edit it

edit : I FIND gfxfontlib.gfx in dynamicxbox.umd but i cant unpack or repack
Replace the scb_unp.bms file with the attached one, and drop it on !export_loc
If no work send the file to me, try to take a look.
[scb_unp.7z](https://xentaxbackup.github.io/file/7258_scb_unp.7z)
## Post #6
- Username: HAIDER6222354
- Rank: beginner
- Number of posts: 27
- Joined date: Wed Jul 04, 2012 12:19 pm
- Post datetime: 2014-04-26T04:03:39+00:00
- Post Title: Splinter Cell Blacklist loc-int.umd (EPCK)

> Reply from swuforce
>
> HAIDER6222354 wrote:but how can i find font file or edit it

edit : I FIND gfxfontlib.gfx in dynamicxbox.umd but i cant unpack or repack

Replace the scb_unp.bms file with the attached one, and drop it on !export_loc
If no work send the file to me, try to take a look.

here this file 
[https://www.firedrive.com/file/10E652C0DD537C9E](https://www.firedrive.com/file/10E652C0DD537C9E)

i am try with new scb_unp.bms to unpack file work 100% but i cant repack file or repack text or loc-int
## Post #7
- Username: swuforce
- Rank: veteran
- Number of posts: 121
- Joined date: Fri Nov 06, 2009 3:46 am
- Post datetime: 2014-04-26T08:50:51+00:00
- Post Title: Splinter Cell Blacklist loc-int.umd (EPCK)

Looks like when quickbms compress a part of this file, it will be bigger than the original.
When quickbms gives a warning, skip the files.
But im not sure this will work.
## Post #8
- Username: connortg12
- Rank: advanced
- Number of posts: 42
- Joined date: Sun Nov 10, 2013 9:19 pm
- Post datetime: 2014-05-19T12:11:28+00:00
- Post Title: Splinter Cell Blacklist loc-int.umd (EPCK)

Texts will not import. Help me!
## Post #9
- Username: swuforce
- Rank: veteran
- Number of posts: 121
- Joined date: Fri Nov 06, 2009 3:46 am
- Post datetime: 2014-05-19T15:26:03+00:00
- Post Title: Splinter Cell Blacklist loc-int.umd (EPCK)

> Reply from connortg12
>
> Texts will not import. Help me!  :(
Which file you want to reimport? What is the error message?
## Post #10
- Username: connortg12
- Rank: advanced
- Number of posts: 42
- Joined date: Sun Nov 10, 2013 9:19 pm
- Post datetime: 2014-05-20T13:07:40+00:00
- Post Title: Splinter Cell Blacklist loc-int.umd (EPCK)

> Reply from swuforce
>
> connortg12 wrote:Texts will not import. Help me!  
Which file you want to reimport? What is the error message?
Problem: 0 files reimported in 1 seconds. AND "the 'import' folder doesn't exist, do you want to create it?
I created but still this message: 0 files reimported in 1 seconds.
I need the translate this game. Please help me.
