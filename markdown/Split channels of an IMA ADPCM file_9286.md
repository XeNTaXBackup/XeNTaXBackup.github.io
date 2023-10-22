## Post #1
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-07-17T13:20:50+00:00
- Post Title: Split channels of an IMA ADPCM file?

Hi there,
I've just encountered several IMA ADPCM files with 4-6 channels that are actually layers (DJ Hero for PS3). Can anyone tell me how the channels are interleaved so I can split the layers?
Here's a screen where you should be able to see the interleave (maybe it's even stated in the header?): 
[](http://imageshack.us/photo/my-images/59/imau.png/)
Uploaded with [ImageShack.us](http://imageshack.us)
Any help is appreciated!
## Post #2
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2012-07-22T08:54:06+00:00
- Post Title: Split channels of an IMA ADPCM file?

Hmm well all the header can tell is adpcm block encoding size of 55296 bytes for this 6 channel file and secondary variable says for ima chunks 16384 bytes within the block(?), not sure why the secondary value differs in some ima encoding appliances as typically it is same as blocksize minus 7 unless I mislooked entirely the header stuff here.

Usually adpcm data just takes turns to tell each channel data by means of 4 bytes(AFAIK) and switch channel and multichannels just add more turns usually wothin the block but can't be sure how they handled it here as multi channel ima isn't standard so they had freedom to customize, anyhow the block math matches up to normal ima encoding scheme atleast.

Maybe its of help, good luck.
## Post #3
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-07-22T12:08:52+00:00
- Post Title: Split channels of an IMA ADPCM file?

Thanks for your reply! 
I'll try with 4 bytes interleave and see how it sounds. Will the header stay the same (except for the channel count and sizes) when the file is split?
## Post #4
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2012-07-22T12:46:43+00:00
- Post Title: Split channels of an IMA ADPCM file?

I would figure header stay the same except for the need to adjust the file size, channels and the adpcm block size and its secondary value since you remove content from block, its size needs to be reset and generally its always multiples of 4 based so same concept may help find interleave. The secondary field could be ignored if try playback within VLC which uses only blocksize value to do playback.

Obviously the splitter needs to copy the 7 byte block framing for all I think(?) or one alternative would be to erase blocking material and go for plain raw ima adpcm decode as blocks are only for seeking anyway, not for channels typically in adpcm, just that riff wav format mandates blocks.

Anyhow hcs knows ima adpcm in more detail, mine are educated guesses and partial knowledge from dealing with the format decoding for few years.
## Post #5
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-07-24T11:52:49+00:00
- Post Title: Split channels of an IMA ADPCM file?

Just figured it out. Interleave is standard 2 bytes (also stated at 0x24) for each channel. the blocksize will change into 0x24000 (0xd800/6), channels to 1, rest stays the same. vgmstream can play those. Of course it would still be nice to change the header to standard ima but I have no idea how to. Wouldn't the multichannel file also be playable with a standard header? The header you see here comes from fsbext, which automatically constructs a header when extracting.
Anyhow, I'll write a stereo channel splitter for those non-standard headers later. Just need to somewhat "sort" the channel information to get CH/2 stereo streams.
## Post #6
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2012-07-26T20:00:38+00:00
- Post Title: Split channels of an IMA ADPCM file?

Well, ima adpcm/most adpcm standards have limited the support to stereo while technically its not a big deal, the existing players will just refuse to play higher than stereo as its not the norm... unfortunately splitting it to stereo atleast would have to be done :/

The header is pretty much basic style as is minus the fact chunk which is pointless TBH, its just the blocksize, channels and secondary ima value which no doubt make it refuse to play in usual players which is also scenario with xbox adpcm header files when changed to standard ima header and most players refuse to playback being picky on the values except vlc but then even vlc won't support more than stereo given I know source its based on IMO.

anyhow good thing you figured it out, I misrecalled the interleave off by 2 then.
