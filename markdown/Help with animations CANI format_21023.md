## Post #1
- Username: Pr4pR
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jul 14, 2018 8:34 pm
- Post datetime: 2019-08-23T10:47:54+00:00
- Post Title: Help with animations: CANI format

Hi guys! I was wondering if someone here could help me out getting started with reversing an animation format. The objective would be reversing it then see if it's possible creating a noesis script to export them. I want to start off by saying I am still quite the noob and learning the stuff here and there, but I am willing to do so in order to get more knowledge about this stuff...

So, the animation format I want to look at is the CANI format. This format can be found in PlayStation All-Stars Battle Royale (PSASBR) and, as far as I know, in the BluePoint Engine games generally speaking. In specific I am looking at CANI files from the PS Vita version of PSASBR. I don't have any experience with animations... so I was hoping someone here could give me some guidance. I won't be asking to just get the file and do everything yourself, but I'd need some guidance if you can see anything useful from the file, or any piece of documentation of how animations are generally structured could be of help, since I can't find much... Any help is appreciated! So far these are the only pieces of info I could get about this format.



unknown.PNG (33.08 KiB) Viewed 183 times



Endianness is little-endian because of the PS Vita, if you take a CANI file from a PS3 game the endianness is big-endian.
At offset 0x0 is the magic 60AE. The decoded 60 seems like it stands out for the format version, as CANI files from previous builds of this game have the decoded number being lower, such as 50AE.
Offsets 0x4 and 0x8 are Uints which purpose is not known. Being reallu big values I don't think they are important?
Offset 0xC is Ushort and it seems that it indicates an offset in the file.
Offset 0xE is another Ushort and it indicates the number of bones the animation transforms.

After there I still can't tell what the other stuff means. The next 4 bytes are definitely 2 Ushorts but I don't know what they mean yet... I should look for keyframes or something I guess? At least that's what I got when looking at the little stuff I could find online about other formats. Then the Ushort at offset 0x14 is a constant 0x2000 value in all the CANI files. Including the latters, so starting from offset 0x10 and skipping 80 bytes (that's like this for every CANI file, I don't know what these 80 bytes contain still), you can see that the values every 2 bytes are incrementing almost sequentially... I honestly don't know what they could mean. Then starting a certain offset, which seems to be the one I mentioned at 0xC, bunch of data starts.

If you want a sample file ask and I'll upload it. Any kind of help is appreciated!
## Post #2
- Username: You'reAnAllStar
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Nov 04, 2016 5:55 am
- Post datetime: 2019-09-18T02:15:14+00:00
- Post Title: Help with animations: CANI format

I remember asking about these files a couple years ago. I'm surprised that to this day very few people have made efforts to extract things from the game; the model extracting script seems to have been lost, as well, unless I'm missing something. I know the game wasn't that popular, but still...

Hopefully someone else takes interest. I'd really like to see more work done with this game.
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-09-18T18:58:47+00:00
- Post Title: Help with animations: CANI format

> Reply from You'reAnAllStar ↑Wed Sep 18, 2019 10:15 am at Wed Sep 18, 2019 10:15 am
>
> Hopefully someone else takes interest.Guess, nobody will care for anims as long as the mesh format isn't clear and the models aren't extracted.

Do the mesh files start with signature 4D4F444C "MODL" (as fat_princess.c0.p0.cskn does)?

Here's here eyeball:



fat_eyeball.png (45.54 KiB) Viewed 145 times
## Post #4
- Username: You'reAnAllStar
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Nov 04, 2016 5:55 am
- Post datetime: 2019-09-22T22:10:09+00:00
- Post Title: Help with animations: CANI format

I remember FP being one in particular there were issues loading for me, I'd seen you mention in another thread about that issue and that honestly made a lot of sense. I wonder why her model us different like that; perhaps her intro animation is a reason for it?

Regardless, the animations wouldn't be much use without the models, so I can see why very few people looked into it.
## Post #5
- Username: Pr4pR
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jul 14, 2018 8:34 pm
- Post datetime: 2019-09-24T14:17:09+00:00
- Post Title: Help with animations: CANI format

