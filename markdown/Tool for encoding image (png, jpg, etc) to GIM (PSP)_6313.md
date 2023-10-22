## Post #1
- Username: iruzer
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Aug 10, 2009 7:28 pm
- Post datetime: 2011-03-28T07:11:38+00:00
- Post Title: Tool for encoding image (png, jpg, etc) to GIM (PSP)?

First, I got program which can decode GIM to format image which can edit on PC (like png, bla bla bla)
After I edit that image with photoshop, i want encoding again to GIM (PSP) again but is there tool encoding it to GIM again?
I am already use Gimconv to encode it again to GIM but it failed loading on PSP.

this is sample GIM from PSP game.
[http://www.box.net/shared/nsgcxojmjz](http://www.box.net/shared/nsgcxojmjz)

anyone can make encoding tool to GIM?
(PNG => GIM)
## Post #2
- Username: akadewboy
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri May 16, 2008 4:08 am
- Post datetime: 2011-04-01T20:11:07+00:00
- Post Title: Tool for encoding image (png, jpg, etc) to GIM (PSP)?

This is what I do when I work with PSP GIM files:

1. Convert it to PNG using GimConv

```
gimconv "s_ui_mp_01.gim" -o "s_ui_mp_01.png"
```


2. Convert the new 8bit+Alpha PNG to 32bit PNG using [pngout](http://www.advsys.net/ken/utils.htm). 

```
pngout "s_ui_mp_01.png" "s_ui_mp_01(32bit).png" /c6 /force
```


3. Edit s_ui_mp_01(32bit).png with whatever graphic program you want (I use [Gimp](http://www.gimp.org/)).

4. Convert s_ui_mp_01(32bit).png to 8bit+Alpha PNG using [pngnq](http://sourceforge.net/projects/pngnq/files/pngnq/0.5/)

```
pngnq -s 1 -n 256 "s_ui_mp_01(32bit).png"
```


5. Use GimConv to convert s_ui_mp_01(32bit)-nq8.png into a GIM

```
gimconv "s_ui_mp_01(32bit)-nq8.png" --format_style psp --format_endian little --pixel_order faster --image_format index8
```
## Post #3
- Username: iruzer
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Aug 10, 2009 7:28 pm
- Post datetime: 2011-04-02T04:30:10+00:00
- Post Title: Tool for encoding image (png, jpg, etc) to GIM (PSP)?

thank you.
It is working now.
I can continue my project now.
