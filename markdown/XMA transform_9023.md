## Post #1
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-06-01T16:29:49+00:00
- Post Title: XMA transform

Hello fellow revvies, coders, game modders, VGM lovers and gamers!

Several years have passed now and till now I found that the majority of the XMA formats and variations can be decoded with toWAV after a proper manipulation. My goal is to develop a script that has the ability to transform all kinds of XMA variations to files that are decodable by toWAV.
For the script in the attachment to work you'll need xma_parse ([http://hcs64.com/vgm_ripping.html](http://hcs64.com/vgm_ripping.html)) in the same path than the script or in any path that is added to the PATH variable in Windows.
Please read the instructions inside the script, you WILL need to adjust variables!

If you encounter any XMA file that doesn't work with this script, please post here!
I'll update the script from time to time when I encounter new variants.

Good luck!
And Remember: a little thanks doesn't hurt. 


Major Update 2013-09-10

Ubisoft multilayer XMA script awaiting approval: [viewtopic.php?f=17&t=9023&p=88021#p88021](http://forum.xentax.com/viewtopic.php?f=17&t=9023&p=88021#p88021)
[XMA_transform_2016-01-28.zip](https://xentaxbackup.github.io/file/10380_XMA_transform_2016-01-28.zip)
## Post #2
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2012-06-02T06:36:09+00:00
- Post Title: XMA transform

fwiw, my xmash program (bottom of [http://hcs64.com/vgm_ripping.html](http://hcs64.com/vgm_ripping.html) ) will handle most of these steps for some of the most common XMA types (FSB, RIFF wav, .bnk).  Might be a good first thing to try, it'll save you everything but running the output through towav.

Good to have some clear directions for when that doesn't work, though.
## Post #3
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-06-12T13:43:34+00:00
- Post Title: XMA transform

Checked out your xmamash program and very soon found xma files that didn't transform properly.
I've written a QuickBMS script that calls xma_parse externally and which supports all XMA variants I've encountered so far. =) 
No pun intended though, I don't want to undermine your program!
## Post #4
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2012-06-12T22:45:29+00:00
- Post Title: XMA transform

Thanks!!

So this works only if the xma has a RIFF header or can it work on non-Header'ed XMA's?
## Post #5
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-06-13T08:35:56+00:00
- Post Title: XMA transform

I've added one little variation where thee's an "xma." before the RIFF/RIFX but of course there are other variations.
Still need to add multichannel and XMA1 support though. Just PM me files that aren't processable right away.
## Post #6
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-06-18T14:15:22+00:00
- Post Title: XMA transform

MAJOR UPDATE:
Now supports *.SoundNodeWave files from the Unreal 3 engine! 
Still have to work out a correct marker transformation though. If anyone is firm with wave markers, just post here and you could help. 

EDIT: just made another quick update to prevent the saving of the SoundNodeWave header when there are no markers present. I don't want to confuse anyone.
## Post #7
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-06-24T16:26:06+00:00
- Post Title: XMA transform

MAJOR UPDATES:
- corrected function call to COMTYPE and clog (thanks Luigi  )
- simplified runs with different block sizes
- added option to retrieve the file name from the cue section (e.g. The Amazing Spider-Man, Star Wars: The Force Unleashed II)
- added multichannel support !!! 

This scripts is getting bigger and bigger and there are already two XMA types here I want to add support for!

Don't forget to click that little you-know-which button on the first post.
## Post #8
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-06-26T17:23:19+00:00
- Post Title: XMA transform

Update

I just made the script a little bit better to use with the introduction of the BLOCKSIZE variable:
For the first run, only select one file and set the blocksize variable to "" (empty). The script will try to parse the file with the most common block sizes (stated in the file name). 
Set BLOCKSIZE to the correct blocksize (hex notation). The biggest file usually has the right blocksize. Note: If the blocksize is 0x10000, the files parsed with 0x10000, 0x20000 and 0x40000 are the all same size. Now you can select all files you want to process. The script will now leave out the blocksize.
## Post #9
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-06-28T14:43:16+00:00
- Post Title: XMA transform

UPDATE

Something with the heuristics was wrong, so I skipped some automated blocksize identification. This will be implemented later on anyway.
## Post #10
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-06-29T01:05:55+00:00
- Post Title: XMA transform

UPDATE

XMA variant with hex "00000000 00000200" file start and stream start at 0x800 supported. Encountered in "Are You Smarter Than A 5th Grader: Make the Mark" (XBLA) as *.wav files but there may by other games that use this variant.
## Post #11
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-06-30T18:26:36+00:00
- Post Title: XMA transform

Update

Added another *.SoundNodeWave variant I just encountered in Alien Breed: Evolution (XBLA). 

Help me to update this script by sending me XMA files that won't transform properly!
And don't forget to leave a thanks.
## Post #12
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2012-06-30T19:12:25+00:00
- Post Title: XMA transform

Hey alpha that max payne 3 xma file i sent you is it possible if that can be transformed with the script?
## Post #13
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-07-03T02:57:21+00:00
- Post Title: XMA transform

> Reply from OrangeC
>
> Hey alpha that max payne 3 xma file i sent you is it possible if that can be transformed with the script?
Uh no. I didn't save the sample, can you send me one again?
## Post #14
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-07-03T02:59:42+00:00
- Post Title: XMA transform

Update

Just a small update: I added the option to change between XMA2 and XMA1 as source file. That only for now until I've coded some automatic blocksize/XMA version checker.
P.S.: XMA1 files just encountered inside the XWB archive of Bankshot Billiards 2 (XBLA).
## Post #15
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2012-07-03T13:18:36+00:00
- Post Title: XMA transform

> Reply from AlphaTwentyThree
>
> OrangeC wrote:Hey alpha that max payne 3 xma file i sent you is it possible if that can be transformed with the script?
Uh no. I didn't save the sample, can you send me one again?

Hehe i will have to download the game again and get the sample as the sendspace link died.
## Post #16
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-07-03T17:06:19+00:00
- Post Title: Re: All things XMA

UPDATE

1. Introduced the option to skip the parsing of files. This needs to be applied when the stream already has the appropriate form, only the header needs changing. And yes, this will also be implemented into the automated identifier later. 
2. Added support for both *.res variants from the Battlefield Engine.  

TIP: When all files from the test run only consist of the XMA header, try to set XMAVERSION to 1. If that doesn't help, set SKIPPARSE to 1. If that doesn't help either: PM ME!
## Post #17
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-07-04T20:47:40+00:00
- Post Title: Re: All things XMA

UPDATE

Added support for xma streams with "XWV " identifier (encountered in Bloody Good Time XBLA as *.360.wav but I guess there are more games with this format). 

How many more variants can there possibly be out there.... But hey, that's what I'm here for. 

To be honest, those *.res files don't properly work yet (only that one variant) - I'll need to implement the ea_multi_xma functionality, too. Nothing too special but unfortunately I don't have a multilayered EA XMA file here, so if anybody can provide me with one, I'll be happy to include the complete heuristics. 

Remember: A little thanks doesn't hurt.
## Post #18
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-07-04T21:46:07+00:00
- Post Title: Re: All things XMA

UPDATE

Coincidentially stumbled upon another variant and added support: Microsoft XNA Framework *.xnb files (encountered in Boulder Dash XL XBLA). 

Remember: A little thanks doesn't hurt.
## Post #19
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2012-07-04T21:52:31+00:00
- Post Title: Re: All things XMA

Thanks!
## Post #20
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-07-06T12:05:30+00:00
- Post Title: Re: All things XMA

MAJOR UPDATE!

Ok, this is the biggest update so far and I've worked several hours at this one. The then already big script with 250 lines now has more than 700.

First of all, I've given the whole script a more comprehensive structure: I've sorted the functions to where they are used and given each one a header. To find what you're searching, I've added a table of contents to copy and search for the needed paragraph.

And then there are the internal updates and additions:
1. introduction of a more sophisticated test mode for the first run (very useful):
- always writes two unparsed files to disk, one with header (if the file doesn't need to be parsed at all), one without header for manual testing with xma_parse (if the test mode doesn't produce any usable results)
- tests various block sizes and both xma versions in the parsing and writes files to disk with names according to the xma_parse function call
- if the file is multichannel, only the first channel pair is parsed in test mode to speed it up
- the test mode can additionally be sped up a great deal by only testing for the most common block sizes and skip the XMA1 tests
2. new file supports/corrections:
- option to skip file parsing and just add a manipulated header in the final run
- EA XMA multilayer variant working for single layer (multi_ea_xma functionality implemented)
- support for headerless streams - now the script can also function as a normal header adder!
- support for RIFF files with XMA2 identifier after the data stream
- corrected the processing for big endian RIFX files
3. some major internal changes regarding processing order and option processing (basically, everything is better than before  ).

This is a really big step forward. It accelerates XMA transformation processes by far and is much easier to use and understand!
So, try out the new script and if you like it, click the "Thank" button of this post (and for the first one if you haven't done so already)
## Post #21
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2012-07-06T17:15:32+00:00
- Post Title: Re: All things XMA

WOW WOW WOW!! alpha your work on xma transformation is just phenomenal!! I cannot wait for the other features such as blocksize detection.

EDIT: Strange your zip file says: no files to extract.
## Post #22
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2012-07-06T17:35:03+00:00
- Post Title: Re: All things XMA

What about Resident Evil 6 XMA??
## Post #23
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-07-07T01:23:55+00:00
- Post Title: Re: All things XMA

> Reply from OrangeC
>
> WOW WOW WOW!! alpha your work on xma transformation is just phenomenal!! I cannot wait for the other features such as blocksize detection.
Glad you like it. 

> Reply from OrangeC
>
> EDIT: Strange your zip file says: no files to extract.
fixed
## Post #24
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-07-07T01:24:29+00:00
- Post Title: Re: All things XMA

> Reply from C00L12345
>
> What about Resident Evil 6 XMA??
Try my script and PM me if it doesn't work.
## Post #25
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2012-07-07T11:18:16+00:00
- Post Title: Re: All things XMA

> Reply from AlphaTwentyThree
>
> C00L12345 wrote:What about Resident Evil 6 XMA??
Try my script and PM me if it doesn't work.
Thanks alot
## Post #26
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-07-07T19:03:08+00:00
- Post Title: Re: All things XMA

UPDATE

Added support for reversed-header RIFF xma, used in Resident Evil 6. 
Note that the decoded wave files may play with the exact double frequency, so you'll need to change that, e.g. with this script (only apply on the decoded wave files!):

```
get FREQ long
math FREQ /= 2
get SIZE asize
putVarChr MEMORY_FILE SIZE 0
log MEMORY_FILE 0 0
append
log MEMORY_FILE 0 SIZE
append
putVarChr MEMORY_FILE 0x18 FREQ long
get NAME basename
string NAME += "_new.wav"
log NAME 0 SIZE MEMORY_FILE
```
## Post #27
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-07-07T23:41:07+00:00
- Post Title: Re: All things XMA

UPDATE

After some tests and undecodable multichannel SoundNodeWave, I made some corrections and improved and expanded the XMA stream start detection.
Unless you encounter some special files, you won't notice any difference. Still I thought it's enough for an update.
## Post #28
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-07-25T18:19:02+00:00
- Post Title: Re: All things XMA

Some *.soundnodewave files didn't work, so I made another little update a week ago - added a much more sophisticated way to detect xma starts.
Process has been slow recently, but I'll update the script frequently as soon as I've overcome the motivational blockade for another update. 
Next update will include the scanning of some miscalleneous format that may or may not include an XMA stream. So you'll be at least able to tell if the file contains an XMA start or not and can send me the file.
Another thing: Including automatic blocksize detection isn't economical at all because the script would check all possibilities for each file, even of run in batch mode. Thus, it will take much too long - it's faster to run the test mode for one file and set the variables accordingly. And checking for the biggest file from the test mode shouldn't be the problem here.
## Post #29
- Username: nitoiviorel
- Rank: beginner
- Number of posts: 21
- Joined date: Fri Oct 07, 2011 6:37 pm
- Post datetime: 2012-09-10T10:38:35+00:00
- Post Title: Re: All things XMA

I made extract some files without name and extension from chuncksaudio.toc .sb.
I start demux that 774 files using ea multi xma.
All was fine but i meet a problem:not exactly but i demux only 60%.ea_multi_xma skipped many files and i cant demux.

I open quickbms,select ur script then select file wich result from chuncksaudio.toc and nothing hapening.
Need for Speed The Run xbox file
## Post #30
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-09-10T11:49:34+00:00
- Post Title: Re: All things XMA

Please remove the links first and PM them to me!
I haven't finished my research on the EA XMA variant yet. But just one variant missing, the others seem to work fine. But until everything works, I won't add it to the transforming script. 
Anyway, it's always practical to have more examples to look for other variants and to test the script.
## Post #31
- Username: nitoiviorel
- Rank: beginner
- Number of posts: 21
- Joined date: Fri Oct 07, 2011 6:37 pm
- Post datetime: 2012-09-10T12:36:13+00:00
- Post Title: Re: All things XMA

done
## Post #32
- Username: Gromber
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Oct 06, 2010 4:42 am
- Post datetime: 2012-09-15T18:33:16+00:00
- Post Title: Re: All things XMA

hi with this tool can i convert *.360.wav audio from orangebox 360?  i need some tool!!! 

[viewtopic.php?f=17&t=4967&hilit=valve](http://forum.xentax.com/viewtopic.php?f=17&t=4967&hilit=valve)

thanks
## Post #33
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-10-03T15:15:37+00:00
- Post Title: Re: All things XMA

> Reply from Gromber
>
> hi with this tool can i convert *.360.wav audio from orangebox 360?  i need some tool!!! 

viewtopic.php?f=17&t=4967&hilit=valve

thanksPM me a sample and I'll take a look.
## Post #34
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-10-03T15:23:39+00:00
- Post Title: Re: All things XMA

MAJOR UPDATE
(line count rises to over 900 with this  )

Another long-overdue update: Scanning for possible XMA streams!
Notes:
I have only included the XMA heuristics I stumbled upon and included in the script. This doesn't mean that a correct XMA start can ALWAYS be detected because there can be data structures that accidentially look exactly like an XMA stream but actually aren't.
the scanning function will only be enabled when no known header type is found
once a possible stream start is detected, the file is header-cut to this position and written to disk (offset included in name for later research, e.g. look for a valid frequency)
the written file then has to be run through the script again with testmode on to check if the XMA is valid or not
I know it's possible to test the last step internally with xma_parse ("-x" option) but for now this should suffice. As soon as I find a file with valid XMA streams included, I'll update the script again. I know that the Viva Pinata uses these but I'll take a look at them some time in the future (when I'm motivated enough ).
## Post #35
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-10-06T01:06:03+00:00
- Post Title: Re: All things XMA

Just corrected a little mistake that prevented some XWV files to convert properly.
## Post #36
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-10-07T12:31:25+00:00
- Post Title: Re: All things XMA

UPDATE

Added files with XMA2 multichannel header. toWAV only seems to support those, i.e. it decodes them - but the file sizes for the channel pairs are different, so the header is not fully supported. So I updated the script to parse and split like with multichannel files with the standard RIFF header. Tested with Deadly Premonition (X360) but should work on others, too. If I remember correctly, Ace Combat 6 also uses this kind of header and eventually that was the reason why the format was semi-implemented in toWAV.
## Post #37
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2012-10-09T11:44:24+00:00
- Post Title: Re: All things XMA

lets say I have
bgm4000.xma

using your script it converts it into 3 .xma files

then i drag these onto towav and it gives me 3 wav files which go for like 5 secs what am I doing wrong
## Post #38
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-10-09T13:24:48+00:00
- Post Title: Re: All things XMA

> Reply from cra0
>
> lets say I have
bgm4000.xma

using your script it converts it into 3 .xma files

then i drag these onto towav and it gives me 3 wav files which go for like 5 secs what am I doing wrong
Have you used testmode in the first run to get the blocksize and xma version?
If not, the thing you are doing wrong is not reading the manual.
## Post #39
- Username: Gromber
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Oct 06, 2010 4:42 am
- Post datetime: 2012-10-09T16:00:23+00:00
- Post Title: Re: All things XMA

Thanks for the work and the updates!!!  and for the help  
I have to look carefully, i wanted to add spanish voices to orange box, but there are many audio and i dont know how to convert again to 360.wav easily     


I have pc voices in .wav

Edit: i can convert pc spanish voices to xma with xma2encode.exe, it is posible with a script add XWV compatibility? thanks!
## Post #40
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2012-10-10T11:20:17+00:00
- Post Title: Re: All things XMA

> Reply from AlphaTwentyThree
>
> cra0 wrote:lets say I have
bgm4000.xma

using your script it converts it into 3 .xma files

then i drag these onto towav and it gives me 3 wav files which go for like 5 secs what am I doing wrong
Have you used testmode in the first run to get the blocksize and xma version?
If not, the thing you are doing wrong is not reading the manual.
Never mind I ended up using xmash it works perfectly however when it converts it makes 3 wav files which sound exactly the same except the 2nd one is only left audio, which one do i take 1 or 3
## Post #41
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-10-10T15:31:31+00:00
- Post Title: Re: All things XMA

> Reply from cra0
>
> AlphaTwentyThree wrote:cra0 wrote:lets say I have
bgm4000.xma

using your script it converts it into 3 .xma files

then i drag these onto towav and it gives me 3 wav files which go for like 5 secs what am I doing wrong
Have you used testmode in the first run to get the blocksize and xma version?
If not, the thing you are doing wrong is not reading the manual. 
Never mind I ended up using xmash it works perfectly however when it converts it makes 3 wav files which sound exactly the same except the 2nd one is only left audio, which one do i take 1 or 3Please also send me the file, I want to check if my scripts works properly.
I highly doubt they actually are the same, it's a surround file. Unless you don't look at it with an audio editor, you can't say that. Surround is normall Fl-Fr-C-LFE-Rl-Rr, so the "only left channel" you're talking about is the center/LFE pair....
## Post #42
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2012-10-11T04:29:43+00:00
- Post Title: Re: All things XMA

> Please also send me the file, I want to check if my scripts works properly.
>
> I highly doubt they actually are the same, it's a surround file. Unless you don't look at it with an audio editor, you can't say that. Surround is normall Fl-Fr-C-LFE-Rl-Rr, so the "only left channel" you're talking about is the center/LFE pair....
Ok I have packed the files for you to experiment with

original/bgm6666.xma 
after_xmash/
then_after_towav/

(link removed due to copyright)

 
Now tell me which wav file I take that is 2 channel stereo
## Post #43
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-10-11T10:56:37+00:00
- Post Title: Re: All things XMA

> Reply from cra0
>
> Now tell me which wav file I take that is 2 channel stereo
I don't know what the problem is here. It's a standard 6 ch XMA 2 files with blocksize 0x20000, it decodes correctly to three channel pairs with both xma_mash and my script. *_1.xma=Fl/Fr, *_2.xma=C/LFE, *_3.xma=Rl/Rr - as always. I don't even get your question...
## Post #44
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-10-21T15:00:26+00:00
- Post Title: Re: All things XMA

UPDATE

Added two more header variants 
- FUNl header found in Men in Black: Alien Crisis
- MUSX header (various Electonic Arts games)
Else, I've established a variable to toggle the scanning function because it's too experimental I fancied. 

Line count has risen to over 1000!
## Post #45
- Username: gnoyr13
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Oct 27, 2012 4:48 pm
- Post datetime: 2012-10-27T13:40:10+00:00
- Post Title: Re: All things XMA

Not work with Quake 4 XMA.
[](http://hostingkartinok.com)
## Post #46
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-10-27T15:20:10+00:00
- Post Title: Re: XMA transform

> Reply from gnoyr13
>
> Not work with Quake 4 XMA.First: remove the file, it's copyrighted. Second: PM me.
## Post #47
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-10-27T17:29:39+00:00
- Post Title: Re: XMA transform

UPDATE

Added support for the Quake 4 header variant.
## Post #48
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2012-10-28T14:44:18+00:00
- Post Title: Re: XMA transform

Toolkit - [http://www.mediafire.com/?6460fi1kw1mgfp6](http://www.mediafire.com/?6460fi1kw1mgfp6)

Test script with one game yet - Shadow Complex. 100% Work.
## Post #49
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-10-28T15:58:26+00:00
- Post Title: Re: XMA transform

Thanks. 
However, apart from towav all other programs and my script will chnge over time, so it would be helpful if you'd include links to the download pages for each one (aluigi.org/quickbms.htm, [http://hcs64.com/vgm_ripping.html](http://hcs64.com/vgm_ripping.html), [viewtopic.php?f=17&t=9023](http://forum.xentax.com/viewtopic.php?f=17&t=9023)).
## Post #50
- Username: alanrikkin1
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jul 14, 2012 5:11 am
- Post datetime: 2012-10-30T23:55:52+00:00
- Post Title: Re: XMA transform

Hello !

[http://fr.packupload.com/PXHZKWXCTXI](http://fr.packupload.com/PXHZKWXCTXI) (From Assassin's Creed III ) This .xma (i'm not sur it's a good xma) don't work.
## Post #51
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-10-31T01:19:13+00:00
- Post Title: Re: XMA transform

> Reply from alanrikkin1
>
> Hello !

http://fr.packupload.com/PXHZKWXCTXI (From Assassin's Creed III ) This .xma (i'm not sur it's a good xma) don't work.Well, that's a Wwise ogg - that's why the script doesn't work. 
I could implement some "other format" messages some time - but not right now.
## Post #52
- Username: alanrikkin1
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jul 14, 2012 5:11 am
- Post datetime: 2012-10-31T04:37:43+00:00
- Post Title: Re: XMA transform

> Reply from AlphaTwentyThree
>
> alanrikkin1 wrote:Hello !

http://fr.packupload.com/PXHZKWXCTXI (From Assassin's Creed III ) This .xma (i'm not sur it's a good xma) don't work. Well, that's a Wwise ogg - that's why the script doesn't work. 
I could implement some "other format" messages some time - but not right now.
Shame on me !
Ok thanks but i can't extract the oggs files with your tool ( here : [viewtopic.php?p=80192#p80192](http://forum.xentax.com/viewtopic.php?p=80192#p80192) )
[http://image.noelshack.com/fichiers/201 ... 8158-a.png](http://image.noelshack.com/fichiers/2012/44/1351658158-a.png)

(Désolé pour mon anglais très pauvre, je suis français.   )
## Post #53
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-10-31T13:06:33+00:00
- Post Title: Re: XMA transform

> Reply from alanrikkin1
>
> AlphaTwentyThree wrote:alanrikkin1 wrote:Hello !

http://fr.packupload.com/PXHZKWXCTXI (From Assassin's Creed III ) This .xma (i'm not sur it's a good xma) don't work. Well, that's a Wwise ogg - that's why the script doesn't work. 
I could implement some "other format" messages some time - but not right now.
Shame on me !
Ok thanks but i can't extract the oggs files with your tool ( here : viewtopic.php?p=80192#p80192 )
http://image.noelshack.com/fichiers/201 ... 8158-a.png

(Désolé pour mon anglais très pauvre, je suis français.   )Yeah I know - the script is still in beta and doesn't work for all akpk archives. Problem is the folder names with that zero in between for which I neeed to write another internal function. Will do later this week.
## Post #54
- Username: zhichuner
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Sep 17, 2011 10:51 pm
- Post datetime: 2012-11-04T01:18:53+00:00
- Post Title: Re: XMA transform

Hello AlphaTwentyThree
[http://www.packupload.com/9UWNF8MLNAS](http://www.packupload.com/9UWNF8MLNAS)  (From Assassin's Creed III ) This .xma2stream(from RIFX to uxma)don't work
## Post #55
- Username: zhichuner
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Sep 17, 2011 10:51 pm
- Post datetime: 2012-11-04T01:26:14+00:00
- Post Title: Re: XMA transform

I need riffheader32khz.hed
## Post #56
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-11-04T12:06:29+00:00
- Post Title: Re: XMA transform

> Reply from zhichuner
>
> Hello AlphaTwentyThree
http://www.packupload.com/9UWNF8MLNAS  (From Assassin's Creed III ) This .xma2stream(from RIFX to uxma)don't workYes it works. XMA2, blocksize 0x8000, 32kHz.
## Post #57
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-11-04T12:07:04+00:00
- Post Title: Re: XMA transform

> Reply from zhichuner
>
> I need riffheader32khz.hedUh, I don't know what you want or what this has to do with the script...
## Post #58
- Username: zhichuner
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Sep 17, 2011 10:51 pm
- Post datetime: 2012-11-05T04:14:20+00:00
- Post Title: Re: XMA transform

This is my information

Where the problem is
## Post #59
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-11-05T06:07:56+00:00
- Post Title: Re: XMA transform

Yes, that was exactly my question: Where IS the problem?
## Post #60
- Username: zhichuner
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Sep 17, 2011 10:51 pm
- Post datetime: 2012-11-05T06:41:31+00:00
- Post Title: Re: XMA transform

[www.packupload.com/TGMYRW1YH36](http://www.packupload.com/TGMYRW1YH36)
it can be decoded by towav but  wrong size
## Post #61
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-11-05T18:36:08+00:00
- Post Title: Re: XMA transform

This is an XMA with a wrong frequency in the header. Where does it come from? Have you changed it? Have you run xmatransform on it? Have you read the instructions of xmatransform?
## Post #62
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-11-05T18:45:25+00:00
- Post Title: Re: XMA transform

UPDATE

Wrong sizes in RIFF header don't crash the script anymore.
## Post #63
- Username: diabolik83
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Mar 24, 2011 11:42 pm
- Post datetime: 2013-01-02T14:09:50+00:00
- Post Title: Re: XMA transform

hello I have a file for you    Your script does'nt work with it

[http://depositfiles.com/files/5lnwn84a8](http://depositfiles.com/files/5lnwn84a8)
## Post #64
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2013-01-09T17:55:24+00:00
- Post Title: Re: XMA transform

Nope, works perfectly fine.
## Post #65
- Username: diabolik83
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Mar 24, 2011 11:42 pm
- Post datetime: 2013-01-12T17:53:13+00:00
- Post Title: Re: XMA transform

ah...can you explain me, how did you make it please?
## Post #66
- Username: zouzou69
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Mar 10, 2011 6:46 pm
- Post datetime: 2013-01-17T07:08:55+00:00
- Post Title: Re: XMA transform

can someone know how to edit the sbs et sbr files from fifa games ?

i would edit this files for pc version and xbox version of fifa 13 to change the audio ..the sbs contains probably xma files



here the exemple of the two files.

if someone could transform this ..thks a lot

[http://www.datafilehost.com/download-5b1f42f3.html](http://www.datafilehost.com/download-5b1f42f3.html)

THANKS A LOT
## Post #67
- Username: Scorpion2k7
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Jan 18, 2013 12:39 am
- Post datetime: 2013-02-03T15:21:29+00:00
- Post Title: Re: XMA transform

Not work with Shin Hokuto Musou/Ken's Rage 2 XMA.

[http://www.mediafire.com/?3frbbpnh8a7gd5f](http://www.mediafire.com/?3frbbpnh8a7gd5f)
## Post #68
- Username: ma3x666
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Nov 13, 2010 10:49 pm
- Post datetime: 2013-04-24T15:30:39+00:00
- Post Title: Re: XMA transform

Not work for Wet, take a look please... 
[http://www.mediafire.com/?4c5ih45coztttdm](http://www.mediafire.com/?4c5ih45coztttdm)
PS. Sorry, everything works well, my bad!
## Post #69
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2013-06-05T14:04:40+00:00
- Post Title: Re: XMA transform

I'll try this with Dark Souls XMA
## Post #70
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2013-06-06T12:49:12+00:00
- Post Title: Re: XMA transform

@Devilot

Dark Souls on the Xbox 360 doesn't use XMA. It uses PCM WAV IIRC
## Post #71
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2013-06-07T00:52:40+00:00
- Post Title: Re: XMA transform

> Reply from brendan19
>
> @Devilot

Dark Souls on the Xbox 360 doesn't use XMA. It uses PCM WAV IIRC

Pretty sure the ps3 version uses that in fsb containers and the xbox 360 uses xma in fsb.
## Post #72
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2013-09-10T21:15:44+00:00
- Post Title: Re: XMA transform

MAJOR UPDATE

I think I may have understood the Ubisoft multilayer XMA format.

I've attached the script that at least worked with my samples. It extracts the layers, parses them and adds a header.
I will let this go around for some time to see if it works alright before implementing it in my xma transform script.
[ubi_xma_2013-09-14.zip](https://xentaxbackup.github.io/file/6615_ubi_xma_2013-09-14.zip)
## Post #73
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2013-09-14T14:53:56+00:00
- Post Title: Re: XMA transform

Just updated the above script to support single-layer files.
## Post #74
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2013-10-04T11:09:17+00:00
- Post Title: Re: XMA transform

UPDATE

Added the RAKI variant from Rayman: Legends.
## Post #75
- Username: MiLØ
- Rank: veteran
- Number of posts: 114
- Joined date: Sun Dec 11, 2011 3:00 pm
- Post datetime: 2013-11-01T08:28:50+00:00
- Post Title: Re: XMA transform

Having trouble with XMA from Steel Battalion Heavy Armor (xbox360) by From Software.

Opened FSB containers with fsbext, but toWAV doesn't do anything with resulting XMAs, and QuickBMS gives an error (with your script): 
    there is an error with the decompression 
    the returned output size is negative (-1)

Here's a sample of FSB and XMA file from within it:
10t_BGM_Parmanent.fsb (43mb) [https://mega.co.nz/#!c9kUmDoS!AlHV51zIg ... 6u90_q-4YA](https://mega.co.nz/#!c9kUmDoS!AlHV51zIgjsoZ1-nneubwDpBuVlC3cE4W6u90_q-4YA)
bgm08_test04t stc0db.wav.xma (4mb) [https://mega.co.nz/#!QxUjAIZD!EN0VXWt6_ ... ofYb6OLYQ8](https://mega.co.nz/#!QxUjAIZD!EN0VXWt6_OybPY-M2L6sSA-lobdTwHxc1ofYb6OLYQ8)


Please advice.
## Post #76
- Username: gravissimus
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Sep 26, 2012 1:15 pm
- Post datetime: 2013-11-08T21:03:40+00:00
- Post Title: Re: XMA transform

Latest script does not help for unpack ZUMBA® FITNESS WORLD PARTY (Xbox 360)

it's what i want get
[http://www.zumbafitnessgame.com/audio/z ... oricua.mp3](http://www.zumbafitnessgame.com/audio/zwp/Puerto%20Rico%20-%20Rafa%20Maya%20-%20Zumba%20Boricua.mp3)

sample here
[https://mega.co.nz/#!kZxFCa7C!donK-l6Ji ... D55o2oqqEI](https://mega.co.nz/#!kZxFCa7C!donK-l6JiEAVOG3wXmqezyemDv53BEU0UD55o2oqqEI)

Would you be so kind, look through it please.
## Post #77
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2013-11-11T11:02:11+00:00
- Post Title: Re: XMA transform

> Reply from gravissimus
>
> Latest script does not help for unpack ZUMBA® FITNESS WORLD PARTY (Xbox 360)

it's what i want get
http://www.zumbafitnessgame.com/audio/z ... oricua.mp3

sample here
https://mega.co.nz/#!kZxFCa7C!donK-l6Ji ... D55o2oqqEI

Would you be so kind, look through it please.
I've taken a look at the sample - however these XMA streams are somewhat strange because their block size changes within the stream. So far I haven't even be able to parse the stream manually. Everything went fine with the Rayman: Legends RAKI variant but this one seems to be different. Will keep trying out different things.
## Post #78
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2013-11-11T11:05:33+00:00
- Post Title: Re: XMA transform

> Reply from MiLØ
>
> Having trouble with XMA from Steel Battalion Heavy Armor (xbox360) by From Software.

Opened FSB containers with fsbext, but toWAV doesn't do anything with resulting XMAs, and QuickBMS gives an error (with your script): 
    there is an error with the decompression 
    the returned output size is negative (-1)

Here's a sample of FSB and XMA file from within it:
10t_BGM_Parmanent.fsb (43mb) https://mega.co.nz/#!c9kUmDoS!AlHV51zIg ... 6u90_q-4YA
bgm08_test04t stc0db.wav.xma (4mb) https://mega.co.nz/#!QxUjAIZD!EN0VXWt6_ ... ofYb6OLYQ8


Please advice.All these work fine for me. Make sure you have changed the extension to something different than ".xma" and set the blocksize to 0x8000.
## Post #79
- Username: gravissimus
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Sep 26, 2012 1:15 pm
- Post datetime: 2013-11-11T15:44:01+00:00
- Post Title: Re: XMA transform

> Reply from AlphaTwentyThree
>
> gravissimus wrote:Latest script does not help for unpack ZUMBA® FITNESS WORLD PARTY (Xbox 360)

it's what i want get
http://www.zumbafitnessgame.com/audio/z ... oricua.mp3

sample here
https://mega.co.nz/#!kZxFCa7C!donK-l6Ji ... D55o2oqqEI

Would you be so kind, look through it please.
I've taken a look at the sample - however these XMA streams are somewhat strange because their block size changes within the stream. So far I haven't even be able to parse the stream manually. Everything went fine with the Rayman: Legends RAKI variant but this one seems to be different. Will keep trying out different things.

May be it will help. Firstly I unpacked .xma from .pck file with Ravioli Scanner v.2.7. It worked out with errors however the same had happend with Zumba Fitness Rush and errors had not affected on .xma for convertion with "XMA transform" script.

Previously for extraction for me worked script from Axsis (see. [viewtopic.php?f=21&t=9680](http://forum.xentax.com/viewtopic.php?f=21&t=9680)), now it doesn't.

.pck file sample
[https://mega.co.nz/#!dd4zyRDT!OMUyQHscF ... TgP0mJWdFc](https://mega.co.nz/#!dd4zyRDT!OMUyQHscFdnZxDJMDI_HKUjHyiBOCQdyxTgP0mJWdFc)

Thank you for your efforts.
## Post #80
- Username: MiLØ
- Rank: veteran
- Number of posts: 114
- Joined date: Sun Dec 11, 2011 3:00 pm
- Post datetime: 2013-11-23T21:16:35+00:00
- Post Title: Re: XMA transform

> Reply from AlphaTwentyThree
>
> All these work fine for me. Make sure you have changed the extension to something different than ".xma" and set the blocksize to 0x8000.
Ok, I'll try it again. Thanks.
## Post #81
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2013-12-01T18:30:29+00:00
- Post Title: Re: XMA transform

I don't know if someone already posted this, but DOA5 and DOA5U sounds can be converted with the bms script from the first page. Just extract the DATA and DATA2 files with the g1l bms script, the use XMA_transform.bms and then use towav to encode.

[https://www.mediafire.com/?ybbfbyg9wxcpx5i](https://www.mediafire.com/?ybbfbyg9wxcpx5i)
## Post #82
- Username: Gromber
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Oct 06, 2010 4:42 am
- Post datetime: 2014-01-01T22:27:12+00:00
- Post Title: Re: XMA transform

any update about orangebox to convert standar wav to wav.360
## Post #83
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2014-01-05T16:36:59+00:00
- Post Title: Re: XMA transform

> Reply from Gromber
>
> any update about orangebox to convert standar wav to wav.360
I'm not sure I get what you mean.
## Post #84
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2014-01-08T18:46:51+00:00
- Post Title: Re: XMA transform

erm, can you do a quick reminder on what we need in order for the script to work?
## Post #85
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2014-01-08T22:53:42+00:00
- Post Title: Re: XMA transform

> Reply from Devilot
>
> erm, can you do a quick reminder on what we need in order for the script to work?
Well, just QuickBMS ([http://aluigi.altervista.org/quickbms.htm](http://aluigi.altervista.org/quickbms.htm)). And of course XMA files.
## Post #86
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2014-01-09T08:25:49+00:00
- Post Title: Re: XMA transform

Dragon's Dogma XMA apparently don't work. any idea why?

EDIT: nvm, apparently XMA_parse is in cpp and I don't know how to compile it. can the xma_parse.exe file be uploaded here?
## Post #87
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2014-01-09T10:50:44+00:00
- Post Title: Re: XMA transform

> Reply from Devilot
>
> Dragon's Dogma XMA apparently don't work. any idea why?

EDIT: nvm, apparently XMA_parse is in cpp and I don't know how to compile it. can the xma_parse.exe file be uploaded here?
You can find it here: [http://www.hcs64.com/vgm_ripping.html](http://www.hcs64.com/vgm_ripping.html)
Also, review the options (see readme at beginning of script) to eventually adjust the parameters. A bocksize of 0x8000 or 0x10000 should work in most cases.
Remember to change the suffix of the XMA files to something else before processing, otherwise you'll lose the source files (which is annoying when the parameters are wrong).
## Post #88
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2014-01-09T11:03:44+00:00
- Post Title: Re: XMA transform

I'll just copy the whole folder somewhere else 

but alas, no xma_parse.exe, just xma_test.exe in the rar file.
## Post #89
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2014-01-09T11:33:57+00:00
- Post Title: Re: XMA transform

> Reply from Devilot
>
> I'll just copy the whole folder somewhere else 

but alas, no xma_parse.exe, just xma_test.exe in the rar file.
Just rename it.
## Post #90
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2014-01-09T12:31:47+00:00
- Post Title: Re: XMA transform

I did it but it wouldn't work  I'll try the blocksize and let you know how it works.

EDIT: am I supposed to get other XMA files after the quickbms script?
## Post #91
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2014-01-09T15:01:02+00:00
- Post Title: Re: XMA transform

> Reply from Devilot
>
> EDIT: am I supposed to get other XMA files after the quickbms script?
I don't quite understand what you mean... Have you ever used a QuickBMS script?
## Post #92
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2014-01-09T15:24:36+00:00
- Post Title: Re: XMA transform

I did but it was a disaster, I ended up needing to format the whole pc...
what I mean is: the result of your script would be MORE xma files, not WAV files, right?
## Post #93
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2014-01-09T15:27:10+00:00
- Post Title: Re: XMA transform

ONLY xma files.
## Post #94
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2014-01-10T12:28:03+00:00
- Post Title: Re: XMA transform

> Reply from Devilot
>
> The result of your script would be MORE xma files, not WAV files, right?

Yes. Once you've used the XMA Transform script on the XMA files, the new XMA files that the script gives you can be decoded into WAV format using ToWAV
## Post #95
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2014-02-12T14:14:42+00:00
- Post Title: Re: XMA transform

Update

Small update: Corrected the processing of WAVEXMA2 Riff headers (used in e.g. Terminator: Salvation).
## Post #96
- Username: MaddaCheeb
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Aug 13, 2011 12:43 pm
- Post datetime: 2014-03-16T01:11:53+00:00
- Post Title: Re: XMA transform

Having an issue. When I get everything started through quickBMS, I get this screen:



And even when I type "y" to continue, the command prompt exits. This happens every time. Any ideas?
## Post #97
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2014-03-16T10:54:21+00:00
- Post Title: Re: XMA transform

You're probably missing xma_parse.exe from hcs64.com (called test.exe there - just rename it)
## Post #98
- Username: MaddaCheeb
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Aug 13, 2011 12:43 pm
- Post datetime: 2014-03-16T14:02:18+00:00
- Post Title: Re: XMA transform

That worked, thanks! 

Also another question - what do I do with a multi- channel XMA file? I would like to split the channels into multiple audio files for each channel so I can isolate some elements of the track.
## Post #99
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2014-03-16T23:32:47+00:00
- Post Title: Re: XMA transform

The script already does that. Multichannel xma is not properly supported by towav.
## Post #100
- Username: MaddaCheeb
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Aug 13, 2011 12:43 pm
- Post datetime: 2014-03-17T00:38:39+00:00
- Post Title: Re: XMA transform

Oh. Hm. Can I use xmaencode to do that?
## Post #101
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2014-03-17T06:17:55+00:00
- Post Title: Re: XMA transform

No idea, I've only worked with towav.
## Post #102
- Username: makcar
- Rank: veteran
- Number of posts: 154
- Joined date: Tue May 13, 2014 5:41 am
- Post datetime: 2014-05-27T02:13:55+00:00
- Post Title: Re: XMA transform

New Warhammer 40,000: Kill Team .xma (?)
[W40K_Kill_Team_(xma).rar](https://xentaxbackup.github.io/file/7383_W40K_Kill_Team_(xma).rar)
## Post #103
- Username: Starnova
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Feb 10, 2014 10:19 am
- Post datetime: 2014-06-03T19:33:02+00:00
- Post Title: Re: XMA transform

Hi, could you help me with this SoundNodeWave file? Maybe im not using the proper script, but i would like to know if it is possible extract the subtitles and the audio from this file...  and then repack it again. It is from "A story about my uncle" game. Please, if anyone can help me i'll apreciate it.
[Narrator_Workshop_Postcards.rar](https://xentaxbackup.github.io/file/7428_Narrator_Workshop_Postcards.rar)
## Post #104
- Username: keystothemaxim
- Rank: beginner
- Number of posts: 23
- Joined date: Mon Oct 21, 2013 6:19 pm
- Post datetime: 2014-07-22T08:51:05+00:00
- Post Title: Re: XMA transform

I'm having trouble with the Resident Evil 6 XMA's. The script did work with the XMA's (though the progam kept showing a "parse error"), but after I converted the files with ToWAV, the wavs only have music at the very end of each file, and the rest is just silence.
## Post #105
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2014-07-23T07:18:53+00:00
- Post Title: Re: XMA transform

UPDATE

Added the Call of Duty: World at War variant!
## Post #106
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2014-07-23T07:19:18+00:00
- Post Title: Re: XMA transform

> Reply from keystothemaxim
>
> I'm having trouble with the Resident Evil 6 XMA's. The script did work with the XMA's (though the progam kept showing a "parse error"), but after I converted the files with ToWAV, the wavs only have music at the very end of each file, and the rest is just silence.Can you send me some samples via PM?
## Post #107
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2014-07-23T07:23:29+00:00
- Post Title: Re: XMA transform

> Reply from makcar
>
> New Warhammer 40,000: Kill Team .xma (?)As you can see inside the header, these are xwma files. Luckily they can be decoded with xwmaencode.
## Post #108
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2014-07-23T07:25:24+00:00
- Post Title: Re: XMA transform

If you like my script, please click the little "thumbs up" logo in the first post - we want to reach 100%  Thanks.
## Post #109
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2014-08-31T21:05:49+00:00
- Post Title: Re: XMA transform

UPDATE

RWAV variant from IO Interactive games now supported!
## Post #110
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2014-09-01T07:33:59+00:00
- Post Title: Re: XMA transform

wiii 
an IO game example?
## Post #111
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2014-09-01T08:05:40+00:00
- Post Title: Re: XMA transform

Uhm, not anymore, everything already converted.  You could take a look at Mini Ninjas for Xbox 360 if you like.
## Post #112
- Username: Micadi
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Sep 08, 2014 10:34 am
- Post datetime: 2014-09-08T02:56:12+00:00
- Post Title: Re: XMA transform

I'm kinda new here on these forums so I hope I'm not making here any stupid mistakes but I'm having problems with your script - I'm getting an error "the return output size is negative (-1).
This is kinda annoying since It required a lot of work to actually get to the point where I managed to get those xma files from my xbox360 Gears of War 3 copy

I followed instructions in this topic:
[viewtopic.php?f=17&t=10679](http://forum.xentax.com/viewtopic.php?f=17&t=10679)

Are they outdated or there is something else not working properly?
## Post #113
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2014-09-19T11:23:49+00:00
- Post Title: Re: XMA transform

Renaming xma_test.exe to xma_parse.exe should solve the problem.
## Post #114
- Username: maurid
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Sep 24, 2014 1:19 am
- Post datetime: 2014-10-05T17:11:06+00:00
- Post Title: Re: XMA transform

I get this error:


How can I solve?
## Post #115
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2014-10-05T18:54:11+00:00
- Post Title: Re: XMA transform

First of all, read the explanation at the start of the script before you post question right away.
You can try to set the blocksize from 0x8000 to 0x10000. PM me a sample and I can tell you the parameters.
## Post #116
- Username: Dark Sonic
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Oct 28, 2014 6:39 am
- Post datetime: 2014-10-28T20:14:21+00:00
- Post Title: Re: XMA transform

Hello everyone! 
Knows someone, is there a utility WAV to XMA?
I want to replace the dialogue in the game Sonic The Hedgehog 2006 on XBOX 360.
Threw a couple of files for example. Everywhere looked and can not find a way to convert the file WAV to XMA.
Can someone tell me where to find this utility or write it.

[https://mega.co.nz/#!20dWALRC!vVNZ6E5dl ... vMBuYR9Yl4](https://mega.co.nz/#!20dWALRC!vVNZ6E5dl-xVmujVr_HU1SHfUr-nOS-t_vMBuYR9Yl4)
## Post #117
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2014-10-29T06:32:21+00:00
- Post Title: Re: XMA transform

> Reply from Dark Sonic
>
> Hello everyone! 
Knows someone, is there a utility WAV to XMA?
I want to replace the dialogue in the game Sonic The Hedgehog 2006 on XBOX 360.
Threw a couple of files for example. Everywhere looked and can not find a way to convert the file WAV to XMA.
Can someone tell me where to find this utility or write it.

https://mega.co.nz/#!20dWALRC!vVNZ6E5dl ... vMBuYR9Yl4Try XMAencode.
## Post #118
- Username: Dark Sonic
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Oct 28, 2014 6:39 am
- Post datetime: 2014-10-29T16:09:29+00:00
- Post Title: Re: XMA transform

> Reply from AlphaTwentyThree
>
> 
Try XMAencode.
Tried to convert. Distilled through all the commands. Only with the command "xmaencode.exe E0001_00_TL.wav /T E0001_00_TL.xma /S" game does not crash, but the sound is not played. 
In the title, the original file is written - RIFFl ... WAVEfmt.
In the modified file is written - RIFFL ... WAVEdata.

How to do to the file header was RIFFl ... WAVEfmt?
Which command to be executed to the game does not crash and the sound is played?
## Post #119
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2014-10-29T22:39:41+00:00
- Post Title: Re: XMA transform

Is the resulting file XMA1 or XMA2? If it's XMA2 you could try to convert the file to xma1 with my script and see if the game can play the file. Other than that... I'm lost here. :-\
## Post #120
- Username: Dark Sonic
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Oct 28, 2014 6:39 am
- Post datetime: 2014-10-30T08:44:03+00:00
- Post Title: Re: XMA transform

> Reply from AlphaTwentyThree
>
> Is the resulting file XMA1 or XMA2? If it's XMA2 you could try to convert the file to xma1 with my script and see if the game can play the file. Other than that... I'm lost here. :-\
At the end of the original file is written - XMA2 $ .............................. I ........ seek .. ...... 
In the resulting file is written at the end - XMA2, .................. v ...... / \ .............. ...... seek ........

It turns out ... need a file with XMA2. But here's how to make it play? : \
Can see what could be the reason? Upload both files in the archive to file sharing.
[https://mega.co.nz/#!u40HGDbQ!29z3s9ah_ ... mSO4FK2rVg](https://mega.co.nz/#!u40HGDbQ!29z3s9ah_MLwXwqqJiM91t7KcidxXBUiYmSO4FK2rVg)
## Post #121
- Username: drfsupercenter
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Nov 13, 2011 7:08 am
- Post datetime: 2014-11-13T05:34:14+00:00
- Post Title: Re: XMA transform

Hey guys...

Any update on Guitar Hero Warriors of Rock?  That has the same XMA format as all the other games, but xmash doesn't work anymore and supposedly the encryption is different.  Just wondering if anyone's cracked it yet.

Thanks
## Post #122
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2014-12-19T15:47:55+00:00
- Post Title: Re: XMA transform

XMA file from Pac-Man and the Ghostly Adventures 2. Some of the larger XMA's convert just fine but there are some that don't. I've attached a sample for you

[http://www47.zippyshare.com/v/81051239/file.html](http://www47.zippyshare.com/v/81051239/file.html)

I'm using the latest version of QuickBMS and your XMA Converter script as well.
## Post #123
- Username: LarsMasters
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Aug 25, 2014 10:30 am
- Post datetime: 2014-12-24T00:41:32+00:00
- Post Title: Re: XMA transform

Will this work for MUA GE/Marvel Ultimate Alliance Gold Edition ZSM/ZSS?
## Post #124
- Username: trojannemo
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Nov 19, 2011 12:46 pm
- Post datetime: 2015-01-26T16:13:42+00:00
- Post Title: Re: XMA transform

> Reply from drfsupercenter
>
> Hey guys...

Any update on Guitar Hero Warriors of Rock?  That has the same XMA format as all the other games, but xmash doesn't work anymore and supposedly the encryption is different.  Just wondering if anyone's cracked it yet.

Thanks

I would love to know this as well. In December I spent a while searching as much as I could and trying anything that had come out in the last couple of years. Was never able to get at the files inside the new FSB.XEN files. So naturally couldn't try this "works with all XMA files" script.
## Post #125
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2015-02-03T12:27:15+00:00
- Post Title: Re: XMA transform

> Reply from brendan19
>
> XMA file from Pac-Man and the Ghostly Adventures 2. Some of the larger XMA's convert just fine but there are some that don't. I've attached a sample for you

http://www47.zippyshare.com/v/81051239/file.html

I'm using the latest version of QuickBMS and your XMA Converter script as well.
Can you upload the samples again?
## Post #126
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2015-02-03T12:38:57+00:00
- Post Title: Re: XMA transform

UPDATE

Corrected an error in the XWV variant processing. New revision uploaded.
## Post #127
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2015-02-03T16:27:01+00:00
- Post Title: Re: XMA transform

> Reply from AlphaTwentyThree
>
> Can you upload the samples again?
Sure 

It's these files that have some problems when trying to be parsed. Not sure if it's your script or XMA parse.

[Pac-Man and the Ghostly Adventures 2 Samples](http://www11.zippyshare.com/v/JE6RxLq8/file.html)
## Post #128
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2015-02-05T08:16:23+00:00
- Post Title: Re: XMA transform

Delete line 861 (set BLOCKSIZE 0x8000) and it works, hehe.
## Post #129
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2015-05-07T05:25:41+00:00
- Post Title: Re: XMA transform

Can somebody run tests with the ubi xma converter I posted some time ago and send me samples that don't work?
## Post #130
- Username: Errotie
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jun 09, 2015 10:14 am
- Post datetime: 2015-06-09T02:36:55+00:00
- Post Title: Re: XMA transform

I'm too stupid to understand this. [film Galaxy Star 2](http://www.coquegalaxystar2.com/category-film-protection-de-%C3%A9cran-pour-galaxy-star-2-5.html) [coque cuir Samsung Galaxy Star 2](http://www.coquegalaxystar2.com)
## Post #131
- Username: JYSB59
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Aug 09, 2015 7:04 pm
- Post datetime: 2015-08-09T11:48:20+00:00
- Post Title: Re: XMA transform

hey alphat , here I wanted to say that for this XMA file "Forza 4" its not working. I do not know if this is a new type of encryption XMA but would be cool if you could decrypted ps; I'm french and I use google translation so my English is bad
## Post #132
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2015-08-09T12:03:58+00:00
- Post Title: Re: XMA transform

> Reply from JYSB59
>
> hey alphat , here I wanted to say that for this XMA file "Forza 4" its not working. I do not know if this is a new type of encryption XMA but would be cool if you could decrypted ps; I'm french and I use google translation so my English is bad
What's the error? I've personally converted these with the script and it worked perfectly.
## Post #133
- Username: JYSB59
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Aug 09, 2015 7:04 pm
- Post datetime: 2015-08-11T12:38:59+00:00
- Post Title: Re: XMA transform

the error is "not responding" but I give you the link of xma, if you could try the decrypted : [http://www.mediafire.com/download/8thwm ... _08016.xma](http://www.mediafire.com/download/8thwmwti1xl9fir/EngB_08016.xma) Thanx
## Post #134
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2015-08-11T20:08:15+00:00
- Post Title: Re: XMA transform

Like I suspected, it works perfectly... have you located xma_parse.exe in the same folder as the script?
## Post #135
- Username: JYSB59
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Aug 09, 2015 7:04 pm
- Post datetime: 2015-08-12T12:22:51+00:00
- Post Title: Re: XMA transform

I have xml_parser.cpp / .h and xma_test.exe but not xma_parse.exe, could you do without a copy of ToWAV please, the website that was proposing was the close and he was not found , Thanx
## Post #136
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2015-08-12T12:27:54+00:00
- Post Title: Re: XMA transform

Rename xma_test to xma_parse. It's the exact same program. It will work just fine then 

Also, here's a copy of [ToWAV](http://www63.zippyshare.com/v/a3XmyeLS/file.html)
## Post #137
- Username: JYSB59
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Aug 09, 2015 7:04 pm
- Post datetime: 2015-08-13T11:02:43+00:00
- Post Title: Re: XMA transform

brendan thank you  , it works perfectly, but I have another question, I would like to know how created a file XMA from an XACT project, I heard about a xma_encode.exe who find in the XDK but I is not found , thanx
## Post #138
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2015-08-13T14:28:04+00:00
- Post Title: Re: XMA transform

> Reply from JYSB59
>
> I have xml_parser.cpp / .h and xma_test.exe but not xma_parse.exe, could you do without a copy of ToWAV please, the website that was proposing was the close and he was not found , Thanx
Rename xma_test to xma_parse and it will work. Will upload towav later.
## Post #139
- Username: JYSB59
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Aug 09, 2015 7:04 pm
- Post datetime: 2015-08-13T17:48:28+00:00
- Post Title: Re: XMA transform

Thanx Alpha
## Post #140
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2015-08-13T18:10:17+00:00
- Post Title: Re: XMA transform

Here's towav.
[towav.zip](https://xentaxbackup.github.io/file/9526_towav.zip)
## Post #141
- Username: JYSB59
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Aug 09, 2015 7:04 pm
- Post datetime: 2015-08-13T19:52:42+00:00
- Post Title: Re: XMA transform

Thanx for Towav Alpha "but I have another question, I would like to know how created a file XMA from an XACT project, I heard about a xma_encode.exe who find in the XDK but I is not found , thanx" you would know how to do?
## Post #142
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2015-08-13T20:54:06+00:00
- Post Title: Re: XMA transform

> Reply from JYSB59
>
> Thanx for Towav Alpha "but I have another question, I would like to know how created a file XMA from an XACT project, I heard about a xma_encode.exe who find in the XDK but I is not found , thanx" you would know how to do?
Sorry, I have no experience with that. :\
## Post #143
- Username: JYSB59
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Aug 09, 2015 7:04 pm
- Post datetime: 2015-08-14T10:19:06+00:00
- Post Title: Re: XMA transform

thanks anyway
## Post #144
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2015-08-30T18:40:50+00:00
- Post Title: Re: XMA transform

UPDATE

Corrected a little mistake when adding a header without parsing. Now you only have to set PARSE 0 and leave WRITE_UNPARSED at 0 to work. Silly mistake.
## Post #145
- Username: JYSB59
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Aug 09, 2015 7:04 pm
- Post datetime: 2015-09-13T11:17:25+00:00
- Post Title: Re: XMA transform

hi, it's me again here is the script works perfectly except for XMA  Forza 2 and Forza 3 or it puts me an error with a number of byte (56), if someone could help me (Forza 3  [http://www.mediafire.com/download/h4de6 ... Xtrack.xma](http://www.mediafire.com/download/h4de6ts4tnq5gzd/UI_Xtrack.xma) ) (Forza 2  [http://www.mediafire.com/download/t4m5i ... l85/34.xma](http://www.mediafire.com/download/t4m5ikovcuprl85/34.xma) )
## Post #146
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2015-09-20T15:23:05+00:00
- Post Title: Re: XMA transform

> Reply from JYSB59
>
> hi, it's me again here is the script works perfectly except for XMA  Forza 2 and Forza 3 or it puts me an error with a number of byte (56), if someone could help me (Forza 3  http://www.mediafire.com/download/h4de6 ... Xtrack.xma ) (Forza 2  http://www.mediafire.com/download/t4m5i ... l85/34.xma )
No need to run them through my tool, they are already ready to decode with towav.
## Post #147
- Username: JYSB59
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Aug 09, 2015 7:04 pm
- Post datetime: 2015-09-21T18:44:31+00:00
- Post Title: Re: XMA transform

Ok thanx man
## Post #148
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2015-10-21T06:37:21+00:00
- Post Title: Re: XMA transform

UPDATE

Corrected a major mistake in the UT3 file type heuristic. Now almost all UT3 variants are supported!
## Post #149
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2015-10-22T18:05:05+00:00
- Post Title: Re: XMA transform

UPDATE

Added yet another UT3 variant.
## Post #150
- Username: Extreme110
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jul 09, 2011 8:43 pm
- Post datetime: 2015-11-01T07:16:38+00:00
- Post Title: Re: XMA transform

Christ above Alpha, you're a goddam legend.

I've been trying to rip the music from Halo 3; I'm using the tool [Adjutant](http://forum.halomaps.org/index.cfm?page=topic&topicID=45590), which automatically parses the extracted .xma files into towav.exe. Unfortunately, they don't support the cinematic music because it's multi-channel, and they couldn't get it work with towav.

Using your script, I could extract the headerless .xma files, put them through your script and then into towav. I initially forgot to change the default frequency so the files were coming out high pitched, but I solved that right quick.

Cheers for the hard work
## Post #151
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2015-11-01T11:58:12+00:00
- Post Title: Re: XMA transform

> Reply from Extreme110
>
> Christ above Alpha, you're a goddam legend.

I've been trying to rip the music from Halo 3; I'm using the tool Adjutant, which automatically parses the extracted .xma files into towav.exe. Unfortunately, they don't support the cinematic music because it's multi-channel, and they couldn't get it work with towav.

Using your script, I could extract the headerless .xma files, put them through your script and then into towav. I initially forgot to change the default frequency so the files were coming out high pitched, but I solved that right quick.

Cheers for the hard work
Glad my script was useful to you.
## Post #152
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2015-11-16T22:00:26+00:00
- Post Title: Re: XMA transform

UPDATE

Added the variant from Star Wars: The Force Unleashed.

Script for xp/xd extraction: [viewtopic.php?f=13&t=4450&p=112374#p112374](http://forum.xentax.com/viewtopic.php?f=13&t=4450&p=112374#p112374)
## Post #153
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2015-11-20T08:43:26+00:00
- Post Title: Re: XMA transform

UPDATE

Corrected the variant from Star Wars: The Force Unleashed. Some variations weren't supported correctly.
## Post #154
- Username: LarsMasters
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Aug 25, 2014 10:30 am
- Post datetime: 2015-12-15T13:26:20+00:00
- Post Title: Re: XMA transform

Can you do Marvel Ultimate Alliance? It was found right here: [http://zenhax.com/viewtopic.php?t=1075](http://zenhax.com/viewtopic.php?t=1075)
## Post #155
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2015-12-15T17:59:50+00:00
- Post Title: Re: XMA transform

Can't do anything without samples...
## Post #156
- Username: LarsMasters
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Aug 25, 2014 10:30 am
- Post datetime: 2015-12-16T04:49:04+00:00
- Post Title: Re: XMA transform

An xma file?
## Post #157
- Username: LordNazo
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jan 02, 2016 6:08 am
- Post datetime: 2016-01-02T01:33:02+00:00
- Post Title: Re: XMA transform

Hi, Destiny isn't working with the script. You need an XMA, correct?
## Post #158
- Username: AnonBaiter
- Rank: veteran
- Number of posts: 82
- Joined date: Fri Oct 16, 2015 3:15 am
- Post datetime: 2016-01-04T00:42:28+00:00
- Post Title: Re: XMA transform

Is it just me or am i the only one who doesn't know how to convert XMA to WAV?

EDIT: Nevermind, I just discovered how to convert them anyway.
## Post #159
- Username: AnonBaiter
- Rank: veteran
- Number of posts: 82
- Joined date: Fri Oct 16, 2015 3:15 am
- Post datetime: 2016-01-27T21:45:46+00:00
- Post Title: Re: XMA transform

[https://mega.nz/#!IIszzbDQ!M_v3BWyYMgqh ... 74m6N8ebA8](https://mega.nz/#!IIszzbDQ!M_v3BWyYMgqhAECfq4kTBPbiQUxXrHwlV74m6N8ebA8) - Here's an XMA2 file from Beautiful Katamari. It doesn't work with this script.
## Post #160
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2016-01-28T08:51:56+00:00
- Post Title: Re: XMA transform

Have you tried different settings? Have you located xma_parse in the script folder?
## Post #161
- Username: AnonBaiter
- Rank: veteran
- Number of posts: 82
- Joined date: Fri Oct 16, 2015 3:15 am
- Post datetime: 2016-01-28T16:45:56+00:00
- Post Title: Re: XMA transform

> Reply from AlphaTwentyThree
>
> Have you tried different settings? Have you located xma_parse in the script folder?
>Have you tried different settings?
No.
>Have you located xma_parse in the script folder?
Yes.

But as it turns out, only 5 of the .nps files were converted into .xma files, although I have yet to test them. The rest of them however, didn't work because it caused some errors("zero frames in this packet"). I can upload all .nps files of them if you wish.
## Post #162
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2016-01-28T17:28:52+00:00
- Post Title: Re: XMA transform

UPDATE

New revision: XMA2 processing corrected (e.g. Beautiful Katamari *.nps).

Thanks go out to AnonBaiter for providing a sample.
## Post #163
- Username: slavikus
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Feb 17, 2016 4:14 pm
- Post datetime: 2016-04-12T17:36:41+00:00
- Post Title: Re: XMA transform

Thanks for a great tool!

Trying to use it against Destiny's XMA files as they are definitely a RIFX from looking at the binary, but not having much success. Can you please look into it and maybe you'll have an insight?

Here's two examples:

[http://slavikus.ru/1caKq](http://slavikus.ru/1caKq)
[http://slavikus.ru/156Xg](http://slavikus.ru/156Xg)

Getting errors like 
```
Parse error: skip bits (14336) did not match previous packet overflow (0)
```


TIA!
## Post #164
- Username: AnonBaiter
- Rank: veteran
- Number of posts: 82
- Joined date: Fri Oct 16, 2015 3:15 am
- Post datetime: 2016-05-17T19:46:37+00:00
- Post Title: Re: XMA transform

Hi.

So I tested these .xma files with your script and they all gave me errors, each with a different issue. Here are the files if you're interested:
[https://mega.nz/#!1VUnlYjI!vbx3AHzUhs4n ... l8gkz38Fn4](https://mega.nz/#!1VUnlYjI!vbx3AHzUhs4nhNVj2FdFZfuV1PblJwSjel8gkz38Fn4)

Thanks.
## Post #165
- Username: kurczaczak
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jun 02, 2016 3:58 am
- Post datetime: 2016-06-01T20:09:02+00:00
- Post Title: Re: XMA transform

Tony Hawk's Project 8, Parse error: skip bits (18728) did not match previous packet overflow
[https://mega.nz/#!CNkH2Q4T!6OxgFgluA3bv ... gVG7I68DMM](https://mega.nz/#!CNkH2Q4T!6OxgFgluA3bvRXMQ3OfaH8C5PJ0F55QJEgVG7I68DMM)
## Post #166
- Username: dallasbelt
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Dec 31, 2016 1:17 pm
- Post datetime: 2016-12-31T17:57:00+00:00
- Post Title: Re: XMA transform

Hello. I'm new here. I was wondering if you can assist me. My goal is to convert a .xma file (which I extracted from a Gears of War 3 disc for the Xbox 360) to a .wav or .mp3 file. Is that what this tool is for? I'm sorry, I don't have all the knowledge in the audio scene.

I will appreciate any help.

Thank you.
## Post #167
- Username: Liandril
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Aug 02, 2010 11:11 pm
- Post datetime: 2016-12-31T23:47:15+00:00
- Post Title: Re: XMA transform

> Reply from dallasbelt
>
> My goal is to convert a .xma file (which I extracted from a Gears of War 3 disc for the Xbox 360) to a .wav or .mp3 file.
[xmaencode](http://forum.xentax.com/viewtopic.php?f=17&t=4367)

Happy New Year!
## Post #168
- Username: truston
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Dec 15, 2014 5:42 pm
- Post datetime: 2021-02-19T12:28:58+00:00
- Post Title: Re: XMA transform

audio from PS3, (NPUB90862) Army of TWO The Devil's Cartel Demo, CANNOT WORK
this audio file here is a sample, I'm not sure what format actually it is, I wanna decode or convert it, no luck 
[d7fcac9b749dcd94633542d7646c4d9c.zip](https://xentaxbackup.github.io/file/19629_d7fcac9b749dcd94633542d7646c4d9c.zip)
## Post #169
- Username: kumar0raja
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Mar 30, 2021 3:45 am
- Post datetime: 2021-03-29T21:06:12+00:00
- Post Title: Re: XMA transform

Just a small update: I added the option to change between XMA2 and XMA1 as source file. That only for now until I've coded some automatic blocksize/XMA version checker.  [sbi hrms](https://hellodear.in/sbi-hrms-onlinesbi/) [teatv app](https://teatv.ltd)
## Post #170
- Username: jfwfreo
- Rank: veteran
- Number of posts: 124
- Joined date: Sat Nov 15, 2008 8:31 am
- Post datetime: 2021-04-03T12:06:27+00:00
- Post Title: Re: XMA transform

Does anyone know of any open source code I can use that can decompress Xbox 360 XMA audio? Specifically whatever variant(s) Electronic Arts was using in its 360 titles. Code for compressing into XMA would probably also be useful.
## Post #171
- Username: jlnhlfan
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Dec 10, 2020 4:00 am
- Post datetime: 2022-06-17T02:15:24+00:00
- Post Title: Re: XMA transform

Attempting to use the script, as expected (if you're me), results in the following error. What can I do?
[Screenshot_June_16_2022_07_14_36_PM.png](https://xentaxbackup.github.io/file/22379_Screenshot_June_16_2022_07_14_36_PM.png)
