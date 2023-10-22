## Post #1
- Username: cienislaw
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Mar 30, 2013 5:22 am
- Post datetime: 2017-01-23T16:29:41+00:00
- Post Title: Evolution Engine 1.6 font bitmap

[In this file](https://www.dropbox.com/s/p1704u3mhp6wnkv/evolution_engine_1.6_english_russian_font_bitmap.rar?dl=0) you can find Evolution Engine 1.6 (The Darkness II) bitmap fonts - English and Russian. Files are split in 2 parts - header and bitmap itself.

```
DWORD - string count
for each string:
DWORD - string lenght
X * BYTE - string
after there are 0xA0 bytes:
DWORD - zero
DWORD - 0x94 - probably a size of this structure, but even without this 4 bytes, its 8 bytes longer
QWORD - 01 00 01 00 00 00 00 02
QWORD - something related to width and height or size in general 
0x54 bytes - unknown
DWORD - checksum? different for each file
0x0C bytes - zeros
DWORD - checksum? different for each file
8 x 00 00 80 3F
DWORD - zeros
```


bitmap looks like block based, you can get 'something' using [Warframe method for textures](http://forum.xentax.com/viewtopic.php?f=18&t=10991), but I can't get it fully right. does anyone has idea how to convert bitmap to readable format?
## Post #2
- Username: AndylgRu
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Jul 29, 2009 9:15 pm
- Post datetime: 2019-10-27T13:03:15+00:00
- Post Title: Evolution Engine 1.6 font bitmap

No news?
## Post #3
- Username: cienislaw
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Mar 30, 2013 5:22 am
- Post datetime: 2019-10-27T15:12:09+00:00
- Post Title: Evolution Engine 1.6 font bitmap

nothing  we released Polish translation without national chars because of that. I was trying to contact various Digital Extreme devs involved in TD2, but it's to ancient stuff for them, so no luck here too.
## Post #4
- Username: vadim
- Rank: advanced
- Number of posts: 41
- Joined date: Fri Apr 09, 2010 11:15 pm
- Post datetime: 2019-11-14T18:55:06+00:00
- Post Title: Evolution Engine 1.6 font bitmap

[Darkness II Bitmap-fonts.ru.rar](https://xentaxbackup.github.io/file/17056_Darkness II Bitmap-fonts.ru.rar)
## Post #5
- Username: cienislaw
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Mar 30, 2013 5:22 am
- Post datetime: 2019-11-14T19:02:28+00:00
- Post Title: Evolution Engine 1.6 font bitmap

thx, but withou magical D2.exe its useless for me;-( if you know how to convert EE1.6 bitmaps to 'normal' format and back, please share your findings. I would gladly update our translation to support zażółć gęślą jaźń chars;-) Спасибо.
## Post #6
- Username: ripper
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Nov 20, 2014 4:52 am
- Post datetime: 2019-11-15T01:04:45+00:00
- Post Title: Evolution Engine 1.6 font bitmap

DXT3   
Well, [here is bms script](https://zenhax.com/download/file.php?id=4770) written by episoder. Just replace lines 3-25 with 

```
w = 1024
h = 128
f = 5
```

ofs - is offset. In our case is always 0.
w -width (you can find it in files from H. prefix)
h - height (you can find it in files from H. prefix too)
f - out format 5 is for DXT5 you could manualy change each file after converting or replace value in line 117 to 861165636. 
And now all you need to do is change width and height for images. I'll share my little converter later(mb in december, when have more time), if nobody share it first =-)
## Post #7
- Username: cienislaw
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Mar 30, 2013 5:22 am
- Post datetime: 2019-11-15T08:20:31+00:00
- Post Title: Evolution Engine 1.6 font bitmap

thx. looks promising. i've closed project almost 3 years ago and will have to dig it up first. with working script and reversed format I can manage rest on my own.
