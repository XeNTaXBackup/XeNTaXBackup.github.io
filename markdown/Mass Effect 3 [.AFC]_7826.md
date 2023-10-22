## Post #1
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2011-12-08T18:32:49+00:00
- Post Title: Mass Effect 3 [.AFC]

Hello, I cannot extract/convert the Mass Effect 3 .AFC with the current tools which work for Mass Effect 2/Gears Of War 3. It seems that the format has been changed slightly.

Can someone take a look for me please?

Regards

Solved
## Post #2
- Username: Droolie
- Rank: veteran
- Number of posts: 114
- Joined date: Fri Aug 19, 2005 11:31 pm
- Post datetime: 2011-12-08T18:49:47+00:00
- Post Title: Mass Effect 3 [.AFC]

It's because there are multiple audio files in an AFC file. Use VGMToolbox's cutter to look for RIFX headers and convert the output files with ww2ogg. That's what I did, at least (I have all the music from it).
## Post #3
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2011-12-08T19:02:24+00:00
- Post Title: Mass Effect 3 [.AFC]

> Reply from Droolie
>
> It's because there are multiple audio files in an AFC file. Use VGMToolbox's cutter to look for RIFX headers and convert the output files with ww2ogg. That's what I did, at least (I have all the music from it).Is there a more specific steps. The 
> look for RIFX headers

doesn't really help much.
## Post #4
- Username: Droolie
- Rank: veteran
- Number of posts: 114
- Joined date: Fri Aug 19, 2005 11:31 pm
- Post datetime: 2011-12-08T19:29:57+00:00
- Post Title: Mass Effect 3 [.AFC]

> Reply from C00L12345
>
> Droolie wrote:It's because there are multiple audio files in an AFC file. Use VGMToolbox's cutter to look for RIFX headers and convert the output files with ww2ogg. That's what I did, at least (I have all the music from it). Is there a more specific steps. The 
look for RIFX headers

doesn't really help much.
In VGMToolbox's Advanced cutter, use the RIFF header preset, change the string it looks for from RIFF to RIFX, give the output files the wwise extension instead of wav, and there you go.
## Post #5
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2011-12-08T19:40:02+00:00
- Post Title: Mass Effect 3 [.AFC]

> Reply from Droolie
>
> C00L12345 wrote:Droolie wrote:It's because there are multiple audio files in an AFC file. Use VGMToolbox's cutter to look for RIFX headers and convert the output files with ww2ogg. That's what I did, at least (I have all the music from it). Is there a more specific steps. The 
look for RIFX headers

doesn't really help much.
In VGMToolbox's Advanced cutter, use the RIFF header preset, change the string it looks for from RIFF to RIFX, give the output files the wwise extension instead of wav, and there you go.
I figured all that out, the problem is there is no button to extract ;/


This program is buggy now I can't even drag the file in itself.
## Post #6
- Username: Droolie
- Rank: veteran
- Number of posts: 114
- Joined date: Fri Aug 19, 2005 11:31 pm
- Post datetime: 2011-12-08T19:52:05+00:00
- Post Title: Mass Effect 3 [.AFC]

> Reply from C00L12345
>
> I figured all that out, the problem is there is no button to extract ;/
This program is buggy now I can't even drag the file in itself.
You'll have to go to the Advanced cutter, configure it as I said and then drag the files onto the screen. I honestly have no idea why you wouldn't be able to drag the files in. Try restarting it, and if that doesn't work, download the newest revision?
## Post #7
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2011-12-08T19:57:12+00:00
- Post Title: Mass Effect 3 [.AFC]

> Reply from Droolie
>
> C00L12345 wrote:I figured all that out, the problem is there is no button to extract ;/
This program is buggy now I can't even drag the file in itself.
You'll have to go to the Advanced cutter, configure it as I said and then drag the files onto the screen. I honestly have no idea why you wouldn't be able to drag the files in. Try restarting it, and if that doesn't work, download the newest revision?
Ok I managed to fix it by changing compability. Thanks, will take a look later.
## Post #8
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2011-12-09T16:25:25+00:00
- Post Title: Mass Effect 3 [.AFC]

I followed what you say and I get:

KRO001_AUDIOLOG_03_A_D_INT.AFC]
  Warning: For string found at: 0x00000000, total file end will go past the end of the file (00650000)
  Extracted [KRO001_AUDIOLOG_03_A_D_INT_00000000.wwise] begining at 0x00000000, for string found at: 0x00000000, with size 0x00650008


It's not splitting the files at all.
## Post #9
- Username: Droolie
- Rank: veteran
- Number of posts: 114
- Joined date: Fri Aug 19, 2005 11:31 pm
- Post datetime: 2011-12-09T18:17:34+00:00
- Post Title: Mass Effect 3 [.AFC]

> Reply from C00L12345
>
> I followed what you say and I get:

