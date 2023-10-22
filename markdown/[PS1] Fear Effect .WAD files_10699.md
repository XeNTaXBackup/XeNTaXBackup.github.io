## Post #1
- Username: feareffectinferno
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Nov 13, 2011 1:43 am
- Post datetime: 2013-08-19T23:20:25+00:00
- Post Title: [PS1] Fear Effect .WAD files

Hi, i need help, i've been talking with a programmer of the game, he told me the WAD files are not encrypted, but compressed.

I have exctracted ( using PSicture ) textures from those WAD files, but i don't know how to extract them.

I've opened the files with Hex Edit, i can see some .TIM .RMD .DB .ANM files but i don't know how to extract them. He told me the lowpoly models were made with Maya.



Attached some Wad files from the game. If some of you can extract and open the model ( Hana & Rain ) i would like to know how to do. Thanks, i'm  trying to extract them since 2009.

Some WAD files from the game : [http://www.mediafire.com/?8lre8clbo7e9b05](http://www.mediafire.com/?8lre8clbo7e9b05)
## Post #2
- Username: feareffectinferno
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Nov 13, 2011 1:43 am
- Post datetime: 2013-08-20T17:59:07+00:00
- Post Title: [PS1] Fear Effect .WAD files

Hi, done, i've finally extracted the WAD Files, now i don't know, how to extract the .RMD files :/


----

I found .TIM .RMD .DB .ANM files, .RMD should be the models.
## Post #3
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2013-08-25T22:32:06+00:00
- Post Title: [PS1] Fear Effect .WAD files

> Reply from feareffectinferno
>
> Hi, done, i've finally extracted the WAD Files, now i don't know, how to extract the .RMD files :/


----

I found .TIM .RMD .DB .ANM files, .RMD should be the models.
What header do the rmd files have
## Post #4
- Username: OverLung
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Mar 08, 2011 7:04 am
- Post datetime: 2014-01-04T16:43:34+00:00
- Post Title: [PS1] Fear Effect .WAD files

You can use the tool mentioned here:
[http://www.the-horror.com/forums/showth ... chive-Tool](http://www.the-horror.com/forums/showthread.php?8052-BioHazard-File-Archive-Tool)
to extract the Fear Effect 1 & 2 WADs. It extracts the RMD, TIM, ANM files etc under a new ROOT folder in the same directory as the WAD file.
I had a go at decompiling the RMD files a few years ago and came up with some stuff - static objects like weapons have their 3d data in the RMD files, but animated ones are a bit more complicated - only the data for the body seems to be in there, I guess the rest is in the ANM and DB files; I didn't go too far into it, only made a 3d mesh importer for Blender, without any texture stuff. I have a couple of ODF files with some RMD structure information in them if you want.
## Post #5
- Username: feareffectinferno
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Nov 13, 2011 1:43 am
- Post datetime: 2014-05-07T11:53:07+00:00
- Post Title: [PS1] Fear Effect .WAD files

> Reply from OverLung
>
> You can use the tool mentioned here:
http://www.the-horror.com/forums/showth ... chive-Tool
to extract the Fear Effect 1 & 2 WADs. It extracts the RMD, TIM, ANM files etc under a new ROOT folder in the same directory as the WAD file.
I had a go at decompiling the RMD files a few years ago and came up with some stuff - static objects like weapons have their 3d data in the RMD files, but animated ones are a bit more complicated - only the data for the body seems to be in there, I guess the rest is in the ANM and DB files; I didn't go too far into it, only made a 3d mesh importer for Blender, without any texture stuff. I have a couple of ODF files with some RMD structure information in them if you want.

Looks like the new version can't open WAD files anymore ...

Guys, this is a cry for help, I need someone to make a Fear Effect 1-2 Model Extractor ! Please !
