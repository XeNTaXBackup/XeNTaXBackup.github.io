## Post #1
- Username: mypantsfelldown
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Dec 14, 2019 1:53 am
- Post datetime: 2020-01-10T03:40:58+00:00
- Post Title: Encoder for EA ADPCM?

Does anyone know of an encoder for any of the EA ADPCM variants (XAS preferably)? There seems to be a decoder out there but no way to encode. I'm attempting to replace sounds from The Sims 3 with custom ones. Some of the game's audio is in mp3, which I've managed to replace with the EALayer3 tool, but some of the smaller sounds are in ADPCM. Whilst some of the ADPCM sounds can be replaced with mp3 files instead, some simply will not work and crash the game. The Sims 4 also seems to use the exact same formats, if that helps any. I'm a bit confused as to how there isn't an encoder by now, considering the decoder seems to have been out for quite a while now. Plus, a lot of games use this codec.
## Post #2
- Username: allangod
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Apr 25, 2018 6:58 am
- Post datetime: 2020-01-16T14:56:37+00:00
- Post Title: Encoder for EA ADPCM?

ealayer3 (v.0.7.0) does encode in various EA formats, but I am not sure if they are the ones you want, tho according to this website [http://simswiki.info/wiki.php?title=Sims_3:0x01A527DB](http://simswiki.info/wiki.php?title=Sims_3:0x01A527DB) it does (also, it seems that the EA XAS ADPCM encodes in FFMPEG, so you probably only need an ffmpeg.exe encoder).
## Post #3
- Username: mypantsfelldown
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Dec 14, 2019 1:53 am
- Post datetime: 2020-01-18T02:04:02+00:00
- Post Title: Encoder for EA ADPCM?

> Reply from allangod ↑Thu Jan 16, 2020 10:56 pm at Thu Jan 16, 2020 10:56 pm
>
> 
ealayer3 (v.0.7.0) does encode in various EA formats, but I am not sure if they are the ones you want, tho according to this website http://simswiki.info/wiki.php?title=Sims_3:0x01A527DB it does (also, it seems that the EA XAS ADPCM encodes in FFMPEG, so you probably only need an ffmpeg.exe encoder).
EALayer3 only encodes mp3 files from what I can tell. And that wiki page is wrong, as I'm fairly certain that FFMPEG can only decode.
## Post #4
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2020-01-24T12:42:39+00:00
- Post Title: Encoder for EA ADPCM?

Correct, FFMPEG will only decode XAS and the guy who did that particular decoding code considers the EA ADPCM codecs real crap which they are given ADPCM dates from phone lines from 80s and we have far superior audio codecs these days but EA keeps clinging to the past just like using MP3 (1992) with ealayer3 edit.

I would say its very hard to find someone with motivation to write encoders for EA's obscure formats which are not loved, only encoders that exist are only provided by EA in their mod sdk's for some games modding (plus the variations of the format keep changing over the years so support of a tool would be nightmare) but beyond those there is no separate tool to conveniently use and unless your a programmer to juryrig a separate encoder hacking their dlls, not much luck there.
## Post #5
- Username: mypantsfelldown
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Dec 14, 2019 1:53 am
- Post datetime: 2020-01-25T01:37:16+00:00
- Post Title: Encoder for EA ADPCM?

> Reply from Apollo ↑Fri Jan 24, 2020 8:42 pm at Fri Jan 24, 2020 8:42 pm
>
> 
Correct, FFMPEG will only decode XAS and the guy who did that particular decoding code considers the EA ADPCM codecs real crap which they are given ADPCM dates from phone lines from 80s and we have far superior audio codecs these days but EA keeps clinging to the past just like using MP3 (1992) with ealayer3 edit.

I would say its very hard to find someone with motivation to write encoders for EA's obscure formats which are not loved, only encoders that exist are only provided by EA in their mod sdk's for some games modding (plus the variations of the format keep changing over the years so support of a tool would be nightmare) but beyond those there is no separate tool to conveniently use and unless your a programmer to juryrig a separate encoder hacking their dlls, not much luck there.
I agree that both codecs are utter crap. I was completely shocked to find out a couple of months ago that Sims 4 (released 2014!!!) STILL uses the exact same mp3+ealayer3 format. Not only is the efficiency of MP3 terrible, but it's so much slower to decode than most other modern codecs... It's bewildering. 

I feared as much tbh. I figured that since people had figured out how to decode all of these formats, it would be much simpler to make an encoder, but I guess that's not the case? I've been looking at C# recently but I have next to no programming knowledge off the bat and math certainly isn't my strong suit, so I might be at a dead end here. Thanks for taking the time to explain stuff!
## Post #6
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2020-01-29T10:49:54+00:00
- Post Title: Encoder for EA ADPCM?

> Reply from mypantsfelldown ↑Sat Jan 25, 2020 9:37 am at Sat Jan 25, 2020 9:37 am
>
> 
I agree that both codecs are utter crap. I was completely shocked to find out a couple of months ago that Sims 4 (released 2014!!!) STILL uses the exact same mp3+ealayer3 format. Not only is the efficiency of MP3 terrible, but it's so much slower to decode than most other modern codecs... It's bewildering. 

I feared as much tbh. I figured that since people had figured out how to decode all of these formats, it would be much simpler to make an encoder, but I guess that's not the case? I've been looking at C# recently but I have next to no programming knowledge off the bat and math certainly isn't my strong suit, so I might be at a dead end here. Thanks for taking the time to explain stuff!

I forgot add that one reason EA game may crash when replacing sounds with another format can also be that like in many games, they use a 'streaming' kind of a way of storage so headers/some relevant info of files are in one place and the actual audio data in other and when you go replace the actual audio file, some of the info will obviously not match and it can crash and this is another detriment to modding EA games besides the intentionally customized formats EA does to hinder their games being extracted/changed. That EALayer3 is a big mp3 fraunhofer license thing that EA bought with big moneys including 5.1 surround support yet no benefits beyond that and free lame 3.97 mp3 encoder probably yields better quality.
EALayer3 is mp3 entirely when it comes to actual audio data storing/encoding but the data framing system is just changed thus why EALayer3 tool can change inbetween.

And no, writing an encoder is always the hardest job as then whole format (given its EA's own they don't provide a guide...)  has to be understood down to smallest detail as even singular byte of wrong way can just crash the EA audio engine within the games at worst case while to wav decoder has to understand the bare minimums to get the job done.

XAS is just 4:1 compression and lower than that given 76 byte blocks which overbloat as bigger blocks would have been better for long files, since your not much of programmer, your only good bet would be to extract XAS files and then use some of EA mod sdks that can encode the format and then compare the header layouts if they match or you need to hex editor copy and paste and cut some or try learn programming, no easy road regardless path.

Ironically, EA themselves comment in C&C3 mod sdk guide that XAS is shit for 'music' audio quality wise (and thus should not be used for music) yet some games they do exactly that and you got some 40mb files or worse as result.

EA did adapt 'speex' codec for VOIP and actually did use for audio files but as one might guess, they customized the encoder to write 'EASpeex' which would not play on official decoder just like ealayer3 won't play on mp3 decoder as is, knowing this its hard to endorse them to use newer codecs too xD
## Post #7
- Username: mypantsfelldown
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Dec 14, 2019 1:53 am
- Post datetime: 2020-01-30T04:52:56+00:00
- Post Title: Encoder for EA ADPCM?

> Reply from Apollo ↑Wed Jan 29, 2020 6:49 pm at Wed Jan 29, 2020 6:49 pm
>
> 
I forgot add that one reason EA game may crash when replacing sounds with another format can also be that like in many games, they use a 'streaming' kind of a way of storage so headers/some relevant info of files are in one place and the actual audio data in other and when you go replace the actual audio file, some of the info will obviously not match and it can crash and this is another detriment to modding EA games besides the intentionally customized formats EA does to hinder their games being extracted/changed. That EALayer3 is a big mp3 fraunhofer license thing that EA bought with big moneys including 5.1 surround support yet no benefits beyond that and free lame 3.97 mp3 encoder probably yields better quality.
EALayer3 is mp3 entirely when it comes to actual audio data storing/encoding but the data framing system is just changed thus why EALayer3 tool can change inbetween.

And no, writing an encoder is always the hardest job as then whole format (given its EA's own they don't provide a guide...)  has to be understood down to smallest detail as even singular byte of wrong way can just crash the EA audio engine within the games at worst case while to wav decoder has to understand the bare minimums to get the job done.

XAS is just 4:1 compression and lower than that given 76 byte blocks which overbloat as bigger blocks would have been better for long files, since your not much of programmer, your only good bet would be to extract XAS files and then use some of EA mod sdks that can encode the format and then compare the header layouts if they match or you need to hex editor copy and paste and cut some or try learn programming, no easy road regardless path.

Ironically, EA themselves comment in C&C3 mod sdk guide that XAS is shit for 'music' audio quality wise (and thus should not be used for music) yet some games they do exactly that and you got some 40mb files or worse as result.

EA did adapt 'speex' codec for VOIP and actually did use for audio files but as one might guess, they customized the encoder to write 'EASpeex' which would not play on official decoder just like ealayer3 won't play on mp3 decoder as is, knowing this its hard to endorse them to use newer codecs too xD
Yes, Sims 3 uses SNR header files and SNS files which contain the actual mp3 data. I've finally figured out a way to make the game work with my custom sounds using this method, and it requires configuring the audio correctly. Each sound comes with a config file that applies effects and probabilities, amongst other things. Using a polyphony setting seems to do the trick! I'm guessing the game had problems loading the audio into memory multiple times or something.

Thanks for the tips. I'm still learning C# as it's the game's scripting language and I have a few modded objects in mind. Hopefully it'll come in useful at some point.

XAS music does sound terrible. I've been converting some music from Sims 2 that has ADPCM menu/loading music, with the rest of the music in MP3. While the MP3s still sound terrible, I've managed to salvage the quality a little with some plugins. This one loading song is almost unbearable to listen to. All of the higher frequencies are butchered; it's just a bunch of hiss and unpleasant noise.
## Post #8
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2020-02-03T14:35:49+00:00
- Post Title: Encoder for EA ADPCM?

> Reply from mypantsfelldown ↑Thu Jan 30, 2020 12:52 pm at Thu Jan 30, 2020 12:52 pm
>
> 
Yes, Sims 3 uses SNR header files and SNS files which contain the actual mp3 data. I've finally figured out a way to make the game work with my custom sounds using this method, and it requires configuring the audio correctly. Each sound comes with a config file that applies effects and probabilities, amongst other things. Using a polyphony setting seems to do the trick! I'm guessing the game had problems loading the audio into memory multiple times or something.

Thanks for the tips. I'm still learning C# as it's the game's scripting language and I have a few modded objects in mind. Hopefully it'll come in useful at some point.

XAS music does sound terrible. I've been converting some music from Sims 2 that has ADPCM menu/loading music, with the rest of the music in MP3. While the MP3s still sound terrible, I've managed to salvage the quality a little with some plugins. This one loading song is almost unbearable to listen to. All of the higher frequencies are butchered; it's just a bunch of hiss and unpleasant noise.

Use most recent LAME encoder to get as high quality MP3 as possible for replacements, it beats the official fraunhofer encoders quality and transition it to ealayer3 but yes, mp3 cuts the higher freqs and many other supposedly 'unheard' frequencys which considered pretty bad vs modern codecs now that have more improved way of compressing without such drastic frequency cuts.

as for SNR/SNS, they are basicly the same but different way of storing, SNS is for 'streamed form' audio data and typically lacks complete header as that info is put elsewhere only and just comes with streaming block headers. SNR on other hand is straight loaded into RAM and ideal for small audio files.

XAS or EALAYER3, choose your poison as neither is spectacular as ideally you'd want Ogg Vorbis, AAC, Opus these days. 
Oh right, I got reminded, value of x02 is uncompressed pcm option where x04 (or x14 in frostbite engine) is xas so if you managed use ea tools save uncompressed and not mind size, you could have untampered audio, unfortunately I think EA tool swaps endianness of pcm data so direct wav header edit may not suffice. Good luck to the EA rocky road adventure.
