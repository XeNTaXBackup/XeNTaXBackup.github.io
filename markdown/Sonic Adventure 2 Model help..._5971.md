## Post #1
- Username: ItsEasyActually
- Rank: n00b
- Number of posts: 18
- Joined date: Fri Dec 17, 2010 7:49 am
- Post datetime: 2011-02-03T00:44:56+00:00
- Post Title: Sonic Adventure 2 Model help...

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2011-02-03T13:57:22+00:00
- Post Title: Sonic Adventure 2 Model help...

The contents of this post was deleted because of possible forum rules violation.
## Post #3
- Username: ItsEasyActually
- Rank: n00b
- Number of posts: 18
- Joined date: Fri Dec 17, 2010 7:49 am
- Post datetime: 2011-02-04T01:22:00+00:00
- Post Title: Sonic Adventure 2 Model help...

Well, I'm having issues with the output file. It outputs a .obj file, but I can't open it in any programs I have. I've tried Frag, 3DS Max, and Blender. After looking at the file via a hex editor, it seems to have been error'd upon export. I don't know if I did something wrong or not. I tried three different files in it, and they all gave me the same issue. Also, the error listed is this.

> Error:
>
> vertex coordinate too big
>
> adjust object-scale
The inner workings of it though show that it's broken upon the program compiling it. It has errors riddled within the text side of the code throughout the entire file. Not sure where to go from here ultimaespio.
## Post #4
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2011-02-04T13:33:37+00:00
- Post Title: Sonic Adventure 2 Model help...

Just re read your original post...there is a good reason why it's not working. Your using the wrong file. Your supposed to use SONICMDL not SONICMTN. MTN is the animations, MDL is the model.

Did you make sure you decompressed the PRS to BIN before you used it?
## Post #5
- Username: ItsEasyActually
- Rank: n00b
- Number of posts: 18
- Joined date: Fri Dec 17, 2010 7:49 am
- Post datetime: 2011-02-04T16:34:54+00:00
- Post Title: Sonic Adventure 2 Model help...

I know which file is which. I used both Sonic's model AND City Escape. It exports a useless .obj file. I can even upload it (when I get home) to show you the evidence of this happening. And besides, it won't rip anything from the mtn file.
## Post #6
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-02-05T00:48:53+00:00
- Post Title: Sonic Adventure 2 Model help...

have anyone been able to extract the model
## Post #7
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2011-02-05T14:23:36+00:00
- Post Title: Sonic Adventure 2 Model help...

Step by step:

Drag your model file onto SA2MDL

When it asks for a start address, enter 0

When it asks about generating a key automatically, press Y

Then it should rip everything. I honestly don't know why it won't work for you.
## Post #8
- Username: ItsEasyActually
- Rank: n00b
- Number of posts: 18
- Joined date: Fri Dec 17, 2010 7:49 am
- Post datetime: 2011-02-05T15:36:30+00:00
- Post Title: Sonic Adventure 2 Model help...

1: Done
2: Done
3: Done
4: I watched it rip several times. 
It's something about it's export. It's giving me corrupted .obj files because when I opened one, 3DS gave me an error, Fragmotion froze, and Blender returned an error as well. I opened it in Hex Workshop, I saw this data.

```
#DEBUG: g group3444_1848.#ERROR: 91 - Unknown vertex type..
#DEBUG: g group3446_21495808.#ERROR: 91 - Unknown vertex type..
#DEBUG: g group3448_328.#ERROR: 91 - Unknown vertex type..
#DEBUG: g group3450_501678080.#ERROR: 91 - Unknown vertex type..
#DEBUG: g group3452_-1105781273.#ERROR: 0 - Unknown vertex type..
#DEBUG: g group3454_358792727.#ERROR: 0 - Unknown vertex type..
#DEBUG: g group3456_-1082190494.#ERROR: 0 - Unknown vertex type..
#DEBUG: g group3458_-1814446209.#ERROR: 0 - Unknown vertex type..
#SIZE=397.#OFFSET=0.g group3468_23.#Vertex: 66, Vertex Total: 1.v
```

After that, it's just a normal obj file. I've tried removing different portions of that starting bit, and the same error continues to prevent me from doing anything with it. I've tried pretty much everything I can think of to get it to open and it just refuses to. So as you are, I'm stumped. Also, you're sure there wasn't any other files in the original sa2mdl package, right?
## Post #9
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2011-02-05T15:52:05+00:00
- Post Title: Sonic Adventure 2 Model help...

Better check, are you using the Dreamcast one or the Gamecube one? The ones from the gamecube have different endians, so it won't work.

And no, the only other stuff that comes in the package is the prsdecompressers.
## Post #10
- Username: ItsEasyActually
- Rank: n00b
- Number of posts: 18
- Joined date: Fri Dec 17, 2010 7:49 am
- Post datetime: 2011-02-05T15:53:52+00:00
- Post Title: Sonic Adventure 2 Model help...

I'm only using the Dreamcast files.
## Post #11
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2011-02-05T15:55:19+00:00
- Post Title: Sonic Adventure 2 Model help...

Should work, I've just tried it out. Works fine.

Get MrAdult's Noesis model viewer, and see if that opens the exported .obj. If it does, you can just convert it to something else that you can open.
## Post #12
- Username: ItsEasyActually
- Rank: n00b
- Number of posts: 18
- Joined date: Fri Dec 17, 2010 7:49 am
- Post datetime: 2011-02-06T02:15:56+00:00
- Post Title: Sonic Adventure 2 Model help...

That fixed the character's issue. Levels seem to still not want to cooperate with me even when using Noesis. I'm wanting the levels moreso than the character models...so...

EDIT: Welp, it seems only a few characters were actually fixed while others still don't work. This really pisses me off that I can't get this thing to work.
