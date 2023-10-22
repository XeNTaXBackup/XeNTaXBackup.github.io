## Post #1
- Username: RiccoChicco
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Apr 06, 2015 12:45 am
- Post datetime: 2017-12-25T22:11:20+00:00
- Post Title: WRC7 .PTX textures

Hi!

I try to edit some textures from the last WRC game, unfortunately once I extracted archives, I find a lot of .PTX textures. I'm quite conviced it's some sort of .DDS since it mentions DXT1/3/5 when reading it with an hex editor. I saw that someone else already asked something similar for WRC6, unfortnately no one answered.

If anyone know how to go to/from PTX to a more standard format, it will be greatly appreciated!   

An example texture has been joined to the post  
[example.rar](https://xentaxbackup.github.io/file/13728_example.rar)
## Post #2
- Username: MaKiPL
- Rank: advanced
- Number of posts: 60
- Joined date: Sat Sep 13, 2014 9:05 pm
- Post datetime: 2017-12-27T10:45:39+00:00
- Post Title: WRC7 .PTX textures

Normal un-compressed/un-obfuscated DXT3/5 file with MipMaps (Big endian!). See attachement

This file has modified/damaged DDS format, but you'll be fine if you read it after normal DDS header size. Anyway, just grab sample DXT1 DDS file and rebuild header.
[example.jpg](https://xentaxbackup.github.io/file/13738_example.jpg)
## Post #3
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-12-27T13:58:21+00:00
- Post Title: WRC7 .PTX textures

its not big-endian or modified/damaged, just typical dxt stored in RIFF container with a 130 byte header. 
seems the data might be stored in max chunk size of 0x80000, though before i make a script i need more 
variety of samples to look at for compare. i plan on making a script to work with both WRC6 and WRC7.   

[https://en.wikipedia.org/wiki/Resource_ ... ile_Format](https://en.wikipedia.org/wiki/Resource_Interchange_File_Format)
## Post #4
- Username: MaKiPL
- Rank: advanced
- Number of posts: 60
- Joined date: Sat Sep 13, 2014 9:05 pm
- Post datetime: 2017-12-28T12:34:55+00:00
- Post Title: WRC7 .PTX textures

> Reply from AceWell
>
> its not big-endian or modified/damaged, just typical dxt stored in RIFF container with a 130 byte header.

Every day I learn something new, I though RIFF is only audio file. Thanks!
## Post #5
- Username: RiccoChicco
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Apr 06, 2015 12:45 am
- Post datetime: 2018-01-02T22:35:45+00:00
- Post Title: WRC7 .PTX textures

Wow! Great news! Thanks a lot!
## Post #6
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-01-02T23:22:28+00:00
- Post Title: WRC7 .PTX textures

if you upload more samples i will make a Noesis python script  

edit
my WRC 6 ptx Noesis python script here seems to work with this game samples.   
[viewtopic.php?p=139861#p139861](http://forum.xentax.com/viewtopic.php?p=139861#p139861)
## Post #7
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2018-01-03T00:01:31+00:00
- Post Title: WRC7 .PTX textures

it got brembos on it.