KRO001_AUDIOLOG_03_A_D_INT.AFC]
  Warning: For string found at: 0x00000000, total file end will go past the end of the file (00650000)
  Extracted [KRO001_AUDIOLOG_03_A_D_INT_00000000.wwise] begining at 0x00000000, for string found at: 0x00000000, with size 0x00650008


It's not splitting the files at all.
After loading the RIFF style header preset, changing the search string to RIFX and the output extension to .wwise, try changing the cut size's byte order from Little Endian to Big Endian. I think that's what I did. 
I can't test anymore though as I don't have the original files anymore and the sample you posted seems to be gone (if you posted one).
If it doesn't work though I could just send you the files you need as I do still have the converted ones.
## Post #10
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2011-12-10T01:53:52+00:00
- Post Title: Mass Effect 3 [.AFC]

> Reply from Droolie
>
> C00L12345 wrote:I followed what you say and I get:

KRO001_AUDIOLOG_03_A_D_INT.AFC]
  Warning: For string found at: 0x00000000, total file end will go past the end of the file (00650000)
  Extracted [KRO001_AUDIOLOG_03_A_D_INT_00000000.wwise] begining at 0x00000000, for string found at: 0x00000000, with size 0x00650008


It's not splitting the files at all.
After loading the RIFF style header preset, changing the search string to RIFX and the output extension to .wwise, try changing the cut size's byte order from Little Endian to Big Endian. I think that's what I did. 
I can't test anymore though as I don't have the original files anymore and the sample you posted seems to be gone (if you posted one).
If it doesn't work though I could just send you the files you need as I do still have the converted ones.
Extraction is working now. It was an issue with the endianness. 

ww2ogg fails to output the correct audio.
## Post #11
- Username: Droolie
- Rank: veteran
- Number of posts: 114
- Joined date: Fri Aug 19, 2005 11:31 pm
- Post datetime: 2011-12-10T11:26:02+00:00
- Post Title: Mass Effect 3 [.AFC]

> Reply from C00L12345
>
> ww2ogg fails to output the correct audio.
Alright, if you could post a sample I would be able to figure out what I missed when explaining what you should do.
Or if you want me to upload all the audio in ogg format, I could just do that as well.
## Post #12
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2011-12-10T15:09:07+00:00
- Post Title: Mass Effect 3 [.AFC]

The contents of this post was deleted because of possible forum rules violation.
## Post #13
- Username: Droolie
- Rank: veteran
- Number of posts: 114
- Joined date: Fri Aug 19, 2005 11:31 pm
- Post datetime: 2011-12-10T15:20:24+00:00
- Post Title: Mass Effect 3 [.AFC]

