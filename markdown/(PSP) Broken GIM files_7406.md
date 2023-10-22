## Post #1
- Username: eycaramba
- Rank: veteran
- Number of posts: 86
- Joined date: Wed Sep 02, 2009 8:52 pm
- Post datetime: 2011-09-23T19:09:19+00:00
- Post Title: (PSP) "Broken" GIM files?

Hey there guys,

I recently stumbled upon some kinda "broken" GIM files which seem to miss out the palette data.
Do you have any idea how to fix / convert them?

I uploaded some of them here: [http://vuvu.bplaced.net/brokengim.zip](http://vuvu.bplaced.net/brokengim.zip)

Everything helps me, closer analysis etc 

Kind regards and thanks in advance,
eycaramba
## Post #2
- Username: 0xFAIL
- Rank: VVIP member
- Number of posts: 50
- Joined date: Fri Oct 21, 2011 5:59 pm
- Post datetime: 2011-10-25T20:12:29+00:00
- Post Title: (PSP) "Broken" GIM files?

(I don't think this counts as a necro bump, cause one month is like nothing on xentax ;-D )

None of those files are GIM files, every single one either contains random data or nothing of value at all.
Where did you get them?
## Post #3
- Username: eycaramba
- Rank: veteran
- Number of posts: 86
- Joined date: Wed Sep 02, 2009 8:52 pm
- Post datetime: 2011-10-26T16:05:43+00:00
- Post Title: (PSP) "Broken" GIM files?

They are from a texture container of MonsterHunterPortable series.
So I highly assume they are some kind of textures and I was told that they are gims but missing out palette data or sth.
## Post #4
- Username: 0xFAIL
- Rank: VVIP member
- Number of posts: 50
- Joined date: Fri Oct 21, 2011 5:59 pm
- Post datetime: 2011-10-26T20:03:36+00:00
- Post Title: (PSP) "Broken" GIM files?

None of those files seem to have a valid GIM header ("MIG" as the first three bytes at the beginning of the file
if I remember correctly)

Can you tell me exactly where/how you got those files, maybe I can reconstruct the GIM files you wanted.
I will also look into the GIM file format and will probably post again in 2-3 days.
## Post #5
- Username: eycaramba
- Rank: veteran
- Number of posts: 86
- Joined date: Wed Sep 02, 2009 8:52 pm
- Post datetime: 2011-10-27T13:47:51+00:00
- Post Title: (PSP) "Broken" GIM files?

Look at the folder I provided here: vuvu.bplaced.net/MHP3rd/5142.zip
In the 002_image subfolder, that is where the files are from.

Thanks for taking a look!
## Post #6
- Username: Kono
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Feb 02, 2011 5:33 am
- Post datetime: 2011-10-30T17:46:39+00:00
- Post Title: (PSP) "Broken" GIM files?

This is because the first bytes have been removed. none.gim are really gim image. But the number at the offset 0x18 specifie the type of bloc wich is following this number. 0x04 is a pixel image, 0x05 a palette. The problème is that in the none.gim this is a 0x08 which is written. I tried to change this number but the result isn't a texture too. I think there is more changement to do byte per pixel for example.

I'm sorry for my bad english, i'm French ^^ (Hello Vuze It's been a long time )
## Post #7
- Username: 0xFAIL
- Rank: VVIP member
- Number of posts: 50
- Joined date: Fri Oct 21, 2011 5:59 pm
- Post datetime: 2011-11-01T20:03:00+00:00
- Post Title: (PSP) "Broken" GIM files?

Try gimconv (to see what the header looks like), maybe you can use it to make yourself a working header
(if you can guess the dimensions of the gim file, which are probably depended on the filesize)
Additionally you can also use a hand made palette (if you know the format of the palette) in greyscale until you find the real one.

(I couldn't find a file spec for gim so sadly I can't help you much)
## Post #8
- Username: eycaramba
- Rank: veteran
- Number of posts: 86
- Joined date: Wed Sep 02, 2009 8:52 pm
- Post datetime: 2011-11-02T07:58:51+00:00
- Post Title: (PSP) "Broken" GIM files?

@Kono: Mh, must have been a very long time or you are using another nickname here as well 
Thanks for validiating, it is actually GIM data.

@0xFAIL: Okay I will try this, thanks 
Btw, this is a GIM format analysis I found ages ago. [http://pspdum.my.land.to/psp/gim.html](http://pspdum.my.land.to/psp/gim.html)
It is old and incomplete, but the header is quite figured out.
