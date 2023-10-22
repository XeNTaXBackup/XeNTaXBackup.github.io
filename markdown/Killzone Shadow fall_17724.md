## Post #1
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2018-02-19T18:04:45+00:00
- Post Title: Killzone Shadow fall

I managed to access the contents of pkg files
core file can be uncompressed using quickbms
[http://aluigi.altervista.org/quickbms.htm](http://aluigi.altervista.org/quickbms.htm)
Now we need to convert the models and textures.
Some models have already been extracted, so the tool can already exist, but I did not find it
examle files:
[https://www.dropbox.com/s/6fd0phijstnkm ... ll.7z?dl=0](https://www.dropbox.com/s/6fd0phijstnkmlc/killzone%20shadow%20fall.7z?dl=0)
## Post #2
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-02-19T18:49:18+00:00
- Post Title: Killzone Shadow fall

I don't think there is an existing tool for it. Luxox was extracting those models by hand, using hex2obj.
## Post #3
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2018-02-19T19:49:45+00:00
- Post Title: Killzone Shadow fall

Well, what about the textures?
I'll try to get the models myself

Another couple of questions 
- PS4 uses an inverted byte order?

-When I unpack the core using quickbms, I get one large file.
At first glance, it is several of joined files - as in a container without compression. They can somehow be divided (so it's easier to analyze them)?
## Post #4
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-02-19T20:23:18+00:00
- Post Title: Killzone Shadow fall

Killzone Shadow fall tool

Usage:
- unpack .core files with BMS script
- drop .UNP file onto the tool
- to convert textures, put UNP files in some folder, create "streams" subfolder there, and put .corestreams into that "streams" subfolder.

Important note: packages sometimes have LINKS to some assets used from common packages
i extracted a few most used of them, just put this stuff next to the tool
notify me if something else is missing, tool will give messages

There are some unsupported texture types (RGBA, 1-channel grey etc...)



Tool can also extract static meshes and level geometry:


[Killzone_core.rar](https://xentaxbackup.github.io/file/14032_Killzone_core.rar)
## Post #5
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-02-19T20:34:16+00:00
- Post Title: Killzone Shadow fall

As expected of daemon . I guess he saved you from some trouble.
## Post #6
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2018-02-19T20:52:42+00:00
- Post Title: Killzone Shadow fall

Cool! Are the textures also extracted?
 When can we use it?
I'm mostly interested in weapons and vehicles.
## Post #7
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-02-19T21:08:06+00:00
- Post Title: Killzone Shadow fall

> Reply from erik945
>
> Cool! Are the textures also extracted?
yes
## Post #8
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2018-02-19T21:42:10+00:00
- Post Title: Killzone Shadow fall

Great!
Will wait.
## Post #9
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2018-02-20T05:43:36+00:00
- Post Title: Killzone Shadow fall

> Reply from erik945
>
> I managed to access the contents of pkg files
core file can be uncompressed using quickbms
http://aluigi.altervista.org/quickbms.htm
Now we need to convert the models and textures.
Some models have already been extracted, so the tool can already exist, but I did not find it
examle files:
https://www.dropbox.com/s/6fd0phijstnkm ... ll.7z?dl=0

I did try to extract the .core files using the latest version of Quickbms with the following script, but I have got always an error message.
[http://aluigi.altervista.org/bms/killzone.bms](http://aluigi.altervista.org/bms/killzone.bms)
[Error.jpg](https://xentaxbackup.github.io/file/13936_Error.jpg)
## Post #10
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-02-20T09:56:36+00:00
- Post Title: Killzone Shadow fall

> Reply from Karpati
>
> 
I did try to extract the .core files using the latest version of Quickbms with the following script, but I have got always an error message.

That script is for Killzone Liberation, the psp game. Use this for the Shadow Fall files : [viewtopic.php?p=125936#p125936](http://forum.xentax.com/viewtopic.php?p=125936#p125936)
## Post #11
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2018-02-24T13:35:47+00:00
- Post Title: Killzone Shadow fall

The tool has been released. Check zenhax forum.
## Post #12
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-02-26T15:13:54+00:00
- Post Title: Killzone Shadow fall

Xentax was unavailable here for 3 days. Tool posted.
## Post #13
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2018-03-06T03:11:34+00:00
- Post Title: Killzone Shadow fall

Wow another good work by Daemon1 !
## Post #14
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-03-14T19:23:54+00:00
- Post Title: Killzone Shadow fall

Tool updated! More packages must work now.
Also multi-uv problem fixed.
