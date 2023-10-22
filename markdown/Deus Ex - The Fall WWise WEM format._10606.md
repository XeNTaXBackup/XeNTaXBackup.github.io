## Post #1
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2013-07-11T04:05:47+00:00
- Post Title: Deus Ex - The Fall WWise WEM format.

I think its some sort of ffmpeg codec but i could not decode it.

[https://mega.co.nz/#!TIAXHByC!FgSllTZvj ... 5NagV5PTjQ](https://mega.co.nz/#!TIAXHByC!FgSllTZvjum_JjJ3GYH4c33omJE1F53aw5NagV5PTjQ)
## Post #2
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2013-07-11T10:51:44+00:00
- Post Title: Deus Ex - The Fall WWise WEM format.

Ah, curious that wwise guys have now adapted AAC among their formats.
Decoding those is not even necessary, just strip the 64 byte riff header and play back the AAC.
## Post #3
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2013-07-11T17:47:29+00:00
- Post Title: Deus Ex - The Fall WWise WEM format.

I stripped 64 bytes but still nothing. can you describe the offsets and what extension i need to rename?
## Post #4
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2013-07-11T20:23:48+00:00
- Post Title: Deus Ex - The Fall WWise WEM format.

keep in mind, a hex editor sometimes lists the offest as hexidecimal values instead of decimal. HxD (what i use) does this, so i have to change to decimal format or just count out 64 bytes (64 characters) otherwise you end up deleting 100 bytes. rename to .aac and open with a compatible player, quicktime is a good bet as aac is associated with apple.
## Post #5
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2013-07-11T21:08:25+00:00
- Post Title: Deus Ex - The Fall WWise WEM format.

I got it actually. 

thanks.
