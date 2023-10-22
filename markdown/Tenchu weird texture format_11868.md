## Post #1
- Username: Lyserg1260
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Aug 18, 2014 7:28 pm
- Post datetime: 2014-08-30T16:59:14+00:00
- Post Title: Tenchu weird texture format

Hi, i am trying to edit PSP game "Tenchu Time of The Assassins", this game is very weird. Models and their textures are not in the same files. Now i know where are textures, i was trying to replace them - it works. But i would like to preview them to know which texture i am replacing, it would be much easier. I've uploaded a sample, it's one of these textures. I hope you will find a way to open them...

This texture should look like this:
[http://i.imgur.com/mGB9Day.png](http://i.imgur.com/mGB9Day.png)
[texture_sample.rar](https://xentaxbackup.github.io/file/7761_texture_sample.rar)
## Post #2
- Username: root670
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Dec 18, 2010 6:11 am
- Post datetime: 2014-09-03T17:42:59+00:00
- Post Title: Tenchu weird texture format

I think it goes like this:

0x00 data offset (long)
0x04 palette offset (long)
0x08 and 0x10 width (short)
0x0A and 0x10 height (short)

Length of the data is width * height. The data is swizzled and the palette is probably RBGA. Here's how it looks in Console Texture Explorer:
