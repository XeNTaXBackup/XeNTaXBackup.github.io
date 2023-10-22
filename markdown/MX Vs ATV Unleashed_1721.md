## Post #1
- Username: mambox
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Wed Mar 24, 2004 9:06 pm
- Post datetime: 2006-02-03T12:28:35+00:00
- Post Title: MX Vs ATV Unleashed

hello,

i played this game,seen a track editor but it can't import the official tracks 

your created track is then converted to .pak

would be funny to a way to use the official track into editor,modding community wont to share their tool claiming that another users want steal their work..well kiddies community.

here's an example...

[http://rapidshare.de/files/12449557/MST.pak.html](http://rapidshare.de/files/12449557/MST.pak.html)

greets.
## Post #2
- Username: PXR
- Rank: VIP member
- Number of posts: 61
- Joined date: Thu Mar 24, 2005 2:55 am
- Post datetime: 2006-02-03T13:28:41+00:00
- Post Title: MX Vs ATV Unleashed

```

//for each file:
    100 - Filename
    004 - File Offset relative to start of data
    004 - File Length

//for each file:
      x - file data
```


I know I've seen this format in another game, but can't find out which one. Anyway, here's a compiled BMS-script that will support importing.
[PAK.zip](https://xentaxbackup.github.io/file/603_PAK.zip)
## Post #3
- Username: mambox
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Wed Mar 24, 2004 9:06 pm
- Post datetime: 2006-02-03T17:19:21+00:00
- Post Title: MX Vs ATV Unleashed

thanks a lot!

you make my day!
## Post #4
- Username: Kamshaft
- Rank: VIP member
- Number of posts: 43
- Joined date: Thu Mar 30, 2006 1:18 am
- Post datetime: 2006-03-29T22:59:37+00:00
- Post Title: MX Vs ATV Unleashed

> Reply from PXR
>
> 
I know I've seen this format in another game, but can't find out which one. Anyway, here's a compiled BMS-script that will support importing.

I hope you can remember which game because I'd like to get importing/file replacement for this file format?
## Post #5
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-03-31T10:41:27+00:00
- Post Title: MX Vs ATV Unleashed

Well, I have written a plugin for this that will enable extract and replacement. 
Working on creation and adding.
## Post #6
- Username: Kamshaft
- Rank: VIP member
- Number of posts: 43
- Joined date: Thu Mar 30, 2006 1:18 am
- Post datetime: 2006-03-31T15:59:51+00:00
- Post Title: MX Vs ATV Unleashed

Mr. Mouse is the man!
Thanks!

Don't forget to check out the graphic files too.
## Post #7
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-04-01T21:45:55+00:00
- Post Title: MX Vs ATV Unleashed

Okay, I fixed a bug Kamshaft pointed out when opening the common.pak. 

Turns out the plugin tripped over a 0-sized file in the common.pak when replacing and recreating. What use could a zero sized file have?Perhaps a placeholder. Whatever the use, the plugin couldn't handle it. Now, it can. 

So, no adding/new yet, but at least that minor bug fixed. 

Get the attached plugin and throw it in the plugins/pak folder, overwriting the old plugin as needed.
## Post #8
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-04-02T11:39:04+00:00
- Post Title: MX Vs ATV Unleashed

Ah a swift update. 

Now with creation support. 

This should go a long way in helping people mod. You see, in theory you can extract files from an original archive somewhere. Then alter some of the files and then recreate the archive (in the base folder where you saved the extracted files) and you should have a new archive that containes the altered files as well. 

Just go to File->New to create a PAK file from this game. Then say Yes to create from directory/folder and point to the folder where your files are. That should create an archive from the files (recursively) in that folder.
## Post #9
- Username: Kamshaft
- Rank: VIP member
- Number of posts: 43
- Joined date: Thu Mar 30, 2006 1:18 am
- Post datetime: 2006-04-02T12:19:26+00:00
- Post Title: MX Vs ATV Unleashed

The path doesn't seem to be retained.
The files seem to be.

Try making a path that is long...like...

\Data\UserTracks\Swan_Hills_2006\Swan_Hills_2006.scn

It only keeps....

erTracks\Swan_Hills_2006\Swan_Hills_2006.scn
## Post #10
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-04-02T12:45:11+00:00
- Post Title: MX Vs ATV Unleashed

odd
## Post #11
- Username: Kamshaft
- Rank: VIP member
- Number of posts: 43
- Joined date: Thu Mar 30, 2006 1:18 am
- Post datetime: 2006-04-02T12:55:01+00:00
- Post Title: MX Vs ATV Unleashed

Your telling me.
## Post #12
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-04-02T13:59:33+00:00
- Post Title: MX Vs ATV Unleashed

fixed (test it please)
## Post #13
- Username: Kamshaft
- Rank: VIP member
- Number of posts: 43
- Joined date: Thu Mar 30, 2006 1:18 am
- Post datetime: 2006-04-02T14:13:40+00:00
- Post Title: MX Vs ATV Unleashed

Seems to grab the full path instead of the one you point to.

Everything is else seems fine, except for the .PAK extension needs to be .pak (lowercase) otherwise the game doesn't read the archive, must be case sensitive.

Any luck with the DXT graphics files?
## Post #14
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-04-02T14:18:40+00:00
- Post Title: MX Vs ATV Unleashed

Ok, fixed another small thing. The previous version ignored zero sized files. Now it saves those as well. 

Please provide the two files of the tracks , one that does show and the other that doesn't.
## Post #15
- Username: Kamshaft
- Rank: VIP member
- Number of posts: 43
- Joined date: Thu Mar 30, 2006 1:18 am
- Post datetime: 2006-04-02T14:28:22+00:00
- Post Title: MX Vs ATV Unleashed

Modified my post. PLease re-read.
## Post #16
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-04-02T15:19:11+00:00
- Post Title: 

Ok, yet another version, this should fix the lot. 

Check out the screen..spot the differences.  The ert.pak is a recreation of the common.pak. 
[test.jpg](https://xentaxbackup.github.io/file/674_test.jpg)
## Post #17
- Username: Kamshaft
- Rank: VIP member
- Number of posts: 43
- Joined date: Thu Mar 30, 2006 1:18 am
- Post datetime: 2006-04-02T17:03:16+00:00
- Post Title: 

Cool, we're almost there...

The only thing I can see left is, making the file extension the program creates, lowercase (.pak, not .PAK)..because the game won't read the uppercase files. Weird, but true.

The other bug is, the path imbedded in the file.  What I mean is...

if I tell the program to grab files within this....
d:\mva_test\files1\(then the rest of the files and dir here)

in the PAK file it embeds, the full path ...
mva_test\files1\

rather than excluding that part of the path. Make sense?
## Post #18
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-04-02T17:17:46+00:00
- Post Title: 

Hmm, what it does: it takes the path of the pak file you wish to create and if that path matches any path part of the files that you wish to insert it will remove that part. So,it depends where you save the pak. You can save it in the folder you wish to include, the pak file itself will be ignored in the inclusion.
## Post #19
- Username: bruceatk
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Apr 03, 2006 1:50 am
- Post datetime: 2006-04-02T17:55:28+00:00
- Post Title: 

I just installed and registered MultiEX this weekend.  The MXvsATV plugin is the first one that I've installed.  When I go to open an MXvsATV pak file the "Files of type" displays this:

MXvsATVUnleashed(*.)

So it doesn't list any files unless I enter a filename.  When you go to create a pak file (File-->New) it doesn't show up in the list as a *.PAK file it is at the top of the list as "*. (MXvsATVUnleashed)".

Kam's doesnt do this instead his shows *.PAK.  

Bruce
## Post #20
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-04-02T18:40:13+00:00
- Post Title: 

Where did you put the dll ? What folder?
## Post #21
- Username: bruceatk
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Apr 03, 2006 1:50 am
- Post datetime: 2006-04-02T20:24:36+00:00
- Post Title: 

That's all it was.  It was in the plugins folder not the plugins\pak folder.  I moved it and that fixed it.

Thanks,
Bruce
## Post #22
- Username: ocr_smokngrn
- Rank: VIP member
- Number of posts: 27
- Joined date: Mon Apr 03, 2006 11:57 am
- Post datetime: 2006-04-03T08:39:44+00:00
- Post Title: 

i got the plugin and donated to the site.
Sooo.. i been playing around and i think i have a good grasp on what things i can add (aud files and animation files sun flare stuff in the .toy files.

My question is... have you successfully repaked a track and had it run in game?

I have been able to get it to show up in game, but it crashes to desktop.

 i have been noticing the diference on the way the stock tracks are structured, and the way the repaks are structured. do i need to organize these files in a certian way to get this to work? it seams as if i cant unpak and repak (without making any changes) and get it to even show up anymore
## Post #23
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-04-03T09:36:09+00:00
- Post Title: 

Let's take a track as an example and please post it here.
## Post #24
- Username: ocr_smokngrn
- Rank: VIP member
- Number of posts: 27
- Joined date: Mon Apr 03, 2006 11:57 am
- Post datetime: 2006-04-03T10:23:00+00:00
- Post Title: 

here is a rar with 2 tracks. 1 stock and one quick test track... the user created track is fresh from the track editor, i have not touched it. 

[http://home.comcast.net/~smesple/test.rar](http://home.comcast.net/~smesple/test.rar)

i have tried putting the extracted files in different named folders.....i wasnt able to do anything that worked... but then agian ima ultra-noob.


also off topic. do these companies use a in house codec for .wav files? i cant seam to play any of the extracted wav files.
## Post #25
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-04-05T18:18:49+00:00
- Post Title: 

Guys, I have been away for a couple of days. But I looked at it now, briefly, and it seems the bug is that the plugin unstably leaves out the last file during repack, that would of course explain a crash. Rest assured that I will not rest myself until I have this solved.
## Post #26
- Username: ocr_smokngrn
- Rank: VIP member
- Number of posts: 27
- Joined date: Mon Apr 03, 2006 11:57 am
- Post datetime: 2006-04-06T04:50:40+00:00
- Post Title: 

You are the man....
## Post #27
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-04-06T17:40:30+00:00
- Post Title: 

Okay, I fixed it, I think. I tried it on a pak file and it repacked perfectly as expected. So, please go ahead and try the new plugin on the track you noticed crashed earlier.
## Post #28
- Username: ocr_smokngrn
- Rank: VIP member
- Number of posts: 27
- Joined date: Mon Apr 03, 2006 11:57 am
- Post datetime: 2006-04-06T18:25:29+00:00
- Post Title: 

testing now
## Post #29
- Username: ocr_smokngrn
- Rank: VIP member
- Number of posts: 27
- Joined date: Mon Apr 03, 2006 11:57 am
- Post datetime: 2006-04-06T18:44:06+00:00
- Post Title: 

perfect!!!!! thank you sooooo much
## Post #30
- Username: Kamshaft
- Rank: VIP member
- Number of posts: 43
- Joined date: Thu Mar 30, 2006 1:18 am
- Post datetime: 2006-04-06T21:51:28+00:00
- Post Title: 

YOu rock man!
## Post #31
- Username: BPh_Designs
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Apr 05, 2006 7:14 pm
- Post datetime: 2006-04-21T09:31:54+00:00
- Post Title: 

Great work guys, thks for all.
Phil.
## Post #32
- Username: REV_Kustomken
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue May 02, 2006 2:42 am
- Post datetime: 2006-05-01T19:11:57+00:00
- Post Title: 

Saw OCR_smokingrn ask before, but no reply yet, I can't get the .wav files extracted from the aud.pak to play in any player.  Anyone know if there is a proprietary codec needed/available anywhere for this?  Or is it an extraction problem?

The files extracted show properties of 1411kbps 16bit 2chan stereo 44kHz MS ADPCM format.  but I can't play them in anything.

thanks in advance for any info
## Post #33
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-05-01T19:22:50+00:00
- Post Title: 

i wanna see that file =o , i dont have the game though so i cannot extract the files =( ....plz upload?
## Post #34
- Username: REV_Kustomken
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue May 02, 2006 2:42 am
- Post datetime: 2006-05-01T21:41:27+00:00
- Post Title: 

Here is a zip with a few of the extracted .wav files.  These ones are lower bitrate, 1 channel mono, and 16kHz sample rate, the stereo music tracks are too large to send.  

I did enclose a jpg screenshot of the properties tab for one of them, showing the higher bitrate, etc.
## Post #35
- Username: BPh_Designs
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Apr 05, 2006 7:14 pm
- Post datetime: 2006-05-02T09:06:05+00:00
- Post Title: 

The contents of this post was deleted because of possible forum rules violation.
## Post #36
- Username: REV_Kustomken
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue May 02, 2006 2:42 am
- Post datetime: 2006-05-03T03:24:07+00:00
- Post Title: 

Thank you for the effort in uploading the files.  Did you try playing the .wav files in a player?  If so, and it worked, what player?

If not, please try them.  They do the same thing here for me as the ones I extracted do.  They don't play and I get the following messages.

windows error from winamp

Couldn't find destination format.


media player error message

Windows Media Player cannot play the file. One or more codecs required to play the file could not be found.


The properties for the files all say they are Microsoft ADPCM, and I have the proper codecs installed.  All other .wav files on my system play normally.

Thanks again.
## Post #37
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-05-03T06:40:31+00:00
- Post Title: 

They dont play correctly........=o   (same error as you)

and they have a header of a normal RIFF file and codec ID for Microsoft ADPCM. im not sure what this is. is this an XBOX game? =o
## Post #38
- Username: BPh_Designs
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Apr 05, 2006 7:14 pm
- Post datetime: 2006-05-03T11:14:15+00:00
- Post Title: 

No, I can't listen the sounds, that's why I uploaded the file lol.
Yes it's a pc game from the XBOX port.
Maybe someone will find how to open this format (codec ? ...) and than we'll be able to add our prefered song or something else into our creations.
## Post #39
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-05-03T11:19:29+00:00
- Post Title: 

Maybe its just as simple as being the standard XBOX ADPCM ? =///
*just a thought*
## Post #40
- Username: ocr_smokngrn
- Rank: VIP member
- Number of posts: 27
- Joined date: Mon Apr 03, 2006 11:57 am
- Post datetime: 2006-05-03T19:30:04+00:00
- Post Title: 

I tried the xbox codecs a few weeks ago.. No luck
## Post #41
- Username: BPh_Designs
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Apr 05, 2006 7:14 pm
- Post datetime: 2006-07-29T21:02:00+00:00
- Post Title: 

I removed the link if you don't mind  - Mr.Mouse
## Post #42
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-07-30T07:17:05+00:00
- Post Title: 

Thanks for the info, I have come into contact with that forum. They will take action. 

In the meantime, let's sit down and see how we can get to rideorange, as this is his address he provided with PayPal.


I have also send him a small notice:

> Your betrayal of the MultiEx Commander community has not become unnoticed.
>
> 
>
> We and others will take appropriate action. By registering via PayPal you have provided us also with an address.
>
> 
>
> In the meantime, all future versions of MultiEx Commander will be useless with the code you got, and those that downloaded it will also have a non-functioning code, thanks to you.
>
> 
>
> The forum you posted it on have been notified and will also soon take action against you.
>
> 
>
> Fans of the MX vs ATV game series came to us for help and we helped them out.You have no idea of the amount of personal free time people have put into that support. The free version of MultiEx Commander make everyone able to extract, the extremely small donation needed to get the other features never ad up to the amount of work. You disgust us and everybody else in the world with this childish act of puberty.
>
> 
>
> This is not the last message you will recieve.
>
> 
>
> Mike Zuurman
## Post #43
- Username: BPh_Designs
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Apr 05, 2006 7:14 pm
- Post datetime: 2006-07-30T10:19:33+00:00
- Post Title: 

Good job Mike
## Post #44
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-07-30T17:39:23+00:00
- Post Title: 

This matter has been resolved. The key code has been removed and we have been contacted by a parent of the 10-year old rideorange. They apologized for his actions and would discipline him accordingly. Rideorange also sent an email to apologize for his actions. We will leave it at that, of course.
