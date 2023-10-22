## Post #1
- Username: iisdev
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Aug 03, 2012 12:20 am
- Post datetime: 2012-08-02T18:25:41+00:00
- Post Title: [Request] help with Princess Crown (various file formats)

Hi everyone,

I'm working on a project with the Sega Saturn game Princess Crown. (predecessor to 'Odin Sphere' and 'Muramasa: The Demon Blade' and possibly the spiritual prequel to Vanillaware's upcoming 'Dragon Crown') This game has never been released outside of Japan even though there has been numerous requests for localization. The only re-release of the game has been on the Japanese PSP where it appeared to be running under emulation (it's believed that the original source has been lost). There have been some partial translations by fans but nothing in along the lines of a full translation patch that can be applied to your legally owned copy of the game.

I need some help mapping everything out and identifying these file formats (and what's in them).

CHB - believed to contain (background?) tile data as well as some other stuff
CHR - contains image data.. not sure if 'chr' is abreviation of character (sprite) or character (text)
CLB - no idea.
EVN - possibly short for 'event', some sort of script?
MCB - no idea. the 'B' might stand for 'bank'
MPB - no idea. the 'B' might stand for 'bank'
PAK - archive of some sort? might contain sprite data
PCM - definitely in-game music for non-redbook areas
PRG - no idea. (animation related?)
SND - probably sound effects, not sure of the format

Here are some screenshots of just some of the different types of text in the game:


Title screen


Text in the attract demo


In-game dialog


Text in the save/load menu

The text in the second screenshot is located near very end of the main program (0.bin). Each letter maps to a corresponding letter sprite. Other text in the game works in a similar manner and this may also be true of the in-game dialogue but were' not 100% sure. It could be located as part of the event system or possibly bundled with the character or stage data. That's the current theory anyway - we won't know for sure until we can unpackage some of these files and decode the graphic data.

So, yeah - it's a challenge. If anyone has some free time to take a look at a file in their area of expertise and offer some advice it would be greatly appreciated.

Regards,

Jason
## Post #2
- Username: abrillee
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jul 26, 2012 10:45 pm
- Post datetime: 2012-08-04T12:04:35+00:00
- Post Title: [Request] help with Princess Crown (various file formats)

Hi.
I was working on it some years earlier and I have something which may help you.

*.evn files are scripts as you thought.
An evn file can be divided into 2 parts; one from 0x0 to 0xFFF, and the other from 0x1000 to end of file.
Second part is the one which contains text scripts and some control codes.
I have no idea what first part has inside it.

The game uses big-endian system which means the highest byte of a word comes first.
x86 uses little-endian.

Its character code system is very unique: 10 bits a letter.
Basically 5 bytes represent 4 letters. Even if there're 3 letters left they take 5 bytes. Empty spaces are padded with 0.
Each of first 4 bytes is lower part of 10 bits and 5th byte has 4 of 2-bits which goes for higher part of 10 bits.
Assume that the most significant bit of a byte is bit7 and the least one is bit0.
bit7 + bit6 + 1st byte would be the first letter out of 4.
bit5 + bit4 + 2nd byte, the second.
And so on.

Good luck to you.


I'm curious if you can understand all my words, because I am not a native English speaker.
If you don't know what I am saying please feel free to ask it.
## Post #3
- Username: iisdev
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Aug 03, 2012 12:20 am
- Post datetime: 2012-08-05T14:13:37+00:00
- Post Title: [Request] help with Princess Crown (various file formats)

> Reply from abrillee
>
> Hi.
I was working on it some years earlier and I have something which may help you..

..I'm curious if you can understand all my words, because I am not a native English speaker.
If you don't know what I am saying please feel free to ask it.

Thanks for the info abrilee - and yes I could understand you perfectly.
