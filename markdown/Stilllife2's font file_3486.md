## Post #1
- Username: shaneno
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Oct 17, 2008 12:15 pm
- Post datetime: 2009-05-17T02:07:01+00:00
- Post Title: Stilllife2's font file

The contents of this post was deleted because of possible forum rules violation.
[EXTDATASFONT.rar](https://xentaxbackup.github.io/file/2043_EXTDATASFONT.rar)
## Post #2
- Username: Reggy
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jun 22, 2009 10:15 am
- Post datetime: 2009-06-22T17:23:22+00:00
- Post Title: Stilllife2's font file

You can be sure that it's compressed. xc ---> engine's name(look dlls in game's dir). and pk means packed, i think. So the combination is xcpk for those font files. While i was looking the ExE, i saw a good hint about the fonts. xcFont.dds ==> filename that i saw in memory strings. So that means our font file has a dds and charlist i think. But need to find out what algo is using to compress the font file.

More interesting: When you delete or rename, sl2fnt.dat file, game is using default fonts from windows (i think...)
Maybe you can figure this out.

Edit; Yeah, sure! It's using Windows/Fonts/arial.tff for default font.
## Post #3
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2009-06-23T23:54:21+00:00
- Post Title: Stilllife2's font file

Can you find any way to save the xcfont.dds or uncompress the font file?

And if i delete the sl2fnt.dat file,the fonts on my chinese winxp is very strange.
It seems just show a part of the fonts.
Can you post a screenshot of the default font on your system?(I think it's english version winxp.)

The last question,how do you know the game using Windows/Fonts/arial.tff ?
I want to translate the game ,how could i do?
## Post #4
- Username: Reggy
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jun 22, 2009 10:15 am
- Post datetime: 2009-06-24T16:21:35+00:00
- Post Title: Stilllife2's font file

Q:Can you find any way to save the xcfont.dds or uncompress the font file?

A:I really don't have enough time to make that happen.I need to analyze the extraction codes in a debugger.Animations,Models are packed with xc engine.Sounds,music,images are not packed, simplely xor'ed bytes.

Q:Can you post a screenshot of the default font on your system?

A:Here it is, it's using arial.tff.


Q:How do you know the game using Windows/Fonts/arial.tff ?

A:First of all, i look at the codes with a debugger. Then, i simplely deleted the arial.tff font from Windows/Fonts. After i deleted the font, it selected another default font from Windows/Fonts.

I hope, i could be able to help you with your questions.
## Post #5
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2009-06-25T15:31:56+00:00
- Post Title: Stilllife2's font file

Very thanks for your help!
## Post #6
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2009-06-26T03:33:29+00:00
- Post Title: Stilllife2's font file

My screenshot is here.
Does anyone know why the font is so strange on my chinese xp?
[20_5394_f51a523e3f8e799.jpg](https://xentaxbackup.github.io/file/2159_20_5394_f51a523e3f8e799.jpg)
