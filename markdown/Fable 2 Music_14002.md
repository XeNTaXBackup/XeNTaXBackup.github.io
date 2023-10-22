## Post #1
- Username: ufive
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Feb 21, 2016 8:44 pm
- Post datetime: 2016-02-21T16:13:10+00:00
- Post Title: Fable 2 Music

Hi there,

I've just registered here after developing an interest in the Fable series and its potential for modding.  I am at the moment attempting to extract the music.bnk file in order to listen to all the wav files therein, however no media player seems to be able to read them, despite apparently all of them being wav files.  I have read elsewhere that Xbox game audio is usually in the .xma format, but that doesn't seem to be the case here.

I'm wondering if this is an issue with the Hunter/Silver BNKExplorer program that has been posted on this site? Or is there a step I am missing in order to correctly decompress the bnk file?  Perhaps there is a codec I need to obtain so that I can play them/convert them to something that IS playable?

Many thanks for any help that anyone can provide
## Post #2
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2016-02-22T08:46:41+00:00
- Post Title: Fable 2 Music

Fable II uses XMA compression which nearly all of games on Xbox 360 will use as there is specific hardware in the machine designed to handle audio decompression and processing.

The file extension .WAV given by the BNKextractor is not correct.

You will probably need [Xplorer's ToWAV](http://www.ctpax-x.org/?goto=files&show=24) to decode the XMA into WAV.

But I cannot remember exactly if the XMA files could be decoded just as they are or if they needed their header manipulated.

If ToWAV doesn't convert the XMA files just as they are, you'll need [QuickBMS](http://aluigi.altervista.org/quickbms.htm) and [this script made by AlphaTwentyThree](http://forum.xentax.com/viewtopic.php?f=17&t=9023). Run the script on the .XMA files and then ToWAV should be able to decode it.

The only track that can be an issue is the "crescendo" track which is actually 5 audio files that are interleaved IIRC.
## Post #3
- Username: ufive
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Feb 21, 2016 8:44 pm
- Post datetime: 2016-02-22T12:40:57+00:00
- Post Title: Fable 2 Music

Thanks a lot for your help!
## Post #4
- Username: hmargot360
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Sep 18, 2020 8:20 pm
- Post datetime: 2020-09-18T14:12:01+00:00
- Post Title: Fable 2 Music

> Reply from brendan19 ↑Mon Feb 22, 2016 4:46 pm at Mon Feb 22, 2016 4:46 pm
>
> 
Fable II uses XMA compression which nearly all of games on Xbox 360 will use as there is specific hardware in the machine designed to handle audio decompression and processing.

The file extension .WAV given by the BNKextractor is not correct.

You will probably need Xplorer's ToWAV to decode the XMA into WAV.

But I cannot remember exactly if the XMA files could be decoded just as they are or if they needed their header manipulated.

If ToWAV doesn't convert the XMA files just as they are, you'll need QuickBMS and this script made by AlphaTwentyThree. Run the script on the .XMA files and then ToWAV should be able to decode it.

The only track that can be an issue is the "crescendo" track which is actually 5 audio files that are interleaved IIRC.

I appreciate that this is a very old post, but I've been trying to convert Fable 2's files to a playable format. I've tried using the script made by AlphaTwentyThree, but I get the error "Error: No XMA code found at designated offset (20).  Aborting all operations."

I'm at a loss honestly. Extracting fable 3's audio was a breeze, but this has been pretty complicated. Any help would be greatly appreciated!
## Post #5
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2020-09-19T08:36:51+00:00
- Post Title: Fable 2 Music

Good news, [vgmstream](https://github.com/bnnm/vgmstream-builds/raw/master/bin/vgmstream-latest-test-u.zip) now has really great support for XMA and XMA2 compressed audio.

The files should playback without any need for modification to them. You can even convert them to WAV easily too.

Note: The crescendo tracks are multichannel so they won't playback with vgmstream but you can convert them to WAV first and then listen to them.
