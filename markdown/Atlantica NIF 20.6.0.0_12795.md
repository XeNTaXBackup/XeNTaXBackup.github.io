## Post #1
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2015-04-24T22:28:45+00:00
- Post Title: Atlantica NIF 20.6.0.0

Hello community, well today I going to check the Atlantica files but for some reason I see mayor part of models won't load, so I checking via hex what happened and see the header files was changed to Gamebryo File Format, Version 20.6.0.0 to NDSNIF....@....@...., Version 20.6.0.0.__es..............., ok so now what I do is change the header for the one is loaded but anyway won't load, so my question is if can take a look, really grateful for thats guys, have a nice day.



[https://cloud.mail.ru/public/36iPWDNHSp ... Samples.7z](https://cloud.mail.ru/public/36iPWDNHSpqF/Atlantica%20NIF%20Samples.7z)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-04-25T05:58:01+00:00
- Post Title: Atlantica NIF 20.6.0.0

> Reply from CriticalError
>
> so I checking via hex what happened and see the header files was changed to Gamebryo File Format, Version 20.6.0.0 to NDSNIF....@....@...., Version 20.6.0.0.__es"to..to"?, mean: "from..to"? 
From what I see it's NDSNIF since October 2009 (at least for the AFELEPHANTF1.NIF).
[viewtopic.php?f=18&t=9914&p=81327#p81327](http://forum.xentax.com/viewtopic.php?f=18&t=9914&p=81327#p81327)

> the one is loaded but anyway won't load,a contradiction in terms... 



AFElephantF1_.JPG (76.65 KiB) Viewed 379 times
## Post #3
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2015-04-26T01:25:45+00:00
- Post Title: Atlantica NIF 20.6.0.0

> Reply from shakotay2
>
> CriticalError wrote:so I checking via hex what happened and see the header files was changed to Gamebryo File Format, Version 20.6.0.0 to NDSNIF....@....@...., Version 20.6.0.0.__es"to..to"?, mean: "from..to"? 
From what I see it's NDSNIF since October 2009 (at least for the AFELEPHANTF1.NIF).
viewtopic.php?f=18&t=9914&p=81327#p81327
the one is loaded but anyway won't load,a contradiction in terms... 
AFElephantF1_.JPGummmm well interesting view, so my question is, is possible modify the python script of noesis for support 20.6 version?
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-04-26T13:41:20+00:00
- Post Title: Atlantica NIF 20.6.0.0

> Reply from CriticalError
>
> ummmm well interesting view, so my question is, is possible modify the python script of noesis for support 20.6 version?I didn't care and wrote my own tool:


 Make_H2O-AtlanticaOnl.zip
(51.67 KiB) Downloaded 66 times


[](http://www.pic-upload.de/view-26841353/AncientGiant.jpg.html)

Items not supported.
So I finally had a look at fmt_Gamebryo_nif.py which seemed to be written by the master himself (whoever it is, guess Rich aka MrAdults)

There's a simple workaround, just comment out these lines:
#if "File Format" not in headerString:
#	return 0

Then the Amazone and Agamemnon will load even with the skeleton shown (F6).
The AncientGiantF1 will crash the script.

You've been warned! Use this tip on your own risk.

(well, when I see Agamemnon - holding his sword correctly with the Noesis script and with my tool not
 I have to realize I never, never will become a pro, but it's me who can load the Giant,   )
## Post #5
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2015-04-26T20:31:58+00:00
- Post Title: Atlantica NIF 20.6.0.0

Well, yeah, you can't just comment those lines out. That'll leave garbage for the file version, which means all of the version checks will be wrong, and you're lucky anything happened to load. If you make it parse the proper version out of the string and pick up in the right place to parse the object count it will work just fine in Noesis with every sample there. It'll be handled in the script whenever I put a new build up.
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-04-27T09:14:51+00:00
- Post Title: Atlantica NIF 20.6.0.0

I see. I've made another hack to load the AncientGiant:

in def loadHeader(self)
after
self.fileVer = bs.readUInt()

```
    self.fileVer=335937536
```

(take care of the indentation)



AncientGiant_Noesis.JPG (66.78 KiB) Viewed 326 times


Tried items:
Bow205.nif works (a cube to be deleted?)
Bow291 is flat but I won't care for that.

---------------
This is a patch to load version 20.2.0.8 NDSNIF:

```
			self.fileVer=335675400
```


Successfully tested with: Alcaes4, Alexandra, AllroundMechB1, Anastasya

That's so simple that I wonder why noone interested in these models (I'm not) did this patch since about half a year or so?
(MrAdults was too busy, marrying and so on, I know  )

As always: use this ugly hack on your own risk. Don't blame Noesis.

(The "File Format" check must be commented out as mentioned above for these patches to work.)
## Post #7
- Username: CriticalError
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2015-04-27T20:40:10+00:00
- Post Title: Atlantica NIF 20.6.0.0

None of that is necessary, or right. If you really can't wait for me to get a new build up, just use this instead.

```
		bs = self.bs
		self.isNDSNIF = False
		try:
			headerInfo = bytearray()
			while not bs.checkEOF():
				b = bs.readBytes(1)
				if b[0] == 0x0A:
					break
				headerInfo += b
			headerString = nifStrFromBytes(headerInfo)
			if "File Format" not in headerString:
				if "NDSNIF" in headerString:
					bs.setOffset((bs.getOffset() + 15) & ~15)
					self.isNDSNIF = True
					#default the file version of NDSNIF, then try to parse it out of the string if possible
					self.fileVer = nifVersion(20, 2, 0, 8)
					verPos = headerString.find("Version ")
					if verPos >= 0:
						verString = headerString[verPos + 8:]
						versionValues = [int(x) for x in verString.split('.')]
						self.fileVer = nifVersion(*versionValues)
				else:
					return 0
			self.header = headerString
		except:
			return 0

		if self.isNDSNIF:
			self.isLittleEndian = True
			self.userVersion = 0
		else:
			self.fileVer = bs.readUInt()
			if self.fileVer >= nifVersion(20, 0, 0, 3):
				self.isLittleEndian = bs.readUByte() > 0
			else:
				self.isLittleEndian = True
			
			if self.fileVer >= nifVersion(10, 0, 1, 8):
				self.userVersion = bs.readUInt()
			else:
				self.userVersion = 0
			
		self.numObjects = bs.readInt()
		if self.numObjects <= 0:
			return 0
		
		self.objects = []
		for i in range(0, self.numObjects):
			self.objects.append(NifObject(self, i))

		if self.isLittleEndian is not True:
			bs.setEndian(NOE_BIGENDIAN)
			
		return 1
```
## Post #8
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2015-04-28T12:03:38+00:00
- Post Title: Atlantica NIF 20.6.0.0

many thanks guys but after add it, I got this error if change the name of the .py, anyway if leave default name in .pu like fmt_gamebryo_nif.py it load but when go to load models, I got File could not be previewed.
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-04-28T13:31:17+00:00
- Post Title: Atlantica NIF 20.6.0.0

That's very obviously an indentation error that you have.

But as you seem to ignore my advice via pm nor do even try to understand it I will stop my support for YOU.

(Sry, my time is too limited as to waste it.  )
## Post #10
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2015-04-28T16:36:35+00:00
- Post Title: Atlantica NIF 20.6.0.0

> Reply from shakotay2
>
> That's very obviously an indentation error that you have.

But as you seem to ignore my advice via pm nor do even try to understand it I will stop my support for YOU.

(Sry, my time is too limited as to waste it.  )I don't ignore you mate, I test yours too and got same error there, no idea what happening, I download clean noesis and modify gamebryo py adding this what you told me or Mr.Adults, but anyway still getting errors, no matter what I do, always give me error or just won't load models.
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-04-28T17:18:01+00:00
- Post Title: Atlantica NIF 20.6.0.0

seems you don't know what correct indentation means for a python script:



py_indentation.JPG (87.58 KiB) Viewed 282 times


Proper indentation is required for a python script to work.

Move the def LoadHeader(self): line (marked by the arrow) so that it matches the tab line.
All the lines from xentax forum code have to be handled.

Don't mix blanks and tabs - just use one of them for indentation.
Also there might be different tab sizes in different editors (4 columns or 8 columns for example).
## Post #12
- Username: ilovechii
- Rank: beginner
- Number of posts: 30
- Joined date: Wed Aug 13, 2014 12:49 am
- Post datetime: 2015-04-29T15:12:24+00:00
- Post Title: Atlantica NIF 20.6.0.0

Someone can help me?

I'm need use Noesis 3D in other game, but have same version from the Gamebryo 2.6.
So, I can load my *.nif, but I can't load animations.

Example: [https://mega.co.nz/#!b4hBDZxD!KzgiwcA8a ... qsaGCt6Xbc](https://mega.co.nz/#!b4hBDZxD!KzgiwcA8aYHdwmIFgVvA6kxpFNtnUTt1kqsaGCt6Xbc)

Thanks,
Cheers.
## Post #13
- Username: jumpjack
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Apr 25, 2020 9:44 pm
- Post datetime: 2020-04-25T13:50:13+00:00
- Post Title: Atlantica NIF 20.6.0.0

I know this is an ancient thread, but I cannot find any suitable program to properly import version 20.6.0.0 of NIF files.
I would like to "revive" this old model and convert it to make it visible in VR viewers:
[http://3dreamteamvizerra.s3.amazonaws.c ... 0.0%5d.zip](http://3dreamteamvizerra.s3.amazonaws.com/Locations/SanPietro/SanPietro%5B1.0.0.0%5D.zip)

I tried noesis and nifskope 2.0,  but first one can only import some of the NIF files in the package, and nifskope cannot export to any useful format.

The original viewer of this file was called "3DreamTeam vizerra client" back in 2009, but it's hard to find it to download, and all versions I found are not able to properly download the files, as the original server no longer exists.
## Post #14
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2020-04-25T16:04:24+00:00
- Post Title: Atlantica NIF 20.6.0.0

20.6 version is not properly supported in noesis or nifskope , neither 3studio max plugin or blender. 
Unless someone got a script working with this version or a tool to convert them in a previous format, i think it's impossible to load animation file.

p.s: mesh + skeleton should be loaded in noesis.
## Post #15
- Username: jumpjack
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Apr 25, 2020 9:44 pm
- Post datetime: 2020-04-25T16:41:49+00:00
- Post Title: Atlantica NIF 20.6.0.0

I don't need animation, just mesh+textures.
## Post #16
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2020-04-29T18:22:31+00:00
- Post Title: Re: Atlantica NIF 20.6.0.0

send me some samples that doesn't work with nifskope.
## Post #17
- Username: jumpjack
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Apr 25, 2020 9:44 pm
- Post datetime: 2020-05-01T17:32:24+00:00
- Post Title: Re: Atlantica NIF 20.6.0.0

This is a full model:
[http://win98.altervista.org/vizerracom/ ... 0.0.0).zip](http://win98.altervista.org/vizerracom/zip/Christo_Redentor%281.0.0.0%29.zip)

It's 40MB long...
I am able to import in Noesis only Statue_base.nif , but with some errors and without textures.
All other 3 files raise errors.
In Nifskope:
Statue_base.nif is imported properly, but textures are weird.
fog.nif is properly imported
Plastic_Fence.nif is imported but I can't see anything
Panorama.nif raises error.

These are smaller files from another model: I cannot import none of them.
[http://win98.altervista.org/vizerracom/ ... untain.nif](http://win98.altervista.org/vizerracom/nif/Drinking_Fountain.nif)   (30 KB) (not working in Nifskope)
[http://win98.altervista.org/vizerracom/nif/Lamp_3.nif](http://win98.altervista.org/vizerracom/nif/Lamp_3.nif) (25 KB) (not working in Nifskope)

In same model there is this further file (and many others), which is the only one I am able to import both  in Noesis and in Nifskope:
[http://win98.altervista.org/vizerracom/ ... oxView.nif](http://win98.altervista.org/vizerracom/nif/San_Pietro_BoxView.nif)

These are some installers of ancient Vizerra Client which I found around: not all of them work properly; for one of them (can't remember which one, versioning of these files is a mess...) the right folder where to place locations is C:\ProgramData\3DreamTeam\Vizerra\Media\Content\Locations : you must place here the unpacked folder of each model you can find here: [http://web.archive.org/web/201004150750 ... /locations](http://web.archive.org/web/20100415075028/http://vizerra.com/en/locations)


[http://win98.altervista.org/vizerracom/ ... asetup.zip](http://win98.altervista.org/vizerracom/installers/113_vizerrasetup.zip)
[http://win98.altervista.org/vizerracom/ ... tup113.exe](http://win98.altervista.org/vizerracom/installers/vizerrasetup113.exe)
[http://win98.altervista.org/vizerracom/ ... tup120.exe](http://win98.altervista.org/vizerracom/installers/vizerrasetup120.exe)
[http://win98.altervista.org/vizerracom/ ... rs/Vizerra Demo 2011-1.0.0.exe](http://win98.altervista.org/vizerracom/installers/Vizerra%20Demo%202011-1.0.0.exe)
## Post #18
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-05-01T19:51:04+00:00
- Post Title: Re: Atlantica NIF 20.6.0.0

Panorama.nif seems to contain 1 big picture (panorama, surprise!) only, afaics (maybe composed of smaller ones).

Contained 3D data of smaller nif files is simple:
.



Drinking_Fountain-nif.jpg (187.75 KiB) Viewed 183 times


(Seems there's a competition between game defs to make any nif version files unloadable by "external" tools.  )
## Post #19
- Username: jumpjack
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Apr 25, 2020 9:44 pm
- Post datetime: 2020-05-02T08:24:14+00:00
- Post Title: Re: Atlantica NIF 20.6.0.0

> Reply from jumpjack ↑Sat May 02, 2020 4:22 pm at Sat May 02, 2020 4:22 pm
>
> 
shakotay2 wrote: ↑Sat May 02, 2020 3:51 am
Panorama.nif seems to contain 1 big picture (panorama, surprise!) only, afaics (maybe composed of smaller ones).
The file is way too large to contain just a picture, I think it should contain at least a simple geometry (a sphere for sky and maybe some raw mountains).

> Contained 3D data of smaller nif files is simple:
>
> .
>
> Drinking_Fountain-nif.jpg
Is it your own tool or can I find it somewhere?


> (Seems there's a competition between game defs to make any nif version files unloadable by "external" tools.  )
little bastards...  

Any idea about how to load multiple .NIF files together, positioning each model in a specific location? There are .xblock files in Vizerra models, which describe where each .NIF file must be placed.
## Post #20
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-05-02T08:54:31+00:00
- Post Title: Re: Atlantica NIF 20.6.0.0

> Reply from jumpjack ↑Sat May 02, 2020 4:24 pm at Sat May 02, 2020 4:24 pm
>
> The file is way too large to contain just a picture, I think it should contain at least a simple geometry (a sphere for sky and maybe some raw mountains).You're right - there are 401 objects at the end of the . nif file which I didn't notice:
.



plane_dome.png (86.35 KiB) Viewed 165 times



> Is it your own tool or can I find it somewhere?hex2obj, view 2nd link in my sig.

> Any idea about how to load multiple .NIF files together, positioning each model in a specific location? There are .xblock files in Vizerra models, which describe where each .NIF file must be placed.It's xml files (Christo_Redentor.xblock), easy to read:

<?xml version="1.0" encoding="UTF-8"?>
-<game>
-<entitySet>
-<entity iterations="1" name="BanyanBush 95" modelName="[Trees_and_Shubs]BanyanBush" id="00d2a3c17255404dae77d8167e94f610">
-<property name="Position">
<set value="-92.36383, -2.62919044, -24.98885"/>
</property>
-<property name="Rotation">
<set value="8.617883, 24.49822, 69.92125"/>
</property>
</entity>

-------------------------

(You need to find out in which .nif file "BanyanBush 95" (or its id) and others are contained.)
## Post #21
- Username: jumpjack
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Apr 25, 2020 9:44 pm
- Post datetime: 2020-05-02T10:39:47+00:00
- Post Title: Re: Atlantica NIF 20.6.0.0

> Reply from shakotay2 ↑Sat May 02, 2020 4:54 pm at Sat May 02, 2020 4:54 pm
>
> 
jumpjack wrote: ↑Sat May 02, 2020 4:24 pmThe file is way too large to contain just a picture, I think it should contain at least a simple geometry (a sphere for sky and maybe some raw mountains).You're right - there are 401 objects at the end of the . nif file which I didn't notice:
.
plane_dome.png
So did you find any pattern which I can implement into an hex editor to apply to all NIF files? or a reason for which some NIF files can be properly loaded by Noesis and some do not, altough they are same version (20.6.0.0)? 
By the way, I am in trouble with the tutorial included in your tool, because the screenshots do not match with current version of the program.

> Any idea about how to load multiple .NIF files together, positioning each model in a specific location? There are .xblock files in Vizerra models, which describe where each .NIF file must be placed.It's xml files (Christo_Redentor.xblock), easy to read:

I know they are easy to read... that's why I know each NIF file has its own position. But in which program can I load multiple NIF files into one single object? For example, OBJ and STL files hold position information, so if I load multiple files in a 3d viewer, they are all positioned in different locations.
Or maybe a single NIF file can link to  multiple NIF files?
## Post #22
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-05-02T11:47:31+00:00
- Post Title: Re: Atlantica NIF 20.6.0.0

> Reply from jumpjack ↑Sat May 02, 2020 6:39 pm at Sat May 02, 2020 6:39 pm
>
> So did you find any pattern which I can implement into an hex editor to apply to all NIF files?I searched for 0000 0100 0200 (indices of first face) .

> or a reason for which some NIF files can be properly loaded by Noesis and some do not, altough they are same version (20.6.0.0)?The competition, you remember?  Nif is a complex format where devs seem to have many options to create their custom nif format. Nif files contain many nodes and the problem with most conversion tools is, imho, that they break on an unknown node instead of just skipping it.

> By the way, I am in trouble with the tutorial included in your tool, because the screenshots do not match with current version of the program.Yeah, development has been stopped, since there are better tools out now (see Bigchillghost for example). If you tell, which screenshot in special, I could have a look at - but the basic functionality hasn't been changed, afair. (It starts with 'VB' instead of 'seq', just a toogle and 'float' instead of 'noHF', only a renaming, etc).

> I know they are easy to read... that's why I know each NIF file has its own position. But in which program can I load multiple NIF files into one single object?I have no idea. You might try "batch import" in Noesis or something like that.

> Or maybe a single NIF file can link to multiple NIF files?Same as above: "no idea". I'd do it using the Make_obj project, conversion to obj, applying the positions (after having read them from an xblock file). (But I guess u need to maintain the nif specific features, do you?)

> Reply from shakotay2 ↑Mon Mar 06, 2017 6:01 pm at Mon Mar 06, 2017 6:01 pm
>
> (basic knowledge in 'C' required)
## Post #23
- Username: jumpjack
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Apr 25, 2020 9:44 pm
- Post datetime: 2020-05-02T14:21:13+00:00
- Post Title: Re: Atlantica NIF 20.6.0.0

I was trying to write a "structure file" for FlexHex hex editor... but up to now I was only able to setup this .FSD file:

```
{
	char formatString[20];
	char separator1[2];
	char versionNumber[16];
	char unknown1[16];	
   /*struct {
	unsigned DWORD Length;
	char* Param[Length];
    } test[4];  
*/

} 

```


..then I found [this definition of NIF format as XML file](https://github.com/jonwd7/nifxml/blob/develop/nif.xml)... so I gave up defining a structure file for [FlexHex](http://www.flexhex.com/docs/help/complex_types/structures.phtml), it would take months... 
Instead, maybe with your help I could try to amend the existing XML file to make it (and Nifskope) support Vizerra NIF format.
Description of the XML file: [http://niftools.sourceforge.net/wiki/Ni ... XML_Format](http://niftools.sourceforge.net/wiki/Nif_Format/NifTools_XML_Format)

Further info on NIF format:
[http://www.gamesas.com/nif-tools-and-th ... 04919.html](http://www.gamesas.com/nif-tools-and-the-nif-file-format-knowledge-base-t304919.html)
[https://github.com/niftools/nifxml/wiki ... escription](https://github.com/niftools/nifxml/wiki/Extract-data-from-binary-.nif-file-using-the-nif.xml-file-description)
## Post #24
- Username: jumpjack
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Apr 25, 2020 9:44 pm
- Post datetime: 2020-05-02T14:26:06+00:00
- Post Title: Re: Atlantica NIF 20.6.0.0

> Reply from shakotay2 ↑Sat May 02, 2020 7:47 pm at Sat May 02, 2020 7:47 pm
>
> 
By the way, I am in trouble with the tutorial included in your tool, because the screenshots do not match with current version of the program.Yeah, development has been stopped, since there are better tools out now (see Bigchillghost for example). If you tell, which screenshot in special, I could have a look at - but the basic functionality hasn't been changed, afair. (It starts with 'VB' instead of 'seq', just a toogle and 'float' instead of 'noHF', only a renaming, etc).
Both in online and offline toturials the second step is about "start of UVs", while in my version and in your latest screenshot the second step is about  "vertex block":
## Post #25
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-05-02T14:31:12+00:00
- Post Title: Re: Atlantica NIF 20.6.0.0

Thanks for reporting! Start of uvs is the next step in 'seq' mode. (Just toggle the button from 'VB' to 'seq'.) You can handle 'sequential' mode in VB (Vertex block mode), setting FVFsize to 12 (for floats). 'seq' is vary rare but easier to explain. 

Change this:
'We leave the "seq" button as it is because I know that the structure is "sequential".'
to:
'Toggle the "VB" button to "seq" because I know that the structure is "sequential".'
.
.

> Reply from jumpjack ↑Sat May 02, 2020 10:21 pm at Sat May 02, 2020 10:21 pm
>
> Instead, maybe with your help I could try to amend the existing XML file to make it (and Nifskope) support Vizerra NIF format.Well, that's not my project/interest. You may contact jonwd7 for such.

(Usually I'm just a "15 minutes jobber" here.  )
## Post #26
- Username: jumpjack
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Apr 25, 2020 9:44 pm
- Post datetime: 2020-05-13T14:35:38+00:00
- Post Title: Re: Atlantica NIF 20.6.0.0

Version 4.425 of Noesis is unable to open some NIF files with version 20.6.0.0, raising exceptions like "Unreasonable texture list size" and "Unreasonable shader map list size".
After some experiments, I was able to partially fix this issue by preventing Noesis from attempting loading textures.
It's a first step, but also adding textures is important... Unfortunately I don't know anything about textures and NIF files, I was just lucky with this hack.

I attach the modified fmt_gamebryo_nif.py file


 fmt_gamebryo_nif.zip
(20.56 KiB) Downloaded 50 times



Following package contains 4 NIF files; original version of Noesis can only open statue_base.nif. My version can open all of them.
I also tried it with 30 other NIF files incompatible with 4.425, and they all open fine (without textures).

[http://win98.altervista.org/vizerracom/ ... 0.0.0].zip](http://win98.altervista.org/vizerracom/zip/Christo_Redentor%5B1.0.0.0%5D.zip)
## Post #27
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2020-05-14T12:02:50+00:00
- Post Title: Re: Atlantica NIF 20.6.0.0

Thanks man. I will test it this afternoon
## Post #28
- Username: jumpjack
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Apr 25, 2020 9:44 pm
- Post datetime: 2020-05-16T14:20:02+00:00
- Post Title: Re: Atlantica NIF 20.6.0.0

Did it work?
## Post #29
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2020-05-16T14:52:41+00:00
- Post Title: Re: Atlantica NIF 20.6.0.0

it worked only  with atlantica 20.6 and 20.5 mesh and not generally with 20.5 and 20.6 files. But , I mean, that was the purpose of you edit
