## Post #1
- Username: Blaze Modz
- Rank: advanced
- Number of posts: 42
- Joined date: Mon Dec 28, 2015 8:00 am
- Post datetime: 2015-12-28T00:04:13+00:00
- Post Title: White Noise Online .xnb sound file. Need help extracting!!!

I've been trying to extract the .xnb sound files from White Noise Online. I. TRIED. EVERYTHING. Trust me, I have. Can anyone help!?
## Post #2
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-12-29T19:07:14+00:00
- Post Title: White Noise Online .xnb sound file. Need help extracting!!!

Try uploading an example
## Post #3
- Username: Blaze Modz
- Rank: advanced
- Number of posts: 42
- Joined date: Mon Dec 28, 2015 8:00 am
- Post datetime: 2015-12-29T19:38:49+00:00
- Post Title: White Noise Online .xnb sound file. Need help extracting!!!

@daemon1 Thanks for the reply! This is the example zip: [http://www.mediafire.com/download/5sdtl ... xample.zip](http://www.mediafire.com/download/5sdtlm64am0df7q/WhiteNoiseExample.zip)
## Post #4
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-12-29T20:29:36+00:00
- Post Title: White Noise Online .xnb sound file. Need help extracting!!!

Microsoft ADPCM packed into some strange format. Only need to change the tool included there to support ADPCM, not only PCM.
## Post #5
- Username: Blaze Modz
- Rank: advanced
- Number of posts: 42
- Joined date: Mon Dec 28, 2015 8:00 am
- Post datetime: 2015-12-30T23:47:02+00:00
- Post Title: White Noise Online .xnb sound file. Need help extracting!!!

Woah! Can you link whatever you used please!? I Need it! What tool? Can you link me whatever you used? or teach me how to rip the sounds like you did? You were not very specific D:
## Post #6
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-12-31T04:36:19+00:00
- Post Title: White Noise Online .xnb sound file. Need help extracting!!!

I did it manually with hex editor. I'm making a corrected tool for you, just wait a little.
## Post #7
- Username: Blaze Modz
- Rank: advanced
- Number of posts: 42
- Joined date: Mon Dec 28, 2015 8:00 am
- Post datetime: 2015-12-31T04:38:36+00:00
- Post Title: White Noise Online .xnb sound file. Need help extracting!!!

@daemon1 Yes! Awesome! Thank you! I'll wait :3 I'm so excited!
## Post #8
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-12-31T14:41:25+00:00
- Post Title: White Noise Online .xnb sound file. Need help extracting!!!

ready
[XNBSound.rar](https://xentaxbackup.github.io/file/10252_XNBSound.rar)
## Post #9
- Username: Blaze Modz
- Rank: advanced
- Number of posts: 42
- Joined date: Mon Dec 28, 2015 8:00 am
- Post datetime: 2015-12-31T18:09:56+00:00
- Post Title: White Noise Online .xnb sound file. Need help extracting!!!

@daemon1 Oh my gosh thank you so much! It works! Your awesome! Is there an possible way to do the same with models, animations, and textures? (They all use .xnb)
## Post #10
- Username: Blaze Modz
- Rank: advanced
- Number of posts: 42
- Joined date: Mon Dec 28, 2015 8:00 am
- Post datetime: 2015-12-31T19:07:36+00:00
- Post Title: White Noise Online .xnb sound file. Need help extracting!!!

Do you think its a possibility? Anyone i should ask?
## Post #11
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-12-31T19:14:57+00:00
- Post Title: White Noise Online .xnb sound file. Need help extracting!!!

post examples, and we'll see
## Post #12
- Username: Blaze Modz
- Rank: advanced
- Number of posts: 42
- Joined date: Mon Dec 28, 2015 8:00 am
- Post datetime: 2015-12-31T19:20:54+00:00
- Post Title: White Noise Online .xnb sound file. Need help extracting!!!

@daemon1 Awesome! Thank you! I archived an example rar file. Its got a couple of textures, models and animations. Is there any chatting software/site we can chat on so it would make this easier? Also, whatever program you use to extract these, Link it please  [http://www.mediafire.com/download/q3i0x ... ims%29.zip](http://www.mediafire.com/download/q3i0xeu4023fkps/WhiteNoiseExample%28Textures%2Cmodels%2Canims%29.zip)
## Post #13
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-01-01T08:16:44+00:00
- Post Title: White Noise Online .xnb sound file. Need help extracting!!!

That's your "enemy" and "totem" textures. XNA standard compression, DXT1 textures.



I used xnb.bms script to unpack it, and then made standard DDS headers.

I also decompressed a mesh. This must all be convertable, but this XNA framework is a common thing, and there must be some tools to work with it. Probably if you download XNA, you can work with all these. That depends on what do you want to do.
## Post #14
- Username: Blaze Modz
- Rank: advanced
- Number of posts: 42
- Joined date: Mon Dec 28, 2015 8:00 am
- Post datetime: 2016-01-02T01:49:34+00:00
- Post Title: White Noise Online .xnb sound file. Need help extracting!!!

@daemon1 I PM'd you my Skype so we can continue this  Thanks for your hel pbtw! I look forward to you adding me
## Post #15
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-01-02T12:34:48+00:00
- Post Title: White Noise Online .xnb sound file. Need help extracting!!!

Here's that totem model rendered



after applying normal & specular maps:
