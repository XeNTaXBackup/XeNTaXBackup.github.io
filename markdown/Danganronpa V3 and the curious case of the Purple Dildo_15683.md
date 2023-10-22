## Post #1
- Username: Fentano
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Jan 06, 2017 6:49 am
- Post datetime: 2017-01-05T23:52:44+00:00
- Post Title: Danganronpa V3 and the curious case of the Purple Dildo

I'm a big fan of the Danganronpa series - it's a wackier, darker Phoenix Wright. So I was kind of caught off guard when I saw a tweet from the programmer of the game's first translation saying that the Danganronpa V3 demo had tons of hidden assets. Intially, I thought the programmer was full of it, but then the programmer posted a sprite not seen in the demo - of one of the game's 16 characters waving around a purple dildo[https://twitter.com/BlackDragonHunt/sta ... 0360517633](https://twitter.com/BlackDragonHunt/status/816428520360517633)

Initially, I thought it was a bad shop. The image had obvious artifacting and the like. But then the programmer said that they would not leak most of the assets, because they were the only ones capable of getting into the files.  


Naturally, I took that as a challenge. So I did the basics. Got the Demo with a 3.63 Vita, ripped the files from them and uploaded with a 3.60. Unpacked with Cripak. And you know what, the Programmer was right. For some absurd reason the Demo really did have assets for the entire game - the Demo had more character sprites than Danganronpa2, the game proceeding it.

But the files were encrypted - at least, so I thought. They were saved in SPC format, which Windows and I both made the mistake of thinking were PKCS7 certificates. Tons of wasted time later, the Programmer themselves popped into IRC to tell us SPC had nothing to do with security - that it was a custom encryption format.

So here's where I'm at.

Here's a link to the SPC file(EDIT: All the Character SPC files) which i think is where the purple dildo picture originated - the SPC is Stand_14_019, the picture was Stand_14_019a.jpg - the twitter leaker dumped other, non purple dildo related pictures, but changed their filenames to just a string of numbers. I can dump the whole demo SPC files too - even with the compressed data there's just so many slots for data - far more pictures and effects than were in the demo.

[https://mega.nz/#!6xtmgBzQ!RNfIUlC94bQs ... KdaxqRtCp8](https://mega.nz/#!6xtmgBzQ!RNfIUlC94bQs4YPTVD0GuMFTi3LfqeIMrKdaxqRtCp8)
Here's what I see when looking at the SPC format file in Hexinator 

[http://sli.mg/Woja2z.jpg](http://sli.mg/Woja2z.jpg)

So to sum it all up - this SPC formated file IS a custom compresser, right? I see ELA when looking at the JPG which by its filename seems to have been extracted from the SPC. 

And, if it is a custom compressor... any good ways to go about reverse engineering the compression method? Just based on the filename I'm almost certain the purple dildo JPG is derived from the SPC that shares its name, but does that really matter? Can I use the JPG as a clue, or is it completely irrelevant in trying to do the reverse of whatever compressed everything into the SPC file? I know that the SPC doesn't JUST have the image(it's larger than the jpg), but the Programmer on twitter changing the filename of every leaked image AFTER the dildo image makes me think there's something worth noting about it.

Anyways, compression is definitely not my forte, but I'd sure like to get a look at the uncompressed data before DRv3's release in about week. Just seems unbelievable that a demo of a mystery game about plot twists would be packed with the assets of the full game.
[stand_014_019a.jpg](https://xentaxbackup.github.io/file/12160_stand_014_019a.jpg)
## Post #2
- Username: ufdm
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Aug 14, 2014 3:21 am
- Post datetime: 2017-01-06T04:31:48+00:00
- Post Title: Danganronpa V3 and the curious case of the Purple Dildo

> Reply from Fentano
>
> Here's a link to the SPC file which i think is where the purple dildo picture originated - the SPC is Stand_14_019, the picture was Stand_14_019a.jpg - the twitter leaker dumped other, non purple dildo related pictures, but changed their filenames to just a string of numbers. I can dump the whole demo SPC files too - even with the compressed data there's just so many slots for data - far more pictures and effects than were in the demo.

https://mega.nz/#fm/5lRBWaJJ
That Mega link doesn't work.
## Post #3
- Username: Fentano
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Jan 06, 2017 6:49 am
- Post datetime: 2017-01-06T05:54:15+00:00
- Post Title: Danganronpa V3 and the curious case of the Purple Dildo

Alright. This link should work - it has all the .SPC files for the characters folder

[https://mega.nz/#!6xtmgBzQ!RNfIUlC94bQs ... KdaxqRtCp8](https://mega.nz/#!6xtmgBzQ!RNfIUlC94bQs4YPTVD0GuMFTi3LfqeIMrKdaxqRtCp8)
