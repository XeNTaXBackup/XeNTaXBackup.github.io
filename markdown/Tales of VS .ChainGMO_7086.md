## Post #1
- Username: ShinKun
- Rank: veteran
- Number of posts: 132
- Joined date: Sun Aug 08, 2010 10:02 pm
- Post datetime: 2011-07-31T00:04:26+00:00
- Post Title: Tales of VS .Chain/GMO

Thanks to fatduck, I was able to extract the files from the .mgz
[viewtopic.php?p=56417#p56417](http://forum.xentax.com/viewtopic.php?p=56417#p56417)

[http://dl.dropbox.com/u/32409323/Rips/TOVCHain.7z](http://dl.dropbox.com/u/32409323/Rips/TOVCHain.7z)
These might be the model files or another compressed archive.

They are GMO files inside them. I used GitMo.

GitMO to rip them. The load fine in Noesis  (3.33), but the mesh is meshed up.


 It looks like this in Max.

But, the mesh is messed up. Is there any to fix this?
[http://dl.dropbox.com/u/32409323/Rips/TOVGMO.7z](http://dl.dropbox.com/u/32409323/Rips/TOVGMO.7z)
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-31T00:29:06+00:00
- Post Title: Tales of VS .Chain/GMO

Probably can't do much about it without modifying the GMO parser code.
Someone else had the same problem with GMO files from another game. I think he said the bones were not being done correctly.
## Post #3
- Username: ShinKun
- Rank: veteran
- Number of posts: 132
- Joined date: Sun Aug 08, 2010 10:02 pm
- Post datetime: 2011-07-31T00:44:20+00:00
- Post Title: Tales of VS .Chain/GMO

Is there a way to export without the bones?
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-31T01:02:10+00:00
- Post Title: Tales of VS .Chain/GMO

Ya, I think noesis has that as one of the options. Scroll through the list.
I don't know if that's the problem though.
## Post #5
- Username: ShinKun
- Rank: veteran
- Number of posts: 132
- Joined date: Sun Aug 08, 2010 10:02 pm
- Post datetime: 2011-07-31T01:08:30+00:00
- Post Title: Tales of VS .Chain/GMO

When I switch subtype models, it loads fine.

[http://dl.dropbox.com/u/32409323/Images/Nos001.png](http://dl.dropbox.com/u/32409323/Images/Nos001.png)

Yea, it's the bones.  But, the mesh still needs to fix some how.

[http://dl.dropbox.com/u/32409323/Images/MeshFail003.png](http://dl.dropbox.com/u/32409323/Images/MeshFail003.png)
## Post #6
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2011-07-31T03:35:57+00:00
- Post Title: Tales of VS .Chain/GMO

There is nothing wrong with the bones. (obviously, anims play fine too) There is nothing wrong with most of the model either. On c001_00_00_00000030.gmo, go to Data viewer->Meshes->Mesh 3, double-click Skip render, and there's your evidence. Mesh 3 is probably geometry that's expected to be transformed differently at runtime or something, or a LOD morph target, who knows. Doesn't seem to me that it's got any place on the model at all normally.
[](http://imageshack.us/photo/my-images/12/somemodel.jpg/)
## Post #7
- Username: ShinKun
- Rank: veteran
- Number of posts: 132
- Joined date: Sun Aug 08, 2010 10:02 pm
- Post datetime: 2011-07-31T03:42:37+00:00
- Post Title: Tales of VS .Chain/GMO

Awesome, I'll try that out right now.

I noticed a some of the gmo files crashes Noesis, like "c15_00_00_00000030.gmo" Sort it by size, and it's about 965kb.

So, it still exports with that nasty mesh.
[http://dl.dropbox.com/u/32409323/Images ... esh001.png](http://dl.dropbox.com/u/32409323/Images/NastyMesh001.png)
## Post #8
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2011-07-31T06:21:36+00:00
- Post Title: Tales of VS .Chain/GMO

I don't have that file, only the ones you uploaded. And yes, if you export it, you would have to delete the offending mesh(es) in Max/Maya/whatever.
## Post #9
- Username: rexil
- Rank: veteran
- Number of posts: 124
- Joined date: Tue Mar 15, 2011 10:14 pm
- Post datetime: 2011-07-31T15:46:59+00:00
- Post Title: Tales of VS .Chain/GMO

The contents of this post was deleted because of possible forum rules violation.
## Post #10
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2011-07-31T20:48:26+00:00
- Post Title: Tales of VS .Chain/GMO

Thanks. It was a crash from the line primitives. New release up to fix it. This release also has support to directly extract the .mgz files, with all of their contents. (they contain more than just GMO files)
## Post #11
- Username: ShinKun
- Rank: veteran
- Number of posts: 132
- Joined date: Sun Aug 08, 2010 10:02 pm
- Post datetime: 2011-07-31T21:52:25+00:00
- Post Title: Tales of VS .Chain/GMO

The offending meshes is tied to the same channels map as the some of the polygons on the model. If you export the with the bones, edit it in Max and try to remove the offending mesh,  messes up the bones placement. So, would it be possible to add an option for it not to render mesh that has "skip render 1"
## Post #12
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2011-07-31T22:34:13+00:00
- Post Title: Tales of VS .Chain/GMO

> Reply from ShinKun
>
> The offending meshes is tied to the same channels map as the some of the polygons on the model. If you export the with the bones, edit it in Max and try to remove the offending mesh,  messes up the bones placement. So, would it be possible to add an option for it not to render mesh that has "skip render 1"
That's not true. Unless your Max importer is screwing up or you're exporting to a format that doesn't support multiple meshes. COLLADA with OpenCOLLADA as the importer is usually best for preserving everything.

I've also noticed a trend with people exporting PSK a lot lately, apparently someone made some Noesis tutorial with that as the export target. That was a bad idea. PSK kind of sucks as a format and doesn't preserve a number of data types (most notably vertex normals, they have to be approximated with smoothing groups), and the PSK importers I know of for Max all have significant issues. If you're going to make a tutorial, you should use COLLADA as an example.

But it's a non-issue in your case if you're using the new Noesis release, the screwed up meshes were also line primitives. (ps- you're welcome)
## Post #13
- Username: rexil
- Rank: veteran
- Number of posts: 124
- Joined date: Tue Mar 15, 2011 10:14 pm
- Post datetime: 2011-07-31T22:59:32+00:00
- Post Title: Tales of VS .Chain/GMO

Thank you MrAdults you not just fixed the error but made things better. Thank you very much.
## Post #14
- Username: ShinKun
- Rank: veteran
- Number of posts: 132
- Joined date: Sun Aug 08, 2010 10:02 pm
- Post datetime: 2011-08-01T01:41:15+00:00
- Post Title: Tales of VS .Chain/GMO

Just awesome, a part from some of the models missing, it's fine. That can be added in a 3D Editor.

Would you mind adding a another support, if you can?
.DAT
->.CAB
-->.BIN
-->.BLD
[http://dl.dropbox.com/u/32409323/Rips/T ... %281%29.7z](http://dl.dropbox.com/u/32409323/Rips/TOPX_DAT_BIN_BLD/e001%281%29.7z)

The .dat has a FPS4 header, which FPS4Dumpe can dump.
Then there's a cab file, which any windows, mac, etc tool and uncompressed.
The .BIN, I'm think this the cell data, like the [NCER](http://llref.emutalk.net/docs/?file=xml/ncer.xml) files in NDS games.
The .BLD is the graphic and palette. You can view it TitledGGD, but piece those together would be nearly impossible, or at least very time consuming.