I see what you did wrong. You forgot to extract "packed_codebooks.bin" from the ww2ogg zip file.
You should redownload it and extract everything: [http://hcs64.com/files/ww2ogg019.zip](http://hcs64.com/files/ww2ogg019.zip)
(man I wish other people would help me out on this forum as much as I'm helping you now)
## Post #14
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2011-12-10T17:14:21+00:00
- Post Title: Mass Effect 3 [.AFC]

> Reply from Droolie
>
> I see what you did wrong. You forgot to extract "packed_codebooks.bin" from the ww2ogg zip file.
You should redownload it and extract everything: http://hcs64.com/files/ww2ogg019.zip
(man I wish other people would help me out on this forum as much as I'm helping you now)
That doesn't make any difference, the OGG files can't be played still.

What do you need help with?
## Post #15
- Username: Droolie
- Rank: veteran
- Number of posts: 114
- Joined date: Fri Aug 19, 2005 11:31 pm
- Post datetime: 2011-12-10T17:32:21+00:00
- Post Title: Mass Effect 3 [.AFC]

> Reply from C00L12345
>
> Droolie wrote:I see what you did wrong. You forgot to extract "packed_codebooks.bin" from the ww2ogg zip file.
You should redownload it and extract everything: http://hcs64.com/files/ww2ogg019.zip
(man I wish other people would help me out on this forum as much as I'm helping you now)
That doesn't make any difference, the OGG files can't be played still.

What do you need help with?
It does make a difference. If I'm right, the OGG file from your sample should now be 20,9KB instead of the 186 bytes from before.
The OGG files are perfectly playable in Winamp, but for other players you may need to use Revorb on them (posted in [this topic](http://www.hydrogenaudio.org/forums/lofiversion/index.php/t64328.html)).

I personally need help with:
- [viewtopic.php?f=17&t=7799](http://forum.xentax.com/viewtopic.php?f=17&t=7799)
- [viewtopic.php?f=17&t=7322](http://forum.xentax.com/viewtopic.php?f=17&t=7322)
- [viewtopic.php?f=17&t=7713](http://forum.xentax.com/viewtopic.php?f=17&t=7713)
But I think the problems with those files are too big for anyone to want to help. :/
## Post #16
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2011-12-11T01:41:50+00:00
- Post Title: Re: Mass Effect 3 [.AFC]

I don't think you've converted the audio files at all. Are you trolling me?

It seems that i've done exactly everything you say, I can split the AFC files perfectly fine. 

The problem is the ww2ogg, it's not working at all. I know it's not the splitter because i've extracted them manually a few days back and it didn't work. I'm running out of options and i'm becomming frustrated because the programs are too buggy for use. Does anyone have a solution for this?

Thanks.
## Post #17
- Username: Droolie
- Rank: veteran
- Number of posts: 114
- Joined date: Fri Aug 19, 2005 11:31 pm
- Post datetime: 2011-12-11T10:30:10+00:00
- Post Title: Re: Mass Effect 3 [.AFC]

I have better things to do than trolling you so no I'm not doing that.

Here's an archive that includes some of my OGG files, converted with ww2ogg and then run through Revorb (I included both tools):
[http://www.box.com/s/do8r7d99ayojb4fohk9n](http://www.box.com/s/do8r7d99ayojb4fohk9n)
If my OGG files don't work for you, try another player (VLC, Winamp, etc) because the OGG files definitely work.

Your split files are the same as mine so there's no problem with that.

Try executing ww2ogg in command line like you should. The command is "ww2ogg filename.wwise". It normally tells you what the error is, if any. If there's no error, check if the outputted OGG file from your sample is now 20,9KB (with packed_codebooks.bin in your folder) instead of the 186 bytes from before. If it's still 186 bytes, something went wrong with ww2ogg. If it is 20,9KB, that means you should just use Revorb on it and play it in any OGG-compatible player.
## Post #18
- Username: guestman
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Feb 07, 2011 1:41 pm
- Post datetime: 2012-02-12T18:51:49+00:00
- Post Title: Re: Mass Effect 3 [.AFC]

Jesus H.F. Christ! Can someone just post a screenshot of a properly configured VGMToolbox???

I just read through 2 pages full of contradicting settings and nothing worked.

Please give real help. One screenshot would have made all other posts useless, can it happen please?
## Post #19
- Username: Spy
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Oct 10, 2011 6:41 pm
- Post datetime: 2012-02-14T23:46:24+00:00
- Post Title: Re: Mass Effect 3 [.AFC]

Here is an archive with all playable files that I managed to get out of afc files. I don't think I got out everything, because I'm missing some tracks. Anyway, here is to archive [http://uloz.to/xUQD74X/me3audio-rar](http://uloz.to/xUQD74X/me3audio-rar)
## Post #20
- Username: diego
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Feb 15, 2012 4:39 pm
- Post datetime: 2012-02-15T08:59:55+00:00
- Post Title: Re: Mass Effect 3 [.AFC]

Hi, 

I wanted to reopen this topic if I may. I have gone through all of the steps listed, but I have not had any success extracting the .afc files as described.  I was thinking perhaps something has changed in the files in between the Beta and the release of the official Demo.    Just to recap what I am doing:

I am using the Advanced Cutter from the VGM toolbox(dated 12/03/2011) with these options:
Loaded the RIFF Style Header Preset.
Changed the search string to RIFX.
Changed the output File extension to .wwise.
Changed the byte order to Big Endian.

To recreate the previous steps completely, I am trying to convert kro001_audiolog_03_a_D.Int.afc
But when I drag that file into the window, it completes the search for strings without errors, but it does not extract anything.   So far, the only way that I have been able to get a file to extract is to change the search string back to RIFF.  That, of course gives me the same extraction error that the previous poster had and creates a file the ww2ogg will not convert correctly.

I know you guys are really busy.  Since I don't have a clue what I am doing, I was hoping somebody might be interested in giving this issue another quick look.  

Thanks.
## Post #21
- Username: diego
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Feb 15, 2012 4:39 pm
- Post datetime: 2012-02-15T09:58:37+00:00
- Post Title: Re: Mass Effect 3 [.AFC]

Ha!
I stuck with it a little longer and finally figured out.  For the ME3 demo, The search criteria needs to be RIFF and the byte order should be Little Endian.  With the output file extension as .wwise.  This extracts correctly.  ww2ogg is working fine as well.
## Post #22
- Username: Kyp
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Mar 01, 2010 1:10 am
- Post datetime: 2012-02-17T14:24:55+00:00
- Post Title: Re: Mass Effect 3 [.AFC]

Hi guys!
I updated my original afc2ogg app i posted here about a year ago, and now it works with Mass Effect 3 files.
It makes all this extracting a lot easier.

Get it here: [http://kypapps.co.cc/index.php/afc2ogg](http://kypapps.co.cc/index.php/afc2ogg)
(it's too big for attachment)

It uses my own algorythm to split the afc file to single wave files, then ww2ogg to convert them, and revorb to fix them. (If you dont want to use revorb, just delete it from data directory).
## Post #23
- Username: ScorpyX
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jun 16, 2011 12:38 pm
- Post datetime: 2012-03-23T21:35:44+00:00
- Post Title: Re: Mass Effect 3 [.AFC]

BIG Thanks Kyp - you're the MAN
