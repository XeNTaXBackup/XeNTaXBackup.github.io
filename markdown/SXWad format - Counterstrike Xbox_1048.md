## Post #1
- Username: Rusty_le_Cyborg
- Rank: advanced
- Number of posts: 48
- Joined date: Tue Jan 11, 2005 1:12 am
- Post datetime: 2005-01-10T17:34:51+00:00
- Post Title: SXWad format - Counterstrike Xbox

Hi there

I have been advised to post a request here for support with this file format.

It is the file format used for Counterstrike on the Xbox, but is similar (I would imagine) to the format used in regular Counterstrike.

The sound files are packaged in Xbox soundbanks, but the rest of the files - Maps, Models, Sprites etc are within these files...

They are a little large, but I will attempt to upload a couple of small files with hopefully enough information to get a start on it (or maybe to discount any attempts!)

I have made rar files of the beginning 1 meg and tail end of a couple of the files.

Cheers for now

<edit> 
Can't seem to upload, so I will put the files here...
[http://talisman.clift.org/talismanisland/test/sxwad](http://talisman.clift.org/talismanisland/test/sxwad)
Thanks!
</edit>
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-01-10T22:46:18+00:00
- Post Title: SXWad format - Counterstrike Xbox

Thanks, I 've downloaded them and I can say after a quick glance, that it may be possible to add a script to MultiEx Commander that will extract the files in there. Will have to have a better look to confirm.
## Post #3
- Username: Rusty_le_Cyborg
- Rank: advanced
- Number of posts: 48
- Joined date: Tue Jan 11, 2005 1:12 am
- Post datetime: 2005-01-11T15:52:52+00:00
- Post Title: SXWad format - Counterstrike Xbox

Nice one... well... here's hoping!!

If you need any more information just ask. As I say the files are a little large, usually arounr 50 or 60 megs. But I can always find some way of getting a full one to you... or in fact I could test it test myself 

Cheers for now
## Post #4
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-01-11T22:29:06+00:00
- Post Title: SXWad format - Counterstrike Xbox

Okay, I figured it out. Yet, I can't implement it yet in MultiEx Commander, as my script has a bug i had not detected before that prevents certain variables to be treated the way I want them. I will see if I can write a quick extractor to help you out first. Priority has the new release of MultiEx COmmander though, that will then hopefully also open your files. But if I can find some time a small stand-alone extractor won't be a problem.
## Post #5
- Username: Rusty_le_Cyborg
- Rank: advanced
- Number of posts: 48
- Joined date: Tue Jan 11, 2005 1:12 am
- Post datetime: 2005-01-11T22:35:19+00:00
- Post Title: SXWad format - Counterstrike Xbox

You are a wonder!!

Sounds good to me.... and at least I helped you discover a bug 

I look forward to anything you can help with...

Cheers for now
## Post #6
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-01-13T23:23:20+00:00
- Post Title: SXWad format - Counterstrike Xbox

Well, 

1. I've fixed MultiEx Commander and the next release will open the files
2. I've hastily created SeXWAD, a tool you can use NOW to extract all files in these SXWAD archives. Just point to an archive and select a directory to extract into using "Extract to...". See attachment! Oh, make sure you have MultiEx Commander installed or else it might not work.

Cheers!
[sexwad.zip](https://xentaxbackup.github.io/file/94_sexwad.zip)
## Post #7
- Username: Rusty_le_Cyborg
- Rank: advanced
- Number of posts: 48
- Joined date: Tue Jan 11, 2005 1:12 am
- Post datetime: 2005-01-13T23:46:49+00:00
- Post Title: SXWad format - Counterstrike Xbox

OMG.....

You are an absolute GOD!!

More later!! Too excited!!

Cheers for now

<edit>

There is a slight problem  

The textures that I thought were in these wads don't appear to be. It is likely that they are stored in a file with an "xpr" extension, which I believe Xbox uses for pics etc.

I shall attach one just in case you fancy a look  (PLEASE!)

Other than that, everything else is working really well!!  Damn good job!!

</edit>
[launcher_common.rar](https://xentaxbackup.github.io/file/95_launcher_common.rar)
## Post #8
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-01-14T09:50:17+00:00
- Post Title: SXWad format - Counterstrike Xbox

Okay, please backup your old MC.MRF file in the MultiEx Commander data/config dir, and replace with attached. You can now open xpr files and extract the stuff, EXCEPT for the last file in there. I haven't found a way yet to overcome the format for the last one.

Will release anyway in the next version.  
[mc.rar](https://xentaxbackup.github.io/file/96_mc.rar)
## Post #9
- Username: Rusty_le_Cyborg
- Rank: advanced
- Number of posts: 48
- Joined date: Tue Jan 11, 2005 1:12 am
- Post datetime: 2005-01-14T16:30:19+00:00
- Post Title: SXWad format - Counterstrike Xbox

Nice one 

But 

I can extract files... but those files should be bmps... but they don't seem to be. In fact, they seem to be about half the size they should be... even though they are supposed to be higher quality... I am confused...

Any ideas? 

Great job btw...!!

Cheers for now
## Post #10
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-01-14T17:48:11+00:00
- Post Title: SXWad format - Counterstrike Xbox

Well, that's right though, I didn't find any standard *.BMP in there. Just raw data.
## Post #11
- Username: Rusty_le_Cyborg
- Rank: advanced
- Number of posts: 48
- Joined date: Tue Jan 11, 2005 1:12 am
- Post datetime: 2005-01-14T20:51:17+00:00
- Post Title: SXWad format - Counterstrike Xbox

It's a little strange.

I have found out that.... 

The Xbox executable uses MOST of the origianl counterstrike files to "play" the game...

BUT...

Some things are changed i.e. models use new textures that are contained "elsewhere" namely in these xpr files...

The file structure is as it should be, it's just that they appear to be the wrong size and they are not "readable" by any windows app I have 

I shall attach another example xdr whch will not extract, an example of a file which has been extracted and a supposed overlay of a model texture.

Any more information would be a great help.

Cheers for now

PS - I believe there is something of a problem with xdr files generally. Maybe it's all down to being able to run an Xbox executable? I dunno...

[http://talisman.clift.org/talismanislan ... uzzled.rar](http://talisman.clift.org/talismanisland/test/sxwad/puzzled.rar)  - Can't figure the attach thing again!!!
## Post #12
- Username: Rusty_le_Cyborg
- Rank: advanced
- Number of posts: 48
- Joined date: Tue Jan 11, 2005 1:12 am
- Post datetime: 2005-01-14T21:32:53+00:00
- Post Title: SXWad format - Counterstrike Xbox

Yup... definitely textures in them... I opened one with TextureFinder 2.0 (Tomb Raider Utility). Can't extract them with it though....

They are the same sizes as normal textures, but slightly off-centre 

I could probably manage with doing this and resizing/cropping/putting together, but it'd be nice to be able to just get them out of there 

Cheers for now
[snap.jpg](https://xentaxbackup.github.io/file/97_snap.jpg)
## Post #13
- Username: Rusty_le_Cyborg
- Rank: advanced
- Number of posts: 48
- Joined date: Tue Jan 11, 2005 1:12 am
- Post datetime: 2005-01-14T22:51:24+00:00
- Post Title: SXWad format - Counterstrike Xbox

<EDIT!!>

Actually, these are pretty usable (well the xpr's that can be extracted. 

Strangley I can extra these files (named BMP etc) and then if I load them into Texture Finder I can see them fine 

Quite odd... I gues I will never understand file formats etc!!

Cheers for now
## Post #14
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-01-14T22:51:54+00:00
- Post Title: SXWad format - Counterstrike Xbox

Which XPR is this? Not the one you sent surely?
## Post #15
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-01-14T23:16:23+00:00
- Post Title: SXWad format - Counterstrike Xbox

Ah yes, it works indeed. So, they are DXT3 compressed textures. Good to know. Get yourself the DXTool/Plugin for Photoshop from NVidia I believe and you can edit your own. Just make sure you just copy the data in the DXT3 files (no headers and such).
## Post #16
- Username: Rusty_le_Cyborg
- Rank: advanced
- Number of posts: 48
- Joined date: Tue Jan 11, 2005 1:12 am
- Post datetime: 2005-01-24T21:56:28+00:00
- Post Title: 

These tools are VERY cool Mr. Mouse  

Just having some trouble with the 32 bit bmp textures... just using the Texture Finder to "look" at them, then save them and then open in Photoshop... 

Any idea of a prog that can open them directly? I couldn't get this DTX plug in to work...

Cheers for now
## Post #17
- Username: BIGGJAKE
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Dec 10, 2006 6:39 am
- Post datetime: 2006-12-09T22:58:15+00:00
- Post Title: 

> Reply from Mr.Mouse
>
> Okay, please backup your old MC.MRF file in the MultiEx Commander data/config dir, and replace with attached. You can now open xpr files and extract the stuff, EXCEPT for the last file in there. I haven't found a way yet to overcome the format for the last one.

Will release anyway in the next version.

every time i put the mc.mrf file i downloaded in Commander data/config dir and then i try and open the program it say   MEX Open MRF Failed    can anyone help me with this.
## Post #18
- Username: tschumann
- Rank: advanced
- Number of posts: 57
- Joined date: Sat Jun 03, 2017 4:35 pm
- Post datetime: 2018-03-17T05:24:44+00:00
- Post Title: 

I know it's a little late but does anyone know the .xpr format?
There is documentation at [http://wiki.xentax.com/index.php/Counterstrike_XBox_XPR](http://wiki.xentax.com/index.php/Counterstrike_XBox_XPR) which is mostly right but it doesn't give any details about how to get the actual texture information out in a usable form. Slapping a .dds header on the texture data creates images which you can see are roughly correct but they are not usable. I can't work out how to get the texture dimensions and it looks like the textures are stored in such a way that the data is duplicated (each block of texture data has two instances of the image side-by-side).
Possibly the second uint32 in the unknown uint64 is DDS_HEADER.dwFlags but I'm really not sure.
## Post #19
- Username: tschumann
- Rank: advanced
- Number of posts: 57
- Joined date: Sat Jun 03, 2017 4:35 pm
- Post datetime: 2018-03-29T11:50:59+00:00
- Post Title: 

With some other documentation I was able to work out the structure:

```
	{
		__int32 iType;
		__int32 iOffset;
		__int32 iLock;
		__int16 iFormat; // one of these bytes is the format, and the other is always empty?
		byte iWidthComponent;
		byte iHeightComponent;
		__int32 iSize; // unused?
	};
```


iFormat can be 12 (DXT1), 14 (DXT3) or 15 (DXT3) and you can the usable values like so:

```
			int iWidth = (int)pow(2, (m_pFileData[i].iWidthComponent - (m_pFileData[i].iWidthComponent % 16)) / 16);
			int iHeight = (int)pow(2, m_pFileData[i].iHeightComponent);
```
## Post #20
- Username: tschumann
- Rank: advanced
- Number of posts: 57
- Joined date: Sat Jun 03, 2017 4:35 pm
- Post datetime: 2018-04-07T22:28:46+00:00
- Post Title: 

As a follow up, the .xpr format is meant to be a standard XDK format but the Counter-Strike Xbox .xpr files don't seem to conform. There is any interesting quote from one of the developers at [http://www.ritualistic.com/forums/showp ... stcount=27](http://www.ritualistic.com/forums/showpost.php?p=144287&postcount=27)

> The textures are not stored in the model files (well, they are, but those are the old crappy 8-bit PC counter-strike textures which are never loaded by the engine) but in separate 32-bit resource bundles that are embedded in the sxwad. again, the resource bundles are substantially different from the ones generated by the bundling tool that ships with xbox XDK (we needed added functionality so we ended up writing our own exporter).
