## Post #1
- Username: marcussacana
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Jul 23, 2015 5:08 am
- Post datetime: 2018-10-08T06:54:08+00:00
- Post Title: [Tiled? PNG] Utawarerumono: Itsuwari no Kamen

Well, I'm trying modify the .tex files from the "Utawarerumono: Itsuwari no Kamen" of ps3
At first look seens a .png with a header, and some files works just removing this header.
But a problem, some files looks like a 'tiled' texture...

An texture non-tiled: [https://up.vidyagam.es/ede821da-d258-4e ... -n.tex.png](https://up.vidyagam.es/ede821da-d258-4e68-b4f5-db8bea123c24-general-n.tex.png)
And a texture tiled: [https://up.vidyagam.es/30a8c39a-7d44-42 ... al.tex.png](https://up.vidyagam.es/30a8c39a-7d44-428a-8246-b702762dab4b-general.tex.png)

In both files I just removed the .tex header, 
If I can say something I looks like the value at 0xD, if equals to 0x3 then is tiled, if equals to 0x1 isn't tiled (not sure)


Sample Files:
[https://up.vidyagam.es/d05fedc3-3f64-43 ... exture.rar](https://up.vidyagam.es/d05fedc3-3f64-431c-becf-f3755470ff87-Texture.rar)

Any hints?
## Post #2
- Username: mugi
- Rank: beginner
- Number of posts: 32
- Joined date: Thu Mar 24, 2011 3:02 am
- Post datetime: 2018-10-11T20:38:12+00:00
- Post Title: [Tiled? PNG] Utawarerumono: Itsuwari no Kamen

they are swizzled with morton (aka. z-order)

you're also right about the flag, if you change the flag in the header to disable the swizzle, the graphics work fine without it, so if you can get your hands on the clean image, you can just reassemble it and change the header to not use z-order, then insert it back clean. 

i did a full reverse-engineering of all the compression, filecontainer, text and graphic formats of the game including the sprite coordinates of the multi-image spritesheets, but my data applies to the ps3 versions of the game.
if my memory serves me, vita version had slight differences. (the endianess, for starters, and iirc the graphics stuff had different values for the flags, 0x07 i believe was swizzle toggle.)

oh just for the shits of it, the executable of the game also contains a LZ77 compressed text portion holding the DLC encryption keys in it.
## Post #3
- Username: marcussacana
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Jul 23, 2015 5:08 am
- Post datetime: 2018-10-13T21:48:21+00:00
- Post Title: [Tiled? PNG] Utawarerumono: Itsuwari no Kamen

Thanks for the info, I'm newbie with textures formats, but i will try do something.
(I'm working with the ps3 ver too)

It's this, I'm rigth?: [https://en.wikipedia.org/wiki/Z-order_curve](https://en.wikipedia.org/wiki/Z-order_curve)
## Post #4
- Username: mugi
- Rank: beginner
- Number of posts: 32
- Joined date: Thu Mar 24, 2011 3:02 am
- Post datetime: 2018-10-16T12:45:46+00:00
- Post Title: [Tiled? PNG] Utawarerumono: Itsuwari no Kamen

yeah. Though just so that you know, if my memory serves me, only like... 4 images in the entire game are using this swizzle. (titlescreen image, some menu stuff i believe.) i just fed them to my deswizzler and then disabled the whole junk from the header. They learned their lesson since utawarerumono 3 doesnt use it anymore xD (they blessed me with all sort of other shit to reverse instead lol.) i have a few pics on my site of the title screne actually working after i got rid of that stupid extra layer of bother on it; [https://blacklabel-translations.com/arc ... i-no-kamen](https://blacklabel-translations.com/archives/category/utawarerumono-2-itsuwari-no-kamen)
## Post #5
- Username: marcussacana
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Jul 23, 2015 5:08 am
- Post datetime: 2018-10-20T06:38:52+00:00
- Post Title: [Tiled? PNG] Utawarerumono: Itsuwari no Kamen

Are you trying translate the ps3 version?
If yes, well, take a look in the fuwanovel, I published a 'automatic' port of the psv text to the ps3 script...
Well... needs a revision because this 'automatic' port isn't perfect but if you want do a proper patch this can save your time.
## Post #6
- Username: mugi
- Rank: beginner
- Number of posts: 32
- Joined date: Thu Mar 24, 2011 3:02 am
- Post datetime: 2018-10-23T18:38:17+00:00
- Post Title: [Tiled? PNG] Utawarerumono: Itsuwari no Kamen

I planned to, but it's currently not something im actively working on. I got busy with other things.
That said, i have a full mapping of the script format so editing it in any way i wish is not really an issue.
## Post #7
- Username: marcussacana
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Jul 23, 2015 5:08 am
- Post datetime: 2019-03-14T02:18:25+00:00
- Post Title: [Tiled? PNG] Utawarerumono: Itsuwari no Kamen

Thank you, I added support in my tool, it's late but well, 
If anyone with the same problem: [https://github.com/marcussacana/AquaPlusEditor](https://github.com/marcussacana/AquaPlusEditor)
## Post #8
- Username: mugi
- Rank: beginner
- Number of posts: 32
- Joined date: Thu Mar 24, 2011 3:02 am
- Post datetime: 2019-05-06T14:51:35+00:00
- Post Title: [Tiled? PNG] Utawarerumono: Itsuwari no Kamen

im a bit late too i guess but i decided to just release the tools we coded for this game while poking around with it.
you can download the whole thing from my site; [https://bbs.blacklabel-translations.com ... php?tid=73](https://bbs.blacklabel-translations.com/showthread.php?tid=73)

maybe they'll serve some use for someone.
## Post #9
- Username: marcussacana
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Jul 23, 2015 5:08 am
- Post datetime: 2019-09-14T18:37:23+00:00
- Post Title: [Tiled? PNG] Utawarerumono: Itsuwari no Kamen

Yeah, good work man, I'm glad in know you are trying help the world-wide translation community.

Just notice acutally we can't download because we can't register in your forum after click in 'I agree'
