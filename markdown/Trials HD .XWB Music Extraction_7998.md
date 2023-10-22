## Post #1
- Username: Kaisonic
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Jan 06, 2012 6:14 am
- Post datetime: 2012-01-05T23:11:56+00:00
- Post Title: Trials HD .XWB Music Extraction

Hey everyone! I've been going through a lot of games extracting music, and most of them are a simple case of discovering the file format, getting the right tool from Google, and extracting. But this one has got me stumped.

I'm trying to extract the music from the Xbox Live Arcade game Trials HD. I transferred the file to my PC, extracted everything with wxPirs, and ended up with a pretty simple structure - a Music.xwb file in a XACT folder, and a few pak files in the data folder. I used QuickBMS with the pak script from Trials 2 SE to extract those and found more xwb files (sound effects, voiceovers, etc) and xsb files, including Music.xsb. So here's what I've tried so far on Music.xwb:

1. unxwb - saw the files inside as WMA, extracted with WAV extension and RIFF/WAVE header, but they won't play in VLC
2. towav - doesn't do anything with Music.xwb, extracted WAV files, or extracted raw files (.dat with unxwb)
3. xactxtract (the German one) - it was hard to find this one, as file-upload.net doesn't work for me, but this didn't work (I don't remember exactly what it did and I don't want to try again because AVG kept complaining about it)
4. xactextract ([http://stryder.rev-crew.info/blog/2011/ ... xwb-files/](http://stryder.rev-crew.info/blog/2011/08/19/extracting-bastion-sounds-from-xact-wave-banks-xwb-files/)) - this initially didn't work because Music.xwb is big endian and the program was designed for a PC game (which is little endian). After messing around with the source code a lot, I got it to read the header version and signature, as well as the proper number of files, but they're all flagged as 1 (XMA). When I remove the check for format 3 (xWMA) the program crashes with a call to abort().
5. xWMAEncode - needs a valid xWMA header to work, and only xactextract can create one
6. xmaencode - doesn't work on the raw .dat files and runs forever on the .wav files (which end up just being loud static)
7. xma_test (xma_parse) - complains about skip bits not matching previous packet overflow on both .dat and .wav files
8. EkszBox - freezes when trying to open Music.xwb
9. VGMToolBox - I did some messing around the XMA converter but couldn't get anything to work

The Music.xsb seems to be useless because there aren't any filenames in there, but I'm sure it has some purpose. Also, all of the other xwb's (found in the pak files) have files seen as XMA in unxwb, and towav spit out playable wav files for every xwb with no trouble. I haven't tried it, but those xsb appear to have filenames as well.

So I'm at a loss as to what's different about Music.xwb. I still can't tell if the files inside are XMA or xWMA. Anyone have any ideas?

P.S. Here's the xwb and xsb files I'm working with: [redacted]
## Post #2
- Username: Kaisonic
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Jan 06, 2012 6:14 am
- Post datetime: 2012-01-06T06:02:03+00:00
- Post Title: Trials HD .XWB Music Extraction

Progress! I did some hardcore step-through debugging and found out I had changed something I shouldn't have... then I added a couple more endian-changers and the program works! It was reading the wrong area, and it turns out all the files ARE actually format 3 (xWMA). I tried to play the extracted xwma files in VLC, and it worked! ...er, sort of. The length seems to be right, but it skips around the beginning and a couple times throughout, and then cuts itself off. Running the file through xWMAencode.exe only results in a blank .wav file that is the same length as the song.

So I'm guessing there's just an incorrect value in the header somewhere that's not letting it be played or converted properly. Anyone have any ideas?
## Post #3
- Username: Kaisonic
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Jan 06, 2012 6:14 am
- Post datetime: 2012-01-06T06:55:54+00:00
- Post Title: Trials HD .XWB Music Extraction

Success! I was wrong - VLC just wasn't playing the XWMA files properly. I dropped the WAV files in VLC and they played great! Dropped in Audacity - even better!

So now I guess this thread is for historical reference. Maybe someday someone will be Googling how to extract XWMA files from an Xbox 360 XWB (much like I was) and come across this thread. I removed the XWB I was working with since that's technically copyright infringement, but here's a link to the program I used and the source code (and xWMAEncode.exe, so everything you need is in there):

[xact360extract, a modified xactextract for use with big endian (Xbox 360) files](http://www.kaisonic.net/xact360extract.zip)

Feel free to use my contact info on Kaisonic.net if you have any questions or need help with one of these files!

Thanks to [http://stryder.rev-crew.info/blog/](http://stryder.rev-crew.info/blog/) for the original program!
## Post #4
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2012-01-06T19:13:09+00:00
- Post Title: Trials HD .XWB Music Extraction

Thanks for the tool!

However is it possible to make one for XMA as well?
## Post #5
- Username: Kaisonic
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Jan 06, 2012 6:14 am
- Post datetime: 2012-01-06T20:24:42+00:00
- Post Title: Trials HD .XWB Music Extraction

If an XWB bank has XMA files, then you can either use [towav.exe](http://www.ctpax-x.ru/index.php?goto=files&show=24) (just give it the xwb file and it should extract the XMAs and convert to WAVs) or you can use aluigi's [unxwb.exe](http://aluigi.altervista.org/papers/unxwb.zip), which will extract the XMA files with a WAV extension, and then you should be able to use Microsoft's xmaencode.exe to convert those back to plain WAVs.

P.S. The XWB files with XMAs in Trials HD (on the Xbox 360) were processed fine by both, so I think those programs already handle endian-ness.
## Post #6
- Username: Liandril
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Aug 02, 2010 11:11 pm
- Post datetime: 2012-01-07T14:06:45+00:00
- Post Title: Trials HD .XWB Music Extraction

> Reply from Kaisonic
>
> 
The Music.xsb seems to be useless because there aren't any filenames in there, but I'm sure it has some purpose. Also, all of the other xwb's (found in the pak files) have files seen as XMA in unxwb, and towav spit out playable wav files for every xwb with no trouble. I haven't tried it, but those xsb appear to have filenames as well.
Just a quick note in case you're trying to get file names for your extracted files: .xsb does not store the file names, but the cue names. A little more information about .xsb files can be found in [this](http://forum.xentax.com/viewtopic.php?f=17&t=5486) thread.
## Post #7
- Username: Kaisonic
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Jan 06, 2012 6:14 am
- Post datetime: 2012-01-07T18:16:29+00:00
- Post Title: Trials HD .XWB Music Extraction

Ah, yes. The XWB format has definitions for file names (or at least 64-character descriptions), but the Trials HD one has none. Unxwb will display them in verbose mode, if they exist, but won't automatically name them.

I guess I'll have to name these songs myself!
## Post #8
- Username: namgorf
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jan 06, 2020 10:46 am
- Post datetime: 2020-01-06T02:54:54+00:00
- Post Title: Trials HD .XWB Music Extraction

Thank you Kaisonic, this thread is still delivering 8 years on. I extracted the music from an obscure indie title called "I MAED A GAM3 W1TH Z0MB1ES!!!1" with the help of the information in this thread. 

I had some trouble tracking down towav.exe so here's a mirror on my server.  [http://namgorf.com/towav.zip](http://namgorf.com/towav.zip)
