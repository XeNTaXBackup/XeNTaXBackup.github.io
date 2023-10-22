## Post #1
- Username: IngPereira
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Nov 05, 2011 8:55 am
- Post datetime: 2013-01-25T16:49:42+00:00
- Post Title: Naruto Generations CPK Unpacker

Well people i have been modifying the original utf_tab07b7 to make it compatible with naruto ultimate ninja storm generations CPK file so it can now unpack every CPK of the game, but the CPK on game have many .cpk inside so they now can be extracted and later you can select the .CPK file extracted (most models and textures are still stored in .cpk files on spc folder) but you can extract the models you want by just using again the tool with that cpk file and it will extract a file out.xfbin ready to be used with noesis.

[http://www.mediafire.com/?lk6934xwm3dbr16](http://www.mediafire.com/?lk6934xwm3dbr16)

Usage instructions: cpk_unpack dataCmn.cpk 

And it will extract all the game data in the same folder indicated on utf header.

Now when you find your model you want to have extracted (NDP3 |NTP3, or open .xfbin on noesis directly) you have to use:

cpk_unpack modelxxxx.xfbin

Then it will be a new file named modelxxxx.out.xfbin ready with the textures and models to be exported or whatever you want to do.

Again you can use Noesis with many models files and looking and the executable format there is way to make the game load this files out of the DATA .CPK so the game modding is too posible. 

I think that this works with many other games that use this same version of CRI CPK File system (a new one).

Maybe can work too with the new Naruto ultimate ninja storm 3 but will see if it work when they launch the demo version.

Thanks people.
## Post #2
- Username: darksimonus
- Rank: beginner
- Number of posts: 30
- Joined date: Sun May 02, 2010 3:57 am
- Post datetime: 2013-01-26T09:10:47+00:00
- Post Title: Naruto Generations CPK Unpacker

I'd like to know if the animations are also extractable?

The extractor is for PS3 or Xbox360 or two?
## Post #3
- Username: jrush
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Oct 25, 2012 6:10 pm
- Post datetime: 2013-01-26T11:44:46+00:00
- Post Title: Naruto Generations CPK Unpacker

I must be doing something because everytime I try to extract the .xfbin file, the out file is always 0 bytes. 

I wanted the models. How do i identify the models, does the name of the file start with a modelxxxx?
## Post #4
- Username: darksimonus
- Rank: beginner
- Number of posts: 30
- Joined date: Sun May 02, 2010 3:57 am
- Post datetime: 2013-02-22T17:11:49+00:00
- Post Title: Naruto Generations CPK Unpacker

if you have 0 bytes 

You can creat .bat and write this line:

cpk_unpack modelxxxx.xfbin


after click on .bat

and you obtain modelxxxx.out.xfbin

but me after I dont work to Noesis, i cant extract to format 


NEED HELP PLZ

[viewtopic.php?f=16&t=8768&p=82981#p82981](http://forum.xentax.com/viewtopic.php?f=16&t=8768&p=82981#p82981)
## Post #5
- Username: IngPereira
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Nov 05, 2011 8:55 am
- Post datetime: 2013-02-24T14:12:53+00:00
- Post Title: Naruto Generations CPK Unpacker

First you need to be sure that the out xfbins files are models.

I get some errors with some models but it has nothing to do with my tool is just noesis things.

The unpacker is ps3 and x360 compatible but you need to follow the instructions. 

I get uchiha itachi model to open too but there are errors with noesis and texture mapping.
## Post #6
- Username: darksimonus
- Rank: beginner
- Number of posts: 30
- Joined date: Sun May 02, 2010 3:57 am
- Post datetime: 2013-02-25T20:18:00+00:00
- Post Title: Naruto Generations CPK Unpacker

would you have the name xfbins  of a file that works 100% or upload good xfbins for test 

PLZ

Thank you
## Post #7
- Username: fierce
- Rank: advanced
- Number of posts: 41
- Joined date: Mon Jul 16, 2012 7:18 pm
- Post datetime: 2013-04-04T22:40:58+00:00
- Post Title: Naruto Generations CPK Unpacker

Nice.

I had some trouble extracting archives with that tool from dataCmn.cpk:
      1 [main] cpk_unpack 7948 exception::handle: Exception: STATUS_ACCESS_VIOLA
TION
  90986 [main] cpk_unpack 7948 open_stackdumpfile: Dumping stack trace to cpk_un
pack.exe.stackdump

But I used this bms script on that file and it worked just fine:
[viewtopic.php?p=68964#p68964](http://forum.xentax.com/viewtopic.php?p=68964#p68964)

I then used that tool only for the decompressed .xfbin files.
## Post #8
- Username: weling2010
- Rank: beginner
- Number of posts: 21
- Joined date: Fri Feb 10, 2012 3:35 pm
- Post datetime: 2013-05-11T03:43:08+00:00
- Post Title: Naruto Generations CPK Unpacker

> Reply from IngPereira
>
> Well people i have been modifying the original utf_tab07b7 to make it compatible with naruto ultimate ninja storm generations CPK file so it can now unpack every CPK of the game, but the CPK on game have many .cpk inside so they now can be extracted and later you can select the .CPK file extracted (most models and textures are still stored in .cpk files on spc folder) but you can extract the models you want by just using again the tool with that cpk file and it will extract a file out.xfbin ready to be used with noesis.

http://www.mediafire.com/?lk6934xwm3dbr16

Usage instructions: cpk_unpack dataCmn.cpk 

And it will extract all the game data in the same folder indicated on utf header.

Now when you find your model you want to have extracted (NDP3 |NTP3, or open .xfbin on noesis directly) you have to use:

cpk_unpack modelxxxx.xfbin

Then it will be a new file named modelxxxx.out.xfbin ready with the textures and models to be exported or whatever you want to do.

Again you can use Noesis with many models files and looking and the executable format there is way to make the game load this files out of the DATA .CPK so the game modding is too posible. 

I think that this works with many other games that use this same version of CRI CPK File system (a new one).

Maybe can work too with the new Naruto ultimate ninja storm 3 but will see if it work when they launch the demo version.

Thanks people.


how can make a batch for cpk_unpack decompress all xfbin?
## Post #9
- Username: Wioneul
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Nov 15, 2012 6:00 pm
- Post datetime: 2013-07-19T19:03:32+00:00
- Post Title: Naruto Generations CPK Unpacker

Can you please create the CPK compressor (rebuilder) for modified files?
## Post #10
- Username: namquang93
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Apr 09, 2012 3:40 pm
- Post datetime: 2014-03-31T15:21:42+00:00
- Post Title: Naruto Generations CPK Unpacker

> Reply from Wioneul
>
> Can you please create the CPK compressor (rebuilder) for modified files?
Hi! Can you compressor CPK for modified  files?
## Post #11
- Username: Nogi
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jul 20, 2023 5:25 pm
- Post datetime: 2023-07-26T05:26:05+00:00
- Post Title: Naruto Generations CPK Unpacker

> Reply from IngPereira ↑Sun Feb 24, 2013 10:12 pm at Sun Feb 24, 2013 10:12 pm
>
> 
The unpacker is ps3 and x360 compatible but you need to follow the instructions.naruto senki

Is it compatible with the PS2?
