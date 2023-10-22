## Post #1
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2007-06-08T20:27:32+00:00
- Post Title: Strange fixed Palette.

I have encountered rather unusual situation in the old game palette, where the values of Red Green and Blue do not exceed certain range. They all are from 0 to 60 or just about. 

Obvoiusly as a result of such a situation when I apply palette to greyscale picture it is dark and I need to Autocontrast it in order to bring it to life. At that point the range RGB is being extended from 0 to 255 so I can see. 

What could be the reason of using such a limited palette in the game graphic engine?
## Post #2
- Username: john_doe
- Rank: VIP member
- Number of posts: 80
- Joined date: Sat Oct 21, 2006 9:25 pm
- Post datetime: 2007-06-09T10:25:33+00:00
- Post Title: Strange fixed Palette.

That seems to be a DAC VGA palette. The range there is from 0..63, not from  0..255. You need to shift every byte left by 2 to adjust the range, the palette should be correct then.
## Post #3
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2007-06-10T00:00:00+00:00
- Post Title: Strange fixed Palette.

Thank you John Doe for the pointer. It seems that what I have described in my opening post is 6 bit graphics. I undertsand how to make necessary adjustments to view them in 8 bit format , unsure I am if thats can be done both ways 6 bit ->8bit-> and then back to 6. 

Are there any graphics utylities or graphic programs supporting such a conversion? Or we talking archaic format lost in computer graphic history.
## Post #4
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2007-06-11T19:16:25+00:00
- Post Title: Strange fixed Palette.

Terms in computer graphics are frequently what the call a misnomers. So 8 bit direct color system is often confused with an indexed color depth of 8bpp, as well as common misconception is that 32-bit color produces 4,294,967,296 distinct colors whereas in reality, 32-bit color actually refers to 24-bit color (Truecolor) with an additional 8 bits, either as empty padding space or to represent an alpha channel.

So it is also in our example here that we are talking NOT 6bit color but actually 18bit as there are 6 bits per EACH color RGB giving total 18. Still I am yet to fing the editor which will support that depth. Perhaps I have sudden brain freeze     Anyone to help?

EDIT: EUREKA !!! I think I found it :
[Free Depthdither](http://depthdither.graphest.com/index.htm)
