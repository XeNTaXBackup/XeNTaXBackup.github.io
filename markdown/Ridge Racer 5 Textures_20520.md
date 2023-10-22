## Post #1
- Username: Nega
- Rank: beginner
- Number of posts: 27
- Joined date: Thu Sep 30, 2010 4:57 am
- Post datetime: 2019-05-21T21:42:32+00:00
- Post Title: Ridge Racer 5 Textures

Hello, i'm currently working on Ridge Racer 5 models and was able to figure out how to work with the model format, but i'm currently stumped on the textures.

I've attached a sample from the Kamata Angelus, any idea what's going on with the textures? Many thanks!

Note: I got these from RAM, since the main file seems to have the car assets compressed.
[Angelus.zip](https://xentaxbackup.github.io/file/16273_Angelus.zip)
## Post #2
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2019-05-21T23:04:47+00:00
- Post Title: Ridge Racer 5 Textures

are you serious? the palettes and texture have no relations. how do you think this gonna work? i sure can read the hex. this is a hard egg i think. ps2 data is kinda always a mess tho.
## Post #3
- Username: Nega
- Rank: beginner
- Number of posts: 27
- Joined date: Thu Sep 30, 2010 4:57 am
- Post datetime: 2019-05-21T23:11:21+00:00
- Post Title: Ridge Racer 5 Textures

I included the palette file in case the texture files ever used it. I didn't know if it did or not

Edit: It definitely has an effect, I messed with it and it does this
## Post #4
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2019-05-21T23:45:55+00:00
- Post Title: Ridge Racer 5 Textures

well looks like i found some other form of palette in the wheels file right now. will continue and start coding then. this gonna be a mash of bms and noesis. i dunno how to export multi image files from a noesis script. things to learn. i need the ps2 swizzle from noesis tho.

palette for the rim, the logo and the tire texture. right? 



btw... is the car model available? i would add this to my virtual garage.
## Post #5
- Username: Nega
- Rank: beginner
- Number of posts: 27
- Joined date: Thu Sep 30, 2010 4:57 am
- Post datetime: 2019-05-21T23:52:28+00:00
- Post Title: Ridge Racer 5 Textures

Thanks for looking into this, much appreciated! And yep, that seems about right for the palettes.

As for the model, it's not quite ready yet, but it's definitely being worked on.
## Post #6
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2019-05-22T05:00:47+00:00
- Post Title: Ridge Racer 5 Textures

i might be a lil rusty, but we gettin' somewhere with the code. i need a break now tho. brain drained over nite. and i got a stream to watch.
## Post #7
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2019-05-22T13:57:48+00:00
- Post Title: Ridge Racer 5 Textures

well. for now here are all the wheel textures i could harvest. includes what seems to be lod textures too. automation is impossible. the palettes can not be identified and relation not be done. and the palettes use those triple surfaces which i had to manually split to not complicate things.

[https://www.mediafire.com/file/i7hz9a4h ... /wheel.rar](https://www.mediafire.com/file/i7hz9a4hnsg8hm2/wheel.rar)

here question: how'd you obtain this data? an emulator (pcsx2 ?) gif/gs log or cheat engine dump? cause...

yeh... the body textures may take a while. afai could walk the file, it's like a stream of 300+ 'commands' and texture fragments. maybe as polys are rendered from the command buffers. the ps2 can do that. i gotta (just try really) assemble all of that, somehow. a procedure to figure out.

edit: and i'm stuck.  i rewrote it to 'properly' test for the gif register codes. dled the pcsx2 source again even. but i can't handle this primitive code. the size of the buffer to skip is nowhere to be found or computable. if you or anybody else reading this thread got ideas go ahead. 


[rrv_raw2tgs.rar](https://xentaxbackup.github.io/file/16276_rrv_raw2tgs.rar)
## Post #8
- Username: viperzerofsx
- Rank: veteran
- Number of posts: 95
- Joined date: Thu May 27, 2010 12:07 pm
- Post datetime: 2019-05-22T21:40:10+00:00
- Post Title: Ridge Racer 5 Textures

Hey, I'm super interested in RRV models. When your done, could you post your method?
## Post #9
- Username: Nega
- Rank: beginner
- Number of posts: 27
- Joined date: Thu Sep 30, 2010 4:57 am
- Post datetime: 2019-05-23T02:31:41+00:00
- Post Title: Ridge Racer 5 Textures

Thanks a lot episoder! This is exciting to see!

As for how I got this data, yeah, I got this through PCSX2. I was able to find the pointers in the game to see what data was being set up in the game when cars are loaded. I changed the offsets so they reflected on the file areas instead of having the game pointer offsets instead (originally was like C0XXXX or something like that)...though this could've introduced some issues?

Each car has 4 pointers it looks like:

The mesh
The car textures
The car palette
The wheel textures

Wondering how I can help with this...maybe it's trying to look for the car mesh and is unable to find it? Or maybe these files are supposed to be in one chunk of data, i'm not too sure on this.
## Post #10
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2019-05-23T14:19:07+00:00
- Post Title: Ridge Racer 5 Textures

> Reply from Nega ↑Thu May 23, 2019 10:31 am at Thu May 23, 2019 10:31 am
>
> 
Thanks a lot episoder! This is exciting to see!

As for how I got this data, yeah, I got this through PCSX2. I was able to find the pointers in the game to see what data was being set up in the game when cars are loaded. I changed the offsets so they reflected on the file areas instead of having the game pointer offsets instead (originally was like C0XXXX or something like that)...though this could've introduced some issues?

Each car has 4 pointers it looks like:

The mesh
The car textures
The car palette
The wheel textures

Wondering how I can help with this...maybe it's trying to look for the car mesh and is unable to find it? Or maybe these files are supposed to be in one chunk of data, i'm not too sure on this.

alright. yeh. well... i dunno. it's possible for this stream to run parallel to the car being transformed. it should not rely on any data relation tho. i'm just not sure how to deal with this prim code. it should be intepreted somehow to skip the buffer. i'm thinking to brute force it with a binary search for 0x0000100E and then fiddle the command lists and data, but this is unreliable since the pattern is not really predictable to be just there. i usually don't code with lucky mechanics.

and i'm getting the iso rn. is there anything extractable on the disc? we'll see. 

edit1: nothing extractable in there. beyond improving my sunny beach skills with this monstrosity , i may attempt to hijack the renderer and try dump the textures from the gs memory. i mean the software renderer gets it done.

edit2: the ways of the code. somewhere in this mess is the beef.  the 4 megs frame and texture buffer is not readable, cause in ps2 block format. all below are renderstate, pallette, texture and geometry gs inputs you could hijack and dump. guesstimating by the size, i think the one i pointed at is the body texture. i'm not much of c# tho. i could not code a tiny thing in it. if you can, try it.
## Post #11
- Username: Nega
- Rank: beginner
- Number of posts: 27
- Joined date: Thu Sep 30, 2010 4:57 am
- Post datetime: 2019-05-27T20:27:29+00:00
- Post Title: Ridge Racer 5 Textures

Thanks for trying episoder, didn't think it was gonna be this tricky.

Sadly i'm not sure how to code, it kinda just flies over my head, hah.

I'm curious about what you used in that screen shot, is it what's being mentioned here: [https://wiki.pcsx2.net/PCSX2_Documentation/GSdx_Debug](https://wiki.pcsx2.net/PCSX2_Documentation/GSdx_Debug) ?
## Post #12
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2021-11-30T21:50:58+00:00
- Post Title: Ridge Racer 5 Textures

@Nega, have you released your tool for models anywhere?
I'm interesting in the models
## Post #13
- Username: viperzerofsx
- Rank: veteran
- Number of posts: 95
- Joined date: Thu May 27, 2010 12:07 pm
- Post datetime: 2022-11-17T19:23:28+00:00
- Post Title: Ridge Racer 5 Textures

Does the encryption method have any relation to tekken TT or any of the Ace Combat games?
