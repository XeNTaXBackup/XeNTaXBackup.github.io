## Post #1
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2015-01-03T14:35:11+00:00
- Post Title: rare (xbox) - grabbed by the ghoulies, conker

i'm exploring the 3d models used by rare, starting with grabbed by the ghoulies   

models are named 'aid_model_ghoulies_' but reference other resources in a bnl container - such as textures and pools of floats

and the model files are horrible:

```
footer offset (absolute)
count

footer (for header->count)
chunk type
chunk offset (absolute)

chunks:
varying structures  - and there are ~20 chunk types

chunk ids
0: main model definition
1: ??
2: initial pose ?? 
5: ??
7: texture headers
9: flags ??

the main model info is further split into chunks. named this time, but also varying structures :(

```


i've attached the format (010 binary template) which parses most of the structures, but i'm stuck with describing the 3d data.

dumping one of the float pools shows it is definitely the vertex points, and some of the ushort pools in the model data->chunk 0->ndPushBuffer data are the triangles:


(i think i'm using the wrong triangle mode here)

can anyone help with the skeleton?  
[GbtgModelsV3.zip](https://xentaxbackup.github.io/file/8423_GbtgModelsV3.zip)
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2015-01-03T14:36:42+00:00
- Post Title: rare (xbox) - grabbed by the ghoulies, conker

other references

dxt texture data


render:
## Post #3
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2015-01-03T15:32:05+00:00
- Post Title: rare (xbox) - grabbed by the ghoulies, conker

I might jump on this, thanks for the sample of the format
## Post #4
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2015-01-03T21:44:16+00:00
- Post Title: rare (xbox) - grabbed by the ghoulies, conker

I think it's using some technique but I'm not sure, I can get this when shifting the array and building a second mesh, and then once more shifting the array and building yet another mesh, there's a lot of things wrong like the extruding faces, it's definitely not right, but it might help find the right path, hmm I'll look into it more



edit: (or reading it as a quad and then doing a shift of 2 in the face array has the same effect)
## Post #5
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2015-01-03T23:48:10+00:00
- Post Title: rare (xbox) - grabbed by the ghoulies, conker

thanks for your update   

i haven't made a lot of progress on the data pool.
the 26 textures total 251,392 bytes, and start at offset 358336 - which actually exceeds the data sample - so i cut it short...

before that are several pools of data, and i found some references to them after the ndSkeleton chunk is read

add this to the ND_CHUNK struct:

```

            uint un1, un2;
            uint res_hdrs; // incorrect count? 
            uint pool[7];

            struct res_head
            {
                uint a, b, c, d;
                uint offset, size;
                Printf("%u, %u\n", d, offset);
            } res[res_hdrs +1] <optimize=false>;


```


this highlights several pools -

> 0, 39240 - vertex data - (3270 * x+y+z floats)
>
> 39240, 26160 - odd rounded floating point numbers (24, 33, 30) - no idea what this is
>
> 65400, 26160 - another float pool. values >= 0.0f and <= 1.0f so perhaps uvs
>
> 91560, 39240
>
> 130800, 26160
>
> 0, 0
>
> 0, 0
>
> 0, 0
>
> 156960, 13080 - entire table of -1 bytes...

i had limited success with triangle_strip with the first ndPushBuffer pool



this doesn't work for other pools though
## Post #6
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2015-01-04T15:26:36+00:00
- Post Title: rare (xbox) - grabbed by the ghoulies, conker

Ok so using the technique I was using (reading in as quads and then shifting the array by four)

I firstly read every push buffer into a face array, I noticed that at some point in the array it looks like its starting over [00 00, 00 00, 00 01] so I stopped reading it up to there. I only build the mesh straight from the array after its populated (not one push buffer at a time)

Still not quite there, after building there are still stray faces, so I think there must be parts at which I have stop reading the face array, and then start again (separate objects?) But here's the outcome.

Once reading in the two objects (array, then array shifted by 2) lot of stray faces, flipped normals



After cleaning up the stray faces and unifying the normals for the two objects


Then after combining the two objects and manually flipping a lot(but not all, became too tedious :p) of the face normals


I think we're on the right track, but still need to look into it more.
## Post #7
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2015-01-21T23:43:58+00:00
- Post Title: rare (xbox) - grabbed by the ghoulies, conker

bump in hope this catches some attention   

i can pm model samples from gbtg
## Post #8
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2015-02-10T17:25:20+00:00
- Post Title: rare (xbox) - grabbed by the ghoulies, conker

```

For each model we have 2 files:
1.file info - with name "aid_model_ghoulies_actor_" + model name
2.file data - with name model name + "_resource_pool"

and about 1.
this file has sections which are joint together.
 - each section have header:	offset to section name int32+64
								chunk int16
								unk int16
								offset1 int32
								offset2 int32
								offset3 int32
								offset4 to next section int32+64 - if 0 than stop make sections joint
								unk int32
								unk int32
								offset5 int32
								counter int32
	example:							
		section with chunk 21 joints with section 18	
		section with chunk 18 joints with 11 and 20	
		section with chunk 17 joints with 21	
		section with chunk 12 joints with 17

and about 2.
	- access to this data has only section 19 - ndVertexBuffer
		go to offset5+64 in 1.file
		stream count=counter
		we have stream types:
			2316 - vertex position
			....
			....
			....
			
about faces:
	- access to this data has section 20 and if offset5 is eqal 1 than we have tristrips else we have quads.
about meshes:
	- access to this data have sections 19 and 23
		if section is 23 than all next section 19 joint in one mesh 


```


Updated 2015-02-11
Here is importer for textured models from Grabbed_By_The_Ghoulies [XBOX] .
It requires Blender249 and Python26.
How use:
1.unpack importer
2.run Blender249.blend
3.in Blender Text Window press alt+p and select:
- bnl - for unpacking archive
- info (files with "aid_model" in name)- for import rigged, static or backrounds meshes with textures (skinweights too, but bad bone map).
Importer is not perfect and requires a lot of work to get all models.

for testing:  [https://mega.co.nz/#!z9VCTTLR!p0Ps-IK4s ... K3iVe1vRBo](https://mega.co.nz/#!z9VCTTLR!p0Ps-IK4s2kVHQOpDeWX-WEHygfV3yA1rK3iVe1vRBo)
[Blender249[Rare][XBOX][2015-02-11].7z](https://xentaxbackup.github.io/file/8641_Blender249[Rare][XBOX][2015-02-11].7z)
## Post #9
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2015-02-10T21:29:12+00:00
- Post Title: rare (xbox) - grabbed by the ghoulies, conker

i cannot thank you enough Szkaradek123 - this is fantastic - thank you so much   

edit

this is amazing work!!




the textures are even nicer:


----------------




i want to say that my template didn't really come close to what you archived. thanks again.


the model data for grabbed by the ghoulies is stored in *.bnl files - i'm working on a tool to automate this.
for conker - the archive files are stored in *.caff files. i've reversed the checksum hash but the algorithm is still unknown

sources: https://gist.github.com/x1nixmzeng/c55c248c384bf1c9df2a
## Post #10
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2015-06-20T21:41:15+00:00
- Post Title: rare (xbox) - grabbed by the ghoulies, conker

'rare replay' has just been announced for the xbox one and contains all their old games!!

[http://www.xbox.com/en-US/games/rare-replay](http://www.xbox.com/en-US/games/rare-replay)
## Post #11
- Username: SubDrag
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Aug 23, 2015 8:49 pm
- Post datetime: 2015-08-23T14:25:53+00:00
- Post Title: rare (xbox) - grabbed by the ghoulies, conker

I am interested in this!  Is there any comprehensive documentation on the format, what you guys figured out, or just the python importer?  This is a fantastic tool.  I wonder what leftovers are in here...

Also any way to automate ripping them all?

Too bad test_dialogs.bnl doesn't load.
## Post #12
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2015-09-02T21:09:11+00:00
- Post Title: rare (xbox) - grabbed by the ghoulies, conker

> Reply from SubDrag
>
> I am interested in this!  Is there any comprehensive documentation on the format, what you guys figured out, or just the python importer?  This is a fantastic tool.  I wonder what leftovers are in here...

Also any way to automate ripping them all?

Too bad test_dialogs.bnl doesn't load.

luckily test_dialogs does not contain any meshes 

you could write a script for blender to automatically convert them - although most of the textures need fixing up manually anyway (some uvs are broken in places)

there are plenty of leftovers though. if you're interested i have written tools for most of the file formats (exception animations......)
## Post #13
- Username: SubDrag
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Aug 23, 2015 8:49 pm
- Post datetime: 2015-09-06T14:13:19+00:00
- Post Title: rare (xbox) - grabbed by the ghoulies, conker

Very interested in this, can you post your findings/tools!   I'd love to help, or at least, see them 

> there are plenty of leftovers though. if you're interested i have written tools for most of the file formats (exception animations......)
## Post #14
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2015-09-11T22:58:36+00:00
- Post Title: rare (xbox) - grabbed by the ghoulies, conker

> Reply from SubDrag
>
> Very interested in this, can you post your findings/tools!   I'd love to help, or at least, see them

k. for starters here are the known filenames i know of: [https://gist.github.com/x1nixmzeng/1195c80d2c551fae5b7d](https://gist.github.com/x1nixmzeng/1195c80d2c551fae5b7d)

rough has implementation:

```
{
  unsigned int hash = 0;

  // Skip "aid_" prefix
  str += 4;
  for (; *str; ++str)
  {
    hash = 16 * hash + (*str & 0xDF);

    unsigned int hiBit = hash & 0xF0000000;

    if (hiBit) {
      hash ^= hiBit | (hiBit >> 24);
    }
  }

  return hash;
}

```


the hash is pretty terrible with lots of collisions
## Post #15
- Username: SubDrag
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Aug 23, 2015 8:49 pm
- Post datetime: 2015-09-12T00:07:41+00:00
- Post Title: rare (xbox) - grabbed by the ghoulies, conker

That's certainly a useful mapping.  Do you have a simple text ripper, and a list of some findings?  They seem to for some reason, have 00s in there between characters. Not sure if more special than that, probably some special characters in there.  And do we know format of sound and movies?
## Post #16
- Username: WareWolff
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Aug 26, 2014 6:53 pm
- Post datetime: 2015-10-13T11:55:38+00:00
- Post Title: Re: rare (xbox) - grabbed by the ghoulies, conker

why is the only model in the files the Cook? i'm trying to find Cooper's model but the only models i find is the Cook and some of the Sequence models, i can't find his files? any ideas, i am able to import them but was just looking for his specifically
## Post #17
- Username: SubDrag
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Aug 23, 2015 8:49 pm
- Post datetime: 2016-05-15T21:20:27+00:00
- Post Title: Re: rare (xbox) - grabbed by the ghoulies, conker

Can you post on all the unused stuff you found? I'm still hoping there are unused maps and characters.
## Post #18
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2016-09-10T19:25:09+00:00
- Post Title: Re: rare (xbox) - grabbed by the ghoulies, conker

> Reply from WareWolff
>
> why is the only model in the files the Cook? i'm trying to find Cooper's model but the only models i find is the Cook and some of the Sequence models, i can't find his files? any ideas, i am able to import them but was just looking for his specifically

Cooper is in ghoulies_actor_player_boy.bnl. the importer script still needs some work to support other models - and hooking up skeletons to the armature - as his skeleton isn't hooked up!
## Post #19
- Username: qs12
- Rank: veteran
- Number of posts: 92
- Joined date: Sat Sep 21, 2019 7:55 am
- Post datetime: 2021-01-20T06:21:09+00:00
- Post Title: Re: rare (xbox) - grabbed by the ghoulies, conker

> Reply from Szkaradek123 ↑Wed Feb 11, 2015 1:25 am at Wed Feb 11, 2015 1:25 am
>
> 
Code: Select allAbout rare models:

For each model we have 2 files:
1.file info - with name "aid_model_ghoulies_actor_" + model name
2.file data - with name model name + "_resource_pool"

and about 1.
this file has sections which are joint together.
 - each section have header:	offset to section name int32+64
								chunk int16
								unk int16
								offset1 int32
								offset2 int32
								offset3 int32
								offset4 to next section int32+64 - if 0 than stop make sections joint
								unk int32
								unk int32
								offset5 int32
								counter int32
	example:							
		section with chunk 21 joints with section 18	
		section with chunk 18 joints with 11 and 20	
		section with chunk 17 joints with 21	
		section with chunk 12 joints with 17

and about 2.
	- access to this data has only section 19 - ndVertexBuffer
		go to offset5+64 in 1.file
		stream count=counter
		we have stream types:
			2316 - vertex position
			....
			....
			....
			
about faces:
	- access to this data has section 20 and if offset5 is eqal 1 than we have tristrips else we have quads.
about meshes:
	- access to this data have sections 19 and 23
		if section is 23 than all next section 19 joint in one mesh 



Updated 2015-02-11
Here is importer for textured models from Grabbed_By_The_Ghoulies [XBOX] .
It requires Blender249 and Python26.
How use:
1.unpack importer
2.run Blender249.blend
3.in Blender Text Window press alt+p and select:
- bnl - for unpacking archive
- info (files with "aid_model" in name)- for import rigged, static or backrounds meshes with textures (skinweights too, but bad bone map).
Importer is not perfect and requires a lot of work to get all models.

for testing:  https://mega.co.nz/#!z9VCTTLR!p0Ps-IK4s ... K3iVe1vRBo

the script didn't work
