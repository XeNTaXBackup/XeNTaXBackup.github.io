## Post #1
- Username: GARID
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Apr 06, 2011 8:29 pm
- Post datetime: 2012-09-25T07:05:21+00:00
- Post Title: TGA and JPG not opens on PS

Hi all! i have problem with these
[http://www.mediafire.com/?9hfwn4ouctpje1h](http://www.mediafire.com/?9hfwn4ouctpje1h)

It's all graphic formats but didn't want to open! or compressed ?
Can anyone help?
## Post #2
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2012-09-25T09:55:35+00:00
- Post Title: TGA and JPG not opens on PS

Hi!
The file Back_10_reg_4_textAtlantida.tga contains a jpg (0xB-0x3552) and an indexed bitmap (0x3553-0xB552), the color palette however is not included.

Back_10_reg_4_TextError.tga also contains a jpg and a bitmap (0xB - 0x041B2, 0x41B3 - 0x241B2).

Don't know what MARS_demo_end_window.jpg is, but it's not a jpg.


 TGA and JPG.zip
(25.94 KiB) Downloaded 26 times
## Post #3
- Username: GARID
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Apr 06, 2011 8:29 pm
- Post datetime: 2012-09-25T10:18:39+00:00
- Post Title: TGA and JPG not opens on PS

Hello awesome work! but
does there exist an easier way to edit these? i'm not pro and have no idea what's this  (0xB-0x3552)
## Post #4
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2012-09-25T12:35:43+00:00
- Post Title: TGA and JPG not opens on PS

all your samples share the same basic format. the '.jpg' extension has some run-length encoding and the '.tga' files look like jpg masks

```
char sig[3] // FBN

when flags == CDAh // raw image data
  uint enoffset
  byte jpgMask[ enoffset - FTell() ];

when flags == AEEh // rle 
  byte flags[3] // ??, length, compressed? (0 or -1)


```
## Post #5
- Username: GARID
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Apr 06, 2011 8:29 pm
- Post datetime: 2012-09-25T13:48:20+00:00
- Post Title: TGA and JPG not opens on PS

> Reply from WRS
>
> all your samples share the same basic format. the '.jpg' extension has some run-length encoding and the '.tga' files look like jpg masks
Code: Select alluint flags
char sig[3] // FBN

when flags == CDAh // raw image data
  uint enoffset
  byte jpgMask[ enoffset - FTell() ];

when flags == AEEh // rle 
  byte flags[3] // ??, length, compressed? (0 or -1)

It says
[untitledd.JPG](https://xentaxbackup.github.io/file/5833_untitledd.JPG)
## Post #6
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2012-09-25T14:52:26+00:00
- Post Title: TGA and JPG not opens on PS

that wasn't a bms script - it was first observations.

here is the script (there was no 'rle' - it was an odd byte manipulation)

```
# WRS (xentax.com)

get flags long
idstring "FBN"
get name basename
string name += "_fixed.jpg"

if flags == 0xCDA
  get size long
  math size -= 11
  log name 11 size
  # other data ignored
elif flags == 0xAEE
  get size asize
  math size -= 7
  filexor 0xFF
  log name 7 size
else
  print "ERROR: Unknown texture method"
  cleanexit
endif

```

edit now using filexor   

here is the other file: 


MARS_demo_end_window_fixed.jpg (226.78 KiB) Viewed 64 times
## Post #7
- Username: GARID
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Apr 06, 2011 8:29 pm
- Post datetime: 2012-09-26T12:46:56+00:00
- Post Title: TGA and JPG not opens on PS

> Reply from WRS
>
> that wasn't a bms script - it was first observations.

here is the script (there was no 'rle' - it was an odd byte manipulation)
Code: Select all# Eternal Journey: New Atlantis FBN images
# WRS (xentax.com)

get flags long
idstring "FBN"
get name basename
string name += "_fixed.jpg"

if flags == 0xCDA
  get size long
  math size -= 11
  log name 11 size
  # other data ignored
elif flags == 0xAEE
  get size asize
  math size -= 7
  filexor 0xFF
  log name 7 size
else
  print "ERROR: Unknown texture method"
  cleanexit
endif

edit now using filexor
Hello. thank you for your code but i have one more problem with image transparenting in game. Here is test and how can I solve this shit? 



sdasd.jpg (47.08 KiB) Viewed 50 times
## Post #8
- Username: GARID
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Apr 06, 2011 8:29 pm
- Post datetime: 2012-09-26T13:00:48+00:00
- Post Title: TGA and JPG not opens on PS

Woohoo!!! i have solved this just edit the texture on PS then save file as .PNG format... then rename the image.png to image.tga and presto   

Thank you for all your help and support!



we.jpg (60.06 KiB) Viewed 50 times
