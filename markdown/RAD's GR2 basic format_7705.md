## Post #1
- Username: Privateer
- Rank: veteran
- Number of posts: 104
- Joined date: Fri Oct 21, 2011 8:33 pm
- Post datetime: 2011-11-18T00:05:46+00:00
- Post Title: RAD's GR2 basic format

After nearly 2 years of studying this file? I can tell you many ways to adjust or work with it.
Some Games use different tricks to screw with the files but most are very primitive and preserve the basic layout.
I'd be happy to discuss this file format and how to read it with anyone interested.
## Post #2
- Username: Privateer
- Rank: veteran
- Number of posts: 104
- Joined date: Fri Oct 21, 2011 8:33 pm
- Post datetime: 2011-11-18T22:38:42+00:00
- Post Title: RAD's GR2 basic format

Over the years many have come to the conclusion that one needs to use the granny2.dll to read the basic GR2 format.
This is a false conclusion as long as the file is not OODLE 2 encoded.
(That's RAD's in-house compression.)
It's very easy to see if a file is compressed within 108 bytes or so of the start of the file.
After that? You can read each Section block to determine if following sections are encrypted.
Or if the Section is an empty section.

I have detailed knowledge of the file format by studying it in 010 Hex Editor.
I  have a few scripts for 010 the 'reads' the start of GR2 files.
I also know how to adjust the CRC values and get a GR2 file to show textures that usually don't show with GrannyViewer.

What I don't do is program very well at this time.
## Post #3
- Username: Privateer
- Rank: veteran
- Number of posts: 104
- Joined date: Fri Oct 21, 2011 8:33 pm
- Post datetime: 2011-11-19T01:12:10+00:00
- Post Title: RAD's GR2 basic format

After many contacts with RAD personnel, I know that We can do what we wish with GR2 files.
What they DO NOT like is useing the granny2.dll or useing the leaked SDK's to work the file.
IF you are good at file formats? You don't need the SDK or anything else.
A good understanding of working in Hex is all that is needed.

Take the CRC of GR2 files.
To figure that out?
Delete the first 104 bytes and then do a standard CRC 32.
Add the 104 bytes back and adjust the CRC setting of that.
## Post #4
- Username: Privateer
- Rank: veteran
- Number of posts: 104
- Joined date: Fri Oct 21, 2011 8:33 pm
- Post datetime: 2011-11-19T02:46:24+00:00
- Post Title: RAD's GR2 basic format

More information will be produced if someone shows interest.
If not?
I'll let this thread die.
## Post #5
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-11-19T02:58:29+00:00
- Post Title: RAD's GR2 basic format

Someone would need to reverse the compression used in the granny dll then this thread could go further otherwise i dont see much point.
## Post #6
- Username: Privateer
- Rank: veteran
- Number of posts: 104
- Joined date: Fri Oct 21, 2011 8:33 pm
- Post datetime: 2011-11-19T03:03:42+00:00
- Post Title: RAD's GR2 basic format

Only some GR2 files are compressed.
Those are actually far and few between.
What GR2 file would you be interested in looking at for example?
Send me the first 1000 bytes and I'll tell you if it's compressed and what sections are empty.
Make it harder and send me the whole GR2 and I'll change things in a way you can't miss!

The whole basis of this forum is to promote knowledge of file formats is it not?
Yet you are so ready to dismiss what I have to offer?

You are sadly mistaken if you believe me to be a noob when it involves the GR2 format!
I may be a noob here?
But that is just a forum title for post counts.
## Post #7
- Username: delium
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Jun 14, 2010 6:26 pm
- Post datetime: 2011-11-19T10:35:32+00:00
- Post Title: RAD's GR2 basic format

