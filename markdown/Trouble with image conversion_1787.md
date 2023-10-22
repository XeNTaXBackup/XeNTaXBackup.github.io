## Post #1
- Username: Meds
- Rank: beginner
- Number of posts: 36
- Joined date: Sun Feb 26, 2006 10:16 am
- Post datetime: 2006-03-16T08:53:01+00:00
- Post Title: Trouble with image conversion

Hi,

I modified Valwen's script from the game request forum to convert these extracted uncompressed files to bitmaps. I don't know what type of files they are but the script allows me to save to a bitmap just fine.

The major problem is that everything is in green, it's shifted up by x pixels, and it's..um..flipped from left to right. I've tried to reproduce IceBerg's 4444 pascal code, but no luck so I found this while researching through bitmap tutorials.

Thanks a lot
## Post #2
- Username: Meds
- Rank: beginner
- Number of posts: 36
- Joined date: Sun Feb 26, 2006 10:16 am
- Post datetime: 2006-03-16T09:00:45+00:00
- Post Title: Trouble with image conversion

Oh yes, here's what it should and shouldn't look like:
## Post #3
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2006-03-17T04:15:03+00:00
- Post Title: Trouble with image conversion

It is only my wild guess but ...
the reason why the picture is green is probable because the red channel is not read. Maybe the fact that the code reads alpha first and then red, green and blue and should read red, green, blue and then alpha . Try to change this sequence in the code. About shift up - no idea.
## Post #4
- Username: valvwen
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Mar 03, 2006 8:57 am
- Post datetime: 2006-03-19T15:28:34+00:00
- Post Title: Trouble with image conversion

Yeah, I had attempted modifying the script a couple weeks ago to use the 4444 method you suggested, but the colors still weren't exactly right. 4444 would make perfect sense to me though cause alot of the monsters are semi transparent in the game.

And the reason the images are flipped the wrong way is cause my script is kinda naive. Bitmaps are stored upside down, but you also need to flip all the scanlines. It'd probably be a pretty simple edit to flip it the right way, but it was just a quick and dirty script so you could see what I was seeing basically. 

I haven't had much of a chance to work on it lately, but I was thinking that all the zlib blocks might actually be idat blocks in a png image. I found some info on a png 16 format, but it's not part of the official png standard, and it's kinda complicated, so I'm no sure if it's helpful at all. here's the link

[http://r0k.us/graphics/png16Tech.html](http://r0k.us/graphics/png16Tech.html)
