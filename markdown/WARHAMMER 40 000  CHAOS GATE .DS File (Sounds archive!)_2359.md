## Post #1
- Username: Yarost
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Jan 09, 2007 6:57 am
- Post datetime: 2007-01-08T23:39:26+00:00
- Post Title: WARHAMMER 40 000 : CHAOS GATE *.DS File (Sounds archive!)

Hi,
I'd like to extract the sound files from this old game from SSI : Chaos Gate,which seem to be stored in what seems to be an archive named wh40.ds in the Sounds folder. I'm 100% sure it contains *.wav files because :
-In the game's *.dat files, there are mention of *.wav files 
-When I open the file with a hex editor, I can see plenty of files named xxxx.wav
So far I've been unable to extract any of them with many of the rippers/extractors I've tried   
I hope you guys can help me !
Here is a link of the demo of this game : 

[http://www.fileplanet.com/11574/10000/f ... Chaos-Gate](http://www.fileplanet.com/11574/10000/fileinfo/Warhammer-40,000:-Chaos-Gate)
## Post #2
- Username: Yarost
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Jan 09, 2007 6:57 am
- Post datetime: 2007-01-10T17:41:16+00:00
- Post Title: WARHAMMER 40 000 : CHAOS GATE *.DS File (Sounds archive!)

Hey, no one wants to look at my case?
Surely it can't be that hard since it's from an old game?(Or maybe I'm wrong? Sorry I don't know much about ripping stuff)
There is a *.ds file provided in the demo so you can check it out...
## Post #3
- Username: ice99
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-01-10T21:46:22+00:00
- Post Title: WARHAMMER 40 000 : CHAOS GATE *.DS File (Sounds archive!)

Allright, I've cocked up a simple extractor for ya. 

Run it in command line:

```
dsex <sourcefile> <destination folder>
```


Worked on the demo .DS file in the sounds dir.
[dsex.zip](https://xentaxbackup.github.io/file/1024_dsex.zip)
## Post #4
- Username: Yarost
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Jan 09, 2007 6:57 am
- Post datetime: 2007-01-10T23:34:40+00:00
- Post Title: WARHAMMER 40 000 : CHAOS GATE *.DS File (Sounds archive!)

Hi,
thanx a lot, it worked wonderfully ! Although I noticed that it doesn't work if the name of folders specified had spaces in them.(I'm pretty new at this stuff) So was it a simple archive file using an easy algorithm?
## Post #5
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-01-11T06:32:56+00:00
- Post Title: WARHAMMER 40 000 : CHAOS GATE *.DS File (Sounds archive!)

Hmm, I can have a look, but I should tell you that some wavs are actually saved in the wav folder in the demo, and NOT stored in the ds file, even though they are listed in the header of the ds file. 

It's not a very difficult algorithm, but it's not straightforward. The "data" part of each wave file is stored one after the other, they stripped the headers of each wave file and stored the "WAVEfmt " headers in a separate table. THen there's the problem of the "fact" header in a wave file. They do not store this info in the table, so I had some default values. The extractor puts everything back together to a single .wav file. 

Just open a .wav file with a hex editor and you can see each field in the wav header. (i.e. "RIFF", "WAVEfmt ", "fact" and "data").
## Post #6
- Username: Yarost
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Jan 09, 2007 6:57 am
- Post datetime: 2007-01-11T18:06:37+00:00
- Post Title: WARHAMMER 40 000 : CHAOS GATE *.DS File (Sounds archive!)

All right,
thanx again for all the help ! You guys rock !
## Post #7
- Username: Edvinke
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Dec 11, 2007 5:02 pm
- Post datetime: 2007-12-11T12:27:58+00:00
- Post Title: WARHAMMER 40 000 : CHAOS GATE *.DS File (Sounds archive!)

hi folks,

im new here, can you help me to find out, how to download dsex.exe?
is there a link somewhere here at all?

cheers,
edvin
## Post #8
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-12-11T12:32:00+00:00
- Post Title: WARHAMMER 40 000 : CHAOS GATE *.DS File (Sounds archive!)

> Reply from Edvinke
>
> hi folks,

im new here, can you help me to find out, how to download dsex.exe?
is there a link somewhere here at all?

cheers,
edvin

Yes, scroll up to my post. You'll find a download link there. It's invisible to unregistered users. Now that you've registered, you can find it there!
## Post #9
- Username: Edvinke
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Dec 11, 2007 5:02 pm
- Post datetime: 2007-12-11T21:09:46+00:00
- Post Title: WARHAMMER 40 000 : CHAOS GATE *.DS File (Sounds archive!)

thanks mate, that was a handy tool!
cheers,
edvin
## Post #10
- Username: ice99
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Sep 29, 2018 1:10 am
- Post datetime: 2018-09-28T20:17:46+00:00
- Post Title: WARHAMMER 40 000 : CHAOS GATE *.DS File (Sounds archive!)

I know this thread was forever ago, but I've been looking for something like this off-and-on (not hard enough obviously) for a long time and only now have found it.

Just want to chime in that it's great to get those sound effects extracted and saved me lots of work trying to figure it out myself!
## Post #11
- Username: MSDemon
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jan 05, 2019 11:56 am
- Post datetime: 2019-01-05T04:29:59+00:00
- Post Title: WARHAMMER 40 000 : CHAOS GATE *.DS File (Sounds archive!)

> Reply from Mr.Mouse
>
> Allright, I've cocked up a simple extractor for ya. 



Run it in command line:


Code: Select alldsex <sourcefile> <destination folder>


Worked on the demo .DS file in the sounds dir.

Hi. I made an account just so I could get the extractor, and it worked! Thank you so much. I was having so much trouble trying to find a way to extract the sounds. I tried a couple of game extraction programs, but none of them seemed to find anything.

How were you able to create an extractor? I tried opening up the .ds file with a hex editor, and I saw what you meant about the file names, but I didn't see any other way of extracting the sound files.
## Post #12
- Username: Tombo
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Aug 20, 2020 5:13 pm
- Post datetime: 2020-08-20T10:36:11+00:00
- Post Title: WARHAMMER 40 000 : CHAOS GATE *.DS File (Sounds archive!)

Thank you Mr. Mouse for the extractor.
Has anyone been able to find the weapon sound files?
In the "Data" folder WeapDef.dat file, references are made to Wav files such as "weapon_select_small.wav" but I can not seem to find these.
## Post #13
- Username: BenjaminK
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Sep 29, 2022 10:22 pm
- Post datetime: 2022-09-29T14:56:27+00:00
- Post Title: WARHAMMER 40 000 : CHAOS GATE *.DS File (Sounds archive!)

Hello there !

Just to maintain the rythm of thanks, once per year or so ^^... I've been working on a huge improvement mod for a year or so and that tool helped quite a bit. Thanks a lot !

> Reply from Tombo ↑Thu Aug 20, 2020 6:36 pm at Thu Aug 20, 2020 6:36 pm
>
> 
Thank you Mr. Mouse for the extractor.
Has anyone been able to find the weapon sound files?
In the "Data" folder WeapDef.dat file, references are made to Wav files such as "weapon_select_small.wav" but I can not seem to find these.

They're in the wh40k.ds file. Every sound file can be found either in that one or in the Wave folder.  

Cheers,
BenjaminK