> Reply from shakotay2 ↑Thu Sep 19, 2019 2:58 am at Thu Sep 19, 2019 2:58 am
>
> 
You'reAnAllStar wrote: ↑Wed Sep 18, 2019 10:15 amHopefully someone else takes interest.
Guess, nobody will care for anims as long as the mesh format isn't clear and the models aren't extracted.

Do the mesh files start with signature 4D4F444C "MODL" (as fat_princess.c0.p0.cskn does)?

Here's here eyeball:
fat_eyeball.png

Hi there, sorry for the late reply, I did not expect this to get any attention lol.

Chrrox did already create a Noesis script for these models actually. Yeah, the header magic is MODL. It's the PS Vita model format. The script, however, didn't work correctly, as it couldn't extract all the models, it did throw like 4 different errors, but I fixed it   . It wasn't a mesh problem, chrrox did figure out that on his own, the problem was another one that I will eventually explain later but anyway, consider that we can get access to all models now, and I am still working on the script as other than fixing the errors I would have liked to add more stuff like loading more maps and such, also normals and tangents weren't being loaded, now they are. Fat Princess is one of those who couldn't be extracted before, but with the script I improved now can. Just the face bones are weirdly placed although lined up correctly but this is a problem isolated only to her model and Kratos, and still being lined up correctly anyway so they work where expected. I haven't looked to the skeleton yet anyway (it's strictly connected to the animation format).




fp.png (55.44 KiB) Viewed 114 times



Mind that we may be talking about different models, if the CSKN you are talking about has been extracted from the PS3 version with a RAM dump or something then it will turn out to be 4D4F444C and the next 4 bytes will have the value 7 as the version of the MODL, the PS Vita version is 8 and different from the PS3 one, the animation file I showed is for PS Vita, and we do (now) have access to all the models. They told me it's an Edge Animation file, the only PS Edge thing ported from PS3 to PS Vita and also PS4 as far as I know. The Edge Animation is supposed to be made of two components, a "skel" file and an "anim" file. The "skel" file in the case of this game is incorporated directly inside the model, which makes the skeleton. The anim file instead has been renamed to CANI here.

P.S: I've subscribed to the topic so I won't miss any more replies LOL
## Post #6
- Username: Pr4pR
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jul 14, 2018 8:34 pm
- Post datetime: 2019-09-24T14:26:14+00:00
- Post Title: Help with animations: CANI format

> Reply from You'reAnAllStar ↑Wed Sep 18, 2019 10:15 am at Wed Sep 18, 2019 10:15 am
>
> 
I remember asking about these files a couple years ago. I'm surprised that to this day very few people have made efforts to extract things from the game; the model extracting script seems to have been lost, as well, unless I'm missing something. I know the game wasn't that popular, but still...

Hopefully someone else takes interest. I'd really like to see more work done with this game.

It's not been lost, we just had the chrrox one for the PS Vita models but it really didn't work with a good quantity of them, probably more than half. Errors thrown by the script ended up being 4, with "Tried to set offset beyond buffersize" the common one. Took my time in "debugging" to get what was wrong and welp, got what was going wrong. Managed to fix all errors and this one too, that was being caused due to an unexpected quantity of data in the materials of certain models. Unhandling this data would cause this error, and it did happen for really many, many models in this game. I am still on my way in working into this script anyway, as I just didn't want to stop at fixing the errors, there is much data that can be parsed in noesis to improve and get great models that the old script does not make use of.
## Post #7
- Username: You'reAnAllStar
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Nov 04, 2016 5:55 am
- Post datetime: 2019-09-24T19:54:13+00:00
- Post Title: Help with animations: CANI format

To be entirely fair, I'm incredibly unorganized and as such have issues finding things on my own computer, so part of me figured it was less "lost" and more "I can't find it."

Glad to hear there is still a niche group dedicated to this game over 7 years and 2 Smash games later.
