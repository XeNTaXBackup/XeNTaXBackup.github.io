## Post #1
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2015-07-07T12:41:51+00:00
- Post Title: StarWars Battlefront Closed Beta

hello

i'm looking to unpack  .cas files

engine : FrostBite3



test with DAImoddingTool, we can open it, but cannot extract or see anything ...

samples:
[http://www.filedropper.com/swbf](http://www.filedropper.com/swbf)
## Post #2
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2015-07-08T04:37:27+00:00
- Post Title: StarWars Battlefront Closed Beta

So the packages seem to be the same as DAI and BF4/H and textures are full DX11 dds files and here are some of them.

Credit goes to danielmm8888 and PistonMiner for creating the tool though.

Models are next on their list and than sound and the 5 odd videos that are in the game files.
## Post #3
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2015-07-13T04:21:34+00:00
- Post Title: StarWars Battlefront Closed Beta

So am I right to say at the moment the battlefront files cannot be extracted I'm trying to extract the sounds. 

If not I hope someone can look into adjusting the script to extract the files.
## Post #4
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-07-15T08:24:03+00:00
- Post Title: StarWars Battlefront Closed Beta

Checked danielmm8888's script. It just dumps all files from CAS with no names, including sounds. I can make XAS extractor, if they still didn't make it.
## Post #5
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-07-15T12:52:04+00:00
- Post Title: StarWars Battlefront Closed Beta

Well, it seems my decoder already supports it, because it's standard XAS audio files.

The only thing you need now is to split chunks into individual files. This must be easy.

OK so this is what you can do now:

1. extract all chunks from cas with danielmm8888's script

2. run my tool Frostbyte_chunk on each chunk to merge uncompressed chunks into raw data

3. if chunk has multiple audio files, split them somehow

4. decode XAS into WAV with my tool xas_decode

Checked it with some battlefront music and steps sounds, all worked ok.
[frostbyte_chunk_&_xas_decoder.rar](https://xentaxbackup.github.io/file/9425_frostbyte_chunk_&_xas_decoder.rar)
## Post #6
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2015-07-16T22:46:40+00:00
- Post Title: StarWars Battlefront Closed Beta

OK here's my question though. Where do I get danielmm8888's script because I checked everywhere and can't seem to find it.
## Post #7
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-07-17T06:37:59+00:00
- Post Title: StarWars Battlefront Closed Beta

This is what i googled:

[https://raw.githubusercontent.com/Pisto ... tractor.py](https://raw.githubusercontent.com/PistonMiner/fb3-tools/master/scripts/CASExtractor.py)

But maybe JakeGreen knows better, he was talking about some tool. I don't know who they are or how to contact them.
## Post #8
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2015-07-17T15:41:16+00:00
- Post Title: StarWars Battlefront Closed Beta

Thank you so much, this is different from Frank's script and I'm having a little bit of trouble with it could I trouble you for some help? I've been messing with the script but I can't seem to get it to work. I initially thought it was "OK this is a piece of cake just input the directories and hit F5" 

so I'm putting. 

```
catFileName = sys.argv[1]
catFile = open(catFileName, 'C:\Battlefront\Data\cas.cat') 
catFileSize = os.path.getsize(catFileName)

# Skip the signature
catFile.seek(0x10)

# Create the folder where we'll be dumping the content into (if necessary)
if not os.path.exists("C:/dump/"):
    os.makedirs("dump/")
```


every time I do I get this. 

```
  File "C:\Battlefront\Data\CASExtractor.py", line 8, in <module>
    catFileName = sys.argv[1]
IndexError: list index out of range
```


What am I doing wrong?
## Post #9
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-07-17T16:40:06+00:00
- Post Title: StarWars Battlefront Closed Beta

This script is supposed to be run with command line arguments. If you want to run it without them, do this:

```
catFileName = "C:\Battlefront\Data\cas.cat" 
```

only change 1st line, not others

p.s. also note, I'm not aware if any scripts exist to split audio chunks. The one for DAI doesn't work, maybe there are others. I was splitting them manually. If none exist, I can write a new splitter.
## Post #10
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2015-07-17T16:51:15+00:00
- Post Title: StarWars Battlefront Closed Beta

EDIT: n/m i got it I had to put the script in the data folder. 

alright extracting the files now!
## Post #11
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2015-07-17T17:11:35+00:00
- Post Title: StarWars Battlefront Closed Beta

> Reply from daemon1
>
> p.s. also note, I'm not aware if any scripts exist to split audio chunks. The one for DAI doesn't work, maybe there are others. I was splitting them manually. If none exist, I can write a new splitter.

It worked I got 4,267 files they extract now I just need to work on batch extracting and converting. I haven't seen any example of splitting audio chunks yet but could you work on a tool in case? And if there are multiple files exist what hex code or tag would I be looking for in the file? 

I hope all of the gunfire and vehicles sounds are here, that's what i'm after the most.
## Post #12
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-07-17T17:52:05+00:00
- Post Title: StarWars Battlefront Closed Beta

> Reply from durandal217
>
> And if there are multiple files exist what hex code or tag would I be looking for in the file?

No, chunks are just audio files merged together, there's no way to know how many files they contain. This information is in corresponding EBX files, and we don't have their names now.
## Post #13
- Username: danielmm8888
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jul 20, 2015 6:53 am
- Post datetime: 2015-07-19T22:56:34+00:00
- Post Title: StarWars Battlefront Closed Beta

We've already gotten model texture and sound extraction to work.

Here's an image of the sandtrooper model (viewport in Maya)
[http://i.imgur.com/xuHOk51.png](http://i.imgur.com/xuHOk51.png)
Here's an image of the star destroyer (rendered using Mental ray in Maya)
[http://i.imgur.com/olXszZW.jpg](http://i.imgur.com/olXszZW.jpg)
Here's an image of the star destroyer in UE4 with the proper textures
[http://i.imgur.com/WuEKLnu.png](http://i.imgur.com/WuEKLnu.png)
[http://i.imgur.com/F6lNLKT.png](http://i.imgur.com/F6lNLKT.png)
## Post #14
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2015-07-21T14:38:28+00:00
- Post Title: StarWars Battlefront Closed Beta

> Reply from danielmm8888
>
> We've already gotten model texture and sound extraction to work.

Daniel, have you released the tool? or is it still in a work in progress? is there a way I can get my hands on it?
## Post #15
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-07-21T17:20:27+00:00
- Post Title: StarWars Battlefront Closed Beta

Probably no, or it's a secret tool, he's not answering PM's either. So we don't know if their tool work correctly with sounds. Had you any success finding the sounds you wanted?
## Post #16
- Username: danielmm8888
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jul 20, 2015 6:53 am
- Post datetime: 2015-07-21T17:24:23+00:00
- Post Title: Re: StarWars Battlefront Closed Beta

We're simply just not ready to release the tool yet.
## Post #17
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-07-21T17:30:14+00:00
- Post Title: Re: StarWars Battlefront Closed Beta

What are you using to unpack sounds? Were you able to split chunks? Do you need any help or should I make my own tool for this now?
## Post #18
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2015-07-23T07:02:57+00:00
- Post Title: Re: StarWars Battlefront Closed Beta

> Reply from danielmm8888
>
> We're simply just not ready to release the tool yet.

take your time ....
you do an excellent job !
## Post #19
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2015-07-23T21:55:37+00:00
- Post Title: Re: StarWars Battlefront Closed Beta

> Reply from daemon1
>
> Probably no, or it's a secret tool, he's not answering PM's either. So we don't know if their tool work correctly with sounds. Had you any success finding the sounds you wanted?

I got alot but not all some sounds didn't convert at all for what reason i'm not sure, I thought maybe they were EA layer3 but using the zelch's tool didn't yield any results. It seems like the weapon sounds and the reflection sounds for the blaster are missing.
## Post #20
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-07-24T07:03:26+00:00
- Post Title: Re: StarWars Battlefront Closed Beta

Can you give me some numbers, so I can check if those chunks have multiple files?

The ones that don't convert are raw PCM files.
## Post #21
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2015-07-24T22:33:34+00:00
- Post Title: Re: StarWars Battlefront Closed Beta

> Reply from daemon1
>
> Can you give me some numbers, so I can check if those chunks have multiple files?

The ones that don't convert are raw PCM files.

114, 160, 308 are three example I can give you. If they are pcm files how to you convert those?
## Post #22
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-07-25T06:35:50+00:00
- Post Title: Re: StarWars Battlefront Closed Beta

ok 308 is PCM. Use Frostbyte_chunk on it, then open in sound editor as RAW PCM 16 bit stereo 48000 hz.

The others are XAS with extra info, need some time to think about it.
## Post #23
- Username: PistonMiner
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jul 25, 2015 7:21 pm
- Post datetime: 2015-07-25T17:47:37+00:00
- Post Title: Re: StarWars Battlefront Closed Beta

I will just join the discussion here since it seems like a good idea. To introduce myself, I am PistonMiner, the second person who works on those tools with danielmm8888, who always seems to gets credited alone which is probably due to him doing all the interaction with the public as I am more sorta quiet, so kinda my fault. We basically just wanted to make a tool to extract models and textures etc. cause we needed them for a different project. I see people have already discovered our GitHub repository ([https://github.com/PistonMiner/fb3-tools](https://github.com/PistonMiner/fb3-tools)) and used the tools, which is nice. That repository was made to accomodate tools for Frostbite 3, not just ours, but everyones so we can have a central point of collection. To inform on our "mysterious" tool, it won't get on that Github repository until it is ready, right now it is not (yet). We have finished models for the most part (although daniel told me a bit ago that there's a model type not working, so that's something I need to have a look at). We have full texture export & preview except for a couple of formats like depth buffers for level lights which aren't of any interest to us.

-- PistonMiner
## Post #24
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2015-07-25T19:19:47+00:00
- Post Title: Re: StarWars Battlefront Closed Beta

> Reply from PistonMiner
>
> I will just join the discussion here since it seems like a good idea. To introduce myself, I am PistonMiner, the second person who works on those tools with danielmm8888, who always seems to gets credited alone which is probably due to him doing all the interaction with the public as I am more sorta quiet, so kinda my fault. We basically just wanted to make a tool to extract models and textures etc. cause we needed them for a different project. I see people have already discovered our GitHub repository (https://github.com/PistonMiner/fb3-tools) and used the tools, which is nice. That repository was made to accomodate tools for Frostbite 3, not just ours, but everyones so we can have a central point of collection. To inform on our "mysterious" tool, it won't get on that Github repository until it is ready, right now it is not (yet). We have finished models for the most part (although daniel told me a bit ago that there's a model type not working, so that's something I need to have a look at). We have full texture export & preview except for a couple of formats like depth buffers for level lights which aren't of any interest to us.

-- PistonMiner

thks for all your work, i wait to see all your models .. but take your time ...
## Post #25
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-07-25T19:49:30+00:00
- Post Title: Re: StarWars Battlefront Closed Beta

> Reply from durandal217
>
> 114, 160, 308 are three example I can give you.

New version that will convert audios with extra info, and also it will extract ALL audios from chunks.

I've gathered some statistics, and it seems the sounds with extra audio are ambient mostly.

Multi-audio chunks are mostly voices with many variations, for example there are about 50 variants of "grenade!" contained in one audio chunk. But, there are some weapon sounds too. So you need to check all those again, sorry
## Post #26
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-07-25T19:53:45+00:00
- Post Title: Re: StarWars Battlefront Closed Beta

> Reply from PistonMiner
>
> That repository was made to accomodate tools for Frostbite 3, not just ours, but everyones

So were you able to use old FB3 tools made by frank? Or you're making it all from scratch? Did you handle compressed chunks? Proper filenames?
## Post #27
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2015-07-26T14:39:04+00:00
- Post Title: Re: StarWars Battlefront Closed Beta

> Reply from daemon1
>
> durandal217 wrote:114, 160, 308 are three example I can give you.

New version that will convert audios with extra info, and also it will extract ALL audios from chunks.

I've gathered some statistics, and it seems the sounds with extra audio are ambient mostly.

Multi-audio chunks are mostly voices with many variations, for example there are about 50 variants of "grenade!" contained in one audio chunk. But, there are some weapon sounds too. So you need to check all those again, sorry

So far so good ill report back later if anything but one thing I've noticed is some chunks cause the program to crash for example 1122 gives me 

```
at System.IO.BinaryReader.ReadBytes<>
at Xas_decode.Program.Main<string[]args>
```


The only thing I figure is either these are pcm files causing the program to crash or that there is no audio in these chunks, but I don't know.
## Post #28
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-07-26T15:07:43+00:00
- Post Title: Re: StarWars Battlefront Closed Beta

> Reply from durandal217
>
> So far so good ill report back later if anything but one thing I've noticed is some chunks cause the program to crash for example 1122

This is compressed model or script, not a sound chunk. So my "frostbyte_chunk" gives you "compressed chunks not supported" and outputs 0-length file. I could do something about it, but for now please sort all chunks by size and delete 0-sized files.
## Post #29
- Username: danielmm8888
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jul 20, 2015 6:53 am
- Post datetime: 2015-07-27T01:29:44+00:00
- Post Title: Re: StarWars Battlefront Closed Beta

> Reply from daemon1
>
> PistonMiner wrote:That repository was made to accomodate tools for Frostbite 3, not just ours, but everyones

So were you able to use old FB3 tools made by frank? Or you're making it all from scratch? Did you handle compressed chunks? Proper filenames?

Err, no. We did not use any tools made by frank. What PistonMiner meant to say was that that repository was made to accommodate various FB3 tools. As in, anybody who would like to contribute could do so.

Oh, and to answer your question: Yes, we do have proper filenames.
## Post #30
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-07-28T08:09:03+00:00
- Post Title: Re: StarWars Battlefront Closed Beta

> Reply from danielmm8888
>
> daemon1 wrote:PistonMiner wrote:That repository was made to accomodate tools for Frostbite 3, not just ours, but everyones

So were you able to use old FB3 tools made by frank? Or you're making it all from scratch? Did you handle compressed chunks? Proper filenames?

Err, no. We did not use any tools made by frank. What PistonMiner meant to say was that that repository was made to accommodate various FB3 tools. As in, anybody who would like to contribute could do so.

Oh, and to answer your question: Yes, we do have proper filenames.

Can you please share your research, i mean struct for frostbite 3 engine. Im always trying to get this from ppl who working on such a tools for possible future outcome. Please share with us complete research if you can. Im person who trying to get all together this most difficult formats and keep them know. Same as like MDA with Assassins Creed..

Thx
## Post #31
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-07-28T08:20:32+00:00
- Post Title: Re: StarWars Battlefront Closed Beta

> Reply from michalss
>
> Can you please share your research, i mean struct for frostbite 3 engine. Im always trying to get this from ppl who working on such a tools for possible future outcome.

I hope you already have all scripts done by Frank before he disappeared and his forum went offline. I've also saved his description of their custom compression:

[http://pastebin.com/MacNF5Kc](http://pastebin.com/MacNF5Kc)

Also you may know about DAI tools research, they probably know the whole FB3 structure too.
## Post #32
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2015-07-29T17:02:23+00:00
- Post Title: Re: StarWars Battlefront Closed Beta

I'm having one small problem, when I import a PCM file into audacity i'm always getting clicking sounds. Is there a way to convert this audio without getting the clipping?
## Post #33
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-07-29T17:41:49+00:00
- Post Title: Re: StarWars Battlefront Closed Beta

> Reply from durandal217
>
> I'm having one small problem, when I import a PCM file into audacity i'm always getting clicking sounds. Is there a way to convert this audio without getting the clipping?

> Reply from daemon1
>
> ok 308 is PCM. Use Frostbyte_chunk on it, then open in sound editor as RAW PCM 16 bit stereo 48000 hz.
## Post #34
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2015-07-29T22:00:32+00:00
- Post Title: Re: StarWars Battlefront Closed Beta

I already used Frostbyte_chunk on it. when I import the .Chunk file i'm getting clipping noises.

here is an example [http://www.mediafire.com/listen/zupfrbnqjlaot6p/167.ogg](http://www.mediafire.com/listen/zupfrbnqjlaot6p/167.ogg)
## Post #35
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-07-31T04:31:44+00:00
- Post Title: Re: StarWars Battlefront Closed Beta

oh. its split into small chunks inside. need to make another tool
## Post #36
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-08-02T14:41:08+00:00
- Post Title: Re: StarWars Battlefront Closed Beta

New version that supports those PCM lasers. It's a little wrong, because the tool is called "XAS decoder", but it has really similar block format. Let me know if it will not work with something.
[xas_decode.rar](https://xentaxbackup.github.io/file/9477_xas_decode.rar)
## Post #37
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2015-10-09T03:46:42+00:00
- Post Title: Re: StarWars Battlefront Closed Beta

I'm sorry to bump but has anyone had any luck extracting the files from the beta? 

all the scripts I've tried don't work even PistonMiner's it just keeps telling me:

```
File cas_749956498.cas not found, skipping.
```


but nothing extracts. Franks frostbyte scripts gives me:

```
Patched cat not found.
layout.toc
characters.toc
C:\Users\DURANDAL\Desktop\dumper/bundles/ebx/gameplay/characters/heros/lukeskywalkerphysics.ebx

Traceback (most recent call last):
  File "C:\Users\DURANDAL\Desktop\dumper\bf4dump\bf4dumper.py", line 258, in <module>
    if "tocRoot2" in locals(): dumpRoot(tocRoot2)
  File "C:\Users\DURANDAL\Desktop\dumper\bf4dump\bf4dumper.py", line 248, in dumpRoot
    dump(fname,targetDirectory)
  File "C:\Users\DURANDAL\Desktop\dumper\bf4dump\bf4dumper.py", line 171, in dump
    writePayload(entry, targetPath, sourcePath)
  File "C:\Users\DURANDAL\Desktop\dumper\bf4dump\bf4dumper.py", line 212, in casPayload
    catEntry=cat[bundleEntry.sha1]
KeyError: 'h\x9c\xbf\x1d\t#\x04\x08\x14\xb0C\xb3\r\xb1\xc3t\xca5\x8d\x88'
>>> 
```


I never expected it to work but it extracted two files before giving me that.

Anybody have anything?
## Post #38
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2015-10-09T04:10:33+00:00
- Post Title: Re: StarWars Battlefront Closed Beta

> Reply from durandal217
>
> I'm sorry to bump but has anyone had any luck extracting the files from the beta? 

all the scripts I've tried don't work even PistonMiner's it just keeps telling me:
Code: Select allExtracting entry #32289 (Offset = 0x42a54bda / Size = 0x4ba69f16)
File cas_749956498.cas not found, skipping.

but nothing extracts. Franks frostbyte scripts gives me:
Code: Select allUnpatched cat not found.
Patched cat not found.
layout.toc
characters.toc
C:\Users\DURANDAL\Desktop\dumper/bundles/ebx/gameplay/characters/heros/lukeskywalkerphysics.ebx

Traceback (most recent call last):
  File "C:\Users\DURANDAL\Desktop\dumper\bf4dump\bf4dumper.py", line 258, in <module>
    if "tocRoot2" in locals(): dumpRoot(tocRoot2)
  File "C:\Users\DURANDAL\Desktop\dumper\bf4dump\bf4dumper.py", line 248, in dumpRoot
    dump(fname,targetDirectory)
  File "C:\Users\DURANDAL\Desktop\dumper\bf4dump\bf4dumper.py", line 171, in dump
    writePayload(entry, targetPath, sourcePath)
  File "C:\Users\DURANDAL\Desktop\dumper\bf4dump\bf4dumper.py", line 212, in casPayload
    catEntry=cat[bundleEntry.sha1]
KeyError: 'h\x9c\xbf\x1d\t#\x04\x08\x14\xb0C\xb3\r\xb1\xc3t\xca5\x8d\x88'
>>> 

I never expected it to work but it extracted two files before giving me that.

Anybody have anything?

Yeah i figured out the problem with this, it's cause the beta doesn't contain a UPDATE folder and without it neither the python script or the extraction tool i have works with the game, someone would have to edit the python script to not look for the update folder for it to work.
## Post #39
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2015-10-09T04:14:27+00:00
- Post Title: Re: StarWars Battlefront Closed Beta

send me Franks frostbyte scripts or give link please
## Post #40
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2015-10-09T04:26:48+00:00
- Post Title: Re: StarWars Battlefront Closed Beta

> Reply from erik945
>
> send me Franks frostbyte scripts or give link please

Here is Franks script.( this one worked with the closed alpha but it doesn't work for the beta cause it's missing a update folder)
[https://dl.dropboxusercontent.com/u/881 ... cripts.rar](https://dl.dropboxusercontent.com/u/88155050/Dumper%20Scripts/BF4_Python_Scripts.rar)
## Post #41
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2015-10-09T04:38:34+00:00
- Post Title: Re: StarWars Battlefront Closed Beta

No, the problem is not in directory of "update".
This script skiped unfinded path:

```
Patched cat not found.
layout.toc
characters.toc
C:\Users\DURANDAL\Desktop\dumper/bundles/ebx/gameplay/characters/heros/lukeskywalkerphysics.ebx

```


unpack started (last string), but crush on decrypting/extracting chunks

```
  File "C:\Users\DURANDAL\Desktop\dumper\bf4dump\bf4dumper.py", line 258, in <module>
    if "tocRoot2" in locals(): dumpRoot(tocRoot2)
  File "C:\Users\DURANDAL\Desktop\dumper\bf4dump\bf4dumper.py", line 248, in dumpRoot
    dump(fname,targetDirectory)
  File "C:\Users\DURANDAL\Desktop\dumper\bf4dump\bf4dumper.py", line 171, in dump
    writePayload(entry, targetPath, sourcePath)
  File "C:\Users\DURANDAL\Desktop\dumper\bf4dump\bf4dumper.py", line 212, in casPayload
    catEntry=cat[bundleEntry.sha1]
KeyError: 'h\x9c\xbf\x1d\t#\x04\x08\x14\xb0C\xb3\r\xb1\xc3t\xca5\x8d\x88'

```


I don't know how patch it.
## Post #42
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2015-10-09T04:44:21+00:00
- Post Title: Re: StarWars Battlefront Closed Beta

> Reply from erik945
>
> No, the problem is not in directory of "update".
This script skiped unfinded path:
Code: Select allUnpatched cat not found.
Patched cat not found.
layout.toc
characters.toc
C:\Users\DURANDAL\Desktop\dumper/bundles/ebx/gameplay/characters/heros/lukeskywalkerphysics.ebx


unpack started (last string), but crush on decrypting/extracting chunks
Code: Select allTraceback (most recent call last):
  File "C:\Users\DURANDAL\Desktop\dumper\bf4dump\bf4dumper.py", line 258, in <module>
    if "tocRoot2" in locals(): dumpRoot(tocRoot2)
  File "C:\Users\DURANDAL\Desktop\dumper\bf4dump\bf4dumper.py", line 248, in dumpRoot
    dump(fname,targetDirectory)
  File "C:\Users\DURANDAL\Desktop\dumper\bf4dump\bf4dumper.py", line 171, in dump
    writePayload(entry, targetPath, sourcePath)
  File "C:\Users\DURANDAL\Desktop\dumper\bf4dump\bf4dumper.py", line 212, in casPayload
    catEntry=cat[bundleEntry.sha1]
KeyError: 'h\x9c\xbf\x1d\t#\x04\x08\x14\xb0C\xb3\r\xb1\xc3t\xca5\x8d\x88'


I don't know how patch it.

If you look it is looking for the update folder where the patched .Cat file is (Patched cat not found.) and i even asked the guys that made one of the python scripts Danielmm8888 and PistonMiner an they both told me it's cause the python script and their tool is looking for the patched .Cat file in the update folder and it can't find it. They also told me both methods should work when the full game comes out as well.
## Post #43
- Username: PistonMiner
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jul 25, 2015 7:21 pm
- Post datetime: 2015-10-10T12:44:01+00:00
- Post Title: Re: StarWars Battlefront Closed Beta

> Reply from durandal217
>
> I'm sorry to bump but has anyone had any luck extracting the files from the beta? 

all the scripts I've tried don't work even PistonMiner's it just keeps telling me:
Code: Select allExtracting entry #32289 (Offset = 0x42a54bda / Size = 0x4ba69f16)
File cas_749956498.cas not found, skipping.

but nothing extracts.

If you are using it correctly, thats definitely not to do with the update folder. They may have changed their offsets inside their file structure since when we made that script, one would have to re-adapt the tool.
## Post #44
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2015-10-11T17:04:14+00:00
- Post Title: Re: StarWars Battlefront Closed Beta

this is how i had it. 

```
# Revision 0.1
import sys
import os
import struct

# Get a handle to the CAT file and get its size
catFileName = "C:\Users\DURANDAL\Desktop\STAR WARS Battlefront Beta\Data\cas.cat"
catFile = open(catFileName, 'rb') 
catFileSize = os.path.getsize(catFileName)

# Skip the signature
catFile.seek(0x10)

# Create the folder where we'll be dumping the content into (if necessary)
if not os.path.exists("dump/"):
    os.makedirs("dump/")
```


and I had it in the same folder as the cat file.
## Post #45
- Username: PistonMiner
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jul 25, 2015 7:21 pm
- Post datetime: 2015-10-13T15:11:50+00:00
- Post Title: Re: StarWars Battlefront Closed Beta

Right, well thats not exactly how I intended it to be used, you were supposed to supply the data using command line arguments, but that should be fine. They probably changed up their file structure then.

EDIT: Yep, just checked, they most likely changed it.
## Post #46
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2015-11-17T16:28:51+00:00
- Post Title: Re: StarWars Battlefront Closed Beta

I've tried everything on the retail files and can't get anything to extract with franks script this is what I get. 

```
  File "C:\Users\DURANDAL\Desktop\Recent Programs\fb3tools\bf4dump\bf4dumper.py", line 258, in <module>
    if "tocRoot2" in locals(): dumpRoot(tocRoot2)
  File "C:\Users\DURANDAL\Desktop\Recent Programs\fb3tools\bf4dump\bf4dumper.py", line 248, in dumpRoot
    dump(fname,targetDirectory)
  File "C:\Users\DURANDAL\Desktop\Recent Programs\fb3tools\bf4dump\bf4dumper.py", line 102, in dump
    toc=cas.readToc(tocPath)
  File "C:\Users\DURANDAL\Desktop\Recent Programs\fb3tools\bf4dump\cas.py", line 95, in readToc
    return Entry(unXor(tocPath))
  File "C:\Users\DURANDAL\Desktop\Recent Programs\fb3tools\bf4dump\cas.py", line 37, in __init__
    raise Exception("Entry does not start with \\x82 or (rare) \\x87 byte. Position: "+str(f.tell()))
Exception: Entry does not start with \x82 or (rare) \x87 byte. Position: 1
>>> 
```


with the usual 

```
Patched cat not found.
characters.toc

```
 

anybody have anything that works?
## Post #47
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-11-17T16:45:48+00:00
- Post Title: Re: StarWars Battlefront Closed Beta

> Reply from durandal217
>
> anybody have anything that works?

we don't have the retail files yet
## Post #48
- Username: MattFiler
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Jun 20, 2015 8:47 am
- Post datetime: 2015-11-17T19:22:55+00:00
- Post Title: Re: StarWars Battlefront Closed Beta

Retail is out! Has anyone had a chance to take a look at the files yet?
Each map seems to be in two files, a .sb and .toc file format.
Looking in them with Notepad++ shows a lot of file references in there.
Not even sure if it's worth modding it really, considering there's no way to host private servers.
Modding the GUI might be the only thing worth looking at.
## Post #49
- Username: scribeofthemist
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Nov 18, 2015 4:25 am
- Post datetime: 2015-11-17T20:31:04+00:00
- Post Title: Re: StarWars Battlefront Closed Beta

I don't have anything to offer, but I'd just like to point out that there is a significant amount of new Star Wars music in the retail game, composed by Gordy Haab, veteran of The Old Republic. From what I have heard so far it sounds quite excellent, almost indistinguishable from Williams' style. I came here trying to find a way to extract the music from the .cat files, seems like there is no way to extract everything from this game's files yet, but I hope someone makes it possible eventually. I'd really like to be able to listen to this game's music outside the game and I doubt EA has a soundtrack release planned. 

I post this just to let you all know that there is definitely interest in being able to extract all the audio/music from the retail version.
## Post #50
- Username: MattFiler
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Jun 20, 2015 8:47 am
- Post datetime: 2015-11-17T22:14:32+00:00
- Post Title: Re: StarWars Battlefront Closed Beta

> Reply from scribeofthemist
>
> I don't have anything to offer, but I'd just like to point out that there is a significant amount of new Star Wars music in the retail game, composed by Gordy Haab, veteran of The Old Republic. From what I have heard so far it sounds quite excellent, almost indistinguishable from Williams' style. I came here trying to find a way to extract the music from the .cat files, seems like there is no way to extract everything from this game's files yet, but I hope someone makes it possible eventually. I'd really like to be able to listen to this game's music outside the game and I doubt EA has a soundtrack release planned. 

I post this just to let you all know that there is definitely interest in being able to extract all the audio/music from the retail version.
That's a good point. Exporting the models, textures and sounds would be awesome.
## Post #51
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2015-11-18T21:24:10+00:00
- Post Title: Re: StarWars Battlefront Closed Beta

> Reply from scribeofthemist
>
> I don't have anything to offer, but I'd just like to point out that there is a significant amount of new Star Wars music in the retail game, composed by Gordy Haab, veteran of The Old Republic. From what I have heard so far it sounds quite excellent, almost indistinguishable from Williams' style. I came here trying to find a way to extract the music from the .cat files, seems like there is no way to extract everything from this game's files yet, but I hope someone makes it possible eventually. I'd really like to be able to listen to this game's music outside the game and I doubt EA has a soundtrack release planned. 

I post this just to let you all know that there is definitely interest in being able to extract all the audio/music from the retail version.

If you want music and other audio here you go.

Heroes:[https://mega.nz/#!towjRKqB!rZ5mSHv-B350 ... bkg_yrcsU8](https://mega.nz/#!towjRKqB!rZ5mSHv-B350SrlZKaaMRubWhTh4wEk5Zbkg_yrcsU8)

Vehicles: [https://mega.nz/#!woBzVaSL!KUuCCVF-_T7E ... LK9N2pBiX0](https://mega.nz/#!woBzVaSL!KUuCCVF-_T7EOXqPHuqKX7VaNNgWWmPNeLK9N2pBiX0)

Weapons: [https://mega.nz/#!Y0510aaC!hXWqbPao3SC0 ... oVht8erheM](https://mega.nz/#!Y0510aaC!hXWqbPao3SC0QR3aC9XCEUhQC3gvG3dHuoVht8erheM)

Aliens: [https://mega.nz/#!Yo4llTrS!JJb6MLwxWAzx ... fnR8FtHCt0](https://mega.nz/#!Yo4llTrS!JJb6MLwxWAzxVuN7Xt9WsMFqbpM6yASJsfnR8FtHCt0)

Music: [https://mega.nz/#!x1ZUXBoB!kx56OubmgNMp ... tcaU4Usg20](https://mega.nz/#!x1ZUXBoB!kx56OubmgNMpvbUg2m-QiGBT9Yj4dV2WHtcaU4Usg20)
## Post #52
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2015-11-18T22:56:28+00:00
- Post Title: Re: StarWars Battlefront Closed Beta

All of that is from the beta. There's a lot more in the retail game.
## Post #53
- Username: MattFiler
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Jun 20, 2015 8:47 am
- Post datetime: 2015-11-19T11:39:03+00:00
- Post Title: Re: StarWars Battlefront Closed Beta

Any potential modders out there may want to check out the "initfs_Win32" file.

There are a load of config options in there including mentions of creating servers and stuff.
## Post #54
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2015-11-25T06:27:12+00:00
- Post Title: Re: StarWars Battlefront Closed Beta

any update for the retail version ?
## Post #55
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-11-25T15:42:29+00:00
- Post Title: Re: StarWars Battlefront Closed Beta

This can only be possible if someone provide the files from the retail.
## Post #56
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2015-11-26T08:10:44+00:00
- Post Title: Re: StarWars Battlefront Closed Beta

> Reply from daemon1
>
> This can only be possible if someone provide the files from the retail.

If you want i can send you everything you need just pm me with what you need and i'll get it to you.
## Post #57
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-11-27T16:42:36+00:00
- Post Title: Re: StarWars Battlefront Closed Beta

Here's the very first and quick solution [viewtopic.php?f=10&t=13584](http://forum.xentax.com/viewtopic.php?f=10&t=13584)

Just use swbf_cas.exe on any .cas file and it will unpack it to 1000's of chunks without names. If some of them will be audio chunks, they'll have .EXA extension. Then you can decode those with my decoder (latest version included).

At least it works with all .cas files I've been given.

Later I plan to check the new sb/toc format to have proper filenames.
