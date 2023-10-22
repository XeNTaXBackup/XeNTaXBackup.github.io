## Post #1
- Username: Acidfmhq
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Apr 27, 2005 6:19 am
- Post datetime: 2005-07-02T19:57:04+00:00
- Post Title: Mortal Kombat Deception sound archives

I was look at the sound Archives of MK Deception (.MSX) and noticed in a hex editor that their are wave files inside these..

I would really like it if you guys could take a look at it this ne way were is the archive

[http://fmhq.mustangfreak.us/stuff/music_fatality.rar](http://fmhq.mustangfreak.us/stuff/music_fatality.rar)
## Post #2
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-07-02T22:02:18+00:00
- Post Title: Mortal Kombat Deception sound archives

Greetings... Means I have looked that for a format of music... It is archive in which some files in format WAV (RIFF WAVE) lay but there is one but... Namely that that all sounds which there lay Ñ
## Post #3
- Username: Acidfmhq
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Apr 27, 2005 6:19 am
- Post datetime: 2005-07-03T20:22:46+00:00
- Post Title: Mortal Kombat Deception sound archives

GAP finds the files but....it can't play them as the compression of this wav is not supported by GAP

wonder if theirs a other way of getting these to play...as I would really like to get the BGM from what a fatality is done
## Post #4
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-07-04T02:52:13+00:00
- Post Title: Mortal Kombat Deception sound archives

Hi,

This game is on the XBox or PS2 or something isn't it? If so, the reason why you can't play the WAV files is that they use a non-standard sample rate or compression or something like that. There might be some programs on the net to open and play these audio, but the standard windows programs won't play them.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #5
- Username: Acidfmhq
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Apr 27, 2005 6:19 am
- Post datetime: 2005-07-04T06:28:55+00:00
- Post Title: Mortal Kombat Deception sound archives

its from the Xbox version...but I will look around and see if I can find ne thing to help
## Post #6
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2005-07-04T13:17:25+00:00
- Post Title: Mortal Kombat Deception sound archives

I haven't actually checked or verified it for this game, but the game prolly uses the Xbox ADPCM Codec, which you can find a link to at Xbox Scene.  

Almost all Xbox games use this codec and if you plan on messing with audio files on Xbox games it's wise to install the codec on your computer and give it the highest priority, to make sure it is used when playing the files.  

Edit:  I was in a good mood today and I'll give you the link to it.
[Xbox Scene Driver Page](http://www.xbox-scene.com/tools/tools.php?page=driver)
It's the first download listed, and is improperly listed as the ADCPM Codec.  ADPCM is the correct spelling.
## Post #7
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-07-04T13:59:01+00:00
- Post Title: Mortal Kombat Deception sound archives

OK well I looked at the files and they are actually archives so you will need a plugin or a script to extract the audio files from the archive. I should have a plugin for you by the end of the week.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #8
- Username: Acidfmhq
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Apr 27, 2005 6:19 am
- Post datetime: 2005-07-04T18:45:45+00:00
- Post Title: Mortal Kombat Deception sound archives

ok awesome hope to see it soon 

and I will look at the codec you posted brienj
## Post #9
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-07-04T21:15:46+00:00
- Post Title: Mortal Kombat Deception sound archives

It is an archive indeed, with seemingly the headers from the wav files stripped. Easily joined to get the whole file again. Yet, these are not playable in standard sound programs. Damn XBox sound format again....  
I joined them, the sound didn't play with the codec brienj pointed out. Or perhaps I did something wrong. I miss the "data" string in the wave file. Hmm.. any thoughts?
## Post #10
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2005-07-05T01:35:57+00:00
- Post Title: Mortal Kombat Deception sound archives

> Reply from Mr.Mouse
>
> It is an archive indeed, with seemingly the headers from the wav files stripped. Easily joined to get the whole file again. Yet, these are not playable in standard sound programs. Damn XBox sound format again....  
I joined them, the sound didn't play with the codec brienj pointed out. Or perhaps I did something wrong. I miss the "data" string in the wave file. Hmm.. any thoughts?
They should be 4-bit files if correctly done as an Xbox audio file.  Also, after you install the codec, go to your Control Panel and open the "Sounds and Multimedia" panel.  Then go to the "Hardware" tab, select Audio Codecs, then press the Properties button.  Once that opens, go to the "Properties" tab, and you should have "Microsoft ADPCM Audio Codec" in the list, if not, it wasn't installed correctly.  If it was installed, then click on it and select Properties for it, then make the priority #1, this way it won't try to play these "WAV" files with another codec.  Do not worry, your normal WAV files will still play properly.
## Post #11
- Username: Acidfmhq
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Apr 27, 2005 6:19 am
- Post datetime: 2005-07-05T04:23:11+00:00
- Post Title: Mortal Kombat Deception sound archives

well the codec doesn't want to work with the wavs inside this archive...

but I also got MKDA so it has the same archive type but the wav files inside those work with the codec and play in GAP and able to convert them to a standard windows wav file...

so the MKD wav files most of something else to them or are just missing something
## Post #12
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-07-05T06:12:58+00:00
- Post Title: Mortal Kombat Deception sound archives

> Reply from brienj
>
> Mr.Mouse wrote:It is an archive indeed, with seemingly the headers from the wav files stripped. Easily joined to get the whole file again. Yet, these are not playable in standard sound programs. Damn XBox sound format again....  
I joined them, the sound didn't play with the codec brienj pointed out. Or perhaps I did something wrong. I miss the "data" string in the wave file. Hmm.. any thoughts?
They should be 4-bit files if correctly done as an Xbox audio file.  Also, after you install the codec, go to your Control Panel and open the "Sounds and Multimedia" panel.  Then go to the "Hardware" tab, select Audio Codecs, then press the Properties button.  Once that opens, go to the "Properties" tab, and you should have "Microsoft ADPCM Audio Codec" in the list, if not, it wasn't installed correctly.  If it was installed, then click on it and select Properties for it, then make the priority #1, this way it won't try to play these "WAV" files with another codec.  Do not worry, your normal WAV files will still play properly.

Well, I did all that when I installed it, but the merged header+data I got from the archive did not play. Do you have an example of such a file so I can test if that playing works? Would also be good to compare the files in the archive with.
## Post #13
- Username: Acidfmhq
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Apr 27, 2005 6:19 am
- Post datetime: 2005-07-08T10:11:31+00:00
- Post Title: Mortal Kombat Deception sound archives

well I said in my other post is that MKDA uses the same file format for sounds could it be poissable that you could get the header info from the wavs  in archive and compare them too the ones in the MKD wavs have

just ask I can get you the archive from MKDA for you guys
