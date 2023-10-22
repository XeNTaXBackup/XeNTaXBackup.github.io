## Post #1
- Username: Puterboy1
- Rank: mega-veteran
- Number of posts: 204
- Joined date: Fri Mar 02, 2018 10:05 am
- Post datetime: 2019-03-07T17:53:57+00:00
- Post Title: Star Wars Episode III (PS2 .ilv files)

I was wondering if anyone would like to take a look at these: [https://drive.google.com/open?id=1e4uDM ... sZXLY98S4N](https://drive.google.com/open?id=1e4uDMgCyHJ6Alrlw8hMDq7sZXLY98S4N)

Maybe you can convert these into a playable format.
## Post #2
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2019-03-09T05:08:11+00:00
- Post Title: Star Wars Episode III (PS2 .ilv files)


## Post #3
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-03-09T07:26:50+00:00
- Post Title: Star Wars Episode III (PS2 .ilv files)

batch file for multi processing ilv to wav. 

```
for %%1 in (*.ilv) do start /wait MFAudio "%%1" /IF32000 /IC2 /II4000 /OTWAVU "%%~n1.wav"
```

you will have to determine if the output plays too slow or fast and adjust "Frequency" accordingly.
## Post #4
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2019-03-09T13:04:24+00:00
- Post Title: Star Wars Episode III (PS2 .ilv files)

good. just for the completeness. the common frequencies are 8000, 11025, 16000, 22050, 24000 (possible?), 32000, 44100 and 48000. since they are headerless, i'd guess those music files are all 32000 + 4000 fixed code format.
## Post #5
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-03-09T17:16:42+00:00
- Post Title: Star Wars Episode III (PS2 .ilv files)

yeah they headerless, info could be in another file or they could be classified by file name prefix, like
mus_* files = 32000
cin_* files = 44100 
bg_* files = 44100
