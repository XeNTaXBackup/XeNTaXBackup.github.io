## Post #1
- Username: themortician
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Dec 18, 2007 7:35 am
- Post datetime: 2007-12-18T10:49:58+00:00
- Post Title: Resident Evil 1 - .PAK Files

Hi this is my first post here.
I'm searching for methods to mod the .pak files of Resident Evil 1 for PC.
They contain a compressed bitstream of a .tim Image according to that page in the REWiki [.PAK File Documentation](http://rewiki.regengedanken.de/wiki/.PAK_%28Resident_Evil%29)

As you can see there is also an example decompression routine on the page is linked above.

I'm not a c or c++ coder and i need help with that code. Wouldn't it be possible to reverse this routine and use it for creating .pak files from a .tim file?
Could, or has someone already compiled such a tool from that code?
I need a programm that can "unpack" and "pack" this pak. files.
A simple command line tool would be enough.

I've uploaded some of the .pak files for testing, analyzing etc as an attachment.
[Stage1.rar](https://xentaxbackup.github.io/file/1409_Stage1.rar)
## Post #2
- Username: PmData
- Rank: beginner
- Number of posts: 33
- Joined date: Tue Oct 31, 2006 1:56 am
- Post datetime: 2007-12-18T19:03:17+00:00
- Post Title: Resident Evil 1 - .PAK Files

> Reply from themortician
>
> 
They contain a compressed bitstream of a .tim Image according to that page in the REWiki .PAK File Documentation
More precisely, it is either a compressed TIM image, or a RAW 16 bits image.

> I'm not a c or c++ coder and i need help with that code. Wouldn't it be possible to reverse this routine and use it for creating .pak files from a .tim file?
For that, you need a better understanding of what the compression try to achieve. You can not simply reverse the decompression routine.

> I need a programm that can "unpack" and "pack" this pak. files.
>
> A simple command line tool would be enough.
It is easy to add a routine to save the decompressed file, even adding some command line switch to select the input and output filenames. However the 'pack' tool is an entirely different story.
## Post #3
- Username: themortician
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Dec 18, 2007 7:35 am
- Post datetime: 2007-12-18T22:36:35+00:00
- Post Title: Resident Evil 1 - .PAK Files

Hmm i don't know anything beside the infos given on the REWiki page.
So i don't know if its compressed tim or raw for sure.

It would be nice if someone could code such a decompression tool that would save the decompressed image to a file. But i'm more interested in the packing of the images to a .pak file. That would make it possible to change the entire backgrounds of the game.
## Post #4
- Username: PmData
- Rank: beginner
- Number of posts: 33
- Joined date: Tue Oct 31, 2006 1:56 am
- Post datetime: 2007-12-19T17:49:22+00:00
- Post Title: Resident Evil 1 - .PAK Files

> Reply from themortician
>
> Hmm i don't know anything beside the infos given on the REWiki page.
So i don't know if its compressed tim or raw for sure.

It would be nice if someone could code such a decompression tool that would save the decompressed image to a file. But i'm more interested in the packing of the images to a .pak file. That would make it possible to change the entire backgrounds of the game.
Oops, sorry, I was confusing with ADT files. So it's simpler. They are only TIM images, packed with LZW method. Definitely, packing/unpacking them could be doable.
## Post #5
- Username: themortician
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Dec 18, 2007 7:35 am
- Post datetime: 2007-12-19T18:35:41+00:00
- Post Title: Resident Evil 1 - .PAK Files

Man, i would also like to know how to pack ".adt" files. This would be freakin great. I know someone who can manage that, but he isn't willing to tell anything about it... I just know that he really knows it and i've seen his work in action.

So is here anyone who could code such a simple tool?
For packing and unpacking .pak files of RE1 for pc? That would be awesome..and just as i said before i also think that its "easy" to do.
Because the .pak files are just compressed .tim files.

I and a lot of other people would be grateful for such a thing for the rest of our live.

I really hope someone can help me with this. Btw. who was responsible for the article about .PAK Files on the ReWiki page? i'm sure the same person could solve this problem
## Post #6
- Username: PmData
- Rank: beginner
- Number of posts: 33
- Joined date: Tue Oct 31, 2006 1:56 am
- Post datetime: 2007-12-19T19:02:06+00:00
- Post Title: Resident Evil 1 - .PAK Files

> Reply from themortician
>
> Man, i would also like to know how to pack ".adt" files. This would be freakin great. I know someone who can manage that, but he isn't willing to tell anything about it... I just know that he really knows it and i've seen his work in action.
ADT files use a more complex compression scheme than LZW.

> So is here anyone who could code such a simple tool?
>
> For packing and unpacking .pak files of RE1 for pc? That would be awesome..and just as i said before i also think that its "easy" to do.
>
> Because the .pak files are just compressed .tim files.
I think anyone who knows how to use a LZW packer could write it.

> I really hope someone can help me with this. Btw. who was responsible for the article about .PAK Files on the ReWiki page? i'm sure the same person could solve this problem
Well, it's me, that wrote most Resident Evil related stuff in these wikis, as I like these games so much.
## Post #7
- Username: themortician
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Dec 18, 2007 7:35 am
- Post datetime: 2007-12-19T21:01:18+00:00
- Post Title: Resident Evil 1 - .PAK Files

About .adt files. Yeah i know. I gave hope up on these... I think the only way to get more info about them is kidnapping a capcom employee or the "one" guy and force them to tell   Well that was a joke of course..

I'm interested in the structure of the .adt files, but i would be fully satisfied (for now) with help on the .pak files of RE1.

Hmm anyone eh?

So can you do it? Or could you explain how to pack it?
I would be very grateful for help with this. just as i said before 

I'm currently working on a mod and on a documentation about modifying RE1 for pc.  This programm would be awesome.

Wow cool pmdata, i like your docs. Never thought there would be still some people that try to hack or modify the RE games.
Btw: I could provide some useful information about editing the .DOR files of RE1 for pc for your ReWiki
