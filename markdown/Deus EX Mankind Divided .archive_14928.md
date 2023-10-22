## Post #1
- Username: MiRiKan
- Rank: advanced
- Number of posts: 67
- Joined date: Fri Jul 25, 2014 1:28 pm
- Post datetime: 2016-08-24T07:58:29+00:00
- Post Title: Deus EX: Mankind Divided .archive

They look contains many files of it.
And looking little big complex.

Here is some sample file: [https://www.sendspace.com/file/bjfhu8](https://www.sendspace.com/file/bjfhu8)
I'm checking it now... But, Is there anyone who can figure it out?

```
uint useless; //Nothing
uint files;
uint unk;
Unit id; //Not confirmed
uint unk;
for(int i = 0; i < files; i++) {
//DATA with 4 chars;
//BILR, BIN1, FSB5, SBSF, etc
//All data are headed to 
//char NAME[4];
//uint unk;
//uint unk;
//uint af;
//uint id;
//uint unk;
}
```
## Post #2
- Username: aspadm
- Rank: advanced
- Number of posts: 52
- Joined date: Thu Nov 26, 2015 3:43 am
- Post datetime: 2016-09-09T18:32:22+00:00
- Post Title: Deus EX: Mankind Divided .archive

> Reply from MiRiKan
>
> 
Here is some sample file: https://www.sendspace.com/file/bjfhu8
I'm checking it now... But, Is there anyone who can figure it out?
There [http://aluigi.altervista.org/bms/deus_e ... ivided.bms](http://aluigi.altervista.org/bms/deus_ex_mankind_divided.bms) new QuickBMS script by Luigi Auriemma.
I try to unpack - you can see results there: [https://yadi.sk/d/XrdZqQcauxCKH](https://yadi.sk/d/XrdZqQcauxCKH)

There are 8 .bil files and 13 .sbs(about 8-9MB each).
## Post #3
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2016-10-02T21:49:30+00:00
- Post Title: Deus EX: Mankind Divided .archive

Here's version 1.0 of my Deus Ex:MD Texture converter. (Based on Hitman 2016 converter, as Deus Ex uses a modified Glacier Engine, same engine Hitman uses).

Textures are in *.vap files.  Not all *.vap files are textures, and it will skip over non-texture *vap files.

If you find it reports any formats not supported, or skips a *.vap that is actually a texture, please let me know with a sample.
[DeusExMDv100.rar](https://xentaxbackup.github.io/file/11758_DeusExMDv100.rar)
## Post #4
- Username: Frozik
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Jun 22, 2010 1:27 am
- Post datetime: 2016-10-03T17:17:47+00:00
- Post Title: Deus EX: Mankind Divided .archive

And what about 3D models? Is there any way to extract them?
## Post #5
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2016-10-03T20:43:04+00:00
- Post Title: Deus EX: Mankind Divided .archive

> Reply from Frozik
>
> And what about 3D models? Is there any way to extract them?

I'm working on that, will be a bit. 

As with textures, it shares some similarity to Hitman 2016. So i'm working on Hitman atm, and will then convert that work for Deus Ex. 
Deus Ex is harder to work with, as we don't have a nice folder tree of file types like we have with Hitman. it's hard to find the different file types.
## Post #6
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2016-12-26T01:02:07+00:00
- Post Title: Deus EX: Mankind Divided .archive

Ok, here's the initial release of my Deus Ex:MD model importer for Blender.

This so far works on models I've found, but I'm sure there's probably some It doesn't work on. So let me know what you find. 

The importer is for Blender 2.63 and above, and if you need to know how to install, see my previous tutorial here: 
[viewtopic.php?p=103131#p103131](http://forum.xentax.com/viewtopic.php?p=103131#p103131)

Enjoy.

New version below.
## Post #7
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2016-12-26T01:02:50+00:00
- Post Title: Deus EX: Mankind Divided .archive

-------------------------------------------------------------------------------------------------------

Bonus: because the QuickBMS script doesn't really name files well, it's very hard to tell what is a model and what isn't. So I have created a search tool that will scan files and create a list of name for those files that the contents seem very likely to be models.



Using it is pretty easy, just point the Search Folder at where you have extracted the files, and Press "Search".  You can double click a file to open it in 010 Editor (if you have that), or you can copy entries to clipboard for pasting elsewhere.  Can sort by file path or file size. Requires .Net 4.5

Enjoy
[DirSearch.zip](https://xentaxbackup.github.io/file/12129_DirSearch.zip)
## Post #8
- Username: U2LN
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Dec 11, 2015 1:53 pm
- Post datetime: 2016-12-28T08:26:59+00:00
- Post Title: Deus EX: Mankind Divided .archive

Forgive my ignorance, but how do you open the .bil files?
## Post #9
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2016-12-29T00:14:10+00:00
- Post Title: Deus EX: Mankind Divided .archive

> Reply from U2LN
>
> Forgive my ignorance, but how do you open the .bil files?

Not sure there is a way. Those seem to contain some kind of text, so I haven't really looked at them. I am mostly interested in textures and models.
## Post #10
- Username: U2LN
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Dec 11, 2015 1:53 pm
- Post datetime: 2016-12-29T03:18:32+00:00
- Post Title: Deus EX: Mankind Divided .archive

> Reply from volfin
>
> U2LN wrote:Forgive my ignorance, but how do you open the .bil files?

Not sure there is a way. Those seem to contain some kind of text, so I haven't really looked at them. I am mostly interested in textures and models.
Oh I thought the models and textures were located in the .bil files. My bad.
## Post #11
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-03T23:59:30+00:00
- Post Title: Deus EX: Mankind Divided .archive

New version of the blender plugin here.  I vastly improved the UV detection, and models that have two sets of UV coordinates, both are imported to blender.  I expect there are still a few UV formats I've not found yet, so if you see corrupted UVs, let me know.

Enjoy.

Edit:  new version here: [viewtopic.php?p=125940#p125940](http://forum.xentax.com/viewtopic.php?p=125940#p125940)
## Post #12
- Username: dantesai
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Feb 09, 2014 10:42 am
- Post datetime: 2017-01-05T10:28:01+00:00
- Post Title: Deus EX: Mankind Divided .archive

great work
## Post #13
- Username: FozeSt
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Jul 26, 2015 4:20 pm
- Post datetime: 2017-01-05T18:17:33+00:00
- Post Title: Deus EX: Mankind Divided .archive

Can not unpack Game.layer.1.all.archive
This is a screenshot of the QiuckBMS
[XOgSkzj8qYE.jpg](https://xentaxbackup.github.io/file/12158_XOgSkzj8qYE.jpg)
## Post #14
- Username: U2LN
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Dec 11, 2015 1:53 pm
- Post datetime: 2017-01-08T07:28:41+00:00
- Post Title: Deus EX: Mankind Divided .archive

Hey I don't have this game, but if y'all come across Alex Vega or Adam Jensen, can you let me know?
## Post #15
- Username: aspadm
- Rank: advanced
- Number of posts: 52
- Joined date: Thu Nov 26, 2015 3:43 am
- Post datetime: 2017-01-08T17:06:26+00:00
- Post Title: Deus EX: Mankind Divided .archive

> Reply from U2LN
>
> Hey I don't have this game, but if y'all come across Alex Vega or Adam Jensen, can you let me know?
I found only his robo-legs  

There small script to import big portion of 3d models. I already look to 20 of 80 thousands .dat files, what I unpack
You must install Volfin's addon to use it

```

k = 1 # Number portion of files
ksize = 1000 # Size of portion (files)
dirname = "C:/your_path" # Path to .dat files

z = os.listdir(dirname)
for i in range((k-1)*ksize,k*ksize):
    try:
        path = dirname + "/" + z[i]
        print(path)
        try:
            import_DeusExMD.import_DeusExMD(path, bpy.context,True,True,False,True,1.0)
        except:
            pass
    except:
        pass
```
## Post #16
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-08T17:32:26+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

> Reply from aspadm
>
> U2LN wrote:Hey I don't have this game, but if y'all come across Alex Vega or Adam Jensen, can you let me know?
I found only his robo-legs  

There small script to import big portion of 3d models. I already look to 20 of 80 thousands .dat files, what I unpack
You must install Volfin's addon to use it
Code: Select allimport os, sys, bpy, import_DeusExMD

k = 1 # Number portion of files
ksize = 1000 # Size of portion (files)
dirname = "C:/your_path" # Path to .dat files

z = os.listdir(dirname)
for i in range((k-1)*ksize,k*ksize):
    try:
        path = dirname + "/" + z[i]
        print(path)
        try:
            import_DeusExMD.import_DeusExMD(path, bpy.context,True,True,False,True,1.0)
        except:
            pass
    except:
        pass

yeah not a bad idea under the circumstances. I wish we had filenames so we knew what things were.
## Post #17
- Username: aspadm
- Rank: advanced
- Number of posts: 52
- Joined date: Thu Nov 26, 2015 3:43 am
- Post datetime: 2017-01-08T18:04:16+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

> Reply from volfin
>
> yeah not a bad idea under the circumstances. I wish we had filenames so we knew what things were.
Previos game was also without "human-readable" names. It's game engine's specific...
I think that only way to get correct names is to create a database for all files... But it's very bad way
P.S. Many models that I explore was identical - police suits, as examle - some of them in every 1-1.5 thousand of files.
## Post #18
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2017-01-08T18:43:45+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

This script recursive scan folders, auto import dat files and export to fbx 

```
import bpy
import fnmatch


folder_ = "E:\\Program Files (x86)\\Steam\\steamapps\\common\\Deus Ex Mankind Divided\\DLC\\runtime\\dlc1\\CF14A45978D4D15C17263FACED58B540.pc_resourcelib\\"
print(folder_)

files_ = []
root = 'E:\\Program Files (x86)\\Steam\\steamapps\\common\\Deus Ex Mankind Divided\\DLC\\runtime\\555\\'
pattern = '*.dat'
for folder, subdirs, files in os.walk(root):
	for filename in fnmatch.filter(files, pattern): 
		fullname = os.path.join(folder, filename)
		files_.append(fullname)

for dat_ in files_:
	if(dat_[-4:] == ".dat"):
		print(dat_)
		bpy.ops.object.select_by_type(type = 'MESH')
		bpy.ops.object.delete(use_global=False)
		for item in bpy.data.meshes:
			
			for scene in bpy.data.scenes:
				for obj in scene.objects:
					scene.objects.unlink(obj)
					
			item.user_clear()
			bpy.data.meshes.remove(item)

		
		try:
			bpy.ops.import_scene.deusexmd(filepath=dat_)
			bpy.ops.export_scene.fbx(filepath=(dat_[:-4] + ".fbx"))
			
		
		except Exception:
			print("Importing error")
			pass
		

```
## Post #19
- Username: aspadm
- Rank: advanced
- Number of posts: 52
- Joined date: Thu Nov 26, 2015 3:43 am
- Post datetime: 2017-01-08T23:45:06+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

Thnx erik945 for script - I use it with small changes(export to .obj, other logging etc.)

volfin,
Wanted to say earlier, but forgot: when I import some models it turns out something like this:
[](https://pp.vk.me/c638016/v638016069/19bc8/GpL3iw1M47U.jpg)
I looked .obj file - or all coordinates of vertex are NaN, or x/y is a large integer and the other coords a small(about 1.) floats.

In [this archive](https://yadi.sk/d/bVa2B23o37s6Ub) 5 examples of the different size - the original file and converted to .obj. I hope this will help to improve the import script.
## Post #20
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-09T01:34:17+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

> Reply from aspadm
>
> Thnx erik945 for script - I use it with small changes(export to .obj, other logging etc.)

volfin,
Wanted to say earlier, but forgot: when I import some models it turns out something like this:

I looked .obj file - or all coordinates of vertex are NaN, or x/y is a large integer and the other coords a small(about 1.) floats.

In this archive 5 examples of the different size - the original file and converted to .obj. I hope this will help to improve the import script.

Thanks, I'll take a look. It's hard to find examples of every possible format for testing, so this helps a lot
## Post #21
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-09T04:02:25+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

Ok, I added support for all of those model types. There was 4 new types in among those 6 files, so I bet there's more. Let me know if you find any.

Enjoy.

Edit: new version below.
## Post #22
- Username: U2LN
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Dec 11, 2015 1:53 pm
- Post datetime: 2017-01-09T04:33:46+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

Noob here, but is it possible there exists a database somewhere already? Maybe some kind of xml file or other?
## Post #23
- Username: aspadm
- Rank: advanced
- Number of posts: 52
- Joined date: Thu Nov 26, 2015 3:43 am
- Post datetime: 2017-01-09T07:46:06+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

> Reply from volfin
>
> Ok, I added support for all of those model types. There was 4 new types in among those 6 files, so I bet there's more. Let me know if you find any.

Enjoy.

I'm sorry, but as they say in my country: when fixing one you break another.
Models which correctly imported earlier now broken but what was broken now works 
And I delete old version of script so I don't have files to compare, sorry.

BTW, thank you for this great job   
I think that you incorrectly detect the format of the model. May be you make a version of the script with manually choice of the decoder?
## Post #24
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-09T18:53:13+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

I had to completely change detection methods, as there are no clear flags. I see what I missed though. This new version should restore what was lost.

Edit: Newer version in  later post.
## Post #25
- Username: aspadm
- Rank: advanced
- Number of posts: 52
- Joined date: Thu Nov 26, 2015 3:43 am
- Post datetime: 2017-01-10T11:06:30+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

> Reply from volfin
>
> I had to completely change detection methods, as there are no clear flags. I see what I missed though. This new version should restore what was lost.
So I looked to new version of importer and [there new (old?) broken files](https://yadi.sk/d/XxKEj8Th38B5iZ) - all or most of them. Hope that it help again
## Post #26
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2017-01-10T17:43:19+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

I need remove old version plugin before install new?
## Post #27
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-10T20:54:20+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

> Reply from aspadm
>
> volfin wrote:I had to completely change detection methods, as there are no clear flags. I see what I missed though. This new version should restore what was lost.
So I looked to new version of importer and there new (old?) broken files - all or most of them. Hope that it help again

You need to use the latest importer I posted. All of these are loading fine. Perhaps try deleting the old importer and installing the new one fresh.

> Reply from erik945
>
> I need remove old version plugin before install new?
 See msg above.
## Post #28
- Username: aspadm
- Rank: advanced
- Number of posts: 52
- Joined date: Thu Nov 26, 2015 3:43 am
- Post datetime: 2017-01-13T20:55:31+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

> Reply from U2LN
>
> Hey I don't have this game, but if y'all come across Alex Vega or Adam Jensen, can you let me know?
Yeah, I found it!
Model of Adam was one of this "broken files" - it's a file "0000000000000328.dat" about 15MB. But there's no hair and robo-legs - its in another files.
Big thanks volfin for his great work 
[adam.png](https://xentaxbackup.github.io/file/12213_adam.png)
## Post #29
- Username: U2LN
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Dec 11, 2015 1:53 pm
- Post datetime: 2017-01-13T21:11:28+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

> Reply from aspadm
>
> U2LN wrote:Hey I don't have this game, but if y'all come across Alex Vega or Adam Jensen, can you let me know?
Yeah, I found it!
Model of Adam was one of this "broken files" - it's a file "0000000000000328.dat" about 15MB. But there's no hair and robo-legs - its in another files.
Big thanks volfin for his great work
Ah sweet. Does it have working UVs?
## Post #30
- Username: Robo911
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jan 14, 2017 2:33 pm
- Post datetime: 2017-01-14T08:36:51+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

I've been digging around using these tools but havent been able to find what I'm looking for. Specifically, I'm looking for the furniture in Adam Jensen's apartment because I love that neo-baroque style and I wanted to mess around with it. If anyone can point me in the right direction, i'd be very happy.
## Post #31
- Username: snowboundmage
- Rank: advanced
- Number of posts: 40
- Joined date: Tue Dec 21, 2010 12:24 pm
- Post datetime: 2017-01-15T05:35:44+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

> Reply from Robo911
>
> I've been digging around using these tools but havent been able to find what I'm looking for. Specifically, I'm looking for the furniture in Adam Jensen's apartment because I love that neo-baroque style and I wanted to mess around with it. If anyone can point me in the right direction, i'd be very happy.
The furniture is in there, you just have to manually search every single dat file for it.

Also, erik945, your mass import/export script doesnt work on all .dat files for some reason, here's an example EDIT: NVM, apparently Volfin updating his script fixed it
 
```
https://www.mediafire.com/?w76ac4e2902h6hn
```

A pair of arms that imports/exports no problem when done by file>import, but not recognized by your script. Any clue why?

And while the attachment is there, how about a looksie Volfin? When exported to fbx and opened in max, the legs/feet/arms/eyes/eyelashes are fine, but the head and jacket don't seem to have any UVs. Any reason for that?
## Post #32
- Username: aspadm
- Rank: advanced
- Number of posts: 52
- Joined date: Thu Nov 26, 2015 3:43 am
- Post datetime: 2017-01-15T14:12:33+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

Well, I've already converted all .dat and .vap files what I have so [there small pack](https://yadi.sk/d/vAO3lUGr398zCx) for Jensen/Alex fans   
But there are some problems: missing/wrong UV's, missing textures(Adam's glasses and some other because BC7 and BC4 formats of textures not converts correctly).
Hope that volfin will fix it  

P.S. [All models in .obj format here](https://yadi.sk/d/8-Q_p2HM3994vV) (without textures and sources .dat files! Pay attention that it's not all files - QuickBMS script give me an error on 9% of game archive.)
## Post #33
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-15T20:56:28+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

> Reply from aspadm
>
> Well, I've already converted all .dat and .vap files what I have so there small pack for Jensen/Alex fans   
But there are some problems: missing/wrong UV's, missing textures(Adam's glasses and some other because BC7 and BC4 formats of textures not converts correctly).
Hope that volfin will fix it  

P.S. All models in .obj format here (without textures and sources .dat files! Pay attention that it's not all files - QuickBMS script give me an error on 9% of game archive.)

Well I would try to fix, if I had examples. Without examples, I can do nothing.
## Post #34
- Username: snowboundmage
- Rank: advanced
- Number of posts: 40
- Joined date: Tue Dec 21, 2010 12:24 pm
- Post datetime: 2017-01-15T23:54:16+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

> Reply from volfin
>
> 
Well I would try to fix, if I had examples. Without examples, I can do nothing.
Check my post above, i got an example for ya(for missing uv's anyway)


> Reply from aspadm
>
> missing textures(Adam's glasses and some other because BC7 and BC4 formats of textures not converts correctly).
Hope that volfin will fix it
Are you sure the textures are glitched or can you just not open them. If you can't open them, get this [https://software.intel.com/en-us/articl ... rks-plugin](https://software.intel.com/en-us/articles/intel-texture-works-plugin)

> Reply from aspadm
>
> 
QuickBMS script give me an error on 9% of game archive.
Was this the error? Cause if so, then I also got what you got.
## Post #35
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-16T01:19:29+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

> Reply from snowboundmage
>
> Check my post above, i got an example for ya(for missing uv's anyway)

Ah I missed that note to me at the end. Here's a version that fixes that. Was a new block size on UVs the script didn't handle. It may fix all the missing UVs you've been seeing, but if not, send me another example.

And as for the textures, yes, you need something that handles DX10 formats. The tool only converts when it's 100% sure about the format, if it doesn't know for sure the format, it prints an error message "Unknown Format %d\n" (which I hope would get people to submit the file for identification).  So chances of it being converted incorrectly are low. But anything could happen within the realm of possibility.
## Post #36
- Username: snowboundmage
- Rank: advanced
- Number of posts: 40
- Joined date: Tue Dec 21, 2010 12:24 pm
- Post datetime: 2017-01-16T01:49:49+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

> Reply from volfin
>
> snowboundmage wrote:Check my post above, i got an example for ya(for missing uv's anyway)


Ah I missed that note to me at the end. Here's a version that fixes that. Was a new block size on UVs the script didn't handle. It may fix all the missing UVs you've been seeing, but if not, send me another example.
io_scene_DeusEx-MD.zip

Thanks! Will let you know if I find any more problems.

EDIT:
Well, the missing uv's now seem to work, if a little misplaced.


EDITAGAIN: 
They aren't in the wrong position, there just not exactly scaled right
see here: [http://imgur.com/a/RRX4C](http://imgur.com/a/RRX4C)
## Post #37
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-16T04:15:38+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

yes, unfortunately some games have this problem. (Watchdogs 1 and 2 for instance).  I know with that game there's so far no solution but to adjust the UV's manually.  It's because they do UV manipulation in the shader.

I'll see if there's anything that can be done in this case. But no promises.
## Post #38
- Username: snowboundmage
- Rank: advanced
- Number of posts: 40
- Joined date: Tue Dec 21, 2010 12:24 pm
- Post datetime: 2017-01-16T04:27:11+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

Here's another UV problem.

```
https://www.mediafire.com/?b5o07zzxgm715of
```


> Reply from volfin
>
> yes, unfortunately some games have this problem. (Watchdogs 1 and 2 for instance).  I know with that game there's so far no solution but to adjust the UV's manually.  It's because they do UV manipulation in the shader.

I'll see if there's anything that can be done in this case. But no promises.
Don't stress too much about it, it is a pretty simple fix for most models(but that simple fix does seem to not work right with textures like hair, where the rezised UV's can go anywhere, making it difficult to pick exactly what type of hair texture a certain hair model has)
## Post #39
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-16T05:03:55+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

I think I got very lucky and figured it out. I thought it was a good test case that the jacket itself lined up nearly perfectly, and the sleeves were so incredibly small.  I was right. I was able to identify 4 floats in the model definition that seem to correspond to U_Scale, V_Scale, and U_Offset, V_Offset

After a test run in my debugger I got this:



Looks spot on.  So let me implement this in my code, and take a look at that file you just posted and i'll be back in a bit with a new, improved version. (and then later I'll have to go see if this applies to Hitman too)

Edit: Newer version below.
## Post #40
- Username: snowboundmage
- Rank: advanced
- Number of posts: 40
- Joined date: Tue Dec 21, 2010 12:24 pm
- Post datetime: 2017-01-16T07:05:32+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

Another busted UV for you, if you would so kindly take a look at it.

```
https://www.mediafire.com/?k145eljyqk31bn1
```


And from what I have tested so far, all working uvs seem to be the right size, so congrats on that 

EDIT:
Here's one with some inconsistant UV scaling, different from straight up broken like above

```
https://www.mediafire.com/?39yjb70a69bkwxn
```
## Post #41
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2017-01-16T12:46:59+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

Anybody found inventory models (weapons,implants,e.t.c.)?
## Post #42
- Username: aspadm
- Rank: advanced
- Number of posts: 52
- Joined date: Thu Nov 26, 2015 3:43 am
- Post datetime: 2017-01-16T17:48:21+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

> Reply from volfin
>
> 
Edit: Newest version. Fixes everything, Whoot!

Yeah, it's work 
Because I don't found normal maps in game archives, I use Ninja ripper so [here archieve with all textures and some models of Adam Jensen](https://yadi.sk/d/VKOAjhza39JinA). Enjoy!

P.S. His hairs and beard - another textures that using nvidia hairworks, but it aren't here.
## Post #43
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-16T22:15:42+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

> Reply from snowboundmage
>
> Another busted UV for you, if you would so kindly take a look at it.
Code: Select allhttps://www.mediafire.com/?k145eljyqk31bn1

And from what I have tested so far, all working uvs seem to be the right size, so congrats on that 

EDIT:
Here's one with some inconsistant UV scaling, different from straight up broken like above
Code: Select allhttps://www.mediafire.com/?39yjb70a69bkwxn

yep whoops. I forgot to factor in a block of skipped data when calculating the UV block size. only a very few models have this skipped block.

Fixed.

As for the askew UVs, they are actually fine. there's some models that actually have two sets of UVs. one is for effects, the other is for the texture. 

Effect UVs:


Texture UVs:


So just be sure to use the right UVs. you can delete the  other if not wanted.
## Post #44
- Username: snowboundmage
- Rank: advanced
- Number of posts: 40
- Joined date: Tue Dec 21, 2010 12:24 pm
- Post datetime: 2017-01-16T22:54:45+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

I think something bad happened.
 I uninstalled the old version, now it's gone. I installed the new version, now it's not showing up, in the plugins menu and the File>import>dat option doesn't exist anymore. Never had this problem with updating your script before.
EDIT: Well, manually copying the addon folder into the blender appdata folder seems to have done the trick, did something change with the folder layout in the zip? Cause apparently ctrl+alt+u>"install from file" didn't seem to work like the last few updates.
EDITAGAIN: Didn't work as well as I thought. Shows up in menus now, but don't seem to import anything. Now I'm getting this:
regardless of what .dat I import
## Post #45
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-17T00:31:22+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

> Reply from snowboundmage
>
> I think something bad happened.
 I uninstalled the old version, now it's gone. I installed the new version, now it's not showing up, in the plugins menu and the File>import>dat option doesn't exist anymore. Never had this problem with updating your script before.
EDIT: Well, manually copying the addon folder into the blender appdata folder seems to have done the trick, did something change with the folder layout in the zip? Cause apparently ctrl+alt+u>"install from file" didn't seem to work like the last few updates.
EDITAGAIN: Didn't work as well as I thought. Shows up in menus now, but don't seem to import anything. Now I'm getting this:
regardless of what .dat I import

Derp. I packaged it wrong. sorry.

Edit: new file in subsequent post.
## Post #46
- Username: snowboundmage
- Rank: advanced
- Number of posts: 40
- Joined date: Tue Dec 21, 2010 12:24 pm
- Post datetime: 2017-01-21T03:39:46+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

Is this model broken or the way it's supposed to be?

```
http://www.mediafire.com/file/129gymmfkzyp0f3/000000000002ad2b.dat
```

EDIT: Wrong link, fixed
## Post #47
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-21T06:24:56+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

> Reply from snowboundmage
>
> Is this model broken or the way it's supposed to be?
Code: Select allhttp://www.mediafire.com/file/129gymmfkzyp0f3/000000000002ad2b.dat
EDIT: Wrong link, fixed

Congrats, you found a completely new vertex/UV format.   

Added support.

Edit: newer version below.
## Post #48
- Username: aspadm
- Rank: advanced
- Number of posts: 52
- Joined date: Thu Nov 26, 2015 3:43 am
- Post datetime: 2017-01-22T13:22:38+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

In archive that I already post were some mistakes in models - see picture above. I'm completely forgot about it...
[Here link to archive (again)](https://yadi.sk/d/vAO3lUGr398zCx), filenames Adam_hand and Adam_suit (overlapping/incorrect scaled UV's, missed geometry(?) and "separate mesh layer" not import some parts of model)

P.S. Now it's crush with enabled "separate mesh layer" (model AlexV.dat from this archieve)

```
model count:10
Table:274720
Table:296912
Table:379856
Table:387504
Table:420768
Table:430048
Table:734976
Table:1079696
Table:1691696
Table:1936336
FormatFlag =2
SkipFlag =4099
UV Flag:31
ID1:0 ID2:0
Vert count:2845
Face count:15330
mat_offset:0
wght_offset:144496
Vertice offset:30688
Mesh #0 Alt_format:False ID1:0
UV Block Size is:28
UVs offset:64828 Mat offset:0
using alt UV format 2
vertex array length:2845
normal array length:0
weights array length:0
index array length:0
UV1 array length:2845
UV2 array length:0
UV3 array length:0
Colors array length:0
Faces offset:16
count / 3:5110
faces array length:5110
Traceback (most recent call last):
  File "C:\Users\username\AppData\Roaming\Blender Foundation\Blender\2.78\scripts\addons\io_scene_DeusEx-MD\__init__.py", line 83, in execute
    result=import_DeusExMD.import_DeusExMD(self.filepath, bpy.context,self.randomize_colors,self.import_vertcolors,self.skip_blank,self.use_layers,self.mesh_scale)
  File "C:\Users\username\AppData\Roaming\Blender Foundation\Blender\2.78\scripts\addons\io_scene_DeusEx-MD\import_DeusExMD.py", line 828, in import_DeusExMD
    result=import_mesh(context,randomize_colors,import_vertcolors,use_layers,mesh_scale,i,block_offsets[i])
  File "C:\Users\username\AppData\Roaming\Blender Foundation\Blender\2.78\scripts\addons\io_scene_DeusEx-MD\import_DeusExMD.py", line 315, in import_mesh
    bpy.ops.object.shade_smooth()
  File "C:\Program Files\Blender Foundation\Blender\2.78\scripts\modules\bpy\ops.py", line 189, in __call__
    ret = op_call(self.idname_py(), None, kw)
RuntimeError: Operator bpy.ops.object.shade_smooth.poll() failed, context is incorrect
```

[errors.jpg](https://xentaxbackup.github.io/file/12264_errors.jpg)
## Post #49
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-22T16:57:35+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

Thanks for letting me know. I'll take a look and see what I can do.
## Post #50
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-22T21:34:38+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

Ok, as for Adam_suit. there's nothing wrong. That's simply all that's in the file. I suspect either the Trenchoat is in another file (since you can change trenchcoats from settings), or because it's flexible cloth, is generated on the GPU.  But there's nothing wrong with the file import.

As for Alex_V, the error "Context is Incorrect" indicates you weren't in Object mode when importing the model. Maybe Edit mode, or Weighting mode, or Posing mode.  My script is dumb on that, and expects Object Mode.  Next version i'll add code to Force Object mode for cases like this where people forget.   Model imports fine when in object mode.

Lastly the hand UVs.  I see the same you see. I'll investigate it further, but I suspect this is how it's supposed to be.

If you look ingame:





Those parts are a high shine metal only, no real texture. They use varying sizes of UV to vary the scale of a scratch-map and that type of thing. It's a common technique.  However, I want to be double sure, so I'll verify this model is coming out right. It's also possible this model uses multi-material (which would be the first I've seen for Deus Ex:MD, I've seen it in Hitman 2016 a lot.) if there is a texture for this part of the hand, it would be helpful it you can point me to it.

Edit: yes I've verified, the UVs are correct. There's only one scaling factor and one block of UVs for that whole object. That's how the Devs made it. (for better or worse   )
## Post #51
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-01-27T02:21:13+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

Minor update to importer.
 - Ensure Object mode is active before attempting import
 - Validated functionality back to Blender version 2.70 (oldest supported)

Edit: newer version below.
## Post #52
- Username: U2LN
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Dec 11, 2015 1:53 pm
- Post datetime: 2017-02-11T05:53:21+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

Found Alex. Anyone know where her hair is?
[alexvega_nohair.png](https://xentaxbackup.github.io/file/12431_alexvega_nohair.png)
## Post #53
- Username: Chiff
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jan 19, 2016 10:29 pm
- Post datetime: 2017-02-12T13:34:50+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

Hi folks, noob here, anyone know where the audio, or more specifically music files are?
## Post #54
- Username: hhchunter
- Rank: beginner
- Number of posts: 29
- Joined date: Tue Sep 08, 2015 4:51 pm
- Post datetime: 2017-02-16T11:03:33+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

> Reply from Chiff
>
> Hi folks, noob here, anyone know where the audio, or more specifically music files are?

Seems like music is contained within the .pc_fsb files within the runtime directory, not sure if they're encrypted.

Dawn engine is built on the Absolution version of G² engine, and seems to be using FMOD.
[assembly:/sound/localization/dialogue/french/barks/ai/uniques/slaw/slaw_civalert.wavebank].pc_fsb

On that note, has anyone seen the Helle / Eliza Cassan's model? Apparently it's in the game.
## Post #55
- Username: SmiffinWeffin
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Feb 01, 2017 1:57 pm
- Post datetime: 2017-02-24T05:40:46+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

Hey, another noob here.  So, maybe I'm missing something obvious and/or am just stupid, but... could somebody tell me the step-by-step process of extracting all models and textures from the game?  I'm still fairly new to all this, but I'm eager to get my hands on (and make use of) some of the models.

(On that note, I don't suppose anyone's thrown together a pack with all the weapon models and textures yet?  Because that's my #1 priority.)
## Post #56
- Username: hhchunter
- Rank: beginner
- Number of posts: 29
- Joined date: Tue Sep 08, 2015 4:51 pm
- Post datetime: 2017-02-27T11:00:43+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

> Reply from SmiffinWeffin
>
> Hey, another noob here.  So, maybe I'm missing something obvious and/or am just stupid, but... could somebody tell me the step-by-step process of extracting all models and textures from the game?  I'm still fairly new to all this, but I'm eager to get my hands on (and make use of) some of the models.

(On that note, I don't suppose anyone's thrown together a pack with all the weapon models and textures yet?  Because that's my #1 priority.)

Here's a super quick breakdown.

Step 1. Extract the Game_Layer Archive using QuickBMS & the QuickBMS script, it should be the biggest file.

Step 2. 
* Find all models using the model finder tool posted in this thread. They're normally .dat files.
* Convert all the .vap files extracted to .dds files using the texture tool posted in this thread.

Step 3. Open the models in blender using the blender addon.
## Post #57
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2017-02-27T14:52:29+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

[https://sktest.aruarose.com/DXMDExtract_v002.7z](https://sktest.aruarose.com/DXMDExtract_v002.7z)

Due to the nature of the asset names, it produces filenames like "00BB10BBA81D424A.bin".
The actual names and their matching hashes go into NameMap.txt.
## Post #58
- Username: SmiffinWeffin
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Feb 01, 2017 1:57 pm
- Post datetime: 2017-03-01T00:34:14+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

> Reply from hhchunter
>
> SmiffinWeffin wrote:Hey, another noob here.  So, maybe I'm missing something obvious and/or am just stupid, but... could somebody tell me the step-by-step process of extracting all models and textures from the game?  I'm still fairly new to all this, but I'm eager to get my hands on (and make use of) some of the models.

(On that note, I don't suppose anyone's thrown together a pack with all the weapon models and textures yet?  Because that's my #1 priority.)

Here's a super quick breakdown.

Step 1. Extract the Game_Layer Archive using QuickBMS & the QuickBMS script, it should be the biggest file.

Step 2. 
* Find all models using the model finder tool posted in this thread. They're normally .dat files.
* Convert all the .vap files extracted to .dds files using the texture tool posted in this thread.

Step 3. Open the models in blender using the blender addon.

Exactly what I needed, thanks!
## Post #59
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-03-01T03:42:40+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

> Reply from Sir Kane
>
> http://sktest.aruarose.com/DXMDExtract.7z

Due to the nature of the asset names, it produces filenames like "00BB10BBA81D424A.bin".
The actual names and their matching hashes go into NameMap.txt.

Where was this 6 months ago?   
But seriously, how is it determining the original filenames?
## Post #60
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2017-03-01T08:54:07+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

If you mean the asset names in NameMap.txt, those come from the pc_headerlib files.

I also figured most of it out a while ago, but never got around to make a fully functional tool.
## Post #61
- Username: SmiffinWeffin
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Feb 01, 2017 1:57 pm
- Post datetime: 2017-03-04T11:35:26+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

> Reply from Sir Kane
>
> http://sktest.aruarose.com/DXMDExtract.7z

Due to the nature of the asset names, it produces filenames like "00BB10BBA81D424A.bin".
The actual names and their matching hashes go into NameMap.txt.
How do I use this, and should it be used before or after converting the files to the more useable formats?
## Post #62
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2017-03-04T16:39:24+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

Run it from the command shell (cmd.exe). Running it without any parameters will show the usage, but it should be DXMDExtract.exe <dir with .archive & .pc_headerlib files> <output dir> or something like that.
## Post #63
- Username: SmiffinWeffin
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Feb 01, 2017 1:57 pm
- Post datetime: 2017-03-05T08:34:07+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

> Reply from Sir Kane
>
> Run it from the command shell (cmd.exe). Running it without any parameters will show the usage, but it should be DXMDExtract.exe <dir with .archive & .pc_headerlib files> <output dir> or something like that.
Forgive my idiocy, but I'm entering "start DXMDExtract.exe" and it's only telling me "The system cannot find the file "DXMDExtract.exe".
## Post #64
- Username: qwzzz
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Oct 13, 2011 1:29 am
- Post datetime: 2017-03-05T17:51:25+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

hi all, noob here

what are the exporters needed to export to fbx? i dont really know how to use blender
## Post #65
- Username: lapdragon
- Rank: beginner
- Number of posts: 30
- Joined date: Tue Dec 28, 2010 4:24 am
- Post datetime: 2017-03-07T07:31:14+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

> Reply from SmiffinWeffin
>
> Sir Kane wrote:Run it from the command shell (cmd.exe). Running it without any parameters will show the usage, but it should be DXMDExtract.exe <dir with .archive & .pc_headerlib files> <output dir> or something like that.
Forgive my idiocy, but I'm entering "start DXMDExtract.exe" and it's only telling me "The system cannot find the file "DXMDExtract.exe".

It sounds like your command prompt isn't running in the same directory as DXMDExtract.

Move your copy of DXMDExtract to C:\Program Files\Steam\steamapps\common\Deus Ex Mankind Divided\runtime (or wherever your Steam install actually is).  In that same folder, right-click and make a new folder named "extracted", and then right click and make a new text file.  Open the new text file in notepad, and enter the following line "DXMDExtract . .\extracted" (without the quotes), then save and exit.  Rename the file from "new text document.txt" to "unpack.bat", and now you can double-click on it to unpack the game.

You will need 22gb of free space to unpack the game, so make sure you're ready.
## Post #66
- Username: xendance
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Mar 08, 2017 11:38 pm
- Post datetime: 2017-03-10T13:14:49+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

Hey guys, been lurking for a while and made an account just to say how amazed I am at the effort you guys put into this. I want to help but I have no skills to volunteer, so I'll just sit here and cheer you loudly like an overproud dad at his kid's ball game.

I thought I'd also let you guys know about the Deus Ex model archive I've got, since someone was asking for an Alex Vega in the thread? They're not the MD models but they might tie you over if you're desperate: [https://deus-ex-3d-models.tumblr.com/](https://deus-ex-3d-models.tumblr.com/)

Do you guys have models you want in particular? Here are the ones I want the most:
(This is not a request, I would give a leg for these models but I totally get that guys are busy enough already just trying to figure out how the game files work)

-Koller
-Ivan Berk (seen briefly just before station bombing)
-Naked Adam Jensen (from the first Sarif dialogue) (only god can judge me)
-Police uniform K
-Bob Page (not sure if he's in the game files at all; I only remember seeing him in pre-rendered cutscenes)
-Overweight hooker lady
-Train station child (that may or may not be a Denton)

-Train station dead mom lady
-Shadowchild’s NSN avatar

Also, could a graphics card ripper help? Something like Ninja Ripper or 3D Ripper DX? I've had a little bit of success with them in the past. 

You guys are great and you are doing the lord's work
## Post #67
- Username: SmiffinWeffin
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Feb 01, 2017 1:57 pm
- Post datetime: 2017-03-11T06:51:30+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

Alright, sorry for needing my hand held through every step of the process, but... how do I use the texture converter, exactly?  I tried putting it in the folder I extracted to and clicking on it but it just briefly opens and immediately closes again before I can even see what it says.
## Post #68
- Username: hhchunter
- Rank: beginner
- Number of posts: 29
- Joined date: Tue Sep 08, 2015 4:51 pm
- Post datetime: 2017-03-11T10:12:26+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

> Reply from SmiffinWeffin
>
> Alright, sorry for needing my hand held through every step of the process, but... how do I use the texture converter, exactly?  I tried putting it in the folder I extracted to and clicking on it but it just briefly opens and immediately closes again before I can even see what it says.

In the folder the executable is, shift + right click the window background and it should come up with an option "open command window here" then drag the executable onto that command window.

It should then give you instructions what to do
## Post #69
- Username: hhchunter
- Rank: beginner
- Number of posts: 29
- Joined date: Tue Sep 08, 2015 4:51 pm
- Post datetime: 2017-03-11T10:14:11+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

Volfin, I've come across a few models that seem to not be working with your tools. Had a look in hex and they are indeed model files.

60643501754326236 00D772F18C009CDC [assembly:/characters/resources/sidequests/helle/helle.wl2?/ground.weightedprim].pc_weightedprim
16450753511803356 003A71DF875BC9DC [assembly:/characters/resources/sidequests/helle/helle_revealed.wl2?/ground.weightedprim].pc_weightedprim
## Post #70
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-03-11T18:29:17+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

> Reply from hhchunter
>
> Volfin, I've come across a few models that seem to not be working with your tools. Had a look in hex and they are indeed model files.

60643501754326236 00D772F18C009CDC [assembly:/characters/resources/sidequests/helle/helle.wl2?/ground.weightedprim].pc_weightedprim
16450753511803356 003A71DF875BC9DC [assembly:/characters/resources/sidequests/helle/helle_revealed.wl2?/ground.weightedprim].pc_weightedprim

ok, i'll see what I can do.

Edit: seems this new unpacker saves models in a slightly alternate format, they have a variable header on top that wasn't there before. I think I can add support for this so both old and new unpackers work.
## Post #71
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-03-11T20:04:10+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

Okay, newest version, supports old QuickBBS unpacker format, and the newer Unpacker by Sir Kane. 

Enjoy 

Edit: newer version below.
## Post #72
- Username: Nick3d
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Nov 11, 2013 12:30 am
- Post datetime: 2017-03-12T14:06:22+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

Hi all,

If someone could share Adam model ( possibly with the trenchcoat ), I'll rig him ( in Maya ) and share the scene ( using UE4 skeletal hierarchy and Apex cloth for the trenchcoat simulation ).
## Post #73
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2017-03-12T14:15:21+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

> Reply from Nick3d
>
> Hi all,

If someone could share Adam model ( possibly with the trenchcoat ), I'll rig him ( in Maya ) and share the scene ( using UE4 skeletal hierarchy and Apex cloth for the trenchcoat simulation ).this is not the place to share some other people's work including models. This is place to learn how to get models (or else) yourself.
## Post #74
- Username: SmiffinWeffin
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Feb 01, 2017 1:57 pm
- Post datetime: 2017-03-12T20:09:24+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

> Reply from hhchunter
>
> SmiffinWeffin wrote:Alright, sorry for needing my hand held through every step of the process, but... how do I use the texture converter, exactly?  I tried putting it in the folder I extracted to and clicking on it but it just briefly opens and immediately closes again before I can even see what it says.

In the folder the executable is, shift + right click the window background and it should come up with an option "open command window here" then drag the executable onto that command window.

It should then give you instructions what to do
Alright, got that... now, what am I doing wrong here? (see attached image)
[aaaaaaaa.png](https://xentaxbackup.github.io/file/12616_aaaaaaaa.png)
## Post #75
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-03-12T23:07:02+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

your command line is fine. But it would seem it's not finding any valid *.vap files in the 'input' folder.  And just in case you think it will parse down subdirectories inside the 'input' folder, be assured it will not. It will only process *.vap files in 'input' folder itself.  If your *.vap files are in input\someother directory, then you need to specify that directly.
## Post #76
- Username: Vindis
- Rank: advanced
- Number of posts: 44
- Joined date: Sat Apr 09, 2011 4:31 am
- Post datetime: 2017-05-06T12:48:14+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

> Reply from volfin
>
> your command line is fine. But it would seem it's not finding any valid *.vap files in the 'input' folder.  And just in case you think it will parse down subdirectories inside the 'input' folder, be assured it will not. It will only process *.vap files in 'input' folder itself.  If your *.vap files are in input\someother directory, then you need to specify that directly.

Hi Volfin,

Tried to convert all txet (assuming those are the texture files) but I got an error, "unknown format -1" for each one. I renamed every file to vap.
I extracted the files with Sir Kanes' extractor, could be that problem? Should I try quickbms?

Thank you for your help!
## Post #77
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-05-06T16:06:41+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

> Reply from Vindis
>
> volfin wrote:your command line is fine. But it would seem it's not finding any valid *.vap files in the 'input' folder.  And just in case you think it will parse down subdirectories inside the 'input' folder, be assured it will not. It will only process *.vap files in 'input' folder itself.  If your *.vap files are in input\someother directory, then you need to specify that directly.

Hi Volfin,

Tried to convert all txet (assuming those are the texture files) but I got an error, "unknown format -1" for each one. I renamed every file to vap.
I extracted the files with Sir Kanes' extractor, could be that problem? Should I try quickbms?

Thank you for your help!

yes everything was written for the quickbms files. I don't know the differences  involved with the other extractor.
## Post #78
- Username: Vindis
- Rank: advanced
- Number of posts: 44
- Joined date: Sat Apr 09, 2011 4:31 am
- Post datetime: 2017-05-17T15:23:46+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

> Reply from volfin
>
> Vindis wrote:volfin wrote:your command line is fine. But it would seem it's not finding any valid *.vap files in the 'input' folder.  And just in case you think it will parse down subdirectories inside the 'input' folder, be assured it will not. It will only process *.vap files in 'input' folder itself.  If your *.vap files are in input\someother directory, then you need to specify that directly.

Hi Volfin,

Tried to convert all txet (assuming those are the texture files) but I got an error, "unknown format -1" for each one. I renamed every file to vap.
I extracted the files with Sir Kanes' extractor, could be that problem? Should I try quickbms?

Thank you for your help!

yes everything was written for the quickbms files. I don't know the differences  involved with the other extractor.

Is there any chance, that you share the file structure of the texture files, so I can write a program to work with Sir Kanes' extractor? Maybe there's not much difference...
## Post #79
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-05-17T16:13:15+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

> Reply from Vindis
>
> Is there any chance, that you share the file structure of the texture files, so I can write a program to work with Sir Kanes' extractor? Maybe there's not much difference...

The header is as follows:

```
{
	long Unknown0;
	short Unknown1;
	short Unknown2;
	short Unknown7;
	short Unknown8;
	short Width;
	short Height;
	short Format1; // MIP count maybe?
	short Format;
	long Unknown3;
	long Unknown4;
	long Unknown5;
	long Unknown6;
};

```


Directly after the header comes the compressed texture data.  How that data is formatted is dependent on the "Format" variable.  The known "Format" codes are:

```
		if (VAPHeader->Format == 0x4A)
			AttemptedFormat = TEXTURE::DXT1;
		else if (VAPHeader->Format == 0x50)
			AttemptedFormat = TEXTURE::DXT5;
		else if (VAPHeader->Format == 0x53)
			AttemptedFormat = TEXTURE::BC4;
		else if (VAPHeader->Format == 0x56)
			AttemptedFormat = TEXTURE::BC5;
		else if (VAPHeader->Format == 0x5B)
			AttemptedFormat = TEXTURE::BC7;
		else if (VAPHeader->Format == 0x43)
			AttemptedFormat = TEXTURE::U8bpp;
		else if (VAPHeader->Format == 0x1D)
			AttemptedFormat = TEXTURE::U32bpp;

		if (AttemptedFormat == TEXTURE::NO_FORMAT)
		{
			printf("Unknown Format %d\n", VAPHeader->Format);
			continue;
		}

```
## Post #80
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2017-07-06T16:36:09+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

Thank you for your tool
Do you planed update texture convertor?


And what does it mean when in a namemap in a line with a numeric file name there are several symbolic names?
as example:

   71795574635566022 00FF11B1DA9913C6 [assembly:/_g2_assets/templates/aspectdummy.aspect]([assembly:/environment_assets/20_props/10_cluttering/17_industrial/bucket_laundry_garbage_a/bucket_laundry_garbage_a.template?/bucket_laundry_garbage_a bf7f7ac8-1407-421c-bb9a-faa85ce5fcdb.entitytemplate].entitytype,[modules:/runtime.streaming.moduleinfo?zstreamingroot.class].entitytype,[modules:/runtime.activation.moduleinfo?zactivationroot.class].entitytype).pc_entitytype

    6031250991359965 00156D640CE427DD [[assembly:/material_class/2dnsr_pb.uberclass?/blendwithvertexcolor#!diffusemap1##tint,df~0,u~wrap,v~wrap,f~21,uv~uv0!!diffusemap2#bo~maskblend,bc~r,#tint,col!!usenormalmapfiltering#!nmf~1,normalmap1##tint,df~2,u~wrap,v~wrap,f~21,uv~uv0!!normalmap2#bo~add,#tint,df~3,u~wrap,v~wrap,f~21,uv~uv0!!specular1##tint,col!roughness#tint,df~5,u~wrap,v~wrap,f~21,uv~uv0!!specular2#bc~r,#tint,col!roughness#tint,df~7,u~wrap,v~wrap,f~21,uv~uv0,ch~g!!masktypesettings#!masktexture##tint,col!!maskchannelr#channelmap#tint,uf~7!!alphatypesettings#!blendwithvertexalpha#!vertexshadertype#!materialtype1#mt~dielectric!dbm~opaque.ubervariant].fx](dx11).pc_mate
## Post #81
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-07-06T17:14:54+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

as far as I know, there's no need to update the texture tool. it works with all valid textures. If that's not true, I need more information.

As for the number stuff, I have no idea what all that is.
## Post #82
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2017-07-06T18:59:12+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

Convertor don't work with textures extracted by  Sir Kanes tool.
## Post #83
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-07-06T19:07:55+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

> Reply from erik945
>
> Convertor don't work with textures extracted by  Sir Kanes tool.

yes everything was made for the original quickbms script. for that it all works.
## Post #84
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2017-07-09T14:11:31+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

It seems to me Sir Kane's extractor misses some files.
I can not find some models - for example, weapons and augmentations from the screen of equipment.
## Post #85
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2017-07-17T23:14:25+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

[https://sktest.aruarose.com/DXMDExtract_v002.7z](https://sktest.aruarose.com/DXMDExtract_v002.7z)
Fixed a bug that caused files in containers whose names contain upper case characters to not be extracted.
Speculative fix for files containing wrong data.
Now generates a list of external resources and their file names.
Now generates a binary file containing the data required to map resource IDs to asset names.

This is the format for the ResMap.bin file:

```
	struct {
		uint64_t	ResourceID;
		uint32_t	NameLength;
		char		Name[NameLength];
	} Entries[Count];

```

The name is zero terminated.
## Post #86
- Username: Vindis
- Rank: advanced
- Number of posts: 44
- Joined date: Sat Apr 09, 2011 4:31 am
- Post datetime: 2017-07-19T12:15:07+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

I made a texture tool for Sir Kanes extractor (fortunately, the data is already there, uncompressed  ).
It have basic functionality, and convert dxt1,5, bc4,5,7 textures. All you have to do is rename texture bin files to ".tex"
Just put the files into the same folder as the exe, and it converts all tex to DDS. (you can figure out what is texture from names list)


PS: Can't found files for these types, so it's not converting these tho, and you need intel's photoshop plugin to work with BCx dds.

```
      else if (VAPHeader->Format == 0x1D)
         AttemptedFormat = TEXTURE::U32bpp;

      if (AttemptedFormat == TEXTURE::NO_FORMAT)
      {
         printf("Unknown Format %d\n", VAPHeader->Format);
         continue;
      }
```

[Tex2DDS.zip](https://xentaxbackup.github.io/file/13119_Tex2DDS.zip)
## Post #87
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2017-07-19T18:13:08+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

Join the topic - a couple of scripts on the python 2.

The first - copies and renames the extracted files. The result is a correct directory tree.
Fdir = "E: \\ DXMD_DLC_UNPACK" # base unpack folder with nameMap file
Fsrc = "E: \\ md_files_DLC2 \\" # folder with correct filenames


The second for the blender - batch export of 3d models to fbx
Folder to search (recursively)
Fdir = "E: \\ md_files_DLC \\ objects \\" - directory for search



[dxmd_scripts.7z](https://xentaxbackup.github.io/file/13121_dxmd_scripts.7z)
## Post #88
- Username: Vindis
- Rank: advanced
- Number of posts: 44
- Joined date: Sat Apr 09, 2011 4:31 am
- Post datetime: 2017-07-23T17:49:35+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

@Volfin

Hi Volfin,

may I ask you a big favor?
If you have time, could you please write down the file format of the model files?
I've tried to figure out, and write a template in 010 Editor, but it drives me nuts. Sometimes it works,
sometimes the values are offset by an unknown value (the tables for example, it points to an address, there's no vertex number).

I don't know nothing about python scripting, so your importer is not a good starting point for me 

I would really appreciate your help!
## Post #89
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-07-23T19:17:17+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

> Reply from Vindis
>
> @Volfin

Hi Volfin,

may I ask you a big favor?
If you have time, could you please write down the file format of the model files?
I've tried to figure out, and write a template in 010 Editor, but it drives me nuts. Sometimes it works,
sometimes the values are offset by an unknown value (the tables for example, it points to an address, there's no vertex number).

I don't know nothing about python scripting, so your importer is not a good starting point for me 

I would really appreciate your help!

This is because there is no one format. There's 10 to 15 distinct vertex buffer formats. And they can have various sub blocks per format. so it's a very messy thing to decode. I have no real documentation, I figure a block format out in 010, then add it to the python script. then when I or someone else encounters another format, I add it to the script as well.  The only real documentation is the python script. It's not hard to read really. 

I have a library of data readers in the python script:

```
 def BB(n): #unsigned Char
 def Bb(n): # Signed Char
 def BH(n): # Unsigned Short
 def Bh(n): # Signed Short
 def Bf(n): # Float
 def BF(n): # HALF FLoat
 def Bi(n): # Signed Long Int
 def BI(n): # Unsigned Long Int
 def Bd(n): # Double
 def alignPosition(alignment): # align to given byte width (4/8/16 etc)

```


if you see BB(3) in the code, I read in 3 bytes, but didn't assign them to a variable, so I just skipped them
if you see new_var = BB(3), then 'new_var' is now an array of 3 bytes read in. new_var[0] would be the first new_var[1] would be the second etc.
if you see new_var = BB(1)[0], then I immediately assigned the value read in to 'new_var' instead of assigning it as an array.

filehandle.seek(next_offset,0) # SEEK_SET
filehandle.seek(hdr_size,1) #SEEK_CUR
filehandle.seek(0,2) # SEEK_END  
These all do exactly what they do in C, seek on the file stream either from the start (SET), the current position (CUR), or from the end (END).

The rest should be self explanatory.
## Post #90
- Username: Vindis
- Rank: advanced
- Number of posts: 44
- Joined date: Sat Apr 09, 2011 4:31 am
- Post datetime: 2017-07-24T08:30:56+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

> Reply from volfin
>
> Vindis wrote:@Volfin

Hi Volfin,

may I ask you a big favor?
If you have time, could you please write down the file format of the model files?
I've tried to figure out, and write a template in 010 Editor, but it drives me nuts. Sometimes it works,
sometimes the values are offset by an unknown value (the tables for example, it points to an address, there's no vertex number).

I don't know nothing about python scripting, so your importer is not a good starting point for me 

I would really appreciate your help!

This is because there is no one format. There's 10 to 15 distinct vertex buffer formats. And they can have various sub blocks per format. so it's a very messy thing to decode. I have no real documentation, I figure a block format out in 010, then add it to the python script. then when I or someone else encounters another format, I add it to the script as well.  The only real documentation is the python script. It's not hard to read really. 

I have a library of data readers in the python script:
Code: Select alldef readcstr(): #Null Terminated text string
 def BB(n): #unsigned Char
 def Bb(n): # Signed Char
 def BH(n): # Unsigned Short
 def Bh(n): # Signed Short
 def Bf(n): # Float
 def BF(n): # HALF FLoat
 def Bi(n): # Signed Long Int
 def BI(n): # Unsigned Long Int
 def Bd(n): # Double
 def alignPosition(alignment): # align to given byte width (4/8/16 etc)


if you see BB(3) in the code, I read in 3 bytes, but didn't assign them to a variable, so I just skipped them
if you see new_var = BB(3), then 'new_var' is now an array of 3 bytes read in. new_var[0] would be the first new_var[1] would be the second etc.
if you see new_var = BB(1)[0], then I immediately assigned the value read in to 'new_var' instead of assigning it as an array.

filehandle.seek(next_offset,0) # SEEK_SET
filehandle.seek(hdr_size,1) #SEEK_CUR
filehandle.seek(0,2) # SEEK_END  
These all do exactly what they do in C, seek on the file stream either from the start (SET), the current position (CUR), or from the end (END).

The rest should be self explanatory.

Oooh!

The binary reading part avoided my attention. Now it's really not that hard 

Thank You very much!
## Post #91
- Username: Vindis
- Rank: advanced
- Number of posts: 44
- Joined date: Sat Apr 09, 2011 4:31 am
- Post datetime: 2017-07-25T13:34:50+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

With your help, my obj converter starts getting into shape
## Post #92
- Username: kalrua
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Nov 23, 2007 5:29 am
- Post datetime: 2017-07-30T20:42:37+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

[quote="volfin"]I suspect either the Trenchoat is in another file (since you can change trenchcoats from settings), or because it's flexible cloth, is generated on the GPU.
[/quote]

You are right 
Jensen's Trenchoat:[quote]17230170369043947 003D36BFA8442DEB [assembly:/characters/resources/main_characters/jensen/jensen_trench.apx].pc_apex[/quote]

Jensen's hairs:[quote]59216673450565904 00D2614031CD2110 [assembly:/characters/resources/main_characters/jensen/jensen.hair].pc_hair[/quote]
## Post #93
- Username: aspadm
- Rank: advanced
- Number of posts: 52
- Joined date: Thu Nov 26, 2015 3:43 am
- Post datetime: 2017-08-06T17:28:32+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

> Reply from volfin
>
> as far as I know, there's no need to update the texture tool. it works with all valid textures. If that's not true, I need more information.

As for the number stuff, I have no idea what all that is.
"New" format (.bin/.tex) have a 24 bytes header; first 4 bytes - ascii TXET (54 58 45 54), so you can simple add checking and trimming bytes - all other data is unchanged

UPD: here full example dataset of tex files: there are 11 subformats (2 bytes with offset 42 or short Format in volfin script). Link: [https://yadi.sk/d/9zcdSJR53M6KKi](https://yadi.sk/d/9zcdSJR53M6KKi)

UPD 2: looks like DEMD .dat importer can't read UV coordinates from .linkedprim files; and there are some files, that obviously 3d models (collisions, COLA signature), but can't be opened + examples of .apx (clothes) and .hair files. Link: [https://yadi.sk/d/n11L2IQk3M6K5e](https://yadi.sk/d/n11L2IQk3M6K5e)

UPD 3: small teaser for non-console peoples  (I must do some enchantments before upload program)
## Post #94
- Username: rithkhmer
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Aug 08, 2017 6:20 am
- Post datetime: 2017-08-08T21:21:09+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

thank you so much for your sharing this nice article,
I really like to reading your blog !

[ดูหนังออนไลน์](https://movie-review-2017.blogspot.com)
## Post #95
- Username: JimmyJ
- Rank: beginner
- Number of posts: 32
- Joined date: Wed Dec 21, 2011 8:54 am
- Post datetime: 2017-08-25T19:46:22+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

I dont know why, but blender's importer is not working... I used Sir kane tool, and quickbms for extract, but blender still give me messege: "doesent seem to be a model"
## Post #96
- Username: S0UZ
- Rank: advanced
- Number of posts: 40
- Joined date: Tue Apr 05, 2011 6:46 pm
- Post datetime: 2017-08-27T18:23:07+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

> Reply from aspadm
>
> volfin wrote:as far as I know, there's no need to update the texture tool. it works with all valid textures. If that's not true, I need more information.

As for the number stuff, I have no idea what all that is.
"New" format (.bin/.tex) have a 24 bytes header; first 4 bytes - ascii TXET (54 58 45 54), so you can simple add checking and trimming bytes - all other data is unchanged

UPD: here full example dataset of tex files: there are 11 subformats (2 bytes with offset 42 or short Format in volfin script). Link: https://yadi.sk/d/9zcdSJR53M6KKi

UPD 2: looks like DEMD .dat importer can't read UV coordinates from .linkedprim files; and there are some files, that obviously 3d models (collisions, COLA signature), but can't be opened + examples of .apx (clothes) and .hair files. Link: https://yadi.sk/d/n11L2IQk3M6K5e

UPD 3: small teaser for non-console peoples  (I must do some enchantments before upload program)
Hi may i have this tool???
## Post #97
- Username: aspadm
- Rank: advanced
- Number of posts: 52
- Joined date: Thu Nov 26, 2015 3:43 am
- Post datetime: 2017-08-31T22:56:22+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

Hey guys! I did it!
This is the DEMD database - GUI tool for extracting, view and exporting game database.
Big thanks Volfin, Sir Kane for their tools  And thanks for all peoples from this topic

New version below

If you find a bug or need sources, please, PM-me.

P.S. I rewrited tex2dds/vap_converter from scratch, but four formats from 11 supports uncorrectly.
P.P.S. This tool contains portable Blender 3d, Volfin's model converter, Sir Kane's archives extractor, TXET2DDS tools (textures) and other components
P.P.P.S. You can convert audio files (without listening in app)
## Post #98
- Username: S0UZ
- Rank: advanced
- Number of posts: 40
- Joined date: Tue Apr 05, 2011 6:46 pm
- Post datetime: 2017-09-01T09:53:08+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

> Reply from aspadm
>
> Hey guys! I did it!
This is the DEMD database - GUI tool for extracting, view and exporting game database.
Big thanks Volfin, Sir Kane for their tools  And thanks for all peoples from this topic

Here the link - https://yadi.sk/d/di_bL7573MW5hg

If you find a bug or need sources, please, PM-me.

P.S. I rewrited tex2dds/vap_converter from scratch, but four formats from 11 supports uncorrectly.
P.P.S. This tool contains portable Blender 3d, Volfin's model converter, Sir Kane's archives extractor, TXET2DDS tools (textures) and other components
P.P.P.S. You can convert audio files (without listening in app)
Thanks very much! Love it!!!!
## Post #99
- Username: aspadm
- Rank: advanced
- Number of posts: 52
- Joined date: Thu Nov 26, 2015 3:43 am
- Post datetime: 2017-09-17T10:51:39+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

And there are new version of DEMD database: [https://yadi.sk/d/qUxdTmJa3MxHEs](https://yadi.sk/d/qUxdTmJa3MxHEs)
I strongly reccomend to delete old program folder and unzip this new one - some libs were changed.

What's new?
1. Fix problems with OpenGL shader
2. Add .apx file support (only clothes) - including UV coords
3. Other fixes

If you have some issues or you need sources - contact me.

P.S. Clothes can be exported to STL/OBJ and APB format (Nvidia APEX 1.3.x)
## Post #100
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2017-09-18T15:50:53+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

Thanks so much for the tool! It works amazing   
Is there any chance to support the hair curves too?
## Post #101
- Username: aspadm
- Rank: advanced
- Number of posts: 52
- Joined date: Thu Nov 26, 2015 3:43 am
- Post datetime: 2017-09-18T16:01:22+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

> Reply from o0Crofty0o
>
> Thanks so much for the tool! It works amazing   
Is there any chance to support the hair curves too?
Yeah, I'm trying to disassemble the format of hair files. But it can take a long time, as I am very busy now.
If somebody know anything about structure of this files, please, tell me. My thought that is nvidia hairworks, but I still don't read specifications.
## Post #102
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2017-09-18T16:52:27+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

> Reply from aspadm
>
> o0Crofty0o wrote:Thanks so much for the tool! It works amazing   
Is there any chance to support the hair curves too?
Yeah, I'm trying to disassemble the format of hair files. But it can take a long time, as I am very busy now.
If somebody know anything about structure of this files, please, tell me. My thought that is nvidia hairworks, but I still don't read specifications.

Take your time, it's just nice to know someone has interest doing it at all.   

Deus Ex uses PureHair from AMD, it is also known as [TressFX](https://en.wikipedia.org/wiki/TressFX) 3.0. There's a dev presentation on its useage in Deus Ex but not much info on the file structure: [http://cdn.wccftech.com/wp-content/uplo ... FX-3-0.pdf](http://cdn.wccftech.com/wp-content/uploads/2015/03/Augmented-Hair-in-Deus-Ex-Universe-Projects-TressFX-3-0.pdf)

The Tomb Raider reboot from 2013 used TressFX version 1 and the format was a lot simpler. I don't know if it is of any help for comparison to the newer version but here is the TressFX file for TR: [https://yadi.sk/d/Yu0dBevj3MzdwQ](https://yadi.sk/d/Yu0dBevj3MzdwQ)
There's also this presentation on it: [https://de.slideshare.net/WolfgangEngel ... ider-final](https://de.slideshare.net/WolfgangEngel/hair-intombraider-final) but the specifications changed (16 vertices lenght for all strands doesn't apply to newer versions anymore i think)
A friend of mine managed to get bezier curves imported into Blender from that file. It's possible to generate meshes from those:


Additionally AMD released this: [https://github.com/GPUOpen-Effects/TressFX](https://github.com/GPUOpen-Effects/TressFX) but it is version 4 already and possibly different to Deus Ex aswell.
## Post #103
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2017-09-18T16:59:59+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

The way those curves were imported was by manually copying and pasting the vertices point locations into a script like below (this script has around 1500 of these, and here I'm only showing two, there is a lot of strands/curves to import and I'm sure Deus Ex will have more). This might be able to give you an idea on how the curves work.

```
from mathutils import Vector 
  
w = 1 # weight  
listOfVectors = [Vector((-6.635117,1.653948,-3.323807)),Vector((-6.626816,2.027992,-3.724991)),Vector((-6.613327,2.308923,-4.204987)),Vector((-6.594235,2.576662,-4.681885)),
        Vector((-6.558660,2.786073,-5.189697)),Vector((-6.508052,2.973230,-5.703522)),Vector((-6.424452,3.114432,-6.228149)),Vector((-6.320928,3.202100,-6.760651)),
        Vector((-6.203422,3.178222,-7.299698)),Vector((-6.103159,3.000197,-7.811737)),Vector((-6.021204,2.710953,-8.272842)),Vector((-5.938305,2.379366,-8.702637)),
        Vector((-5.836701,2.048806,-9.129242)),Vector((-5.742608,1.708384,-9.550400)),Vector((-5.702582,1.324819,-9.941681)),Vector((-5.683345,0.926187,-10.320999))]
  
def MakePolyLine(objname, curvename, cList):  
    curvedata = bpy.data.curves.new(name=curvename, type='CURVE')  
    curvedata.dimensions = '3D'  
  
    objectdata = bpy.data.objects.new(objname, curvedata)  
    objectdata.location = (0,0,0) #object origin  
    bpy.context.scene.objects.link(objectdata)  
  
    polyline = curvedata.splines.new('NURBS')  
    polyline.points.add(len(cList)-1)  
    for num in range(len(cList)):  
        x, y, z = cList[num]  
        polyline.points[num].co = (x, y, z, w)  
  
    polyline.order_u = len(polyline.points)-1
    polyline.use_endpoint_u = True
    
  
MakePolyLine("NameOfMyCurveObject", "NameOfMyCurve", listOfVectors)

w = 1 # weight  
listOfVectors = [Vector((-6.033971,2.917804,-4.779190)),Vector((-6.371659,3.087809,-4.774216)),Vector((-6.026512,3.690067,-5.414322)),Vector((-5.878336,3.830332,-5.717117)),
        Vector((-5.661849,4.022390,-6.160217)),Vector((-5.475732,4.103107,-6.612518)),Vector((-5.301621,4.134255,-7.082443)),Vector((-5.154976,4.085114,-7.561050)),
        Vector((-5.069383,3.928407,-8.029999)),Vector((-5.054573,3.703187,-8.477707)),Vector((-5.080958,3.469792,-8.920242)),Vector((-5.107432,3.226686,-9.357407)),
        Vector((-5.114311,2.957879,-9.780441)),Vector((-5.103921,2.670656,-10.190857)),Vector((-5.081414,2.371468,-10.592010)),Vector((-5.053456,2.066906,-10.989090))]
  
def MakePolyLine(objname, curvename, cList):  
    curvedata = bpy.data.curves.new(name=curvename, type='CURVE')  
    curvedata.dimensions = '3D'  
  
    objectdata = bpy.data.objects.new(objname, curvedata)  
    objectdata.location = (0,0,0) #object origin  
    bpy.context.scene.objects.link(objectdata)  
  
    polyline = curvedata.splines.new('NURBS')  
    polyline.points.add(len(cList)-1)  
    for num in range(len(cList)):  
        x, y, z = cList[num]  
        polyline.points[num].co = (x, y, z, w)  
  
    polyline.order_u = len(polyline.points)-1
    polyline.use_endpoint_u = True
    
  
MakePolyLine("NameOfMyCurveObject", "NameOfMyCurve", listOfVectors)
```
## Post #104
- Username: aspadm
- Rank: advanced
- Number of posts: 52
- Joined date: Thu Nov 26, 2015 3:43 am
- Post datetime: 2017-09-18T19:30:23+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

Hmm, this looks very useful  Big thanks
Looks like python script has a doubled piece of code - might it be an error? Few days later, I'll try to do something with it. 
Anyway, I have plans to make Adam's cosplay, so I'll try hard to write hair converter 

UPD: in sources of TressFX-3.1.1 I found description of .sdkmesh file format. And examples of this files very similar to .hair files from DEMD
## Post #105
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2017-09-18T19:32:43+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

Yeah the code is copied and pasted multiple times, with the point locations added in differently each time, I believe it was the only way to make the script work since I haven't worked with scripts like that before.
## Post #106
- Username: SmiffinWeffin
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Feb 01, 2017 1:57 pm
- Post datetime: 2017-09-30T15:41:04+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

> Reply from aspadm
>
> And there are new version of DEMD database: https://yadi.sk/d/qUxdTmJa3MxHEs
I strongly reccomend to delete old program folder and unzip this new one - some libs were changed.

What's new?
1. Fix problems with OpenGL shader
2. Add .apx file support (only clothes) - including UV coords
3. Other fixes

If you have some issues or you need sources - contact me.

P.S. Clothes can be exported to STL/OBJ and APB format (Nvidia APEX 1.3.x)

Hey, many thanks for this excellent tool!  I've been poking at it off and on for several days now.

There are a few issues I'd like to bring to your attention though:

1.  I'm not sure is this applies to all ".linkedprim" files, or just the ones I've extracted and tried, but it seems they do not have intact UVs once imported into blender.  This is especially noticeable for the weapons, since the UV maps for all the .prim parts will be fine, but the weapon "base" (usually the grip and trigger) will either have a broken UV map or no UV map whatsoever, since the weapon bases are always .linkedprim files.

2.  A minor functionality issue: After unpacking and opening the archive for the main game, I eventually realized that the DLC content had not been included, so I went back and found it in "Deus Ex Mankind Divided/DLC/runtime" and ran the unpacker on this folder, unpacking it to a different folder than the one the main game's archive was unpacked to.  However, once I opened the unpacked DLC archive, I found that I could no longer use the "Open unpacked DB" function to re-open the main game archive... when I click it, nothing comes up at all, it just seemingly refreshes the DLC archive I have open.

EDIT: Was able to work around the second issue by editing the "last base" field of the config file.
## Post #107
- Username: aspadm
- Rank: advanced
- Number of posts: 52
- Joined date: Thu Nov 26, 2015 3:43 am
- Post datetime: 2017-09-30T16:10:32+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

Thanks for your interest 

1) I just use Volfin's blender addon as model importer. He and I know about this problem, but:
- he haven't time for it
- I didn't try to understand this format
So, sorry. If somebody fix it, please, share your code.

2) Yeah, it's because this tool was made for peoples comfort  Once open the base, program will open it all time as "converted_base.txt" exist or before deletting/changing key "last_base" in config file.
## Post #108
- Username: Feregorn
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Oct 06, 2017 1:31 am
- Post datetime: 2017-10-05T17:41:49+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

> Reply from o0Crofty0o
>
> 
Deus Ex uses PureHair from AMD, it is also known as TressFX 3.0. There's a dev presentation on its useage in Deus Ex but not much info on the file structure: http://cdn.wccftech.com/wp-content/uplo ... FX-3-0.pdf

The Tomb Raider reboot from 2013 used TressFX version 1 and the format was a lot simpler. I don't know if it is of any help for comparison to the newer version but here is the TressFX file for TR: https://yadi.sk/d/Yu0dBevj3MzdwQ

Hi, the .mesh file you posted is the one shown in the picture? How to export it to a common 3d file format?

Edit: I searched online and found out about noesis. But it looks messed up and in no way like yours in the picture does. Is there something I am missing?



P.S. Sorry for the offtopic
## Post #109
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2017-10-05T19:45:36+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

> Reply from Feregorn
>
> 
Hi, the .mesh file you posted is the one shown in the picture? How to export it to a common 3d file format?

Edit: I searched online and found out about noesis. But it looks messed up and in no way like yours in the picture does. Is there something I am missing?

P.S. Sorry for the offtopic

Yeah the file in the picture comes from that .mesh but it was not exported with any of the game's scripts because it isn't a real mesh. It's just curve data. My friend was very kind and got the curve data into blender manually, the mesh generated around them is custom made.
## Post #110
- Username: Feregorn
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Oct 06, 2017 1:31 am
- Post datetime: 2017-10-05T21:19:15+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

> Reply from o0Crofty0o
>
> Feregorn wrote:
Hi, the .mesh file you posted is the one shown in the picture? How to export it to a common 3d file format?

Edit: I searched online and found out about noesis. But it looks messed up and in no way like yours in the picture does. Is there something I am missing?

P.S. Sorry for the offtopic

Yeah the file in the picture comes from that .mesh but it was not exported with any of the game's scripts because it isn't a real mesh. It's just curve data. My friend was very kind and got the curve data into blender manually, the mesh generated around them is custom made.

Thank you for the fast response, if I assume correctly, your friend was TRDaz with the post about the script in the previous page? I want to use this hair model for a free mod on nexus. Is it by any chance still available?
## Post #111
- Username: junk angel
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Jan 14, 2010 11:38 pm
- Post datetime: 2017-10-17T12:30:39+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

Hi,
I've been trying to mess around with the DEMD toolset and I can't get it to read any of the weightedprim files. On the other hand it reads and displays the APX clothing files without any issue. It's weir ding me out.

And I can't get blender itself to read the required bin files either. 

Anyone know what might be going on? Feel like there might be a package version difference. If I try to parse the same packages against BMS I get an ARCH expect got BILH error.
## Post #112
- Username: aspadm
- Rank: advanced
- Number of posts: 52
- Joined date: Thu Nov 26, 2015 3:43 am
- Post datetime: 2017-10-17T13:58:37+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

If I understand correctly, we are talking about my program.
Point by point:
1. The rest of the models are displayed correctly? (.prim, .linkedprim) Apex converter writed by me and not require Blender (all another models use Volfin's script)
2. In the folder with the tools lies a portable version of Blender with the Volfin's script. You can check .bin files manually.
3. All ways to the tools in the settings marked in green?
## Post #113
- Username: Gaffers
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Oct 17, 2017 9:40 pm
- Post datetime: 2017-10-17T16:15:42+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

I tried to unpack the runtime folder but it gets to about a third of the way there and then it fails saying "looks like the base conversion failed"
## Post #114
- Username: junk angel
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Jan 14, 2010 11:38 pm
- Post datetime: 2017-10-17T16:52:35+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

> Reply from aspadm
>
> If I understand correctly, we are talking about my program.
Point by point:
1. The rest of the models are displayed correctly? (.prim, .linkedprim) Apex converter writed by me and not require Blender (all another models use Volfin's script)
2. In the folder with the tools lies a portable version of Blender with the Volfin's script. You can check .bin files manually.
3. All ways to the tools in the settings marked in green?

Yeah I should have clarified more. It's your program. It does seem that running the unpacker creates an error message "Base convertion failed" after a certain runtime. I've also tried one of the newer versions of Sir Kaine's unpackers to get everything out, but no dice. 
nevertheless I tested out the following files. 

Using Characters>sidequests>Daria as an example
Daria.asx - opens without issues
material>daria_hair_diff.texture - opens without issues (same for all other tested mats)
daria.wl2 - Does not load correctly. Only the ground plane shows up.

Image - [https://imgur.com/a/JTC52](https://imgur.com/a/JTC52)

in terms of the rest - everything is in the green and the mesh importer is loaded. But cannot see the bin files.
## Post #115
- Username: junk angel
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Jan 14, 2010 11:38 pm
- Post datetime: 2017-10-22T21:57:54+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

So did some more hunting. And it seems to be an issue with DXMDExtract.exe. It seems to parse all the archives within the runtime folder, but seemingly not extract some. 
But it doesn't throw out an error message. 

It even writes the supposed contents into namesmap. Example being  
60643501754326236 00D772F18C009CDC [assembly:/characters/resources/sidequests/helle/helle.wl2?/ground.weightedprim].pc_weightedprim
## Post #116
- Username: E3245
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Jun 20, 2015 9:35 pm
- Post datetime: 2017-11-06T01:18:53+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

> Reply from aspadm
>
> And there are new version of DEMD database: https://yadi.sk/d/qUxdTmJa3MxHEs
I strongly reccomend to delete old program folder and unzip this new one - some libs were changed.

Hello,

I used your program to extract the combat rifle meshes from DX: MD, but the UVs are messed up and are either all over the place or non-existent. The file is called combat_rifle_highres.wl2, or 00CA49666A70C489.bin.

I also have another question. Is it possible at this point to get the rigs for both the characters and weapons? It'd make everyone's life easier when porting this stuff from MD.
## Post #117
- Username: aspadm
- Rank: advanced
- Number of posts: 52
- Joined date: Thu Nov 26, 2015 3:43 am
- Post datetime: 2017-11-06T09:25:19+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

> Reply from E3245
>
> aspadm wrote:And there are new version of DEMD database: https://yadi.sk/d/qUxdTmJa3MxHEs
I strongly reccomend to delete old program folder and unzip this new one - some libs were changed.


Hello,

I used your program to extract the combat rifle meshes from DX: MD, but the UVs are messed up and are either all over the place or non-existent. The file is called combat_rifle_highres.wl2, or 00CA49666A70C489.bin.

I also have another question. Is it possible at this point to get the rigs for both the characters and weapons? It'd make everyone's life easier when porting this stuff from MD.

Hi!
I know about the problem, but I use Volfin's 3d models converter. So, I can't fix this.
Maybe (!) I'll do something with UV in .linkedprim files this winter (just haven't free time now). And if I can disassemble the format by myself, I'll add bones support.
## Post #118
- Username: E3245
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Jun 20, 2015 9:35 pm
- Post datetime: 2017-11-09T01:33:58+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

> Reply from aspadm
>
> 

Hi!
I know about the problem, but I use Volfin's 3d models converter. So, I can't fix this.
Maybe (!) I'll do something with UV in .linkedprim files this winter (just haven't free time now). And if I can disassemble the format by myself, I'll add bones support.

Thanks for the response. I'll wait until the day UVs get implemented.
## Post #119
- Username: synthosc
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Dec 06, 2017 5:59 am
- Post datetime: 2017-12-06T15:46:27+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

Hey guys, i want to say its so amazing we can take a look into DXMD models and textures, big kudos to everyone who worked hard.   

Is there a way to take a look at the maps? or is it just the character models and or props we can extract?

Thanks in advance
## Post #120
- Username: Feregorn
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Oct 06, 2017 1:31 am
- Post datetime: 2017-12-10T12:38:44+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

I found this very interesting and informative article on the Hair technology used in Deux EX MD: [http://www.makinggames.biz/feature/augm ... ,8881.html](http://www.makinggames.biz/feature/augmented-hair-in-deus-ex-universe,8881.html) Even including a code sample. Will this be useful in finally making hair models exportable and editable?
## Post #121
- Username: aspadm
- Rank: advanced
- Number of posts: 52
- Joined date: Thu Nov 26, 2015 3:43 am
- Post datetime: 2017-12-10T13:01:26+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

Feregorn, thank you for this information. It helps understand, how render works, but I don't know, how data packed. BTW, it help me later.

If somebody need, this is the blender script for loading Tomb Raider hair files (don't need to enter numbers by himself)

```
from mathutils import Vector
import struct
 
#w = 1 # weight 
listOfVectors = []
model = open("C:\\Users\\User\\Documents\\test1.hair", "rb")
for i in range(1500):
    arr = []
    for i in range(3):
        buf = model.read(76)
        arr.append(Vector((list(struct.unpack("19f", buf))[:3])))
    
    listOfVectors.append(arr)
model.close()

 
def MakePolyLine(objname, curvename, cList): 
    curvedata = bpy.data.curves.new(name=curvename, type='CURVE') 
    curvedata.dimensions = '3D' 
 
    objectdata = bpy.data.objects.new(objname, curvedata) 
    objectdata.location = (0,0,0) #object origin 
    bpy.context.scene.objects.link(objectdata) 
 
    polyline = curvedata.splines.new('NURBS') 
    polyline.points.add(len(cList)-1) 
    for num in range(len(cList)): 
        x, y, z = cList[num] 
        polyline.points[num].co = (x, y, z, 1) 
 
    polyline.order_u = len(polyline.points)-1
    polyline.use_endpoint_u = True
   
for stred in listOfVectors:
    MakePolyLine("NameOfMyCurveObject", "NameOfMyCurve", stred)
```


Unfortunately, it don't work with DEMD, but I hope, that I can understand file structure
## Post #122
- Username: synthosc
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Dec 06, 2017 5:59 am
- Post datetime: 2017-12-11T14:40:26+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

> Reply from aspadm
>
> Feregorn, thank you for this information. It helps understand, how render works, but I don't know, how data packed. BTW, it help me later.

If somebody need, this is the blender script for loading Tomb Raider hair files (don't need to enter numbers by himself)

what happens when you import a model, the hair mesh is missing or not correctly laid out?
## Post #123
- Username: Gaffers
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Oct 17, 2017 9:40 pm
- Post datetime: 2017-12-22T11:36:16+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

Hi, im a bit of a noob to this but i want to get the 3d models for adams augmentations from the aug menu but im having trouble getting the DEMD database.exe to unpack all the runtime folders, it gets to around half way then comes up with the error "looks like the base conversion failed". im not sure if there is something im doing wrong but im following the help_en.html. is there something im missing and could you explain if there is? Thanks
## Post #124
- Username: aspadm
- Rank: advanced
- Number of posts: 52
- Joined date: Thu Nov 26, 2015 3:43 am
- Post datetime: 2017-12-22T11:53:47+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

My program show this message when converter (Sir Kaine's DEMDextractor) return non-zero code or if it not create "NameMap.txt".
Looks like converter have some troubles with archives from the latest version of game. I use very old version (~month from first release in steam) and it works well.

You can extract game files using Sir Kaine's program manually, and open unpacked database in my program after that.
## Post #125
- Username: Ghosterer
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Dec 04, 2017 5:42 am
- Post datetime: 2017-12-22T12:20:03+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

Hi

I used "DEMD Databse" to extract all data, but it failed after a few minutes (1476 folders extracted for almost 7650 available).
So i extracted the whole 7650 with QuickBMS, but i can't read data with DEMD (for OBJ and texture extraction) because of no  "NameMap.txt" "ExternalResources.txt" "ContainerNameMap.txt" "ResMap.bin".

is there any way to generate them from actual extracted data ?

Thanks for your reply !
## Post #126
- Username: aspadm
- Rank: advanced
- Number of posts: 52
- Joined date: Thu Nov 26, 2015 3:43 am
- Post datetime: 2017-12-22T12:31:37+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

QuickBMS script not give names for extracted files + it decompress some types wrong.

You can try to unpack files using Sir Kane's extractor, and if (when) error occure just  remove file that cause error and restart extractor (of cource, some data will be missed in my app).
Or you can try to tell him (Sir Kane) about this problem
## Post #127
- Username: Ghosterer
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Dec 04, 2017 5:42 am
- Post datetime: 2017-12-22T15:04:52+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

Thank you for the reply.
The problem is that it seems QuickBMS extract data from .archive (from runtime folder) which is larger and contain the whole obj and textures files, while "DEMD Database" seems extracting data from the ".pc_headerlib" folders (data extracted from DEMD Databse is the exact content from those folders). 

Am i right ?
## Post #128
- Username: aspadm
- Rank: advanced
- Number of posts: 52
- Joined date: Thu Nov 26, 2015 3:43 am
- Post datetime: 2017-12-22T15:16:14+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

Firstly, my app don't extract anything, it's just run 3rd party console program (DEMDextract by Sir Kane) 

Secondly, all variants unpack files from .archive, it need about 23gb. But Sir Kane's extractor also use .pc_headerlib files to create index with names (NameMap.txt) which is used in my program.

QuickBMS script unpack some files incorrectly, I saw it by myself when writing texture converter. It cut or make files too long.

P.S.
There are piece of code that runs convertion

```
    // game_folder - user input, runtime folder
    // path - user input, folder for storing extracted base
    res = subprocess.call([unpacker, game_folder, path], shell=False)
    if res != 0 or not os.path.isfile(path+"NameMap.txt"):
        error_mess = QMessageBox.critical(
            None, app.translate("ConvertError", "Convertion error"),
            app.translate("ConvertErrorText",
                          "Looks like base convertion failed.\nCheck your actions and/or read help."))

```
## Post #129
- Username: Gaffers
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Oct 17, 2017 9:40 pm
- Post datetime: 2017-12-22T15:29:56+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

does this mean the DEMD database.exe wont work with the new version of mankind divided unless sir kane makes it or is there a work around because i tried to open the extractor from the tools folder but it closes straight away.
## Post #130
- Username: aspadm
- Rank: advanced
- Number of posts: 52
- Joined date: Thu Nov 26, 2015 3:43 am
- Post datetime: 2017-12-22T15:35:02+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

> Reply from Gaffers
>
> does this mean the DEMD database.exe wont work with the new version of mankind divided unless sir kane makes it or is there a work around because i tried to open the extractor from the tools folder but it closes straight away.

First one. If Sir Kane fix DEMDextract, my app will be work again

Window closes because you need to open program in console (shift + rmb in folder with program, after that type: DEMDextract.exe "full path to runtime folder" "full path to export folder")
## Post #131
- Username: Gaffers
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Oct 17, 2017 9:40 pm
- Post datetime: 2017-12-23T12:33:29+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

I messaged Sir Kane to see if he can fix it but ive used the extractor manually through command prompt and have been able to get all the files and name tree on your Deus ex Database.exe. Thanks guys
## Post #132
- Username: aspadm
- Rank: advanced
- Number of posts: 52
- Joined date: Thu Nov 26, 2015 3:43 am
- Post datetime: 2018-01-20T19:55:04+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

Ok guys, looks like .linkedprim files now with working UVs 



Updated version below

If you use my DEMD Database, you need to replace "__init__.py" and "import_DeusExMD.py" files in folder "tools\Blender\2.78\scripts\addons\io_scene_DeusEx-MD" by new version. Closing the program is not necessary, the update will work right away.

If nothing change, I'll look at rig data.
## Post #133
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2018-01-21T18:22:59+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

Aspadm came to me with the idea for his fix, but I wanted to implement it in the right way. I guess in his enthusiasm, He went ahead and released his version.  I however recommend you use this version, as it integrates the fix so as to not break other existing formats.

I thank Aspadm for his efforts in finding a solution.
[io_scene_DeusEx-MD.zip](https://xentaxbackup.github.io/file/13826_io_scene_DeusEx-MD.zip)
## Post #134
- Username: MikkelMikkelsen
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Feb 15, 2018 1:14 am
- Post datetime: 2018-02-14T17:36:06+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

You guys are doing really neato work
## Post #135
- Username: iero79
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Apr 18, 2017 2:46 am
- Post datetime: 2018-02-20T11:10:31+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

Hello friends.
I don't know English, so I'm using an online translator to communicate with you.
I'll try to be brief.
I know that this thread has not been answered for a long time, but I think it is the most suitable for receiving help.
I'm trying to understand everything they say, but it's impossible.
What I try to do is NOT extract 3d models and then edit them.
I would be interested in extracting the load animation, and saved from games. Yes, the one that is a triangle that turns on itself, and makes like mini triangles, in a loop.
Since I can't do it, because I don't know what tools I have to use either, I hope you'll help me, at least tell me which tools, and I'll find them myself.
I have managed to extract an animation from the bk2 videos, but it doesn't work for me, it has very little definition, I imagine that in the pc_headerlib files should be the other 2 or 3 animations remaining.
Thank you, and a greeting.

Translated with [www.DeepL.com/Translator](http://www.DeepL.com/Translator)
## Post #136
- Username: aspadm
- Rank: advanced
- Number of posts: 52
- Joined date: Thu Nov 26, 2015 3:43 am
- Post datetime: 2018-02-20T11:59:53+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

Hi there, iero79!

That animation splitted between texture files and .swf elements (user interface). You can find this files using DEMD Database program:

1. Download and unzip DEMD Database (some posts above)
2. Create file "unpack_ext.txt" in folder where is file "DEMD database.exe" and write this lines to it:

```
pc_swf
pc_tex
```

3. "File"->"Unpack game DB"
4. "File"->"Open unpacked DB"

Now you can see file tree in left side. Look at files in "UI/Flash/swf" folder: there are a lot of .swf files with interest names.
You need to save needed files using "File"->export functions.

After that you need HEX-editor. Just trim first bytes before 47 46 58 0B bytes (GFX)

Next step is to google and read some articles about SWF/GFX game UI editing (Scaleform GFx). As example, [http://alloutmodding.wikia.com/wiki/.gfx](http://alloutmodding.wikia.com/wiki/.gfx).

Enjoy 

P.S. If you already tryed to use DEMD Database early, you don't need to unpack all game files anew. Just replace step 3 to this: delete file "converted_base.txt" (if exist) in folder where lay "NameMap.txt" (do NOT delete THIS file!)

UPD:

I poked around and write small tool for trimming unused first bytes/change magic and exporting DDS textures from DEMD .swf files. So, you don't need HEX editor to start working with .swf file 
Link: [https://yadi.sk/d/xTps1wLy3Scfcm](https://yadi.sk/d/xTps1wLy3Scfcm)
## Post #137
- Username: iero79
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Apr 18, 2017 2:46 am
- Post datetime: 2018-02-20T18:23:40+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

> Reply from aspadm
>
> Hi there, iero79!

That animation splitted between texture files and .swf elements (user interface). You can find this files using DEMD Database program:

1. Download and unzip DEMD Database (some posts above)
2. Create file "unpack_ext.txt" in folder where is file "DEMD database.exe" and write this lines to it:
Code: Select allpc_localized-swf
pc_swf
pc_tex
3. "File"->"Unpack game DB"
4. "File"->"Open unpacked DB"

Now you can see file tree in left side. Look at files in "UI/Flash/swf" folder: there are a lot of .swf files with interest names.
You need to save needed files using "File"->export functions.

After that you need HEX-editor. Just trim first bytes before 47 46 58 0B bytes (GFX)

Next step is to google and read some articles about SWF/GFX game UI editing (Scaleform GFx). As example, http://alloutmodding.wikia.com/wiki/.gfx.

Enjoy 

P.S. If you already tryed to use DEMD Database early, you don't need to unpack all game files anew. Just replace step 3 to this: delete file "converted_base.txt" (if exist) in folder where lay "NameMap.txt" (do NOT delete THIS file!)

Hi, I'm finding it very useful, but I'm stranded.

I get to the point where I have to do the hexadecimal edition, where I've tried many combinations of deleting the first characters, but I can't get "RABCDAsm" to do its job, always throws me error.
In UltraEdit I have tested searches for the digits you mention, and they don't appear in any of the extracted files.

Attached is a screenshot of one of the "swf" open in "UltraEdit", to see if any of you are able to see where the error is.

P.S. I've had enough of Google searches, but I don't think I'm looking good, because the information I find doesn't guide me at all.
Excuse my clumsiness, I'm a rookie.
[scrshoot ultraedit.png](https://xentaxbackup.github.io/file/13942_scrshoot ultraedit.png)
## Post #138
- Username: aspadm
- Rank: advanced
- Number of posts: 52
- Joined date: Thu Nov 26, 2015 3:43 am
- Post datetime: 2018-02-20T18:44:39+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

> Reply from iero79
>
> 
In UltraEdit I have tested searches for the digits you mention, and they don't appear in any of the extracted files.

It's my fault... You need to trim bytes before GFX text (bytes 47 46 58, it's in middle of screen) on the right panel of HEX editor. After that, replace this letters to FWS.

But when you've writing this post, I wrote a tool, that do this operations automatically  See updated post below.
## Post #139
- Username: iero79
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Apr 18, 2017 2:46 am
- Post datetime: 2018-02-21T10:33:13+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

Thanks to the help of aspadm, I was able to extract all the files I was interested in.
But there's one thing I don't understand, why do I get dds and swf files separately, and I can't see or find the images in the swf?
I mean, I get two files, but the extracted images, you can't see them inside the swf, is there any explanation for this?, is there the possibility of inserting those images into the swf?, because I'm thinking that, you don't see them, or find them because they have been extracted.

Thank you again, and forgive my ignorance.

P.S. the images are seen inside the swf as a red square, that's what I mean.
[scrshoot.png](https://xentaxbackup.github.io/file/13944_scrshoot.png)
## Post #140
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2018-02-22T14:05:59+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

It's just an optimization, since images embedded in SWF are either JPEG or zlib compressed. Loading whatever native engine format is typically faster.
## Post #141
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-07-24T19:29:40+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

Pure Hair research almost complete. Tools will be available soon.
## Post #142
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-08-02T08:24:42+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

model/hair tools release here 
[viewtopic.php?f=16&t=18534](http://forum.xentax.com/viewtopic.php?f=16&t=18534)
## Post #143
- Username: TheMaestro55555
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Aug 30, 2018 2:34 am
- Post datetime: 2018-08-29T18:38:38+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

Hi friends! Did anyone can help me with Game.layer.1.all.archive from DXMD.
I using HEX editor, edit some values like stack of items and sizes of items, but i cant find all.
I dont know this:
How edit weapons height? (all weapons have height "2", but i cant find how edit this)
How edit pistols width? (10mm,Revolver and Stun Gun, i cant find them)
How edit wight of ammo from weapons? (9mm,10mm,5,56mm,40mm and other)
All this i think must be inside Game.layer.1.all.archive, but i cant find it(  
Maybe some one can help?
## Post #144
- Username: hydin
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jan 02, 2016 1:48 pm
- Post datetime: 2018-10-05T02:33:09+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

Edit - Bought the game, managed to get the masks found. Big thanks for all the tools and instructions in the thread!
## Post #145
- Username: AzothRaven
- Rank: beginner
- Number of posts: 28
- Joined date: Tue Mar 09, 2021 7:23 pm
- Post datetime: 2021-04-01T09:25:24+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

> Reply from aspadm ↑Tue Feb 20, 2018 7:59 pm at Tue Feb 20, 2018 7:59 pm
>
> 
Hi there, iero79!

That animation splitted between texture files and .swf elements (user interface). You can find this files using DEMD Database program:

1. Download and unzip DEMD Database (some posts above)
2. Create file "unpack_ext.txt" in folder where is file "DEMD database.exe" and write this lines to it:
Code: Select allpc_localized-swf
pc_swf
pc_tex
3. "File"->"Unpack game DB"
4. "File"->"Open unpacked DB"

Now you can see file tree in left side. Look at files in "UI/Flash/swf" folder: there are a lot of .swf files with interest names.
You need to save needed files using "File"->export functions.

After that you need HEX-editor. Just trim first bytes before 47 46 58 0B bytes (GFX)

Next step is to google and read some articles about SWF/GFX game UI editing (Scaleform GFx). As example, http://alloutmodding.wikia.com/wiki/.gfx.

Enjoy 

P.S. If you already tryed to use DEMD Database early, you don't need to unpack all game files anew. Just replace step 3 to this: delete file "converted_base.txt" (if exist) in folder where lay "NameMap.txt" (do NOT delete THIS file!)

UPD:

I poked around and write small tool for trimming unused first bytes/change magic and exporting DDS textures from DEMD .swf files. So, you don't need HEX editor to start working with .swf file 
Link: https://yadi.sk/d/xTps1wLy3Scfcm

Hi Espadm! 
Frist of all wanted to thank you for the tool for Deus Ex Mankind Divided! I ma noob in this community and i´m using it, but just after unpacking it I get an error and I cannot progress, here are screenshots of what happens, could you please help me a little?
I think that the NameMap.txt. is not getting created but I have no idea why or how to fix it.
## Post #146
- Username: aspadm
- Rank: advanced
- Number of posts: 52
- Joined date: Thu Nov 26, 2015 3:43 am
- Post datetime: 2021-04-01T09:29:36+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

> Reply from AzothRaven ↑Thu Apr 01, 2021 5:25 pm at Thu Apr 01, 2021 5:25 pm
>
> 
I think that the NameMap.txt. is not getting created but I have no idea why or how to fix it.

Hi!
It's an old problem in my program. It's a false positive message, i.e. in reality unpacking completed.
You must just open created NameMap.txt (Open unpacked DB).
## Post #147
- Username: Goeuff
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Jul 16, 2021 3:48 am
- Post datetime: 2021-07-15T20:34:45+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

Hi, sorry if I come off as ret*rded but can someone give me concise instructions on how to get the models and textures from the files?
I've already gotten the huge collection of .dat (and other) files, now what?
Also I don't know if it's my fault but I can't find the "updated versions" of volfin's script.
Thank you in advance!
## Post #148
- Username: aspadm
- Rank: advanced
- Number of posts: 52
- Joined date: Thu Nov 26, 2015 3:43 am
- Post datetime: 2021-07-15T20:50:16+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

> Reply from Goeuff ↑Fri Jul 16, 2021 4:34 am at Fri Jul 16, 2021 4:34 am
>
> 
I've already gotten the huge collection of .dat (and other) files, now what?

There is not a big amount of GUI tools, so I can recommend DEMD DB program (latest build: [https://yadi.sk/d/qUxdTmJa3MxHEs](https://yadi.sk/d/qUxdTmJa3MxHEs)).
It allows to preview and convert textures, most of models formats, FSB (audio) files.

If you used SirKane's script to unpack files, you have directory with file "NameMap.txt" inside it. In that case simply open this file from DEMD DB ("Open unpacked game").
If not, just read help from program. The only remark is that it give an error after unpacking - just skip that message.

P.S. I'm now writing more stable standalone version from scratch, but it may take a lot of time to finish it.
## Post #149
- Username: Goeuff
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Jul 16, 2021 3:48 am
- Post datetime: 2021-07-15T20:55:31+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

> Reply from aspadm ↑Fri Jul 16, 2021 4:50 am at Fri Jul 16, 2021 4:50 am
>
> 
Goeuff wrote: ↑Fri Jul 16, 2021 4:34 am
I've already gotten the huge collection of .dat (and other) files, now what?


There is not a big amount of GUI tools, so I can recommend DEMD DB program (latest build: https://yadi.sk/d/qUxdTmJa3MxHEs).
It allows to preview and convert textures, most of models formats, FSB (audio) files.

If you used SirKane's script to unpack files, you have directory with file "NameMap.txt" inside it. In that case simply open this file from DEMD DB ("Open unpacked game").
If not, just read help from program. The only remark is that it give an error after unpacking - just skip that message.

P.S. I'm now writing more stable standalone version from scratch, but it may take a lot of time to finish it.
Thank you so much for the link and for the quick reply
## Post #150
- Username: samboychips
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Sep 07, 2020 4:04 pm
- Post datetime: 2021-09-03T04:43:20+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

Sorry to dredge up an old thread, but if anyone here still has Sir Kane's DEMDextractor and can repost it here, that would be amazing. The original link isn't valid anymore and I can't seem to find it anywhere else!
## Post #151
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2021-09-11T18:05:23+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

The URL changed slightly. Here's the updated one:
[https://sktest.aruarose.com/DXMDExtract_v002.7z](https://sktest.aruarose.com/DXMDExtract_v002.7z)
## Post #152
- Username: momo1
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Nov 28, 2021 9:05 am
- Post datetime: 2021-12-07T02:12:43+00:00
- Post Title: Re: Deus EX: Mankind Divided .archive

@Sir Kane
Do you have a tool or know how to import the textures back into the game?
