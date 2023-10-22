## Post #1
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2010-05-11T13:09:34+00:00
- Post Title: Unknown graphic and music file format

Hello folks. As you may know, we've had a slight breakthrough in reverse-engineering the Multimedia Fusion WGM files. Unfortunately, though we have extracted all contained in them, it only leads to further unknown files (Without even an extension!). It's become somewhat vital to me that I get the graphics out of these files and I hope to do it soon. I was hoping someone could have a look at these mysterious files and tell me what to do with them so I can extract the graphics (and possibly music). Looking over these with a hex editor I notice a lot of WAV files within them, but the larger files I assume are graphics.
Someone please take a look at the 'ins' files included in these folders and tell me if the graphics are salvagable.
[http://www.sendspace.com/file/8mziys](http://www.sendspace.com/file/8mziys)
## Post #2
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2010-05-16T07:28:29+00:00
- Post Title: Unknown graphic and music file format

The files in the LOP folder are mainly ImpulseTracker files with altered header, the INS files contains the samples for Impulse files,
so what this is, is the files without extension are songdata, the INS files contains the Samples for the Songdata. im trying to join them together and see if i can create
a normal output.
## Post #3
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2010-05-17T22:41:45+00:00
- Post Title: Unknown graphic and music file format

Thank you for the help. I was wondering about these files. Unfortunately, they're obviously not graphics files, which are what I need most. I'll have to explore the actual EXE files...
