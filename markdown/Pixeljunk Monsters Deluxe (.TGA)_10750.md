## Post #1
- Username: arg274
- Rank: beginner
- Number of posts: 27
- Joined date: Mon Aug 26, 2013 3:05 am
- Post datetime: 2013-09-04T18:21:46+00:00
- Post Title: Pixeljunk Monsters Deluxe (*.TGA)

These are some TGA files of Pixeljunk Monsters Deluxe(PSP).They might be compressed(?)Well one of them can be easily viewed but with wrong colors and the other one seems to be distorted.Please help.Thnx in advance.
[PJMD.rar](https://xentaxbackup.github.io/file/6593_PJMD.rar)
## Post #2
- Username: SILENTpavel
- Rank: advanced
- Number of posts: 54
- Joined date: Fri Aug 05, 2011 12:53 pm
- Post datetime: 2013-09-24T00:46:40+00:00
- Post Title: Pixeljunk Monsters Deluxe (*.TGA)

I can help with it.
Just looked into UMD imgage and found all textures in TGA, but not normal TGA. Some textures like your HOWTOPLAY_ADHOC.TGA have standart ps2/psp Swizzling ([http://en.wikipedia.org/wiki/Swizzling_ ... _graphics)](http://en.wikipedia.org/wiki/Swizzling_%28computer_graphics%29)).
Some textures like MEDALROOM.TGA have just console color space and in upside down position.

If we are talking about HOWTOPLAY_ADHOC.TGA/plus all others like that:
* Download Console Texture Explorer;
* Create text file with name "pixel-256x128.ini";
* Open this file and copy this into, then save it:

```
count=1
[item_0]
name=texture
platform=PSP
offset=1042
width=256
height=128
BPP=8
mipmaps=-1
palette_offset=18
swizzling=Enabled
```

(thanks to Dageron for little research this code)
* Open Dageron's CTE, File -> Open -> HOWTOPLAY_ADHOC.TGA;
* Press button "Load *.ini" and select file "pixel-256x128.ini";
* Now just select "texture" inside of "texture name (custom)" list and you will see unswizzled texture.
* You can save it with "Export" button whatever format you like.



HOWTOPLAY_ADHOC11.png (38.7 KiB) Viewed 180 times


If we are talking about MEDALROOM.TGA/others like it:

* Download [http://www.xnview.com](http://www.xnview.com);
* Open TGA;
* Image -> Swap -> RGB > BGR;
* Press Shift+V;
* Done.

[](http://imageshack.us/photo/my-images/5/v9p2.jpg/)

p.s. there is more specific texture you can find, but i will write about it later.
## Post #3
- Username: arg274
- Rank: beginner
- Number of posts: 27
- Joined date: Mon Aug 26, 2013 3:05 am
- Post datetime: 2013-10-01T18:23:43+00:00
- Post Title: Pixeljunk Monsters Deluxe (*.TGA)

HOOT!my first help on xentax.really appreciated,thanks man.now this game is fully moddable.+1!
## Post #4
- Username: arg274
- Rank: beginner
- Number of posts: 27
- Joined date: Mon Aug 26, 2013 3:05 am
- Post datetime: 2013-10-04T08:53:54+00:00
- Post Title: Pixeljunk Monsters Deluxe (*.TGA)

OOPS!a problem again!swapping RGB>BGR isnt just working for me.the colors are wrongly outputted..
## Post #5
- Username: SILENTpavel
- Rank: advanced
- Number of posts: 54
- Joined date: Fri Aug 05, 2011 12:53 pm
- Post datetime: 2013-10-04T21:00:05+00:00
- Post Title: Pixeljunk Monsters Deluxe (*.TGA)

> Reply from arg274
>
> OOPS!a problem again!swapping RGB>BGR isnt just working for me.the colors are wrongly outputted..
write names of the textures, that don't work right with my method
i have this game, and i can test any resourse inside of it, just need the names
## Post #6
- Username: arg274
- Rank: beginner
- Number of posts: 27
- Joined date: Mon Aug 26, 2013 3:05 am
- Post datetime: 2013-10-05T07:38:59+00:00
- Post Title: Pixeljunk Monsters Deluxe (*.TGA)

even MEDALROOM.TGA isnt working for me.which version of XnView do you have?i have the extended one.
## Post #7
- Username: SILENTpavel
- Rank: advanced
- Number of posts: 54
- Joined date: Fri Aug 05, 2011 12:53 pm
- Post datetime: 2013-10-05T21:18:17+00:00
- Post Title: Pixeljunk Monsters Deluxe (*.TGA)

> which version of XnView do you have?
XnView Windows v. 1.98.1 (Jun 21 2011)
all working, like i said upper
## Post #8
- Username: arg274
- Rank: beginner
- Number of posts: 27
- Joined date: Mon Aug 26, 2013 3:05 am
- Post datetime: 2013-10-08T16:28:36+00:00
- Post Title: Pixeljunk Monsters Deluxe (*.TGA)

problem resolved.i forgot to convert index>RGB first.thanks for the help!
