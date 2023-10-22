## Post #1
- Username: RageX
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Aug 25, 2015 2:15 am
- Post datetime: 2017-10-03T17:22:49+00:00
- Post Title: FIFA 18 (CAS) Files - ZSTD streams dumping help

Hi, previous FIFA 17 was known to contain ZSTD streams and it was pretty easy to pick them up by their headers. FIFA 18 also seems to have ZSTD streams but at many places the headers are not even complete (modified?) so its hard to pick ZSTD streams and dump them out.

Can anyone please find a solution to dump all the found ZSTD streams in a CAS file of this game ?

Sample file: 
```
https://www.mediafire.com/file/f5ovyzca66532ys/cas_01.cas
```

If you want a smaller sample please tell here.
## Post #2
- Username: Aquacube
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jul 02, 2018 7:27 pm
- Post datetime: 2018-07-05T11:54:58+00:00
- Post Title: FIFA 18 (CAS) Files - ZSTD streams dumping help

we need help really

i try to extract fifa 18 commentary with FB2Dumper script but i found just a chunks folder with unknown files
## Post #3
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-07-06T20:16:42+00:00
- Post Title: FIFA 18 (CAS) Files - ZSTD streams dumping help

> Reply from Aquacube
>
> we need help really

i try to extract fifa 18 commentary with FB2Dumper script but i found just a chunks folder with unknown files
Your using the wrong script for the game, and based on the split hashed names for chunks your using the JnWCrTIIrc (by NoFaTe) script, which is not recommended.
Those chunks need the EBX files in order for a proper decoding/conversion of the audio your looking for with full names and all. Plus chunk files always have hashes instead of real names, that's why the EBXs are needed, they hold the rest of the information.

I do not think there is a script out there that fully supports any FIFA Frostbite games yet, I personally haven't found any, UFBE by daemon1 doesn't work either.

BUT, you might have luck to just try the EALayer3 run trough all chunks and what ever is the correct audio will be decoded to wav/mp3 and then you'll have to listen to each and all of them to see what's what.

PS: Forgot to mention, I only tried on the DEMO version so I have no clue if it would work on a full version of the game to see the difference.
## Post #4
- Username: Aquacube
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jul 02, 2018 7:27 pm
- Post datetime: 2018-07-08T12:21:54+00:00
- Post Title: FIFA 18 (CAS) Files - ZSTD streams dumping help

@mono24
yes exactly, i use that script
2day i try to extract the full game
and the folder of EBX CREATED but i dtop on thar error
## Post #5
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-07-08T23:44:29+00:00
- Post Title: FIFA 18 (CAS) Files - ZSTD streams dumping help

> Reply from Aquacube
>
> @mono24
yes exactly, i use that script
2day i try to extract the full game
and the folder of EBX CREATED but i dtop on thar error
Unfortunately there is nothing at the moment that can extract any of the FIFA Frostbite games in full, and that error is quite common for all scripts I have tried so far.

And also you have a different option that you could try on your full game:
[http://aluigi.altervista.org/bms/frostbite.bms](http://aluigi.altervista.org/bms/frostbite.bms)
I personally do NOT recommend it on any Frostbite games because it does a poor job and up on extraction it makes a mess.

And since you already posted on ZENHAX and Luigi himself couldn't help, you might as well just try it and then run the EALayer3 on all chunks to decode audio, you simply never know what might work.

Good luck.
## Post #6
- Username: Aquacube
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jul 02, 2018 7:27 pm
- Post datetime: 2018-07-14T15:55:34+00:00
- Post Title: FIFA 18 (CAS) Files - ZSTD streams dumping help

thanks @mono24 
I tried to do it, but it seem EA very ingenious about files encrypting 
i Extracted audio files but unfortunately, the files are poor quality
## Post #7
- Username: mksharma
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Aug 02, 2018 3:55 pm
- Post datetime: 2018-08-02T08:12:48+00:00
- Post Title: FIFA 18 (CAS) Files - ZSTD streams dumping help

What's strange is that these invalid zstd chunks have the same 0x0f70 flag of the good ones, the only difference is that 0x01000000 added to the decompressed chunk size which is just another flag (so the size is 24bit).
Trying all the legacy zstd gave the same invalid results and even scanning all the compression algorithms was the same.
