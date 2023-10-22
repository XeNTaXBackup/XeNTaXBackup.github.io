## Post #1
- Username: songokou
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Nov 30, 2012 10:37 pm
- Post datetime: 2012-12-01T16:57:44+00:00
- Post Title: Sonic 2006 .XNO Model Format

--This is for the game "SONIC THE HEDGEHOG" (2006) for XBOX 360 and PS3--

This is going to be a theoretical topic for insight, so understand that I don't expect too much from anyone.
To the better bit of my knowledge, chrrox created the converter which imports the (.XNO) models into 3DS MAX.

So I'm just trying to gather information about these files, and possibly .xnm (animation) and .xnv files.

So from what I know there are apparently no tools out there to edit them as .xno files that can be re-inserted back into the game. I think they may be related to DirectX .x models. There are also .fxo (shaders) in the game while .fx is a DirectX shader. Maybe they are pre-compiled?

When opening the .xno files in a hex editor, the first 4 bytes are always NXIF shortly followed by NXTL, perhaps those are headers for the program which built them?

So getting on to the reason why I bring all of this up... Is that I'm trying to find a way to add Nvidia normal maps to specific models in the game. ([https://developer.nvidia.com/nvidia-tex ... -photoshop](https://developer.nvidia.com/nvidia-texture-tools-adobe-photoshop))

They are already present in the character models and used to be present in many other models in beta versions of the game... now I understand that adding these would change the performance of the game, but it would make it a hell of a lot prettier and if balanced properly, shouldn't hurt the performance badly.

In the hex editor, I found the list for the .dds texture files, and before them there is a value which sets the number of textures to look for, and before that there is some other data that either defines the length or position of each texture file (I'm guessing).

The Red highlight is NXIF and NXTL that I mentioned earlier, the blue highlight is the value that defines how many texture files to look for. Hex value: 26, decimal: 38. There are 38 textures. The yellow highlight is 38 rows long, so I imagine they have something to do with the file names.



I imagine that even if I do manage to properly get the file to allow an extra texture, it would have to be defined somewhere as to what type of texture it is and the parameters for how it is applied.

If I were to do it, for example, the first texture would have another in front of it titled "twn_a1swalk1_dfnw_b.dds". changing sp to nw same as how the Nvidia normal map textures are named for the character models. That texture would have the same parameters as the first one, but would need to be defined as a normal map texture.

I would imagine that chrrox would be the best person to ask since he wrote the model converter to get them in 3DS MAX... but I figure it is better to throw this out in the open, hopefully he will have a look at this and give a little input.

Thanks for reading.
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-12-01T19:43:48+00:00
- Post Title: Sonic 2006 .XNO Model Format

Send some samples.
## Post #3
- Username: songokou
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Nov 30, 2012 10:37 pm
- Post datetime: 2012-12-02T18:34:37+00:00
- Post Title: Sonic 2006 .XNO Model Format

> Reply from finale00
>
> Send some samples.

Sent.
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-12-02T23:23:12+00:00
- Post Title: Sonic 2006 .XNO Model Format

The format is chunk-based with 16-byte alignment.
Each chunk has the format

```
   char[4] chunkType
   uint32 chunkSize
   byte[] data...
}

```


I would imagine all of them start with NXIF, and end with NEND.
Judging from the names referenced in each chunk, you have chunks like

NXTL - textures?
NXEF - effects
NXNN - ?
NXOB - object data (verts, faces, ...)
NOF0 - ?
NFN0 - ?

Lots of fields that I don't know what they are for though.
