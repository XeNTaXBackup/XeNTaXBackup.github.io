## Post #1
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-01-03T18:57:11+00:00
- Post Title: GuildWars models

After going through[viewtopic.php?f=10&t=1645&start=195](http://forum.xentax.com/viewtopic.php?f=10&t=1645&start=195) I decided to try and have a go at  the ffna format.

I have been able to import some models:




by examining about 50 files in 010 editor and creating a template that seems to work for most files.
I am however completely new to this and it seems some files just act completely different and I can't figure it out on my own. (for example the 13097_ffna.raw included below)
If perhaps someone could shine some light on this (or help by reversing the .exe?)

I am also looking for a way to find specific meshes since they all have numbers in the .dat browser.
And a way to find their textures/animation files.

010 editor template example:

(I'm not used to c/c++, which you'll no doubt notice if you open up the template. I also didn't comment it entirely and it looks like a mess, but if you do take a look at it and have questions go ahead and ask them.)

I'm currently rewriting the template with my handwritten comments and trying to clean up the code itself.

currently this is what I've found out so far:

first 4 bytes = FFNA
byte = 02 = model
4 bytes= some sort of type identifier
4 bytes = byte amount
byte = 26 = start of file
7 bytes = unknown
4bytes seem to have an influence on the amount of meshes
4bytes = format type1 ?
4bytes = format type2 ?
20 bytes = unknowns that seem to interact with the bytes that follow the mesh identifiers? i've tried to get an algorythm from them in the template
2*4 bytes = scale
20 bytes = unknown (seems to only change when according to my "algorythm" there are zero meshes)
byte = amount of meshes (influenced if there's a 29/0C instead 08/09 in the dword described higher above)
8 bytes * amount of meshes (named "quads" in my template from before i knew what they were)
the amount of following bytes depends on the amount of meshes and the values of their bytes

after that come the facelists (in the template picture starting at the second group with black background)
the black bar itself is the amount of faces in mesh 
there are 3 values and they seem to add up if the values are different
--> value 1
if value1 differs from value2 --> value1 + 2
then
if value1 differs from value3 --> value1 + 2 +3

followed by 5*4bytes unknowns
red = faces --> seem to be in threes, still looking if in some files they are in fours
directly after start the vertices and rest
sometimes float1,2,3 are x,y,z, sometimes it's float 4,5,6
and if the format type 1 == F095B2D6 there are 4 extra bytes inserted after the first 3 floats

EDIT: for those who do not have a guildwars account, perhaps this can help [http://www.guildwars.com/support/gwtrial.php](http://www.guildwars.com/support/gwtrial.php)


 ffna.rar
(27.42 KiB) Downloaded 50 times
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-03T20:12:50+00:00
- Post Title: GuildWars models

Here's what I got out of the 130907 model.
The parser was written in python for noesis.

Unfortunately it's hardcoded cause I didn't look at the other files (just followed your notes lol)
Here's the header

```
byte (1, 2, ...)
int ? // seems to have decimal values 3000, 4000, ?
int ? // always a little smaller than filesize
int ? // 0x26

...

```



btw, do you have a working unpacker?
I downloaded an archive off the wiki but the exe's couldn't be extracted.
## Post #3
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-01-03T20:58:11+00:00
- Post Title: GuildWars models

I'll have a look at Noesis, I've already been cooking something up in python for blender anyways.

If by unpacker you mean to extract the ffna files out of the guildwars.dat, I used the tool posted [viewtopic.php?p=24493#p24493](http://forum.xentax.com/viewtopic.php?p=24493#p24493)
I'm not sure what you mean by exe's. If it's the game's main exe, you can download it from the official site and, iirc, you can just run it with the -image cmd and it'll download all the game's assets into the dat file.
You do need an account (trial account) to log in though.
[http://www.guildwars.com/support/downloadclient/](http://www.guildwars.com/support/downloadclient/)

My files are from the .dat from the 20th december or something and with each update the "filenames" change. I mostly look up the files by their type + filesize.
## Post #4
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-01-16T19:50:55+00:00
- Post Title: GuildWars models

Finally some time off, so bumping time.

Created a Noesis script and it loads a fair amount of meshes, not perfect yet though.
Any tips on how to 'clean up' my code are more than welcome.

I'm also still looking for help on how to find the files that contain the (link to) animations and textures and a way to figure out how to find the meshes I want. I was thinking using ollydbg but I have no only a little experience.

below the script + meshes it can load.
[temp.rar](https://xentaxbackup.github.io/file/4996_temp.rar)
## Post #5
- Username: Axolotl
- Rank: advanced
- Number of posts: 44
- Joined date: Sun Nov 07, 2010 7:52 am
- Post datetime: 2012-01-16T22:29:12+00:00
- Post Title: GuildWars models

Does your script can load creatures meshes?

It will be great if it will be possible to ipmort models from this game. Looked on screens, creatures model are realy impressive.
## Post #6
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-01-17T10:17:01+00:00
- Post Title: GuildWars models

I haven't encountered a monster file yet, the only creature parts I saw were faces, leggings, pelvis and hands.
The problem is all the model files aren't named, they only have numbers so I do not know what a file contains before (or if the current script even can) it's loaded.
## Post #7
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-01-21T15:20:26+00:00
- Post Title: GuildWars models

Tiny update:





Still having some trouble with multipart monsters.

In Noesis, how do I mirror the UV's in the Python script? I have to mirror them over the Y-axis (blender Y-axis) for them position correctly.
## Post #8
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-01-21T16:50:29+00:00
- Post Title: GuildWars models

this will mirror the uv's in the y axis.
rapi.rpgSetUVScaleBias(NoeVec3 ((1.0, -1.0, 1.0)), NoeVec3 ((1.0, 1.0, 1.0)))
## Post #9
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-01-21T17:34:29+00:00
- Post Title: GuildWars models

Thanks, I'll have a look at it, might have to rewrite the script since I'm not using the rapi module.
## Post #10
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-21T17:39:56+00:00
- Post Title: GuildWars models

Did you manually create NoeMesh objects and stuff?
You can just manually transform the vector.
## Post #11
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-01-21T18:07:08+00:00
- Post Title: GuildWars models

Yes I did, I feel stupid for not thinking about that.

first multipart monster:
## Post #12
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-21T19:20:58+00:00
- Post Title: GuildWars models

Nice. Are you exporting it from noesis and then importing into blender?

Now all we need is to figure out how to write a tool that will export data from noesis and into blender directly!
## Post #13
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-01-21T19:42:14+00:00
- Post Title: GuildWars models

Yeah, I initially started out with direct import into Blender.
If I have the time I might convert the script from Noesis to work for Blender and a maxscript as well. But that won't be untill the format is more or less figured out, there still are variables that suddenly behave differently especially when going towards larger files.
## Post #14
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-01-21T19:42:36+00:00
- Post Title: GuildWars models

there is a max script that does that from max to blender you could just copy that.
## Post #15
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-22T02:32:44+00:00
- Post Title: GuildWars models

Can you draft out an outline of the format?
The code up there is kind of hard to follow and not sure if you changed how it looks lol, particularly the getattr/setattr which I think is making things a little more complicated than it should be.

I was looking at it and it sort of looks like you have your header with a bunch of flags, followed by a list of meshes, where each mesh has a bunch of information and then finally followed by index buffer, vertices, normals and UV. And other stuff.

But it looks a little more complicated than that from your parser.
## Post #16
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-01-22T09:49:27+00:00
- Post Title: Re: GuildWars models

There are so many "if else if not then else " in the script format/script it's even hard for me to follow the code but i'll give it a shot.

Global overview of the file:


Header:


```
1 byte  = constant 02 for models
4 bytes = might be the difference between a model file and an animation file but i still have to look into that
4 bytes = INT slightly smaller than filesize
1 byte = always 26, end of header

```


Modifiers:


```
4 bytes = has an impact on how many meshes, usually if not 0800 or 09xx it's +2 meshes and weird behavior
4 bytes = TYPEA : defines global behavior on every part of the rest of the file
          -reduce meshamount
          -more dwords in the vertex list
          -behavior after/inbetween vertex lists
4 bytes = TYPEB : I haven't seen it influence anything (yet)
20 bytes = "modifiers" -> determine, along with the mesh modifiers( listed lower) how many bytes are in between meshmodifiers and facelist
8 bytes = double float : small range of constant floats, could be scaling values
20 bytes = unknown
1 byte = amount of "meshes"

```


Meshmodifiers:


```
meshamount * 8 bytes = i think global mesh info, it's mostly the last byte (#8) that influences anything in the file; here there are 2 "meshes"
next bytes untill end of image (usually terminated by "00 00 00 00") I have no clue what they do, probably some shadow settings or whatnot, way too complicated

```


Face-Vertex:


```
4 bytes = Int : amount of vertices
4 bytes = Int : defines the amount of dwords in 1 "vertex line","17" adds a "00 00 00 00" inbetween xyz and the normals
8 bytes = 2 * Int: add up to define part 1 after vertex list
4 bytes = Int: define part 2 after vertex list

```


After that the facelist immediately starts, followed by the vertex list:


```
depending what else is in there it usually is, I have seen it add up to 12*4 bytes, perhaps bones? still have to look into it
12 bytes = normals
8 bytes = UV

```


after the vertex list comes a chunk which i do not know what it does: (part 1 and 2 described above in light and dark gray)


immediately the face count + vertex count again if multiple meshes in file
## Post #17
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-22T18:31:14+00:00
- Post Title: Re: GuildWars models

Good work.
That outline is easier to understand than reading from the code.
Now I can look at the code and go "oh ya, that's what that flag is for and that's what the condition is about"

I think the more complicated part of the code is the getattr and setattr. You really don't need those if you're just setting/getting values. Just store them in a list.

Ya, conditionals...I don't really have a fixed way of describing them either.
## Post #18
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-01-22T19:34:31+00:00
- Post Title: Re: GuildWars models

I'm used to the get/setattr but seeing as how my code is one giant clusterfuck I'd try anything to make it readable.
I mainly use it when there are a variable amount of subclasses to be declared, like the meshmodifiers. When using Meshes[0][0], for example, I always forget what I'm actually looking up. Granted Meshes.mesh1._1 isn't that much clearer.

I'm still looking at some variables that behave oddly and I'll start rewriting/cleaning up the code after my next exam.
## Post #19
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-22T20:11:52+00:00
- Post Title: Re: GuildWars models

I usually don't use classes like structs (it looks like that's how they're being used). I just toss stuff in lists or dicts and grab them later. That's what they're for anyways lol

Here's my attempt at reproducing the code (based on what you've written and uploaded so far)
But I'm using the rpg interface so a lot of things require less code to do.

Only handles the cases where meshamounts == 1
For vertex parsing, I only checked one variable (faces.unknown2, I called it vertexType)

Didn't feel like continuing cause you most likely figured out more of those odd conditions.
[fmt_GuildWars_raw.7z](https://xentaxbackup.github.io/file/5007_fmt_GuildWars_raw.7z)
## Post #20
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-02-05T22:54:41+00:00
- Post Title: Re: GuildWars models

I was rewriting the script while I noticed something weird

> print(self.inFile.tell())
>
> self.inFile.read('hihc')
>
> print(self.inFile.tell())
gives me 105 -> 116

> print(self.inFile.tell())
>
> self.inFile.read('ihhc')
>
> print(self.inFile.tell())

gives me 105->114 as I expected the code above to do as well.
Is this a bug or intended? I don't need the format to be in that order necessarily, but it does help me figure out how/where to edit when making format adjustments.
## Post #21
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-06T00:36:44+00:00
- Post Title: Re: GuildWars models

That is a known issue with the struct module. First time I ran into it, had no clue what was going on and spent about an hour just trying to figure out why I'm reading 22 bytes rather than (what I thought would be) 14   

[http://docs.python.org/library/struct.html#examples](http://docs.python.org/library/struct.html#examples)

```
struct.calcsize('ih')
6
struct.calcsize('hi')
8
```


Because of this I typically don't mix formats.
## Post #22
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-02-06T14:34:39+00:00
- Post Title: Re: GuildWars models

I hope this one is easier to follow. Script attached below.

I also used the extractor posted on the wiki which netted me 89k files.
after sorting them I came up with 10 'filetypes" and filetype "a00f0000" had 3020 "formattypes". So turns out i'm not nearly done going through them all.

I also noticed theformatSUBtypes 0C00 and 2900 follow what seems to be a pretty fixed format, but they don't seem to contain any vertex data.

They might be the bone files for the models but not sure yet as I don't really know what the boneinfo should look like.
[GW_ffna.rar](https://xentaxbackup.github.io/file/5038_GW_ffna.rar)
## Post #23
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-06T22:25:09+00:00
- Post Title: Re: GuildWars models

Ya I think it's a lot easier to follow now.
