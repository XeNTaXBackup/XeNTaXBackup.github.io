## Post #1
- Username: adol365
- Rank: advanced
- Number of posts: 70
- Joined date: Fri Nov 21, 2014 7:21 pm
- Post datetime: 2016-09-06T08:23:08+00:00
- Post Title: [Font] Tales of symphonia

I'm not sure how does this game calculates font width and height.
On top of that there's no information of width and height of total font image;768x1728.
And it is weird that font index file contains Shift-JIS font data but there's no such font image on DDS file.

0036339.TLFNTB_D - Font index file.


0036340.TOTEXB_D - ???

0083362.TOTEXP_P - Font DDS file.

[font.zip](https://xentaxbackup.github.io/file/11666_font.zip)
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2016-09-06T22:18:57+00:00
- Post Title: [Font] Tales of symphonia

its a tilesheet. glyphs are square!

there are 16 glyphs per row.

768/16 = 48
1728/478 = 36

its a grid of 16x36 tiles @ 48x48 per glyph... no need for spacing data  

edit

or is it  i will check the data
