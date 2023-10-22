## Post #1
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2013-03-31T14:59:28+00:00
- Post Title: [REQ][PC]Masters of the World Geopolitical Simulator 3 (.gp)

Hi, guys 

Can someone look at .gp archives in this game - Masters of the World: Geo-political Simulator 3?
I will be very grateful if you could try to create some tool or quick bms script to unpack/repack these files.

< link expired >
## Post #2
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2013-04-02T20:35:08+00:00
- Post Title: [REQ][PC]Masters of the World Geopolitical Simulator 3 (.gp)

Hi!
I only managed to convert mainmenu.gp so far - it's the only file that is not compressed 

[](http://imageshack.us/photo/my-images/441/mainmenue.png/)
mainmenu.gp:
@0xA0	width (int16)
@0xA2	height (int16)
width: 0x620 = 1568d
height:0x5C8 = 1480d

size of RGBA pixel data = width*height*4 = 0x8DA400
pixel data starts at 0xD0 I guess.
## Post #3
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2013-04-02T20:44:58+00:00
- Post Title: [REQ][PC]Masters of the World Geopolitical Simulator 3 (.gp)

Thanks for your work 
Is there any chance for possibility to convert other archives?


btw. Why did you upload so big picture in your post? ;D
## Post #4
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2013-04-02T21:10:33+00:00
- Post Title: [REQ][PC]Masters of the World Geopolitical Simulator 3 (.gp)

> Reply from ikskoks
>
> btw. Why did you upload so big picture in your post? ;DI copied the wrong link from ImageShack - I edited my post and now it only shows a thumbnail 

Well, I think that the other files are zlib compressed (they all start with 78 DA, or in ASCII: xÚ). But I'm not sure about this...
## Post #5
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2013-04-02T22:28:51+00:00
- Post Title: [REQ][PC]Masters of the World Geopolitical Simulator 3 (.gp)

If you will have any info about converting and compression, please let me know in this topic
## Post #6
- Username: swuforce
- Rank: veteran
- Number of posts: 121
- Joined date: Fri Nov 06, 2009 3:46 am
- Post datetime: 2013-04-03T09:54:02+00:00
- Post Title: [REQ][PC]Masters of the World Geopolitical Simulator 3 (.gp)

> Reply from herbert3000
>
> Well, I think that the other files are zlib compressed (they all start with 78 DA, or in ASCII: xÚ). But I'm not sure about this...
I think its not compressed, but also headerless png files. I took the header from your menu file, paste it to a cutted "compressed" data, modify the width, height and i get this.
[http://img824.imageshack.us/img824/3402/78424978.jpg](http://img824.imageshack.us/img824/3402/78424978.jpg) I know its a mess, but maybe with correct header its a real image.

btw in gp files, at 0x34 - number of file, at 0x50 starts the offset table

for a block if type 1
4b - type?
4b - size of block
4b - null
4b - unknown
16b - usually there is a name here
24b- null
4b - unk
4b - null
2b - width
2b - height
4b - unknown
4b - unknown
36b - null
4b - size of (image) data - 4
data
## Post #7
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2013-04-03T12:05:39+00:00
- Post Title: [REQ][PC]Masters of the World Geopolitical Simulator 3 (.gp)

you can parse the format like so:

```
# NOTE: Image data is not converted into a readable format

# although zsize is known..
comtype unzip_dynamic

get SIZE1 long
get SIZE2 long # dupe
get HASH long # ??
get ZERO long
getdstring GPNAME1 16
getdstring GPNAME2 16 # dupe
get TYPE long
get FILES long

## ---- info pointers
goto 0x50
for f = 0 < FILES
  get INFOPNTR long
  putarray 0 f INFOPNTR
next f

## ---- file info + data
for f = 0 < FILES
  getarray INFOPNTR 0 f
  goto INFOPNTR

## ---------------------- 112 bytes
  get TYPE long
  get SIZE1 long
  get ZERO long
  get SIZE2 long
  getdstring NAME 40
  get FLAG long
  get UNKNOWN long
  get WIDTH short
  get HEIGHT short
  get UNKNOWN1 long
  get UNKNOWN2 long
  get UNKNOWN3 long
  getdstring DUMMY 32
## ----------------------

  string FNAME p= "%s_%02ix%02i.dat" NAME WIDTH HEIGHT

  if FLAG == 0
    # uncompressed

    savepos CURPOS
    math SZE = SIZE1
    math SZE -= 112 # size of structure

    log FNAME CURPOS SZE

  elif FLAG == 0xFE000000
    # compressed

    get ZSIZE long
    math ZSIZE -= 4
    savepos CURPOS
    clog FNAME CURPOS ZSIZE 0xFFFFFF
  else
    print "Got %FLAG% for %FNAME%"
  endif

next f

# NOTE: Always an extra 80 bytes at end of file

```


the graphical data that remains is unknown

some of the files use 2 bytes for each colour (width*height*2)
you could guess the bbp by :   filesize / (width*height)
## Post #8
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2013-04-04T16:25:12+00:00
- Post Title: [REQ][PC]Masters of the World Geopolitical Simulator 3 (.gp)

Thank you for script 

But what can I do with this unpacked DAT files? Is possible to edit it in this form? Or maybe it is just beginning of the analysis process? 

(maybe stupid questions but i had to ask ;p)
## Post #9
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2013-04-04T21:55:26+00:00
- Post Title: [REQ][PC]Masters of the World Geopolitical Simulator 3 (.gp)

If you open some of that unpacked .dat files in TextureFinder, you will get pics like this one



And unpacking files manually with offzip from fonds2v2.gp you can get pics in different format. 



But there are also JPEGs inside, when you use WRS's BMS script.
## Post #10
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2013-04-05T01:41:05+00:00
- Post Title: [REQ][PC]Masters of the World Geopolitical Simulator 3 (.gp)

> Reply from ikskoks
>
> Thank you for script 

But what can I do with this unpacked DAT files? Is possible to edit it in this form? Or maybe it is just beginning of the analysis process? 

(maybe stupid questions but i had to ask ;p)

the .dat files are just image/pixel data

they are not in any specific format (such as jpg/png/bmp/dds) as they do not have a header, but it is possible to add them yourself or using a texture finder (see above post)
