## Post #1
- Username: mugi
- Rank: beginner
- Number of posts: 32
- Joined date: Thu Mar 24, 2011 3:02 am
- Post datetime: 2012-10-14T10:18:44+00:00
- Post Title: Utawarerumono portable (PSP)

evening peoples, long time lurker here 

i've been examining this thing for a while now and after going through the .dar archive (simple table and embedded zLib wasnt too hard ) i ran into a problem...
now, the whole gamedata is inside this one archive, and when extracted, it's nothing but .at3/vag (audio) 
and a shitload of .tpl files that seem to use some form of compression unknown to me.

i was examining a .tpl that's supposedly a background image with the size of 480x272 (psp reso) but no matter what, i cant get it to display properly, and opening it up as a raw, gives
repeating blocks of messed up pixels that would indicate compression..

looks like this:


anyone care to take a look at one ?

for what i know so far, the tpl files use a 48 byte header (per file) and then have a variable amount of unknown data at the end of the file after the actual data.

i figured out a little from the header but it doesn't really say me much..

the header i looked at looks like this:


```
0x10 | 1001 E001 E001 0500 3000 0000 0000 0000 | ........0.......
0x20 | 0000 0000 0001 0300 30FE 0100 0000 0000 | ........0.......

```


what i know about it so far is that 
0x00: number of files [hex] <--- not 100% on this though
0x10: vertical resolution [hex]
0x12: horizontal resolution [hex]
0x18: data start [hex]
0x28: data end [hex]

the problem i have with these files is that all the game data is these same tpl files, and since i doubt that the whole game consists of images, i really dunno how to deal with these 

thanks for looking
## Post #2
- Username: mugi
- Rank: beginner
- Number of posts: 32
- Joined date: Thu Mar 24, 2011 3:02 am
- Post datetime: 2013-11-03T12:58:00+00:00
- Post Title: Utawarerumono portable (PSP)

could still use help with this, anyone ?
pretty please   

uploaded some example files too

[Utaware_psp examples](http://mce.do.am/dev/psp/utawarerumono_examples.rar)
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-11-04T11:50:52+00:00
- Post Title: Utawarerumono portable (PSP)

[](http://www.pic-upload.de/view-21231989/egeru01.tpl.jpg.html)set width to 160 to get a single head and shift to 468
## Post #4
- Username: mugi
- Rank: beginner
- Number of posts: 32
- Joined date: Thu Mar 24, 2011 3:02 am
- Post datetime: 2013-11-04T16:29:41+00:00
- Post Title: Utawarerumono portable (PSP)

thanks !

that's a great help already, even though im trying to get a hold of how these files are actually built more than just dumping them.
any idea of the garbage that's above the graphics ?

also, did you get anything sensible out of any other file than the one you posted the pic of ?

edit:

upon further inspection, i managed to dig out these:

[](http://farm8.staticflickr.com/7455/10676670125_98ca97eebe_o.png)

[](http://farm6.staticflickr.com/5481/10676713566_45b88b0da6_o.png)

[](http://farm6.staticflickr.com/5544/10676731004_d3453bcec1_o.png)

[](http://farm6.staticflickr.com/5482/10676731874_06fe8e0645_o.png)



now... i don't really know.. im completely clueless when it comes to graphic formats but i see a definite resemblance to the 160px "thumbnail" picture
on the garbage above..

judging by the 160px uncompressed preview image, the graphics share the aspect ratio of the PC version of the game (i think it's 640x480 or 800x600)
they doo seem a littel cropped in the psp version of the game compared to it's pc counterpart anyway.

im fairly sure that the 160px ones are not the actual game grapchis judging by the smoothness of them in-game. There's no way a 160px scales to 480px without any quality loss..

continuing my research....
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-11-04T20:35:52+00:00
- Post Title: Utawarerumono portable (PSP)

> Reply from mugi
>
> any idea of the garbage that's above the graphics ?scrambled picture data?
[](http://www.pic-upload.de/view-21236819/egeru01_2.jpg.html)
Seems you'll need to find some algo to create the original picture from it.

> also, did you get anything sensible out of any other file than the one you posted the pic of ?nope
## Post #6
- Username: mugi
- Rank: beginner
- Number of posts: 32
- Joined date: Thu Mar 24, 2011 3:02 am
- Post datetime: 2013-11-04T20:40:11+00:00
- Post Title: Utawarerumono portable (PSP)

> Reply from shakotay2
>
> mugi wrote:any idea of the garbage that's above the graphics ?scrambled picture data?

Seems you'll need to find some algo to create the original picture from it.
also, did you get anything sensible out of any other file than the one you posted the pic of ?nope

feared as much, im too dumb for this type of things xD

thanks in any case, i'll be poking it more in an attempt to get it figured out.
(hoping to get to chat with the people who hacked and translated the pc version)

in the meantime, i would appreciate it if someone who knows what they're doing unlike me, would care to take a jab at it 

it's becoming more clear to me that this is some form of obfuscation algorithm, since it applies to ALL gamedata, sans the main executable, FMV videos and audio.
everything else in the game is .tpl and looks just like these examples on hex editor. (well there are those FMP files but they dont seem to contain anything i might want to extract/modify)

are there any forms of tutorials or examples or someting around that would maybe shed a little light on how should i start solving this mystery, or am i just SOL ?
