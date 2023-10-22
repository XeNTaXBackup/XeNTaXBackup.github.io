## Post #1
- Username: spider91
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Feb 14, 2011 3:09 pm
- Post datetime: 2014-11-04T09:49:57+00:00
- Post Title: CoD Advanced Warfare .pak and .ff

Any ideas about this files? .ff seems to contain texts and sounds (FLAC). Magic number is S1ffu100 on both types, but .pak looks like compressed file. What about script?

[https://mega.co.nz/#!9gwR0ZLC!8TrF9981y ... -R34wgaZ8k](https://mega.co.nz/#!9gwR0ZLC!8TrF9981y2_JrNiGWBI-WRr0rAj8OJC0j-R34wgaZ8k)
## Post #2
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-11-05T04:17:30+00:00
- Post Title: CoD Advanced Warfare .pak and .ff

[http://dev.cra0kalo.com/?p=195](http://dev.cra0kalo.com/?p=195)
works for sound paks since its just flacs mushed 


as for imagepaks they are encrypted
## Post #3
- Username: m0xf
- Rank: n00b
- Number of posts: 19
- Joined date: Fri Aug 17, 2012 1:57 am
- Post datetime: 2014-11-06T19:43:48+00:00
- Post Title: CoD Advanced Warfare .pak and .ff

Imagefiles not encrypted, it compressed with LZ77-like algorithm instead of zlib. Decompression code: [http://pastebin.com/GhfXDhE7](http://pastebin.com/GhfXDhE7) .
## Post #4
- Username: spider91
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Feb 14, 2011 3:09 pm
- Post datetime: 2014-11-06T21:46:38+00:00
- Post Title: CoD Advanced Warfare .pak and .ff

> Reply from m0xf
>
> Imagefiles not encrypted, it compressed with LZ77-like algorithm instead of zlib. Decompression code: http://pastebin.com/GhfXDhE7 .

Can someone implement that code in script or tool?
## Post #5
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-11-07T02:56:27+00:00
- Post Title: CoD Advanced Warfare .pak and .ff

> Reply from m0xf
>
> Imagefiles not encrypted, it compressed with LZ77-like algorithm instead of zlib. Decompression code: http://pastebin.com/GhfXDhE7 .
ah yeah you're right sub_14014A350

there are about 4 types of compression methods 1 is zlib


Yep  sub_1404E9010 is zlib



If compressiontype is 1 call zlib function
## Post #6
- Username: Koma
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Nov 07, 2014 8:59 pm
- Post datetime: 2014-11-07T14:02:30+00:00
- Post Title: CoD Advanced Warfare .pak and .ff

> Reply from cra0
>
> http://dev.cra0kalo.com/?p=195
works for sound paks since its just flacs mushed 

as for imagepaks they are encrypted

That is a fine tool indeed. But there is one problem with it.

When going only through archives "soundfile1.pak", "soundfile48.pak" and "soundfile57.pak", your extractor reaches a specific loop point which leads you back to the first file of the archive, and it just stays there until it's shut down. The rest of the archives remains completely unaffected. It is a kinda annoying issue which doesn't let your extractor unpack more audio files after reaching that point, even if it can be circumvented by just moving the affected archives somewhere else.

soundfile1.pak loop point is at "soundfile1_00227800.flac"
soundfile48.pak loop point is at "soundfile48_09986800.flac"
soundfile57.pak loop point is at "soundfile57_09449000.flac"

Is it me doing something wrong, or aren't the archives right? I lack the needed knowledge to look upon this issue and that's why I sincerely request that you'll look it up.


EDIT: Okay, you can disregard that issue now! I just used the 32-bit version of it and the bug doesn't seem to occur anymore. At least for now.
## Post #7
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-11-07T15:09:04+00:00
- Post Title: CoD Advanced Warfare .pak and .ff

> Reply from Koma
>
> cra0 wrote:http://dev.cra0kalo.com/?p=195
works for sound paks since its just flacs mushed 

as for imagepaks they are encrypted

That is a fine tool indeed. But there is one problem with it.

When going only through archives "soundfile1.pak", "soundfile48.pak" and "soundfile57.pak", your extractor reaches a specific loop point which leads you back to the first file of the archive, and it just stays there until it's shut down. The rest of the archives remains completely unaffected. It is a kinda annoying issue which doesn't let your extractor unpack more audio files after reaching that point, even if it can be circumvented by just moving the affected archives somewhere else.

soundfile1.pak loop point is at "soundfile1_00227800.flac"
soundfile48.pak loop point is at "soundfile48_09986800.flac"
soundfile57.pak loop point is at "soundfile57_09449000.flac"

Is it me doing something wrong, or aren't the archives right? I lack the needed knowledge to look upon this issue and that's why I sincerely request that you'll look it up.


EDIT: Okay, you can disregard that issue now! I just used the 32-bit version of it and the bug doesn't seem to occur anymore. At least for now.

Ill have a look

-edit- 

try
[http://rel.cra0kalo.com/depot/CODAW_Fla ... 64_3.0.zip](http://rel.cra0kalo.com/depot/CODAW_FlacDumper_x64_3.0.zip)

should be much faster + fixed the issue was to do with my pattern finder function was returning 0 which i never checked
## Post #8
- Username: Koma
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Nov 07, 2014 8:59 pm
- Post datetime: 2014-11-07T15:34:32+00:00
- Post Title: CoD Advanced Warfare .pak and .ff

It's all unpacked now. Thanks, cra0.

Have a beer.
## Post #9
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2014-11-08T21:42:50+00:00
- Post Title: CoD Advanced Warfare .pak and .ff

It's LZ4.
## Post #10
- Username: Psp1000
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Nov 10, 2014 1:00 am
- Post datetime: 2014-11-09T17:09:03+00:00
- Post Title: CoD Advanced Warfare .pak and .ff

great tool 
What about the files of the xbox 360 version? 

for example
soundfile1.pak - 26,3 MB
## Post #11
- Username: mono24
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2014-11-10T12:39:23+00:00
- Post Title: CoD Advanced Warfare .pak and .ff

can you pleae share stucture ? Did you find any text by any chance ?? Thx
## Post #12
- Username: Psp1000
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Nov 10, 2014 1:00 am
- Post datetime: 2014-11-11T17:21:17+00:00
- Post Title: CoD Advanced Warfare .pak and .ff

hey, i found: RIFFX0..WAVEfmt. i found out this is an audio format   

example file:
[https://mega.co.nz/#!sV0CQQoa!akjd2SPHK ... YzTkIEc9Ag](https://mega.co.nz/#!sV0CQQoa!akjd2SPHKz1pYbgqdh2dw0EOLSh2rHooRYzTkIEc9Ag)

does it help? i'm new at this topic, thx
## Post #13
- Username: cloudslsw
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Nov 04, 2010 5:37 pm
- Post datetime: 2014-11-14T11:52:01+00:00
- Post Title: CoD Advanced Warfare .pak and .ff

> Reply from cra0
>
> 
try
http://rel.cra0kalo.com/depot/CODAW_Fla ... 64_3.0.zip

should be much faster + fixed the issue was to do with my pattern finder function was returning 0 which i never checked

hi ,cra0,i try version 3.0 ,but console stuck at decompressing soundfile13.pak/soundfile18.pak/soundfile20.pak,rest of files im not test.but with version 2.0,i could decompress with it.it's werid,my os are win7 64bit,any ideas?
## Post #14
- Username: Abohack
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Nov 12, 2014 9:18 pm
- Post datetime: 2015-04-02T19:28:40+00:00
- Post Title: CoD Advanced Warfare .pak and .ff

hey guys

first of all I want to thank u for your great tool. I want to extract some imagefile.pak files but I cant find a tool for that, Could please anyone help me?

thanks
## Post #15
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2022-07-26T00:04:35+00:00
- Post Title: CoD Advanced Warfare .pak and .ff

Link was dead I didn't realize:
[https://cra0.net/public/bin-published/C ... 64_3.0.zip](https://cra0.net/public/bin-published/CODAW_FlacDumper_x64_3.0.zip)
Here is the new one.

I'll try find the source and open source this on github. Better late then never right
## Post #16
- Username: HD8x
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Nov 03, 2022 1:00 am
- Post datetime: 2022-11-02T17:09:32+00:00
- Post Title: Re: CoD Advanced Warfare .pak and .ff

> Reply from cra0 ↑Tue Jul 26, 2022 8:04 am at Tue Jul 26, 2022 8:04 am
>
> 
Link was dead I didn't realize:
https://cra0.net/public/bin-published/C ... 64_3.0.zip
Here is the new one.

I'll try find the source and open source this on github. Better late then never right

Hi I have a question about AWFlac.exe.
I am a big fan of Modern Warfare.
I successfully extracted the music files of Modern Warfare 1 Remastered using the AWFlac.exe you created.
However, extracting it from Modern Warfare 2 Remastered seems to be a problem.
It seems like a normal file, but when I play a FLAC file, there is a sound that cuts out once every few seconds.
As a big fan of Modern Warfare 2, I desperately need your help because I want a complete lossless album of Modern Warfare 2.
Also, when playing Modern Warfare 2 Remastered, the sound of the music in the game is too low.
I'm having a hard time because I can't separately adjust the volume of music in the game.
Can you please solve these 2 things?
## Post #17
- Username: HD8x
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Nov 03, 2022 1:00 am
- Post datetime: 2022-11-02T17:59:55+00:00
- Post Title: Re: CoD Advanced Warfare .pak and .ff

[https://tmpstorage.com/download/z8ldlak5ms](https://tmpstorage.com/download/z8ldlak5ms)

Samples and photos of the extracted files.
When I analyzed the spectrum of the FLAC file, the broken part is displayed like this.

> Reply from cra0 ↑Tue Jul 26, 2022 8:04 am at Tue Jul 26, 2022 8:04 am
>
> 
Link was dead I didn't realize:
https://cra0.net/public/bin-published/C ... 64_3.0.zip
Here is the new one.

I'll try find the source and open source this on github. Better late then never right
## Post #18
- Username: Qkkskdkwks81
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Jun 03, 2023 12:48 pm
- Post datetime: 2023-07-13T06:53:58+00:00
- Post Title: Re: CoD Advanced Warfare .pak and .ff

> Reply from cra0 ↑Tue Jul 26, 2022 8:04 am at Tue Jul 26, 2022 8:04 am
>
> 
Link was dead I didn't realize:
https://cra0.net/public/bin-published/C ... 64_3.0.zip
Here is the new one.

I'll try find the source and open source this on github. Better late then never right

Is there a tool to extract imagefile.pak
