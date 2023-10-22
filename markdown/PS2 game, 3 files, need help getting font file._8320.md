## Post #1
- Username: CirqueForge
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Feb 18, 2012 7:36 am
- Post datetime: 2012-02-18T00:39:34+00:00
- Post Title: PS2 game, 3 files, need help getting font file.

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: CirqueForge
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Feb 18, 2012 7:36 am
- Post datetime: 2012-02-19T02:12:20+00:00
- Post Title: PS2 game, 3 files, need help getting font file.

The contents of this post was deleted because of possible forum rules violation.
## Post #3
- Username: Polefish
- Rank: veteran
- Number of posts: 94
- Joined date: Sat Jun 20, 2009 8:47 pm
- Post datetime: 2012-02-20T07:57:48+00:00
- Post Title: PS2 game, 3 files, need help getting font file.

It really looks like one of the TIM2 files is the font (the one that is not just plain white^^). Since it looks scrambled I can imagine there went something wrong when you converted the TIM2.
## Post #4
- Username: CirqueForge
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Feb 18, 2012 7:36 am
- Post datetime: 2012-02-20T12:38:30+00:00
- Post Title: PS2 game, 3 files, need help getting font file.

Here's the thing though. Jaeder Nuab, QuickBMS and the tool I'm using did the same thing in outputting identical .tim2 files each time I extracted the GRAPH0.ARC. I don't think it's quite a human error with conversion. I also used several .tim2 tools and they converted to the same bitmap as you can see. I can't conceivably see what's wrong because the file doesn't seem like it's encrypted but at the same time, it looks like that it may be garbled on purpose? I dunno if anyone can check that for me but yeah, it's the largest file in the whole archive along with the whitespace and I dunno how it would not be the font.

Also, if I can't get the font file, is hacking the .18 file, which is the .ELF via ASM hacking, the only way other than manipulating a font to get it to work?
## Post #5
- Username: Polefish
- Rank: veteran
- Number of posts: 94
- Joined date: Sat Jun 20, 2009 8:47 pm
- Post datetime: 2012-02-20T13:45:37+00:00
- Post Title: PS2 game, 3 files, need help getting font file.

I guess in this case this is not a standard TIM2 file. Maybe its swizzled or some other fancy optimization? I really don't know.

The game gets all the characters it outputs from the font file so if you don't alter the font file you are not able to display other characters than the ones in the font. About the asm hacking, if you are able to code a routine that lets you load your own font your good to go
## Post #6
- Username: CirqueForge
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Feb 18, 2012 7:36 am
- Post datetime: 2012-02-20T16:06:21+00:00
- Post Title: PS2 game, 3 files, need help getting font file.

Is there any way I can modify the .tim2 file by adjusting it's line width, offset, or etc to get something useful out of the .tim2? I still don't know what the .bin file does and why they have a completely white space for image 452.

Also, I really don't want to go and learn MIPS assembly to hack into the binary because I have no idea how to do so and it will take me a whole lot more time to do so, which will probably delay the progress indefinitely for this project. Easiest solution is to just modify the font and resize it so English characters are smaller, but I really have no clue if I can't figure what's so special about this .tim2 file...
## Post #7
- Username: Polefish
- Rank: veteran
- Number of posts: 94
- Joined date: Sat Jun 20, 2009 8:47 pm
- Post datetime: 2012-02-20T19:14:40+00:00
- Post Title: PS2 game, 3 files, need help getting font file.

I don't know for sure but I think the image was made this way by the developers to boost the loading times. The hardware can access the file faster if its arranged this way. That is just a guess there is still the possibility the image has just another format because of something else.

Search the forum for swizzled ps2 textures for more info.
## Post #8
- Username: CirqueForge
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Feb 18, 2012 7:36 am
- Post datetime: 2012-02-20T21:43:45+00:00
- Post Title: PS2 game, 3 files, need help getting font file.

Ok, I kind of get the idea of it. Question is, how do I effectively unswizzle my font picture? Is there any ultilities that can do that?

Edit: I've tried ezswizzle and it didn't seem to work...
## Post #9
- Username: Polefish
- Rank: veteran
- Number of posts: 94
- Joined date: Sat Jun 20, 2009 8:47 pm
- Post datetime: 2012-02-21T16:14:07+00:00
- Post Title: PS2 game, 3 files, need help getting font file.

I dont know of any program that is capable of unzwissling TIM2 textures but I found some detailed information about TIM2 in general and even some code to unzwissle a PS2 texture.

[http://gtamodding.ru/wiki/TIM2](http://gtamodding.ru/wiki/TIM2)
[http://code.google.com/p/puyotools/sour ... le.cs?r=93](http://code.google.com/p/puyotools/source/browse/trunk/PTImgLib/VrSharp/Svr/SvrSwizzle.cs?r=93)
## Post #10
- Username: CirqueForge
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Feb 18, 2012 7:36 am
- Post datetime: 2012-02-21T20:40:57+00:00
- Post Title: PS2 game, 3 files, need help getting font file.

Thanks for the documentation, although I don't think I can really do it within a reasonable amount of time.

But seriously, is it possible that it's not swizzled and that it was compressed, encrypted, etc?
## Post #11
- Username: Polefish
- Rank: veteran
- Number of posts: 94
- Joined date: Sat Jun 20, 2009 8:47 pm
- Post datetime: 2012-02-21T22:11:38+00:00
- Post Title: PS2 game, 3 files, need help getting font file.

Sure they could have compressed the imagedata or something else besides swizzling. Everything is possible^^ but it doesnt look compressed.
## Post #12
- Username: Forte
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Aug 07, 2007 4:51 am
- Post datetime: 2012-02-22T23:10:00+00:00
- Post Title: PS2 game, 3 files, need help getting font file.

I'm just grasping at straws here, but have you tried looking at a memdump to see if the image is in there and looks normal?
(If you didn't know already, load up the game in PCSX2, get to a point with text, save via F1, look in the sstates folder, extract the newly created *.p2s with winrar, eeMemory.bin is the memdump)
## Post #13
- Username: Polefish
- Rank: veteran
- Number of posts: 94
- Joined date: Sat Jun 20, 2009 8:47 pm
- Post datetime: 2012-03-19T17:40:03+00:00
- Post Title: PS2 game, 3 files, need help getting font file.

I don't have the time to fiddle around with this but I found a good site where you could ask for help: [http://asmodean.reverse.net/](http://asmodean.reverse.net/)
