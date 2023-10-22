## Post #1
- Username: Thorongil
- Rank: Banned
- Number of posts: 17
- Joined date: Mon Mar 01, 2010 2:42 am
- Post datetime: 2011-02-16T19:21:34+00:00
- Post Title: Halo Wars (xbox360)  sounds.pck

Hellow guys

I've found some intel about the halo wars format. I have no clue on what his talking about, do you? And most importently how I export the audio out of the sounds.pck file.

> ...Over the next few weeks I'm going to try to post whitepapers on these structures, including the programs that I wrote to open and read the files. Here are a few of the file formats I've unraveled:
>
> 
>
> ..
>
> ..
>
> Halo Wars: sounds.pck (custom PCK format) 
>
> 
>
> These whitepapers will include the basic structure format, as well as a C# style struct, instructions on reading the file in a hex editor, and the program that I wrote to extract the files (along with source code.) Some of these files contain certain format files that require secondary operations to use them. For example, the Halo Wars sounds are in a proprietary Xbox 360 format called XMA (based on WMA.) To use these files you need to convert them to a WAV file using a separate tool, which I will include if required. 
>
> 
>
> As far as the Halo Wars sounds file goes, it's pretty big (368MB) so I probably won't be able to upload it. Another thing is within the .PCK format, there are more package files that I call BKHD files (since that's the first 4 bytes of the header of those files.) I've fully documented the structure of the .PCK file as well as the BKHD files. Along side the 83 BKHD files are regular XMA audio files...7,168 of them. It takes my program 1 minute 37 seconds to read the whole list.
>
> 
>
> source: http://infectionist.com/forum/viewtopic ... hlight=pck

He was talking about some whitepapers he would put online well that was last year.. Can't find anything yet and I tryed to get some contact(3 days ago now) with him no responds yet..
## Post #2
- Username: Thorongil
- Rank: Banned
- Number of posts: 17
- Joined date: Mon Mar 01, 2010 2:42 am
- Post datetime: 2011-02-16T21:02:44+00:00
- Post Title: Halo Wars (xbox360)  sounds.pck

1. I've found out how to extract xbox360 iso in case someone else wonders how to do it.
Make sure your game is in a "ISO" format. Than open it with this program:
[http://gael360.free.fr/wx360.php](http://gael360.free.fr/wx360.php)


2. This file cutter doesn't work for me (win7 64bit) 
ERROR= 
> Run-time error '339': Component 'VBZip_Control.ocx' or one of its dependencies not correctly registrered: a file is missing or invalid. where I downloaded it= [blog/?attachment_id=56](http://forum.xentax.com/blog/?attachment_id=56)
So I can't upload the sounds.pck (low size)


3. I've found this topic about an pck file from a different game they managed to extract files with a quickbms script. 
The Quickbms tool= [blog/?attachment_id=86](http://forum.xentax.com/blog/?attachment_id=86)
Quickbms script = [viewtopic.php?f=10&t=4508&p=40250](http://forum.xentax.com/viewtopic.php?f=10&t=4508&p=40250)

2. Q. where can I find an filecutter that can work for me?

3. I guess I need to upload the low sized file in order to ask you guys  how to get working extraction..
## Post #3
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2011-02-19T10:50:29+00:00
- Post Title: Halo Wars (xbox360)  sounds.pck

Hmm, i decoded all audio more or less months ago from it, sadly filenames don't seem to be in the archives what i checked way back. the RIFX wavs can be just scanner extracted or quickbms script and towav decoded.
## Post #4
- Username: Thorongil
- Rank: Banned
- Number of posts: 17
- Joined date: Mon Mar 01, 2010 2:42 am
- Post datetime: 2011-02-23T20:05:22+00:00
- Post Title: Halo Wars (xbox360)  sounds.pck

Good news!

As you know we all keep learning about these kind of topics. 

Therefor can anyone figure out too make a tool to extract the *.xma files out of the sounds.pck. 

On the following link provided I guess all the info you need to create this very tool.
[http://infectionist.com/forum/viewtopic.php?t=2547](http://infectionist.com/forum/viewtopic.php?t=2547)

(also following link includes a tool to convert xma to wav)

I suggest we can thank the person who worked figuring all this out.
