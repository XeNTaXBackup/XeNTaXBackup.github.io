## Post #1
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2013-06-15T10:25:53+00:00
- Post Title: Extract Binary Domain's Music/Sound (CRI .cpk bgm)

Binary Domain has a sick soundtrack and although some people have ripped it via a capture card from their xbox/ps3 sitting idle in the game as the music plays I wanted the original HQ tracks so I experimented and found a method to get them out.

Tools needed
[*]CRI Packed File Maker
[*]HCA2WAV
[*]SFIV Audio Manager

There are some other tools which also work like the cpk quickbms script but these I found do the job well and have more functionality. 

-GET ALL OF THEM HERE-
[http://cra0kalo.com/public/BinaryDomain ... olpack.zip](http://cra0kalo.com/public/BinaryDomainMusicToolpack.zip)


Step1.

Go to directory 
C:\Program Files (x86)\Steam\steamapps\common\Binary Domain\sound\

or if you have a different version of the game (non-steam china copy) go to the root\sound\ folder

here are the audio streams for the game.

I'm going to be going through on how to extract the music so what we want to look at is 

```
stream.cpk
```


Open up CRI Packed File Maker



Click here and load the stream.cpk, once it has loaded and the listbox populated you will see all the audio streams.

Locate one of the bgm_ files in this tutorial case I'm using 

```
bgm_vs_spider.cpk
```
 
and extract it! 




You will get a .aax file output 

```
bgm_vs_spider_fin_wav.aax
```


Fire up SFIV Audio Manager



Extract the .aax pack to a new folder


Now using HCA2WAV


you can convert it to a wav file.

NOTE SFIV's extractor for binarydomain's ADX files don't work so we use HCA2WAV


```
pause
```


Once it has been converted I use audacity to merge all the files
-start
-loop
-end

and then save it out as song.wav

Thats it, this concept can be applied to the sound files like speech dialogue as well just some of the files need to be converted from AIX2 to ADX using

```
aix2adx.exe
```


Thanks for reading hope this is helpful I guess,
## Post #2
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2018-10-13T12:49:10+00:00
- Post Title: Extract Binary Domain's Music/Sound (CRI .cpk bgm)

Thank's for save my day
