## Post #1
- Username: AchillesPDX
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Mar 17, 2012 1:02 am
- Post datetime: 2012-03-16T17:21:12+00:00
- Post Title: 4-channel MP3 XVAG... Anyone know how to extract them?

Hi Everyone!
I've been lurking around here for some time but just registered as I'm hoping someone out there can help. I'm trying to do my first game soundtrack rip and I've hit a snag when dealing with MP3 XVAG files. The game I'm ripping is a PSN title that uses XVAG for its audio storage. Several of the XVAG files are 2-channel MP3s that extract just fine using Nova Software Extractor, and play perfectly using the VGMStream Winamp plugin. 

Unfortunately, the bulk of the music in the game seems to be 4-channel audio which no program I have found can correctly deal with. I've uploaded a small sample file here:

[http://www.mediafire.com/?95spwnjd7cd6boj](http://www.mediafire.com/?95spwnjd7cd6boj)

I'm hoping someone can have a look at this and find a way to extract these into two separate 2-channel MP3s. I can also upload a working 2-channel XVAG from the same game if it helps figure out the problem.
## Post #2
- Username: AchillesPDX
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Mar 17, 2012 1:02 am
- Post datetime: 2012-04-03T20:58:40+00:00
- Post Title: 4-channel MP3 XVAG... Anyone know how to extract them?

113 views and no suggestions eh? I can't believe I stumped you all! I'm still interested in pursuing this if anyone has any ideas.

Thanks!
## Post #3
- Username: fadi002
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Apr 12, 2012 1:10 pm
- Post datetime: 2012-04-12T05:40:08+00:00
- Post Title: 4-channel MP3 XVAG... Anyone know how to extract them?

The programs that work the most for Journey's audio files are VLC media player and Audacity with FFmpeg. They mess up the file, but it's still recognizable. That's all I can do to help you.
## Post #4
- Username: fadi002
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Apr 12, 2012 1:10 pm
- Post datetime: 2012-04-17T15:22:03+00:00
- Post Title: 4-channel MP3 XVAG... Anyone know how to extract them?

I had a similiar problem, and discovered a way to fix these files. Here is the thread that explains how to do it: [viewtopic.php?f=17&t=8754](http://forum.xentax.com/viewtopic.php?f=17&t=8754). The file you have is very similar to the ones I mentioned in my thread, so it should work, but you have to use different values in the script.
## Post #5
- Username: AchillesPDX
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Mar 17, 2012 1:02 am
- Post datetime: 2012-04-17T17:32:10+00:00
- Post Title: 4-channel MP3 XVAG... Anyone know how to extract them?

> Reply from fadi002
>
> I had a similiar problem, and discovered a way to fix these files. Here is the thread that explains how to do it: viewtopic.php?f=17&t=8754. The file you have is very similar to the ones I mentioned in my thread, so it should work, but you have to use different values in the script.

Thank you! This seems like it's on the right track. The only thing I can't figure out is how to calculate the interleave. I looked at your sample 789_sandlantis_doorwalkthrough.xvag that you posted and you found an interleave of 0x2A00, but I can't for the life of me figure out how you determined that value. Every occurrence of FFFB seems to be exactly 768 bytes apart, which is 0x300 in hex... so if you could shed some light on how you came up with 0x2A00, I'd really appreciate it.

Thanks!
## Post #6
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2012-04-17T18:05:40+00:00
- Post Title: 4-channel MP3 XVAG... Anyone know how to extract them?

The interleave isn't exactly after the first frame, you have to keep going frame by frame to determine the interleave offset.
## Post #7
- Username: fadi002
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Apr 12, 2012 1:10 pm
- Post datetime: 2012-04-17T18:29:27+00:00
- Post Title: 4-channel MP3 XVAG... Anyone know how to extract them?

> Reply from AchillesPDX
>
> fadi002 wrote:I had a similiar problem, and discovered a way to fix these files. Here is the thread that explains how to do it: viewtopic.php?f=17&t=8754. The file you have is very similar to the ones I mentioned in my thread, so it should work, but you have to use different values in the script.

Thank you! This seems like it's on the right track. The only thing I can't figure out is how to calculate the interleave. I looked at your sample 789_sandlantis_doorwalkthrough.xvag that you posted and you found an interleave of 0x2A00, but I can't for the life of me figure out how you determined that value. Every occurrence of FFFB seems to be exactly 768 bytes apart, which is 0x300 in hex... so if you could shed some light on how you came up with 0x2A00, I'd really appreciate it.

Thanks!
Well, initially I just kept guessing and trying every number by adding or subtracting 0x300 to the number that didn't work (I started at 3000). But I just figured out an easier way. Keep looking at the contents of every frame (what's in between the FFFB values) and notice any patterns (usually, in the beginning, it's one repeated ascii character). Keep counting the frames, and when you see the pattern change, remember the number of that frame. Convert that number to hex, then multiply 0x300 by that number. (Here's a hex calculator: [http://www.squarebox.co.uk/hcalc.html](http://www.squarebox.co.uk/hcalc.html)) So if the number you counted was 16, the interleave would be 3000. If you get it wrong, try adding 0x300 or subtracting 0x300. If it still doesn't work, look at the patterns more carefully.

Oh, and btw, the frame value is the address of the character that's before the first frame (for example, if the first frame starts with 11 00 FF FB D4, the frame value would be the address of the 00)
## Post #8
- Username: AchillesPDX
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Mar 17, 2012 1:02 am
- Post datetime: 2012-04-17T19:27:55+00:00
- Post Title: 4-channel MP3 XVAG... Anyone know how to extract them?

> Reply from fadi002
>
> AchillesPDX wrote:fadi002 wrote:I had a similiar problem, and discovered a way to fix these files. Here is the thread that explains how to do it: viewtopic.php?f=17&t=8754. The file you have is very similar to the ones I mentioned in my thread, so it should work, but you have to use different values in the script.

Thank you! This seems like it's on the right track. The only thing I can't figure out is how to calculate the interleave. I looked at your sample 789_sandlantis_doorwalkthrough.xvag that you posted and you found an interleave of 0x2A00, but I can't for the life of me figure out how you determined that value. Every occurrence of FFFB seems to be exactly 768 bytes apart, which is 0x300 in hex... so if you could shed some light on how you came up with 0x2A00, I'd really appreciate it.

Thanks!
Well, initially I just kept guessing and trying every number by adding or subtracting 0x300 to the number that didn't work (I started at 3000). But I just figured out an easier way. Keep looking at the contents of every frame (what's in between the FFFB values) and notice any patterns (usually, in the beginning, it's one repeated ascii character). Keep counting the frames, and when you see the pattern change, remember the number of that frame. Convert that number to hex, then multiply 0x300 by that number. (Here's a hex calculator: http://www.squarebox.co.uk/hcalc.html) So if the number you counted was 16, the interleave would be 3000. If you get it wrong, try adding 0x300 or subtracting 0x300. If it still doesn't work, look at the patterns more carefully.

Oh, and btw, the frame value is the address of the character that's before the first frame (for example, if the first frame starts with 11 00 FF FB D4, the frame value would be the address of the 00)
YEE HAW! Got it! Woo Hoo! Now to finish my rip! Thank you so much!

And of course each track uses a different interleave... goddammit...
## Post #9
- Username: fadi002
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Apr 12, 2012 1:10 pm
- Post datetime: 2012-04-17T20:05:47+00:00
- Post Title: 4-channel MP3 XVAG... Anyone know how to extract them?

> Reply from AchillesPDX
>
> fadi002 wrote:AchillesPDX wrote:

Thank you! This seems like it's on the right track. The only thing I can't figure out is how to calculate the interleave. I looked at your sample 789_sandlantis_doorwalkthrough.xvag that you posted and you found an interleave of 0x2A00, but I can't for the life of me figure out how you determined that value. Every occurrence of FFFB seems to be exactly 768 bytes apart, which is 0x300 in hex... so if you could shed some light on how you came up with 0x2A00, I'd really appreciate it.

Thanks!
Well, initially I just kept guessing and trying every number by adding or subtracting 0x300 to the number that didn't work (I started at 3000). But I just figured out an easier way. Keep looking at the contents of every frame (what's in between the FFFB values) and notice any patterns (usually, in the beginning, it's one repeated ascii character). Keep counting the frames, and when you see the pattern change, remember the number of that frame. Convert that number to hex, then multiply 0x300 by that number. (Here's a hex calculator: http://www.squarebox.co.uk/hcalc.html) So if the number you counted was 16, the interleave would be 3000. If you get it wrong, try adding 0x300 or subtracting 0x300. If it still doesn't work, look at the patterns more carefully.

Oh, and btw, the frame value is the address of the character that's before the first frame (for example, if the first frame starts with 11 00 FF FB D4, the frame value would be the address of the 00)
YEE HAW! Got it! Woo Hoo! Now to finish my rip! Thank you so much!

And of course each track uses a different interleave... goddammit...
What were the values?
I found out some (yes, more than one) of them have a header of 133, interleave of 1200, and 2 layers.

Edit: When I said what's bolded and underlined at the top, I meant multiply the number you found by the number of bytes each frame is, in hex. It's not always 300.
## Post #10
- Username: AchillesPDX
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Mar 17, 2012 1:02 am
- Post datetime: 2012-04-17T20:13:28+00:00
- Post Title: 4-channel MP3 XVAG... Anyone know how to extract them?

Well the first file I tried (and these are from the game Journey) has header: 0xDC, Interleave: 1390 and Layers of 2.

The second file has the same length of header, and each frame seems to be the same length as the first file (626 bytes) but the interleave position is different and I haven't been able to find it yet.
## Post #11
- Username: AchillesPDX
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Mar 17, 2012 1:02 am
- Post datetime: 2012-04-17T21:32:25+00:00
- Post Title: 4-channel MP3 XVAG... Anyone know how to extract them?

Well, it's a pain in the ass, but I figured out a solution. You can easily find the Interleave by looking at the end of the file and finding the huge patches of "00 00 00 00 00" and calculating the distance between the patches. Then you count the patches to get the number of layers. All that's left is to find the length of the header. Sadly, each one of my files seems to have different values for all of these things
## Post #12
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2013-04-20T04:59:41+00:00
- Post Title: 4-channel MP3 XVAG... Anyone know how to extract them?

[Click here to see my post on how to deinterleave MPEG XVAG](http://forum.xentax.com/viewtopic.php?f=17&t=5014&p=86146#p86146)
