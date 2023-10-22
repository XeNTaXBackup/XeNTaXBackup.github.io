## Post #1
- Username: carnage
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Jun 26, 2012 10:21 pm
- Post datetime: 2016-04-08T16:25:07+00:00
- Post Title: Help files SP game Snatcher Sega CD

Friends all right.
Well I'm trying to translate this game into my language, the texts are in easy location, however I would like to know if you have any BMS script that can extract the SP file texts.

From what I saw the files are the same, I leave an example of a text file starting at address 0X37B0, I could not entener how the pointers that file.
can anybody help me?

[https://github.com/ox-carnage/Snatcher- ... N?raw=true](https://github.com/ox-carnage/Snatcher-Sega-CD/blob/master/Scripts/SP06.BIN?raw=true)
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2016-04-08T17:51:22+00:00
- Post Title: Help files SP game Snatcher Sega CD

It could be that the game expects the strings to start at 3800 and each is terminated by a 0XFF or similar 0XFX hexedecimal byte. 
All you need is to make sure you end each new string the same way as you localize the text.
## Post #3
- Username: carnage
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Jun 26, 2012 10:21 pm
- Post datetime: 2016-04-09T03:26:19+00:00
- Post Title: Help files SP game Snatcher Sega CD

> Reply from Mr.Mouse
>
> It could be that the game expects the strings to start at 3800 and each is terminated by a 0XFF or similar 0XFX hexedecimal byte. 
All you need is to make sure you end each new string the same way as you localize the text.

Mr.Mouse, I also thought it might be something related to table pointers, but it is not.
The 0xFF are empty or null spaces.

What I realized is that before each block, has many empty spaces 0x00 and then a sequence can of codes, and soon after the 0xFF.
In 0x20F2 address has two bytes 82 33 think it can indicate the text block size can not say.

I have the same file translated into Spanish, can serve anything if I post here?
