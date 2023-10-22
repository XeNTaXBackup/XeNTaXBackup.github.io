## Post #1
- Username: juancy1234
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Sep 24, 2023 9:08 am
- Post datetime: 2023-09-24T01:25:26+00:00
- Post Title: Baaldur's gate 3 - How to convert audio files in WEM opus format to other formats

I need help. I'm trying to convert the sound files of the game "Baldur's Gate 3" into another audio format. Although I was able to convert some of the files to the ogg format using WEMSharp, a tool developed based on wem2ogg (both can be found on GitHub), many of the game's audios I haven't been able to convert because the tool indicates an error. Reviewing the metadata of the game's sound files, I found a line of code that leads me to believe these audio files use the WEM opus audio codec instead of Vorbis.

WEMSharp:

[https://github.com/Crauzer/WEMSharp](https://github.com/Crauzer/WEMSharp)

wem2ogg:

[https://github.com/hcs64/ww2ogg](https://github.com/hcs64/ww2ogg)

opus:

[https://opus-codec.org/release/dev/2020 ... _0_12.html](https://opus-codec.org/release/dev/2020/06/27/opusfile_0_12.html)

audiokinetic on wem opus:
[https://www.audiokinetic.com/en/library ... _practices](https://www.audiokinetic.com/en/library/edge/?source=Help&id=versions_tips_and_best_practices)

lines of code:

<node id="MapValue">
	<attribute id="Codec" type="FixedString" value="AK_WEM_OPUS" />
	<attribute id="Length" type="float" value="9.887729" />
	<attribute id="Priority" type="FixedString" value="P1_StoryDialog" />
	<attribute id="Source" type="FixedString" value="v00c74e3b588045259558860e4f7c77e2_h025ddeeagb7c7g46bfg87a9g7409f286e3d5.wem" />
</node>
## Post #2
- Username: juancy1234
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Sep 24, 2023 9:08 am
- Post datetime: 2023-09-24T01:27:36+00:00
- Post Title: Baaldur's gate 3 - How to convert audio files in WEM opus format to other formats

I'm talking about the game Baldur's Gate 3.
## Post #3
- Username: juancy1234
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Sep 24, 2023 9:08 am
- Post datetime: 2023-09-24T02:16:26+00:00
- Post Title: Baaldur's gate 3 - How to convert audio files in WEM opus format to other formats

**Update:**

I found a tool that allowed me to play the files and convert them to .wav. It has several versions, although I've only tried the online version. By the way, it's also possible that the files don't use the Vorbis codec but instead ADPCM.

Tool:
[https://vgmstream.org/](https://vgmstream.org/)

I found the solution on this same forum:

FNAF: Security Breach [PC] - Can't extract most Wwise .wem files:

[viewtopic.php?p=180655&hilit=Play+WEM+files#p180655](https://forum.xentax.com/viewtopic.php?p=180655&hilit=Play+WEM+files#p180655)

I create a github repository with a little python program using vgmstream to convert a lot of files faster if you are interested:

[https://github.com/juancy1234/high_data ... _converter](https://github.com/juancy1234/high_data_volume_wem_converter)
