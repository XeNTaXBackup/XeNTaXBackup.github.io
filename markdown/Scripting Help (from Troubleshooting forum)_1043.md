## Post #1
- Username: elcondor
- Rank: VIP member
- Number of posts: 18
- Joined date: Tue Dec 14, 2004 6:28 pm
- Post datetime: 2005-01-07T19:52:41+00:00
- Post Title: Scripting Help (from Troubleshooting forum)

Well, as promised, here's the script I "Guest " wrote for the You Don't Know Jack games (it reads all 'QFold' files only, the files on hard drives or the bigger archives are a different format, which I'll need help on)

I'll post it as a bms, so it can be loaded in MexScriptor and pulled apart or otherwise studied.

As a script, I think the politest term to use for it is 'functional' - in a bid to make things a little clearer i've used the odd DUMMYL to skip past longs rather than anything more elegant.

I assure you, this works 100% on every file of this format I've tried it on (The STR information isn't directly connected to the filenames).

Don't expect to be able to use the extracted files just yet, I think it's a standard Apple sound format (ima4 is present, suggesting something like .snd), but I can't find out the exact details needed to play it.
[srf.zip](https://xentaxbackup.github.io/file/89_srf.zip)
## Post #2
- Username: elcondor
- Rank: VIP member
- Number of posts: 18
- Joined date: Tue Dec 14, 2004 6:28 pm
- Post datetime: 2005-01-07T20:08:56+00:00
- Post Title: Scripting Help (from Troubleshooting forum)

I wonder if someone can help with this:

Basically, I found another SRF format (the one I've coded for already seems to be bulletproof now, but that's the 'quick access' style as opposed to the 'big archive' one).

The files are so big I can't really do much about sending a sample, so bear with my explanation for a second (all mathematical longs are big endian, like the other example).

The first long is an ID, 'srf1' (I think this was supposed to be different to the other one, to show the difference in layout, but no example I've seen has an alternate ID string).
The second long is big endian, and is the overall size of the file, while the third is the total size of the 'header' portion (the data starts immediately after it), However, this is where the fun really starts.

The fourth long is a recognisable text string, such as Mb01. My experiments with the actual executable suggest that the 'M' just acts as a marker, and the real filename is the three other bytes (e.g. b01) So far, so simple, but the next long after one of these M??? strings is a file counter, which leads to a loop of filenumber, file offset, file size, with the last ID being equal to the file counter. We then move back to an M??? string, and the whole process repeats.

How can I get all of these files out (assuming that name duplication is permitted by MEX3, having the three byte code as markers would be fine)? I've noticed that the obvious nested loops approach (setting up one loop looking for M??? strings until we run out of header, while using another internal loop to log the file info until all files between M??? strings are accounted for) seems to confuse the parser and crash the engine.

Since I can't copy out of the MexScriptor directly, I include a JPG of the scripting window
[script2.jpg](https://xentaxbackup.github.io/file/90_script2.jpg)
## Post #3
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-01-07T22:12:29+00:00
- Post Title: Scripting Help (from Troubleshooting forum)

First, thanks for the script, I'm sure going to try it and then add it to the next release! (crediting you of course).  

As to that other format, you can actually copy the text right out of Mex3Scriptor. Just select it all (ctrl+a) and copy it (ctrl+c). Voila.

In the script you make the engine search for an 'M' which is not really the way to go. There may be a lot of bytes in a file, and chances are you will stumble upon an M that is just part of something else and not anything related to your header. 

I also noticed that you load up a long variable in FILENAME (a variable I would expect to be a string) and Reversing it even and then logging it with the Log command. Do you know I never even tried that? I just assumed my code would not be able to handle that, but it does I noticed from the script you attach above!! LOL! Excellent! 
However, I'm pretty sure you can't use a "Math FILENAME += FILEID ;" construction, as the engine has no way to tell whether you wish to append a character to a string, it will just tell you a variable type mismatch occured. 

As for the crash, that is bound to happen if you take account the above. Besides that, IF the script finds an M that is not part of the marker, it might be that your FILECNTL gets a number that is completely inappropriate. 

Hope that helps.
## Post #4
- Username: elcondor
- Rank: VIP member
- Number of posts: 18
- Joined date: Tue Dec 14, 2004 6:28 pm
- Post datetime: 2005-01-08T19:37:39+00:00
- Post Title: Scripting Help (from Troubleshooting forum)

> However, I'm pretty sure you can't use a "Math FILENAME += FILEID ;" construction, as the engine has no way to tell whether you wish to append a character to a string, it will just tell you a variable type mismatch occured.

I took this out of the script, so that no appending occurs - and the crash still happens.

Basically, what I've got to try to figure out is how I can get two concurrent routines, the one which locates and logs the main name, and the one which actually does the extraction (My information on the format shows that the 'M' character does not occur in anything other than these main filenames when in the header portion, where it apparently stands for Media).
## Post #5
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-01-08T21:51:26+00:00
- Post Title: Scripting Help (from Troubleshooting forum)

Ahh.. I wish I could take a look at that file!  

Perhaps it is possible to attach just a small portion of the file (enough to expose the format) ?
## Post #6
- Username: elcondor
- Rank: VIP member
- Number of posts: 18
- Joined date: Tue Dec 14, 2004 6:28 pm
- Post datetime: 2005-01-09T20:06:15+00:00
- Post Title: Scripting Help (from Troubleshooting forum)

I'll have to try to get hold of some webspace, because I can't find a file small enough to fit here.

Bear with me, I'll have something ready by the end of this week.
## Post #7
- Username: Captain
- Rank: Site Admin
- Number of posts: 248
- Joined date: Thu Jan 16, 2003 1:25 am
- Post datetime: 2005-01-09T20:41:05+00:00
- Post Title: Scripting Help (from Troubleshooting forum)

> Reply from elcondor
>
> I'll have to try to get hold of some webspace, because I can't find a file small enough to fit here.

Bear with me, I'll have something ready by the end of this week.
How big is this file? I can open up a public ftp for you if you want...
## Post #8
- Username: elcondor
- Rank: VIP member
- Number of posts: 18
- Joined date: Tue Dec 14, 2004 6:28 pm
- Post datetime: 2005-01-11T14:03:19+00:00
- Post Title: Scripting Help (from Troubleshooting forum)

It's OK, I have a lot of filespace, just wanted to get off dialup first 

[http://www.mametesters.org/elcondor/JACKSND1.SRF](http://www.mametesters.org/elcondor/JACKSND1.SRF) is one example, as is
[http://www.mametesters.org/elcondor/SHORTVAR.SRF](http://www.mametesters.org/elcondor/SHORTVAR.SRF) and

[http://www.mametesters.org/elcondor/COMRCIAL.SRF](http://www.mametesters.org/elcondor/COMRCIAL.SRF)

Shortvar is the smallest, but the others have more info.

PS. If anyone knows of a utility that can play MAC System 7 audio files or SFIL filetypes, but on a Windows platform, I'd like to know about it, because that's the audio format used.
## Post #9
- Username: elcondor
- Rank: VIP member
- Number of posts: 18
- Joined date: Tue Dec 14, 2004 6:28 pm
- Post datetime: 2005-01-11T14:38:47+00:00
- Post Title: Scripting Help (from Troubleshooting forum)

Repeat after me: SRF stands for Script/Resource File - the fork is included already.

If that's right, then the scripting is going to be easier than I thought for the original format, but the new format will still need looking at.
## Post #10
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-01-11T14:41:39+00:00
- Post Title: Scripting Help (from Troubleshooting forum)

Okay thanks, I will download them and take a good look at them!
## Post #11
- Username: Intimidated
- Rank: VIP member
- Number of posts: 4
- Joined date: Wed Dec 21, 2005 2:24 pm
- Post datetime: 2005-12-21T06:37:59+00:00
- Post Title: Scripting Help (from Troubleshooting forum)

Hi guys.

I'm sorry to pull up such an old topic, but i've been trying to deal with the SRF files in the UK version of "You don't know jack" pretty much solidly for the last 7 days now.

Unfortunately MultiEx couldn't deal with the SRF's properly, so I wrote a script in visual basic. I don't know the scripting language that MultiEx uses, so if anybody fancies having a shot at converting my vb code into a script for multiex, go ahead  - This script can handle any srf.

Anyway, my main issue is the format of the audio files.

They appear to be SFIL/SND (Macintosh System 7 sound archive) with IMA4 ADPCM compression.

The closest i've come so far to decoding the audio is to stick a RIFF/WAV header on it with an MS IMA ADPCM compression tag, but the sound is VERY distorted.

Do we have any Mac users who might be able to either a) try and play / convert an extracted SFIL or b) might know how to do so in windows?

Many Thanks

Tom.

Link to the SND sample: [http://www.bolt7.com/Mb04.1.snd](http://www.bolt7.com/Mb04.1.snd)
Link to the same sample with a WAV header: [http://www.bolt7.com/Mb04.1.wav](http://www.bolt7.com/Mb04.1.wav)
[SRF - visual basic.zip](https://xentaxbackup.github.io/file/498_SRF - visual basic.zip)
## Post #12
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-12-21T06:42:02+00:00
- Post Title: Scripting Help (from Troubleshooting forum)

Hi Tom. Thanks for the donation, once again. 

I will go through your code.
## Post #13
- Username: elcondor
- Rank: VIP member
- Number of posts: 18
- Joined date: Tue Dec 14, 2004 6:28 pm
- Post datetime: 2005-12-21T19:56:51+00:00
- Post Title: Scripting Help (from Troubleshooting forum)

Can I just point out here that the problem you may be having with the YDKJUK SRF files (Not the sound stuff) may be due to me not submitting the revised script correctly?


There's a script on the XeNTaX wiki for You Don't Know Jack that is supposed to open any SRF file, including YDKJUK ones, but I didn't send it in time for the latest MultiEx release.

How would I go about submitting the new version?
## Post #14
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-12-21T20:19:19+00:00
- Post Title: Scripting Help (from Troubleshooting forum)

Well, you can actually just sign up at the WIKI and add your new script there, or add it to the page. If you think the script there is not correct, then please do update it with your better one!   The WIKI is open to everyone!
## Post #15
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2005-12-23T18:42:30+00:00
- Post Title: Scripting Help (from Troubleshooting forum)

...Except spambots.
## Post #16
- Username: elcondor
- Rank: VIP member
- Number of posts: 18
- Joined date: Tue Dec 14, 2004 6:28 pm
- Post datetime: 2006-03-05T20:07:38+00:00
- Post Title: 

Right, I've just confirmed that the script on the Wiki is the correct one, and that the sound files in SRFs are macintosh SFIL files (which means that they may need endian swapping)
## Post #17
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-03-05T20:19:15+00:00
- Post Title: 

Ah thanks!
## Post #18
- Username: taraquedo
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Sep 19, 2006 6:44 am
- Post datetime: 2006-09-18T22:55:02+00:00
- Post Title: 

I solved the problem with the confusing soundfiles!

Sorry for my broken english but I am from germany. As mentioned here in the forum it is hard to find a way to play the soundfiles which are extracted of the srf-files. I figured out what it is and how to play these files under win os. Even better: I can also convert them to normal WAVE files.

I don't want to write it twice. So under [http://free.prohosting.com/jellyvis/cgi ... 3;start=17](http://free.prohosting.com/jellyvis/cgi-bin/YaBB/YaBB.cgi?board=news;action=display;num=1100006413;start=17) you can find a short description on how to play/convert the files yourself. This is too difficult for you? Then write a short mail to me and I can send you a small (german  ) program which takes a srf, extracts every resource it knows (graphics too) and converts ima4 to wave. All in one step.

Thanks for the information in this thread which made my program possible.

Greetings from germany!
## Post #19
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-09-19T07:39:30+00:00
- Post Title: 

> Hello folks and sorry for my broken english (i am from germany)! 
>
> 
>
> I have made it! 
>
> I worked two days on hacking the soundfiles of ydkj and now i can play them under win os. I used the german version of ydkj but wikipedia says that the english version will work too. 
>
> 
>
> So okay, here is what i figured out: 
>
> Extract the soundresources like mentioned above. Do so with MultiEx or other tools. MultiEx really does a bad job for this. Better write your own tool or use mine. 
>
> You'll get an ima4 encoded file but WITH a header. I do not understand the header so I deleted it. The header has a constant size of 84 bytes in every soundfile. Without the header the data must be a multiple of 34 - othernwise it is not an ima4. 
>
> Now add a new header in front of the data (for details see the AIFC description). Just use mine: 
>
> 46 4F 52 4D XX XX XX XX 41 49 46 43 46 56 45 52 
>
> 00 00 00 04 A2 80 51 40 43 4F 4D 4D 00 00 00 16 
>
> 00 01 YY YY YY YY 00 10 40 0D AF C8 00 00 00 00 
>
> 00 00 69 6D 61 34 53 53 4E 44 ZZ ZZ ZZ ZZ 00 00 
>
> 00 00 00 00 00 00 
>
> You have to calculate the values for X, Y and Z in big endian. 
>
> X = the total filesize (data+header) - 8 Bytes 
>
> Y = size of data / 34 Bytes 
>
> Z = size of data + 8 Bytes 
>
> Rename the file to an extension ".aifc". With this you can (and should) play it with Quicktime. You can also convert it with a tool aifc2wav. Google for it. My application uses the code of this project to convert the ima4 to wave (ima4 is a really easy codec by the way). But there seems to be a problem: The wavefiles sound cropped. Maybe something wrong in the decoding. 
>
> 
>
> Realize that the musicloops are not ima4 encoded. You can see this in the 84 bytes header at adress 0x3C. There is a "ima4" or 00 00 00 00. In case it is not ima4 encoded it is just plain pcm wave. use it with 22,5kHz 16bit and 1 channel. 
>
> 
>
> You can get a compiled (german) tool which extracts srf to aifc and wave. Just ask me. But I am not going to make the source public for several reasons a) with aifc2wav it is almost trivial b) it is programmed under "stress" - no errorchecks c) legal issues. 
>
> 
>
> Greetings from germany!

I took the liberty to post your comments on that board at this one. 

You say "MultiEx does a bad job", what do you mean? It doesn't save a header? I'd have preferred you'd said "MultiEx doesn't add a header, so you have to add one yourself" . MultiEx extracts the files as they are saved in the archive. It's an extractor. 

You also might have credited El Condor for pointing you in the right direction. 

Oh and greetings from The Netherlands.
## Post #20
- Username: taraquedo
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Sep 19, 2006 6:44 am
- Post datetime: 2006-09-19T09:53:24+00:00
- Post Title: 

Hello again!

I've downloaded MultiEx in the latest version (with the scripts included there) and it works for the question resourcefiles well. But with the bigger (and more interesting) files like intro1.srf I had problems. MultiEx quits the open command to these files with an errormessage and you can do nothing against it.
Sorry I don't wanted to blame it on MultiEx. Of course MultiEx extracts the resources only and this is done quite good for the questionfiles. You can then delete the confusing header and replace it by mine.

Enjoy the Intro1, Intro2 and USD.srf - they are really funny
## Post #21
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-09-19T09:59:26+00:00
- Post Title: 

> Reply from taraquedo
>
> Hello again!

I've downloaded MultiEx in the latest version (with the scripts included there) and it works for the question resourcefiles well. But with the bigger (and more interesting) files like intro1.srf I had problems. MultiEx quits the open command to these files with an errormessage and you can do nothing against it.
Sorry I don't wanted to blame it on MultiEx. Of course MultiEx extracts the resources only and this is done quite good for the questionfiles. You can then delete the confusing header and replace it by mine.

Enjoy the Intro1, Intro2 and USD.srf - they are really funny

Then it must mean that there are multiple SRF formats, and MultiEx supports one of them. It's not MultiEx's fault then, the other SRF format may simply not be supported. I would need to have examples of a file that works and a file that doesn't. To compare.
## Post #22
- Username: elcondor
- Rank: VIP member
- Number of posts: 18
- Joined date: Tue Dec 14, 2004 6:28 pm
- Post datetime: 2006-09-26T19:22:32+00:00
- Post Title: 

Sorry to bring this up again, but is the script on the XentaXWiki the same as the one in MultiEx, as the one on the wiki appears to work for the more 'interesting' SRFs.
## Post #23
- Username: IntimidatedAgain
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-09-26T20:40:12+00:00
- Post Title: 

> Reply from elcondor
>
> Sorry to bring this up again, but is the script on the XentaXWiki the same as the one in MultiEx, as the one on the wiki appears to work for the more 'interesting' SRFs.

Hmm, it's not, so I checked. Damn, how's that possible. 

Anyway, the new script is here in BMS form:
[SRF.zip](https://xentaxbackup.github.io/file/874_SRF.zip)
## Post #24
- Username: taraquedo
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Sep 19, 2006 6:44 am
- Post datetime: 2006-11-26T13:22:32+00:00
- Post Title: 

Hi!

In a few hours you can download the SRF to WAVE Extractor I have made under
[http://srfextra.sourceforge.net](http://srfextra.sourceforge.net)

It uses the GPL - so feel free to download the source and reuse it in your projects or to get a hint on how the srf files work. In a few hours you can download the source and a compiled binary for use under Win32 there. Enjoy!

Greetings from Germany!
## Post #25
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2006-11-27T04:01:14+00:00
- Post Title: 

hmm... might I ask why you didn't just start a new topic for it?
## Post #26
- Username: IntimidatedAgain
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jul 02, 2009 12:30 am
- Post datetime: 2009-07-01T18:20:00+00:00
- Post Title: 

Apologies for the thread necro..

I've made a patch which fixes the audio clipping in the resulting .wav files in taraquedo's project above. 

I've tried to contact taraquedo directly, but I suspect after three years he may be inactive on the project, so i'm posting it here to help anyone who might come accross this.

I've also uploaded a patched binary [here](http://www.streamsense.net/srfextra.zip) for those who are not comfortable with patching source code, but please, always remember that downloading executable files from untrusted sources is risky. I can personally guarantee that the executable linked above is safe, but you have no reason to trust me.
[fixclamping.zip](https://xentaxbackup.github.io/file/2173_fixclamping.zip)
## Post #27
- Username: xjcl
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Sep 16, 2018 7:28 am
- Post datetime: 2018-09-16T00:34:56+00:00
- Post Title: 

I want to replace YDKJ3's question numbers with custom audio. Is this possible?


The SRFExtra program presented in this thread extracts music data from game files, but has no functionality to encode them AFAIK. To draw the whole pipeline:
SRF --SRFExtra--> AIFC (Apple audio) --SRFExtra--> WAV (Windows audio)
SRF <--???-- AIFC <--???-- WAV

So far I've downloaded and ran SRFExtra from [https://sourceforge.net/projects/srfextra/files/](https://sourceforge.net/projects/srfextra/files/), but as I said, that only allows me to extract audio, not encode it. 
Since the file format seems to be known, writing an encoder should be possible, right?

I can't even find the C++ source for SRFExtra! Has this just vanished?


Thus I can't apply the patch posted by IntimidatedAgain. Is this even needed? Wouldn't any other aifc2wav program work? I tried using the BMS files that everyone posted and downloaded quickbms. This produced files with no file extensions that had the same sizes as the AIFC files produced by SRFExtra, so I thought it must be them. But then I ran a program called aifc2wav from http://sed.free.fr in a command line to convert them and it said "bad sound file, can't load".

Windows Media Player fails to play both the SRFExtra and quickbms versions of the AIFC files, although the SRFExtra file works in VLC Player. Only the old script from the wiki (29 July 2005) produces somewhat sensible output, the current one (4 August 2005) produces files garbage files with garbage names. The WAV files from SRFExtra work fine, although they are (as previously stated) cropped at the end and some contain crackling (e.g. QNUMBERS.SRF.1004.wav or QNUMBERS.SRF.2003.wav from YDKJ3)
## Post #28
- Username: xjcl
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Sep 16, 2018 7:28 am
- Post datetime: 2020-05-25T09:02:58+00:00
- Post Title: 

Might as well use that bump to update y'all on my situation. I did figure out how to do it with the help of StackOverflow and plan to publish a blog post about it in the next two weeks.
