## Post #1
- Username: Sajextryus
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Sep 04, 2012 8:07 am
- Post datetime: 2012-09-04T04:28:57+00:00
- Post Title: FEZ 'other.pak' File Decompression Help

Hello, and thank you for taking the time to read this.
Lately, I've been interested in viewing some of the resource files for the game 'FEZ', as there's still many unsolved mysteries and secrets that still lie within the game, and pretty well hidden. I thought I might check these files to see if I can find something, as well as get a better look at the artwork. Checking through the main game file in a HEX editor, I managed to find a few interesting, somewhat official names for things inside the game, like room names and a few other interesting pieces of information about the mysterious world in the game through the resource file names. I extracted all the files using wxpirs.exe, and the resource files like the textures (which are pretty much mostly pixel art) seem to all be inside a file titled 'other.pak', which is in a folder titled Content, along with with 'essentials.pak' and the folders Music, Sound, and Videos. I have been unable to convert the music XWB file to a playable WAV format for some reason (but it would also be great to have help with). Unfortunately, I've tried many different tools to extract or even decrypt other.pak, but have had no luck finding anything that can extract these files. Most programs just give me an "unrecognized format" message. 
I've tried many different things, so I've finally decided to stop trying myself since I'm not that experienced in this kind of stuff and ask those who might actually know better to help.
So, do any of you think you can help me figure out how to decompress this .pak file?


EDIT 9-11-12: New thread: viewtopic.php?f=21&t=9624
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-09-04T05:50:59+00:00
- Post Title: FEZ 'other.pak' File Decompression Help

[viewtopic.php?f=16&t=8312](http://forum.xentax.com/viewtopic.php?f=16&t=8312)

Don't know if that bms script works for everything.
## Post #3
- Username: Sajextryus
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Sep 04, 2012 8:07 am
- Post datetime: 2012-09-04T06:04:45+00:00
- Post Title: FEZ 'other.pak' File Decompression Help

> Reply from finale00
>
> viewtopic.php?f=16&t=8312

Don't know if that bms script works for everything.
Doesn't seem to work out for me.
Also, if anyone is confused, it's this FEZ I'm looking into: [http://www.youtube.com/watch?v=q55RJ41hv4c](http://www.youtube.com/watch?v=q55RJ41hv4c)


EDIT: I'm not sure, but I just found out there's a forum for resource files. Would it be necessary to move this thread?
## Post #4
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2012-09-04T08:42:04+00:00
- Post Title: FEZ 'other.pak' File Decompression Help

try and PM the file
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-09-04T16:26:19+00:00
- Post Title: FEZ 'other.pak' File Decompression Help

Sorry I automatically expanded "FEZ" to "fantasy earth zero" lol
## Post #6
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2012-09-04T16:30:16+00:00
- Post Title: FEZ 'other.pak' File Decompression Help

It's very easy to unpack this file, I'll try and code something when I get home
## Post #7
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2012-09-05T13:24:02+00:00
- Post Title: FEZ 'other.pak' File Decompression Help

here:

[http://www.mediafire.com/download.php?0vuf47r2aq1w6fs](http://www.mediafire.com/download.php?0vuf47r2aq1w6fs)

xnb files are C# compiled resources, there should be tools around the net to unapck them
## Post #8
- Username: Sajextryus
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Sep 04, 2012 8:07 am
- Post datetime: 2012-09-05T19:49:43+00:00
- Post Title: FEZ 'other.pak' File Decompression Help

Thanks! Unfortunately, opening the files in GXview brought up an error message asking for FEZ reader file, which I was worried about.
I've been reading the game's programmer's blog lately out of interest on [http://theinstructionlimit.com](http://theinstructionlimit.com) and a recent entry talks about how the game shipped with 3D textures for all the sprites. The game uses some sort of custom voxel format, which they refer to as Trixels, and he made a program called "Fezzer" to work with those files. Unfortunately, I'm not home right now so I can't reread the exact text with the name of the file needed, but I'll get on later. I'm not sure if it's possible to easily write something to view them, but if it's not too difficult, I would love to see it happen.
## Post #9
- Username: Sajextryus
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Sep 04, 2012 8:07 am
- Post datetime: 2012-09-06T00:50:55+00:00
- Post Title: FEZ 'other.pak' File Decompression Help

Okay, I haven't been able to view anything yet in GXView. Some of the files (which mostly seem to be normal image files) will just yield me a message "Error: End position does not match XNB header: unexpected amount of data was read.", though character sprites give me an error "Error: Can't find type reader 'FezEngine.Readers.AnimatedTextureReader" which I believe is because they are made with the trixel Engine despite them being flat. There is a file in the game files titled FezEngine.dll, so there could be something helpful there if anything at all, but I'm not sure of anything myself.
There also seems to be some in game text in XNB format, but I have no idea how I could view them.
## Post #10
- Username: Sajextryus
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Sep 04, 2012 8:07 am
- Post datetime: 2012-09-09T05:05:21+00:00
- Post Title: FEZ 'other.pak' File Decompression Help

I'm not sure if I should make another topic for figuring out how to read and render some of these files or if it's not worth making a topic for.
## Post #11
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-09-11T22:39:33+00:00
- Post Title: FEZ 'other.pak' File Decompression Help

Just make a new topic.
## Post #12
- Username: Bringbackfez
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Sep 04, 2014 12:22 am
- Post datetime: 2014-09-04T18:33:33+00:00
- Post Title: FEZ 'other.pak' File Decompression Help

This is Sephy from the Bring Back Fantasy Earth Zero movement. We are currently looking for all & any files pertaining to Fantasy Earth Zero from NA, Gamania or any other servers that have closed & no longer restricted by copyrights listed under functioning rights. Please messgae me or contact us at [https://www.facebook.com/BringBackFantasyEarthZero](https://www.facebook.com/BringBackFantasyEarthZero) .
