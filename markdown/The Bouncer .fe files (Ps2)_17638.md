## Post #1
- Username: EikoBiko
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jan 31, 2018 10:57 pm
- Post datetime: 2018-01-31T15:29:13+00:00
- Post Title: The Bouncer .fe files? (Ps2)

Hey! 

Please bear with me here, I'm an incompetent ultra-n00b, but I found this thread about an hour ago and was able to successfully rip out a bunch of .fe, .tex, and .sk files from The Bouncer using QuickBMS. The previous post I linked said they were models, textures, and skeletons respectively. I'm mostly interested in the .fe files at this point. I have no clue how to actually open these things, and Google isn't really providing much help. I'm really just trying to bring the stage models over to VRChat, and the first step is actually grabbing the models. I know it can be done, because there's a batch of character models over at The Models Resource. Could someone point me in the right direction?

Thanks so much in advance!
## Post #2
- Username: Casedey
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Aug 20, 2011 1:27 pm
- Post datetime: 2018-01-31T21:00:22+00:00
- Post Title: The Bouncer .fe files? (Ps2)

You can use Noesis to convert bouncer .fe models, but high polygon models were never fully supported as far as i know, and i don't think it works with stages.
## Post #3
- Username: EikoBiko
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jan 31, 2018 10:57 pm
- Post datetime: 2018-02-01T20:34:28+00:00
- Post Title: The Bouncer .fe files? (Ps2)

Thanks a ton! 

It seems like you're right, I can't grab any stage models or the robot enemy models. They're probably further down in the compressed bins that MrAdults was talking about on the previous thread. I don't really have the technical know-how to crack it, so it looks like I'm at the end of my rope! 

Thanks again, though!

For future reference for anyone else, you can only get as far as what's on The Models Resource with the current code. That's the following:
Sion's outfits
Volt's outfits
Kou's outfits
Dominique's outfits
Dauragon's outfits
Kaldea's outfits
Mugetsu's outfits
Echidna's outfits
PD-4's outfits
Leann's outfits
Guard dog
Security guards
MSF

All of the above are the low-poly battle models. You can extract them for yourself using QuickBMS with this code:

```
get ftbl long
set filetable 0x800
set filebase 0x800
savepos offtable
for i = 0 < files
goto offtable
get offset long
math offset * 0x800
savepos offtable
get size long
math size * 0x800
goto filetable
get nameoff long
savepos filetable
math nameoff + filebase
goto nameoff
get name string
if size == 0
get size asize
endif
math size - offset
log name offset size
next i

```


and they can be found in BOUNCER.bin > debchmdl.bin

There don't appear to be any other points of interest. I did find a couple .ltx files, such as those in BOUNCER.bin > battle.bin, but I'm not sure how to open those.
## Post #4
- Username: Casedey
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Aug 20, 2011 1:27 pm
- Post datetime: 2018-02-02T01:03:34+00:00
- Post Title: The Bouncer .fe files? (Ps2)

I extracted High Poligon Models from Unencrypted PS2 savestates using a hex editor, but Noesis loaded them incomplete.