don´t know if it helps, but regarding to the RAD homepage ([http://www.radgametools.com/granny/customers.html](http://www.radgametools.com/granny/customers.html)), everquest 2 also uses the granny sdk.
and on this page you can find a reader for the *.draw mesh files from eq2:
[http://eq2.blazlabs.com/](http://eq2.blazlabs.com/)
## Post #8
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2011-11-19T10:49:30+00:00
- Post Title: RAD's GR2 basic format

It's great that you offer information about the gr2 format and I am sure many people are interested in it. 

Unfortunately, I have not yet found a complete specification of the gr2 format anywhere. As a start, could you please tell us more about the format of the file header and the different sections in the file? Especially, what data is stored in the files in the first place?

Have you completely analysed the files, including the animations? Or are the animations contained in other files?
## Post #9
- Username: Privateer
- Rank: veteran
- Number of posts: 104
- Joined date: Fri Oct 21, 2011 8:33 pm
- Post datetime: 2011-11-19T16:33:07+00:00
- Post Title: RAD's GR2 basic format

> As a start, could you please tell us more about the format of the file header and the different sections in the file? Especially, what data is stored in the files in the first place?
I'll post the information soon along with a basic template for 010 Hex Editor that breaks the information down.
I highly recommend buying a copy of 010.
At $50.00 it's a fantastic Tool!

> Have you completely analysed the files, including the animations? Or are the animations contained in other files?
Animations may or may not be in the same GR2. Or they may be in a different format depending on what the Dev's did.
A look at SWTOR files is an example of a different way to do the animations.
That's part of the beauty (and confussion) of the Granny system.
## Post #10
- Username: Privateer
- Rank: veteran
- Number of posts: 104
- Joined date: Fri Oct 21, 2011 8:33 pm
- Post datetime: 2011-11-21T21:34:25+00:00
- Post Title: RAD's GR2 basic format

Here is an example of an edited GR2 file I released as a Mod for Silent Hunter 5.
[http://www.subsim.com/radioroom/showthread.php?t=187659](http://www.subsim.com/radioroom/showthread.php?t=187659)

The gate in the Bunker is as far as one could go in the stock file.


After editing you can go MUCH Further and there is no Gate.
Download the video to see the results.
[http://www.mediafire.com/?141175d8yg5d7vy](http://www.mediafire.com/?141175d8yg5d7vy)

Or view it on Youtube if in the U.S.
[http://www.youtube.com/user/PrivateerGW ... gR26wQAKPg](http://www.youtube.com/user/PrivateerGWX#p/a/u/0/AgR26wQAKPg)

I'll upload both versions of the GR2 file ASAP.
## Post #11
- Username: Privateer
- Rank: veteran
- Number of posts: 104
- Joined date: Fri Oct 21, 2011 8:33 pm
- Post datetime: 2011-11-21T22:45:16+00:00
- Post Title: RAD's GR2 basic format

Here's the before and after GR2 files.
[http://www.mediafire.com/?86da3ykn4640bny](http://www.mediafire.com/?86da3ykn4640bny)

With those files I'll start explaining the basic format starting with the Magic Value.
The Magic Block is the first 32 bytes that identify the file as a GR2 file.
I have no idea what it all means but it's what I use to find a GR2 file with no extension or a proper name.
Early SWTOR extracts have a butt load of files labeled as txt files that are infact GR2 files.
My finder finds them though by searching the file beginnings for this Magic Block.

The next 4 bytes are important!
This gives us the total size of the Header.
This whole chunk of data is NEVER encoded.
At lest on PC platforms which I have looked at.
The Header is the total size of everything before the start of the first section or section 0.

The next 12 bytes I'm not sure of or have incomplete data on.

This brings us to the next interesting bunch of data.

07 00 00 00 6C 26 9C 00 66 FD 53 A5 48 00 00 00
08 00 00 00 06 00 00 00 00 00 00 00 00 00 00 00
00 00 00 00 32 00 00 80 00 00 00 00 00 00 00 00
00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
00 00 00 00 00 00 00 00

Open the bunker.gr2 file with GrannyViewer and compare the information in a Hex Editor.
Do you see where I'm at here?

This is all the information you see on the first screen on opening the file with GrannyViewer!
File format revision 7 is the first 4 bytes.
Total file size is the next 4 bytes. (May not be correct depending on Game)
The next 4 bytes is the CRC. This is where Game Dev's will screw things so you can't view in GrannyViewer. No longer an issue!
Now we see the count to Section 0 from File format revision.
Next is total number of sections.
After that is 4 floats that I'm not sure of.
Now the Tag and 8 unknown floats before we hit the first Section Index and probably the most important information we need before we go further.

If the next 4 bytes are NOT 00 00 00 00?
You have a compressed Section!
00 00 00 00 = No Compression.
01 00 00 00 = Oodle compression which is depricated and only used for backwards compatability
02 00 00 00 = Oodle1 the replacement.

I have not seen a file that does not compress just one section.
Most Devs seem to set compression as Yes for the total file and then move on.
If I see a compression on section 0 I'm done anyway as most of the good stuff is in this section.
## Post #12
- Username: Privateer
- Rank: veteran
- Number of posts: 104
- Joined date: Fri Oct 21, 2011 8:33 pm
- Post datetime: 2011-11-22T01:41:31+00:00
- Post Title: RAD's GR2 basic format

If you've figured everything out to this point?
Congratulations. You are learning quickly or are good with Hexing.
As it can get very confuseing from here on?
I'll up load a basic gr2 that you can use to follow along.
The bunker is an advanced form of the basic form.
