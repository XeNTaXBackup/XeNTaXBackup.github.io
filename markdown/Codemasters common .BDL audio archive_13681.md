## Post #1
- Username: Ferrari formula 1
- Rank: advanced
- Number of posts: 72
- Joined date: Mon Aug 11, 2014 6:42 pm
- Post datetime: 2015-12-15T11:43:00+00:00
- Post Title: Codemasters common .BDL audio archive

Hello everyone!

I've been recently looking at the codemasters racing games and found that all of them (DIRT,GRID series) use the same archive type for storing sound data(Like engine revs)

After a long search I couldn't find any extraction tools for this format, so I thought that maybe someone will be able to take a look at them?  

I think they should contain a bunch of sounds in one file like they usually do

Here are the examples,I hope someone can figure them out!  
[http://www.mediafire.com/download/7ctwb ... _DIRT3.rar](http://www.mediafire.com/download/7ctwbbeqkf372gr/BDL_EX_DIRT3.rar)
## Post #2
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-12-17T04:33:34+00:00
- Post Title: Codemasters common .BDL audio archive

Latest version. Supports both Codemasters ADPCM & m-law in all files I had. Tested with Dirt 2, Dirt 3, F1 2014.
[codemasters.rar](https://xentaxbackup.github.io/file/10222_codemasters.rar)
## Post #3
- Username: Ferrari formula 1
- Rank: advanced
- Number of posts: 72
- Joined date: Mon Aug 11, 2014 6:42 pm
- Post datetime: 2015-12-19T12:01:42+00:00
- Post Title: Codemasters common .BDL audio archive

> Reply from daemon1
>
> It must be possible. Some kind of ADPCM. I see 19-byte chunks with 3 byte indexes here. Do you know what type of adpcm their engine use? What do they look like?

I don't know...
Since It's an archive with audio files,maybe it's a bit simmiliar to other audio files in the game?

There's a "Ego Audio Tool" which works with .WIM, .WIP and .DIC files from various codemasters games.
They contain music and some sound FX,but not the engine sounds and I can't even get it to work,since it does not have proper function for manual file opening and autodedects the game(I guess,only steam editions can be detected)  

(Link for a tool)

```
http://www.moddb.com/games/dirt-3/downloads/ego-audio-tool
```


And there was some research with .WIN files
[http://zenhax.com/viewtopic.php?t=795](http://zenhax.com/viewtopic.php?t=795)

However, .BDL files are still a mystery
## Post #4
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-12-19T12:46:04+00:00
- Post Title: Codemasters common .BDL audio archive

Well, mu-law is interesting, but these DBL files doesn't look like mu-law to me. As I said before, more like ADPCM. What would you like to be decoded first: this or NFS?
## Post #5
- Username: Ferrari formula 1
- Rank: advanced
- Number of posts: 72
- Joined date: Mon Aug 11, 2014 6:42 pm
- Post datetime: 2015-12-19T13:35:53+00:00
- Post Title: Codemasters common .BDL audio archive

> Reply from daemon1
>
> Well, mu-law is interesting, but these DBL files doesn't look like mu-law to me. As I said before, more like ADPCM. What would you like to be decoded first: this or NFS?

Well,I think that this archive type is more important because it's used by a lot of games from Codemasters and should be common...
So yeah,I'd love to have an ability to decode this .BDL sound format first
## Post #6
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-12-20T07:22:43+00:00
- Post Title: Codemasters common .BDL audio archive

ok, thats what I was able to decode from your files

[http://www61.zippyshare.com/v/g3oOSSQZ/file.html](http://www61.zippyshare.com/v/g3oOSSQZ/file.html)

Please note that this is only the first attempt, assuming it is 44100Hz and decoding is not precise yet. This is really a sort of XA ADPCM designed by codemasters specifically to encode engine sounds. I'm saying that because of the special parameter tables they used in the algorythm.
## Post #7
- Username: Ferrari formula 1
- Rank: advanced
- Number of posts: 72
- Joined date: Mon Aug 11, 2014 6:42 pm
- Post datetime: 2015-12-20T09:42:19+00:00
- Post Title: Codemasters common .BDL audio archive

> Reply from daemon1
>
> ok, thats what I was able to decode from your files

http://www61.zippyshare.com/v/g3oOSSQZ/file.html

Please note that this is only the first attempt, assuming it is 44100Hz and decoding is not precise yet. This is really a sort of XA ADPCM designed by codemasters specifically to encode engine sounds. I'm saying that because of the special parameter tables they used in the algorythm.

That sounded awesome!   

Judjing by the game's structure,every car has more than one file for sounds.


I suppose that one of them should include gearbox/etc sounds,another one should be including sounds you just decoded and the last one,well,maybe looped samples from different rpm's? (That would make sence,I don't understand how some games can make car sound like a car by using only 2 sounds  )

I can send more samples If you need. Oh,and seems like the game is using different samples for AI cars and splitscreen mode
## Post #8
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-12-20T19:03:04+00:00
- Post Title: Codemasters common .BDL audio archive

Yes I need more samples. Each of the 3 files you sent contain the same type of engine sounds. 4 in each file. And considering their length, all the files on this screenshot are the same.

p.s. there's no need for "loops at different RPMs". These accel/decel files can be used for this. You can hear the idle loop on one side of it, the overrev one on the other. Everything in the middle in used on different RPMs
## Post #9
- Username: Ferrari formula 1
- Rank: advanced
- Number of posts: 72
- Joined date: Mon Aug 11, 2014 6:42 pm
- Post datetime: 2015-12-20T20:16:18+00:00
- Post Title: Codemasters common .BDL audio archive

> Reply from daemon1
>
> Yes I need more samples. Each of the 3 files you sent contain the same type of engine sounds. 4 in each file. And considering their length, all the files on this screenshot are the same.

p.s. there's no need for "loops at different RPMs". These accel/decel files can be used for this. You can hear the idle loop on one side of it, the overrev one on the other. Everything in the middle in used on different RPMs

Here's a load of different example files  
[http://www.mediafire.com/download/4d179 ... AMPLES.rar](http://www.mediafire.com/download/4d1799agbxcdmt9/DIRT3_BDL_SAMPLES.rar)

Well,I never really succeded in looping theese but I will try again
## Post #10
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-12-20T20:48:51+00:00
- Post Title: Codemasters common .BDL audio archive

> Reply from Ferrari formula 1
>
> Well,I never really succeded in looping theese but I will try again

What do you plan to do with these sounds?

In addition to 4 audio samples, these BDL files contain a lot of tables. Such as 1024-elements table of RPMs, 8 to 14 tables with values about 0.9 - 1.4, and some more. I think they are using some advanced techniques to mix small parts of these samples to loop them into the engine sound needed. At least something similar was going on in NFS.

Now the samples you sent now are all the same type: 4 engine sounds each, but those inside AI & splitscreen folders are simply encoded with mu-law. While All in the root are in this special ADPCM codec. Let's see what can I do with these now.
## Post #11
- Username: Ferrari formula 1
- Rank: advanced
- Number of posts: 72
- Joined date: Mon Aug 11, 2014 6:42 pm
- Post datetime: 2015-12-21T15:45:44+00:00
- Post Title: Codemasters common .BDL audio archive

> Reply from daemon1
>
> Ferrari formula 1 wrote:Well,I never really succeded in looping theese but I will try again 

What do you plan to do with these sounds?

In addition to 4 audio samples, these BDL files contain a lot of tables. Such as 1024-elements table of RPMs, 8 to 14 tables with values about 0.9 - 1.4, and some more. I think they are using some advanced techniques to mix small parts of these samples to loop them into the engine sound needed. At least something similar was going on in NFS.

Now the samples you sent now are all the same type: 4 engine sounds each, but those inside AI & splitscreen folders are simply encoded with mu-law. While All in the root are in this special ADPCM codec. Let's see what can I do with these now.

I want to use them to make a couple of mods for NFS/GTA and just for private use(audiophile  )

Pretty hard and impressive technology in my opinion
I also can hear in the game sounds of engine startups,exhaust and others,are they inside or maybe I'm missing something?
## Post #12
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-12-21T15:49:19+00:00
- Post Title: Codemasters common .BDL audio archive

> Reply from Ferrari formula 1
>
> I also can hear in the game sounds of engine startups,exhaust and others,are they inside?

No, the only thing inside of these files you sent me is of the type I already uploaded. The engine sound samples, similar to GIN files of NFS.
## Post #13
- Username: Ferrari formula 1
- Rank: advanced
- Number of posts: 72
- Joined date: Mon Aug 11, 2014 6:42 pm
- Post datetime: 2015-12-21T16:30:26+00:00
- Post Title: Codemasters common .BDL audio archive

> Reply from daemon1
>
> Ferrari formula 1 wrote:I also can hear in the game sounds of engine startups,exhaust and others,are they inside?

No, the only thing inside of these files you sent me is of the type I already uploaded. The engine sound samples, similar to GIN files of NFS.

Well,as I search trough the other files,I found theese,here are the samples

Other files found
Maybe you could make a convertor for both .BDL and .WIP files?
I know that This programm I mentioned should work,but it does not,and can't even autodetect the game or give me an ability to open files manually  



[http://www.mediafire.com/download/8lp4n ... dd_mec.rar](http://www.mediafire.com/download/8lp4nvcjx5zudp3/dd_mec.rar)
## Post #14
- Username: Ferrari formula 1
- Rank: advanced
- Number of posts: 72
- Joined date: Mon Aug 11, 2014 6:42 pm
- Post datetime: 2015-12-21T17:04:18+00:00
- Post Title: Codemasters common .BDL audio archive

Oh,I found a way to make this programm work properly  

Well then,theese .BDL file are the only that need to be converted...
## Post #15
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-12-21T17:04:57+00:00
- Post Title: Codemasters common .BDL audio archive

Well, these WIP files are plain PCM. You don't even need any program to open them. Just open in any sound editor as RAW 16-bit mono files. But if you really need it, use this one: [http://www.moddb.com/games/dirt-3/downl ... -extractor](http://www.moddb.com/games/dirt-3/downloads/eenot-audio-extractor) (use the link to github)

All of engine start/stop, gears, horns, you will find in WIP files.
## Post #16
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-12-22T20:28:30+00:00
- Post Title: Re: Codemasters common .BDL audio archive

here you go

BDL files have a LOT of properties unknown to me, but this converts all of the files you gave me, except those with mu-law codec (from AI folder). I can do these too.
## Post #17
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-12-26T07:32:46+00:00
- Post Title: Re: Codemasters common .BDL audio archive

New version. Moved to the first page for easier access. Now supports m-law too and all BDL versions that I have.

Let's call this new type of ADPCM, like Codemasters ADPCM.
## Post #18
- Username: Tiger33
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Feb 02, 2016 1:18 am
- Post datetime: 2016-02-01T17:31:57+00:00
- Post Title: Re: Codemasters common .BDL audio archive

> Reply from daemon1
>
> New version. Moved to the first page for easier access. Now supports m-law too and all BDL versions that I have.

Let's call this new type of ADPCM, like Codemasters ADPCM.

Great Job !

Now it's possible to hear samples in BDL files so we can create our own sounds if you could make a tool which rebuilds the BDL file with other samples.
## Post #19
- Username: hatchprime
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Dec 19, 2016 1:21 pm
- Post datetime: 2017-11-28T08:10:14+00:00
- Post Title: Re: Codemasters common .BDL audio archive

The program seems to work pretty well, but here's a couple things I found reviewing files for Dirt 2 and Dirt 3.

The samplerate should be 24,000 not 48,000

the 1024 element table looks like float32 RPM values.

the next table (about 200-400 elements, 8 bytes each), the final 4 bytes in each entry are a float32 number of seconds in the wav file used for looping. When you sample the wav file at these times the value is nearly the same (though not zero). The wav file should loop and stitch seamlessly if you splice together parts at these points.

After the audio data are a handful of 92-byte "Unnamed Loop" entries that index into the 200-400 element table. I guess these fields are start/end indexes but I'm not sure how they're used.
## Post #20
- Username: headrushmayor
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Nov 29, 2010 12:03 pm
- Post datetime: 2018-06-24T06:35:10+00:00
- Post Title: Re: Codemasters common .BDL audio archive

hi all i workout how get audio out the bdl files you have use "Ego Audio Tool" but have chance the .bdl to .raw then open file in the Ego Audio Tool program u only need do 1 file as it will unpack all files the sound there but mix up u hear a bit as well do the soundbanks files if chance the bnk to raw then unpack them as well, the Ego Audio Tool need bit more work to it make sounds better but u hear them, i don't how get wav audio play in game have keep looking in text files see enable the wav files work as want do engine sounds and turbo louder. so using the codemasters.exe it make wav files do game pickup the wav file play them in game or do need edit text enable them work.
## Post #21
- Username: dongvanhung
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Sep 29, 2014 2:37 pm
- Post datetime: 2019-07-05T15:11:03+00:00
- Post Title: Re: Codemasters common .BDL audio archive

> Reply from daemon1 ↑Mon Dec 21, 2015 4:48 am at Mon Dec 21, 2015 4:48 am
>
> 
Ferrari formula 1 wrote:Well,I never really succeded in looping theese but I will try again 

What do you plan to do with these sounds?

In addition to 4 audio samples, these BDL files contain a lot of tables. Such as 1024-elements table of RPMs, 8 to 14 tables with values about 0.9 - 1.4, and some more. I think they are using some advanced techniques to mix small parts of these samples to loop them into the engine sound needed. At least something similar was going on in NFS.

Now the samples you sent now are all the same type: 4 engine sounds each, but those inside AI & splitscreen folders are simply encoded with mu-law. While All in the root are in this special ADPCM codec. Let's see what can I do with these now.

Hi @daemon1,
How i can read 1024-elements table of RPMs as you said, because .bdl file are encoded, how i can decode and view the value of RPM table ?
Thanks
## Post #22
- Username: CobraGamer
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Apr 16, 2016 2:30 pm
- Post datetime: 2021-09-26T00:00:49+00:00
- Post Title: Re: Codemasters common .BDL audio archive

Could you take a look at these BDL files? One's from Dirt Rally 2.0, the other one is from Grid 2019.
They are both version 72 instead of 71 and use a "codec 2" which your tool doesn't seem to support.

[https://www.mediafire.com/file/f8xezx48 ... 01.7z/file](https://www.mediafire.com/file/f8xezx48bkoif3q/ego_bnk-samples_01.7z/file)
## Post #23
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2021-09-26T06:38:13+00:00
- Post Title: Re: Codemasters common .BDL audio archive

> Reply from CobraGamer ↑Sun Sep 26, 2021 8:00 am at Sun Sep 26, 2021 8:00 am
>
> 
They are both version 72 instead of 71 and use a "codec 2" which your tool doesn't seem to support.
as i remember, "codec 2" was plain uncompressed audio. So i didnt bother to support them, cause you can just open them with any audio editor.
## Post #24
- Username: CobraGamer
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Apr 16, 2016 2:30 pm
- Post datetime: 2021-09-26T14:34:17+00:00
- Post Title: Re: Codemasters common .BDL audio archive

Interesting. Could you give me a bit more info about the BDL structure so that I can do that?

Much appreciated!
## Post #25
- Username: regsfdgf
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jun 28, 2023 8:47 pm
- Post datetime: 2023-06-28T13:32:34+00:00
- Post Title: Re: Codemasters common .BDL audio archive

> Reply from daemon1 ↑Sun Sep 26, 2021 2:38 pm at Sun Sep 26, 2021 2:38 pm
>
> 
CobraGamer wrote: ↑Sun Sep 26, 2021 8:00 am
They are both version 72 instead of 71 and use a "codec 2" which your tool doesn't seem to support.

as i remember, "codec 2" was plain uncompressed audio. So i didnt bother to support them, cause you can just open them with any audio editor.
Which editors do you know that can open these?
## Post #26
- Username: regsfdgf
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jun 28, 2023 8:47 pm
- Post datetime: 2023-06-28T14:36:59+00:00
- Post Title: Re: Codemasters common .BDL audio archive

Found an ancious sound editor that supports that file and it was a mess when I opened it, same pitch everywhere, leads into earrape, no idea what to do
## Post #27
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2023-06-28T14:42:48+00:00
- Post Title: Re: Codemasters common .BDL audio archive

ALL decent audio editors can open those. All proffessional editors, like Adobe Audition, and all free editors too, like audacity.
