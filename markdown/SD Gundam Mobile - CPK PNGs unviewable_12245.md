## Post #1
- Username: Nigoli
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Mar 29, 2011 2:23 pm
- Post datetime: 2014-11-17T05:06:44+00:00
- Post Title: SD Gundam Mobile - CPK PNGs unviewable

Hello,

For this game, it downloads new CPK packages for game content depending on the event that happens each week or new Gashapon that's given. I've been able to unpack CPKs fine, including HCA audio with fine playback for those files. But I'm having trouble viewing any of the PNGs. I put one through a Hex editor to notice that there's no header for PNGs at all.

But are these really PNG files in the end? I'm posting one PNG out of the pack as an attachment as an example file that I'm having problems with.

Thanks in Advance.
## Post #2
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2014-11-28T20:23:58+00:00
- Post Title: SD Gundam Mobile - CPK PNGs unviewable

Hi,
the whole file was XOR'ed with this sequence: { 99, 199, 246, 235, 32, 40, 110, 148, 40, 209, 27, 162, 36, 84, 20, 9 }

I created a tool which transforms the PNG into its original format.
Usage: Just drag and drop one or multiple PNG files onto the EXE.


 XOR.zip
(42.15 KiB) Downloaded 39 times

 (C source file and Windows binary)

Update: Instead of a single PNG you can now drag & drop multiple files onto the application.
## Post #3
- Username: Nigoli
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Mar 29, 2011 2:23 pm
- Post datetime: 2014-11-29T07:32:25+00:00
- Post Title: SD Gundam Mobile - CPK PNGs unviewable

I can confirm the tool you've compiled works with all other PNGs like this for the game.

Thank you for taking the time to look into this!
## Post #4
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2014-11-29T17:09:13+00:00
- Post Title: SD Gundam Mobile - CPK PNGs unviewable

Great!
I'm glad I could help.

By the way, I just reuploaded the tool which can now handle multiple files.
Cheers!
## Post #5
- Username: Oinkmon
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Nov 29, 2014 6:38 pm
- Post datetime: 2014-11-29T20:52:09+00:00
- Post Title: SD Gundam Mobile - CPK PNGs unviewable

If it's not too much trouble can you make a 32-bit version? this one seems to be for 64-bit systems only.
## Post #6
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2014-11-30T01:37:31+00:00
- Post Title: SD Gundam Mobile - CPK PNGs unviewable

Here's the 32-bit version: 

 XOR_32bit.zip
(2.25 KiB) Downloaded 28 times
## Post #7
- Username: Oinkmon
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Nov 29, 2014 6:38 pm
- Post datetime: 2014-11-30T12:45:37+00:00
- Post Title: SD Gundam Mobile - CPK PNGs unviewable

Thank you for all your efforts!
