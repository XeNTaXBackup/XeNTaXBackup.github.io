## Post #1
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2016-11-21T17:55:32+00:00
- Post Title: [REQ][PC] Tony Hawk's Pro Skater 2 - FNT font files

So I tried to figure out file format of this font. In this case S2FONT1.FNT. But it wasn't so easy as I thought.
Is there anybody here who can help me with this? Font is uncompressed.

You can download font here: [http://ikskoks.pl/XENTAX/THPS2_FONT.rar](http://ikskoks.pl/XENTAX/THPS2_FONT.rar)

File format:

```
4 bytes - number of symbols in font

number of symbols * 
{
     4 bytes - scale?
     4 bytes - ?
     4 bytes - bitmap height
     4 bytes - bitmap width
}


//palette data
32 bytes - palette data (2 bytes per colour)

//bitmaps
number of symbols * bitmap data

```




screenshot000146.jpg (153.81 KiB) Viewed 129 times
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2016-12-18T20:12:02+00:00
- Post Title: [REQ][PC] Tony Hawk's Pro Skater 2 - FNT font files

Hey. I have updated file format in the first post. Now I know more about these fonts.
First I thought that every FNT file has only one bitmap, but I was wrong. There is separate bitmap for each symbol.
And successfully I have found palette data, but I don't know what palette type is it.
So I'm close to figure this out, but not close enough. Any help? :p
## Post #3
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2017-01-28T23:26:19+00:00
- Post Title: [REQ][PC] Tony Hawk's Pro Skater 2 - FNT font files

I have updated file format again. 
I think that these bitmaps are in 4 bytes per pixel format and palette is in 2 bytes per colour format (big endian) and with BGR colour order.

I have also checked for text to translate and unfortunatelly everything is in main exe file. ;/ Too bad.
[screenshot000654.jpg](https://xentaxbackup.github.io/file/12330_screenshot000654.jpg)
