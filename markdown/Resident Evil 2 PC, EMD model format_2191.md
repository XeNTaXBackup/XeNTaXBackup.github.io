## Post #1
- Username: PmData
- Rank: beginner
- Number of posts: 33
- Joined date: Tue Oct 31, 2006 1:56 am
- Post datetime: 2006-11-07T20:09:36+00:00
- Post Title: Resident Evil 2 PC, EMD model format

Hello,

I finished writing a page about why I know about the EMD file format:
[http://rewiki.regengedanken.de/wiki/.EM ... il_2_PC%29](http://rewiki.regengedanken.de/wiki/.EMD_%28Resident_Evil_2_PC%29)
I hope it is clear enough to understand. Atm, I documented only one part of the file. The rest seems to holds links between parts, and maybe animations steps.

Attached is a screenshot of a model with a self made viewer. I translated the different parts of the model a bit, to avoid having them mixed at the same place.

From right to left, body, head, wings, and more stuff. Triangles are purple, quads are blue. I did not try texturing at this stage.
[model002.png](https://xentaxbackup.github.io/file/965_model002.png)
## Post #2
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2006-11-07T22:42:38+00:00
- Post Title: Resident Evil 2 PC, EMD model format

Cool man.
Another addition to the supported formats list i guess.
Strange to see such an old game shown.
have u been doing it since it was released or only recently?
## Post #3
- Username: PmData
- Rank: beginner
- Number of posts: 33
- Joined date: Tue Oct 31, 2006 1:56 am
- Post datetime: 2006-11-08T17:17:56+00:00
- Post Title: Resident Evil 2 PC, EMD model format

> Reply from lionheartuk
>
> 
have u been doing it since it was released or only recently?

I only started 6-7 weeks ago, to play with OllyDbg and IdaPro, and see what I could use them for. Especially since the IdaPro 4.3 freeware runs on Linux/x86 using Wine.

So I first tried to RE the ADT file format, because this is the first file the game loads. It took me 3 weeks to get the decompression routine in C, from the disassembled asm x86.

The EMD format is a bit like the playstation TMD file format, regarding how primitives are stored, so this was a bit easier to get, hum 2 weeks of work.
## Post #4
- Username: PmData
- Rank: beginner
- Number of posts: 33
- Joined date: Tue Oct 31, 2006 1:56 am
- Post datetime: 2006-11-09T23:02:49+00:00
- Post Title: Resident Evil 2 PC, EMD model format

Here is Claire Redfield, in parts, with texturing.

There is not much left to document in the file, but it may be the harder part.

As you can see, only body, head and legs (both left and right), no arms, so they must be taken from another model in the game.
[model003.png](https://xentaxbackup.github.io/file/966_model003.png)
## Post #5
- Username: UnpackerX
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue May 08, 2007 6:26 am
- Post datetime: 2007-05-11T22:38:19+00:00
- Post Title: Resident Evil 2 PC, EMD model format

I was heard that all Resident Evil games was build on Microsoft Softimage, 
about the RDT files they contain the camera information, room information, textures in TM2 format and if the game was in other languages it contains the subtitles show in the game from dialogs, maybe someone can make a tool to extract the RDT subtitles from dialogs?
Maybe the models was build with Softimage also but with a custom export plugin 
In PSX the RDT can viewed in the latest Sony Movie Converter 3.6 just rename from RDT to BS and it work, if the data are too large the program crash then you need to split the files in 64kb then it work.
## Post #6
- Username: PmData
- Rank: beginner
- Number of posts: 33
- Joined date: Tue Oct 31, 2006 1:56 am
- Post datetime: 2007-05-12T20:00:43+00:00
- Post Title: Resident Evil 2 PC, EMD model format

> Reply from UnpackerX
>
> In PSX the RDT can viewed in the latest Sony Movie Converter 3.6 just rename from RDT to BS and it work, if the data are too large the program crash then you need to split the files in 64kb then it work.

What is more likely to happen is that this tool just seek in the file till it finds the signature of a BS data stream (starting with 0x3800 value), and just depack image from this location. I know the RDT contains some 2D images (I also found some in TIM format) mainly the sprites to be drawn above the background.
## Post #7
- Username: BillyRubin
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed May 16, 2007 8:28 am
- Post datetime: 2007-05-17T00:10:41+00:00
- Post Title: Resident Evil 2 PC, EMD model format

I converted the models of BIO1 to lwo, but haven't been able to extract the models of BIO2.  Any chance you can upload them in lwo or obj?
## Post #8
- Username: BillyRubin
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed May 16, 2007 8:28 am
- Post datetime: 2007-05-18T04:26:25+00:00
- Post Title: Resident Evil 2 PC, EMD model format

> So I first tried to RE the ADT file format, because this is the first file the game loads. It took me 3 weeks to get the decompression routine in C, from the disassembled asm x86.

Wow.  That's some fine work.  I did it the hard way  

I've been trying to unlock the beta stuff for a while now.  BTW, for anyone who hasn't figured out how the .SAP files work they're in RIFF wav format.  All you need is a hex editor to change the header, convert it to wav and play it on winamp exp.
## Post #9
- Username: UnpackerX
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue May 08, 2007 6:26 am
- Post datetime: 2007-05-19T20:59:36+00:00
- Post Title: Resident Evil 2 PC, EMD model format

I have take a look in the original Sony documentation about the models and found that EMD model are the same as PMD model (packet model)
this format can contain the model, texture and scripts. The models was build using the Alias 8.0 with official plugins that pack the model in PMD format. Inside the PMD format contain the TMD model encrypted, the TIM textures not encrypted, the models animations called TOD format.

#define TEX_ADDR	0x801c0000	/* texture address */
#define PMD_ADDR	0x801a0000	/* PMD object address */
#define OTLENGTH	8		/* OT depth */
#define OTSIZE		(1<<OTLENGTH)
#define SCR_Z		1024

static int pad_read(void);
static void RotPMD(u_long *ot, int id);
static void loadTIM(u_long *addr);

main()
{
	u_long	otbuf[2][1<<OTLENGTH]; 	/* OT */
	int     id;			/* double buffer ID */

	db_init(640, 480, SCR_Z, 60, 120, 120);	/* init */
	loadTIM((u_long *)TEX_ADDR);		/* load texture */
	SetDispMask(1);				/* start display */

	while (pad_read() == 0) {
		id = id? 0: 1;			/* swap */
		ClearOTagR(otbuf[id], OTSIZE);	/* clear OT */
		RotPMD(otbuf[id], id);		/* add PMD to OT */
		FntPrint("PMD viewer(1)\n");	/* message */
		db_swap(otbuf[id]+OTSIZE-1);	/* draw OT */
	}
	PadStop();				/* quit */
	StopCallback();
	return(0);
}

Load TIM data from main memory to the frame buffer

static void loadTIM(u_long *addr)
{
	TIM_IMAGE	image;		/* TIM header */

	OpenTIM(addr);			/* open TIM */
	while (ReadTIM(&image)) {
		if (image.caddr)	/* load CLUT (if needed) */
			LoadImage(image.crect, image.caddr);
		if (image.paddr) 	/* load texture pattern */
			LoadImage(image.prect, image.paddr);
	}
}



PMD functions 
There are 16 PMD functions accroding to its vertex format


/* independent vertex type (8 type) */
static void (*PMD_func[])() = {
	RotPMD_FT3,	RotPMD_FT4,	RotPMD_GT3,	RotPMD_GT4,
	RotPMD_F3,	RotPMD_F4,	RotPMD_G3,	RotPMD_G4,
};

/* shared vertex type (8 type) */
static void (*PMD_SV_func[])() = {
	RotPMD_SV_FT3,	RotPMD_SV_FT4,	RotPMD_SV_GT3,	RotPMD_SV_GT4,
	RotPMD_SV_F3,	RotPMD_SV_F4,	RotPMD_SV_G3,	RotPMD_SV_G4,
};

/*
 * draw PMD 
 : PMD ‚ð•`‰æ‚·‚é
 */	
static void RotPMD(u_long *ot, int id)
{
	int     i,j;
	long	*pmdtop;	/*PMD file PRIMITIVE Gp top address*/
	long	*pmdwc;		/*PMD file word counter*/
	long	pointer;	/*PMD file POINTER */
	long	*ptop;		/*PMD file PRIMITIVE Gp Block top address*/
	long	pid;		/*PMD file pid*/
	long	*primtop;	/*PMD file PRIMITIVE Gp top address*/
	long	nobj;		/*PMD file NOBJ*/
	long	nptr;		/*PMD file NPTR*/
	long	type_npacket;	/*PMD file PRIMITIVE Gp header*/
	short	type;		/*PMD file PRIMITIVE Gp type*/
	short	ltype;		/*PMD file PRIMITIVE Gp local type*/
	long	*svtop;		/*PMD file Vertex top address*/
	long	backc;		/*PMD file Back clip ON/OFF flag*/

	pmdwc = pmdtop = (long *)PMD_ADDR;

	pid   = *pmdwc;			pmdwc++;
	ptop  = pmdtop + ((*pmdwc)>>2);	pmdwc++;
	svtop = pmdtop + ((*pmdwc)>>2);	pmdwc++;
	nobj  = *pmdwc;			pmdwc++;

	for(i = 0;i < nobj; i++) {
		nptr = *pmdwc;
		pmdwc++;
		for(j = 0;j < nptr; j++){
			pointer      = *pmdwc;
			primtop      = pmdtop+(pointer>>2);
			type_npacket = *(primtop);	
			type         = type_npacket>>16;
			ltype        = type&0x000f;
			backc        = (type&0x0020)>>5;

			/* independent vertex type */
			if (ltype < 0x8)
				(*PMD_func[type])(primtop,
						     ot, OTLENGTH, id, backc);
			/* shared vertex type */
			else if (ltype < 0x10)
				(*PMD_SV_func[ltype&0x0f])(primtop, svtop,
						     ot, OTLENGTH, id, backc);
			pmdwc++;
		}
	}
}

This are the official PSX PMD format that Resident Evil 2, 3 use. Resident Evil 1 dont use the packet PMD format only the simple TMD format.
If anyone want try to create a Windows tool to extract the models, view etc i can show more about the formats
## Post #10
- Username: UnpackerX
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue May 08, 2007 6:26 am
- Post datetime: 2007-05-19T21:21:38+00:00
- Post Title: Resident Evil 2 PC, EMD model format

Here is a TMD normal model and one packed PMD (EMD model)
Anyone know where i can buy the Alias 8.0 or 9.0?
[MODEL.rar](https://xentaxbackup.github.io/file/1167_MODEL.rar)
## Post #11
- Username: PmData
- Rank: beginner
- Number of posts: 33
- Joined date: Tue Oct 31, 2006 1:56 am
- Post datetime: 2007-05-19T21:34:54+00:00
- Post Title: Resident Evil 2 PC, EMD model format

Thanks for the info,

Anyway I have nearly finished my viewer for game backgrounds. I think my next step is either a 3D model viewer, or the room description.
## Post #12
- Username: Goomba
- Rank: n00b
- Number of posts: 11
- Joined date: Sun May 20, 2007 5:48 am
- Post datetime: 2007-05-19T21:57:26+00:00
- Post Title: Resident Evil 2 PC, EMD model format

Hey UnpackerX, the source code you showed can you make a 3D viewer and converter? Lowest system requirements PLEASE! Old computer me have!  or just show the way to create my own tool. Thanks!

Or maybe PmData, You have made good progress with your work. Can you make a Resident Evil2/3 model viewer and converter. I would like the models to convert to .obj, .ma, 3d max. Or just .obj! 

And also PmData, I have compiled the code you wrote on Rewiki, and it returns a 1 and it has errors? I do not understand how to use it? I just want to view and convert models.
## Post #13
- Username: Goomba
- Rank: n00b
- Number of posts: 11
- Joined date: Sun May 20, 2007 5:48 am
- Post datetime: 2007-05-25T21:31:54+00:00
- Post Title: Resident Evil 2 PC, EMD model format

Has anyone tried 3D Ripper DX? Can it extract and convert re2 models? If so put a link to them, preferably Maya format.  I hope I am not annoying people here
## Post #14
- Username: UnpackerX
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue May 08, 2007 6:26 am
- Post datetime: 2007-05-27T15:49:10+00:00
- Post Title: Resident Evil 2 PC, EMD model format

> Goomba writed: Has anyone tried 3D Ripper DX? Can it extract and convert re2 models? If so put a link to them, preferably Maya format.  I hope I am not annoying people here

Well i can say that DX 3D Ripper DX supports only DirectX 9.0 applications. OpenGL, older versions of DirectX and software renderers are not supported. So, Resident Evil 2 and 3 dont use D3D9, its not possible.

Regards
## Post #15
- Username: PmData
- Rank: beginner
- Number of posts: 33
- Joined date: Tue Oct 31, 2006 1:56 am
- Post datetime: 2007-06-13T20:10:14+00:00
- Post Title: Resident Evil 2 PC, EMD model format

Hello,

After hours of work, and learning Python from scratch, I managed to load an EMD model inside [Blender](http://www.blender.org/).

However, like my previous model viewer, I don't know where links between body parts are stored. And I still have texturing to add to it.
[em010-emd.png](https://xentaxbackup.github.io/file/1213_em010-emd.png)
## Post #16
- Username: Goomba
- Rank: n00b
- Number of posts: 11
- Joined date: Sun May 20, 2007 5:48 am
- Post datetime: 2007-06-15T02:04:53+00:00
- Post Title: 

Cool. Coming along nicely I see.

 When I imported RE1 models, someone converted for me, Maya automatically puts most textures in the right place after I assigned them to certain areas of the model. 

But I had to adjust them, because the uv map was either a little too high or low or to the side of the texture. 

I could make a tutorial for you to get started using maya PMData?
## Post #17
- Username: PmData
- Rank: beginner
- Number of posts: 33
- Joined date: Tue Oct 31, 2006 1:56 am
- Post datetime: 2007-06-22T18:45:20+00:00
- Post Title: 

Ok, a bit more progress, now with some texturing. The remaining missing part is to link body parts. I need to learn how to do it in Blender (I found where they are stored in EMD file).

For information, RE games use .EMW or .PLD/.PLW, which nearly are the same format as .EMD (some have embedded .TIM file for texture for example).

Sorry Goomba, but if you want a Maya importer, you'll have to write it. I don't have time to do another one. Once finished, I'll post the Python script for Blender on my site.
[em010-emd.jpg](https://xentaxbackup.github.io/file/1227_em010-emd.jpg)
## Post #18
- Username: PmData
- Rank: beginner
- Number of posts: 33
- Joined date: Tue Oct 31, 2006 1:56 am
- Post datetime: 2007-07-25T20:32:47+00:00
- Post Title: 

Hello,

As I am busy with other stuff, atm, I decided to put 'as-is' import plugin   for Blender on my web site (You know, the www button below the message ).

So the EMD import script also tries to load the TIM file with same name and use it as a texture for the object.

The TMD import script, well, only import the meshes. Don't know if texture coordinates are correct or not though.

I don't know when I'll have time to improve them (the most important missing stuff is the bone/skeleton links in between EMD meshes).
## Post #19
- Username: Goomba
- Rank: n00b
- Number of posts: 11
- Joined date: Sun May 20, 2007 5:48 am
- Post datetime: 2007-07-26T17:31:01+00:00
- Post Title: 

Thanks a lot PMData, But I have been trying to figure out how to make this script work! I am having trouble.

 Please make a detailed Tutorial on how to use the script! I am using the latest version of Blender. 

I have been searching on the web, but the tutorials that I found don't work.

By the way, this script is for RE2, and RE3 EMD file from the PC version? Can it be used for the PSX version too? 



edit: I just figured out how to work it! In the bottom window , I opened the text window, then select the .py script and right clicked it and press  the button that says "Open text", then in the file menu, select run script, then it says to select EMD file. 

edit2: You better just put the tutorial, because I made the script run, but it would let me import the emd file?
## Post #20
- Username: ReeceMix
- Rank: advanced
- Number of posts: 64
- Joined date: Sat Nov 10, 2007 10:01 pm
- Post datetime: 2007-11-10T18:22:48+00:00
- Post Title: 

I have all of the Resident Evil 1 models in UV form

[](http://img215.imageshack.us/my.php?image=weskerkn9.jpg)

I really want to get hold of the RE2 & RE3 models (preferally UV mapped),
I only have the PSX versions of the games.  I know that RE1 EMD models were originally TMDs with a different header file.  But when the same process is applied for the RE2 EMDs the vertex data is messed up.

Does anyone have the RE2/RE3 Models or the EMDs , I downloaded the blender plugin that should open RE EMDs but it doesnt work with the PSX models, apparently only the PC versions
## Post #21
- Username: ReeceMix
- Rank: advanced
- Number of posts: 64
- Joined date: Sat Nov 10, 2007 10:01 pm
- Post datetime: 2007-11-10T22:17:30+00:00
- Post Title: 

Ive been trying to open files with the blender plugin posted here but I just cant get it to work, it seems that it needs the file.emd and a TIM file , but it wont open resident evil 2 PLD (the playable character files) which are the objects I really want.

Nevermind I got the original RE2 and all the EMD's and TIMs are there including the playable characters.
## Post #22
- Username: ReeceMix
- Rank: advanced
- Number of posts: 64
- Joined date: Sat Nov 10, 2007 10:01 pm
- Post datetime: 2007-11-12T15:49:55+00:00
- Post Title: 

PmData, is the importer still in production?

I can rip most of the EMD's but some have bodyparts missing, I can even alter the TIM and texture them in blender.

From what I know about TMDs by looking at them in HEX is the first 12 or 16 numbers are the header and then each body part is 24 ( i think) numbers,  because the EMDs are all different they all have different amounts of TIM texture pages, and probabally located in different places within the EMD so at the moment I think the Importer struggles with picking out all of the meshes

Its cool that they have texture support, but if the importer could just extract all the mesh data and not worry about the TIM texture file that would still be very useful for me.

And secondly, could the process be reversed and have a EMD Exporter, that way people could mod resident evil 2. (personally I just want the models extracted)

Are there any plans to include Resident Evil 1 & 3 in the importer? (I havent used the TMD importer, but I know for RE1 the EMD Headers just need changing to a TMD header to be opened in milkshape, surely it wouldnt be too difficult to have the importer recognise a RE1 EMD alter the header upon import)
## Post #23
- Username: PmData
- Rank: beginner
- Number of posts: 33
- Joined date: Tue Oct 31, 2006 1:56 am
- Post datetime: 2007-11-14T18:59:53+00:00
- Post Title: 

> Reply from ReeceMix
>
> I can rip most of the EMD's but some have bodyparts missing, I can even alter the TIM and texture them in blender.These missing parts are the ones (arms, hands) which carry a weapon, and they are stored in a separate file.

> because the EMDs are all different they all have different amounts of TIM texture pages, and probabally located in different places within the EMD so at the moment I think the Importer struggles with picking out all of the meshesYep it's like the EMD file is a kind of raw format, and the game engine must know where to pick what it needs.
> Its cool that they have texture support, but if the importer could just extract all the mesh data and not worry about the TIM texture file that would still be very useful for me.Unfortunately, if I don't know the size of the texture, the UV coordinates for each vertex can not be calculated (they must be converted from width,height image space to 1.0,1.0 normalized space). And more than mesh data, there is also the link between them (bones), needed to display a complete body with parts being correctly placed relative to each other. I found it, but I did not found a correct tutorial to make the importer build it for Blender.

> And secondly, could the process be reversed and have a EMD Exporter, that way people could mod resident evil 2. (personally I just want the models extracted)For an exporter, the whole format must be well know and understood, to create a correct file, or the game will surely crash when loading it.
> Are there any plans to include Resident Evil 1 & 3 in the importer? (I havent used the TMD importer, but I know for RE1 the EMD Headers just need changing to a TMD header to be opened in milkshape, surely it wouldnt be too difficult to have the importer recognise a RE1 EMD alter the header upon import)Well, I don't know about RE1 files, but RE3 ones seem to be very similar to RE2. As said in the mail I sent you, I'm busy atm.
## Post #24
- Username: ReeceMix
- Rank: advanced
- Number of posts: 64
- Joined date: Sat Nov 10, 2007 10:01 pm
- Post datetime: 2007-11-14T19:12:25+00:00
- Post Title: 

> Reply from PmData
>
> These missing parts are the ones (arms, hands) which carry a weapon, and they are stored in a separate file.

This isnt true for every EMD , when I open the Ada wong EMD she is just a torso with no legs, head or arms, the rest of her must be within the EMD

> Reply from PmData
>
> Unfortunately, if I don't know the size of the texture, the UV coordinates for each vertex can not be calculated (they must be converted from width,height image space to 1.0,1.0 normalized space). And more than mesh data, there is also the link between them (bones), needed to display a complete body with parts being correctly placed relative to each other. I found it, but I did not found a correct tutorial to make the importer build it for Blender.

Im not sure what your saying here, Ive opened RE2 EMDs with the Importer and extracted the TIM image into BMP with Yu_Ri,  I rotated that image 180* and added the UV to the Model

The Importer Keeps the UV texture location, Yu_Ri (Rips TIMs from any files with TIM inside) ripped the UV and I combined them. 
It works great.  I was suggesting that the importer ignored the TIM reference and just focused on picking out the meshes (but keeping the uv coords is a good thing).
## Post #25
- Username: PmData
- Rank: beginner
- Number of posts: 33
- Joined date: Tue Oct 31, 2006 1:56 am
- Post datetime: 2007-11-26T19:55:26+00:00
- Post Title: 

> PmData wrote:Unfortunately, if I don't know the size of the texture, the UV coordinates for each vertex can not be calculated (they must be converted from width,height image space to 1.0,1.0 normalized space). And more than mesh data, there is also the link between them (bones), needed to display a complete body with parts being correctly placed relative to each other. I found it, but I did not found a correct tutorial to make the importer build it for Blender.
>
> Im not sure what your saying here, Ive opened RE2 EMDs with the Importer and extracted the TIM image into BMP with Yu_Ri,  I rotated that image 180* and added the UV to the Model
>
> 
>
> The Importer Keeps the UV texture location, Yu_Ri (Rips TIMs from any files with TIM inside) ripped the UV and I combined them. 
>
> It works great.  I was suggesting that the importer ignored the TIM reference and just focused on picking out the meshes (but keeping the uv coords is a good thing).
What I said is that in EMD file, you have x,y position in the TIM image (so x goes from 0 to width, y goes from 0 to height of image). And u,v texture coordinates of the mesh vertices must be in the range 0.0-1.0 instead. So you calculate u=x/width and v=y/height, it means you need the size of the image, to have correct coordinates.
It could either be possible to find the highest value for x and y used in the mesh, and try to guess an image size from this, or either ask the user at import time, the size of the image, or only use the TIM file to read its width and height.
## Post #26
- Username: Goomba
- Rank: n00b
- Number of posts: 11
- Joined date: Sun May 20, 2007 5:48 am
- Post datetime: 2008-02-29T01:02:14+00:00
- Post Title: 

I decided to try the plug-in again and it worked for the Resident Evil 2 PC version. But I do not know how to get Blender to import the RE2 PSX version? Do I use the .emd python script or the .tmd script? I assume the .PLD format is the same as .EMD?
## Post #27
- Username: PmData
- Rank: beginner
- Number of posts: 33
- Joined date: Tue Oct 31, 2006 1:56 am
- Post datetime: 2008-03-01T20:34:16+00:00
- Post Title: 

> Reply from Goomba
>
> I decided to try the plug-in again and it worked for the Resident Evil 2 PC version. But I do not know how to get Blender to import the RE2 PSX version? Do I use the .emd python script or the .tmd script? I assume the .PLD format is the same as .EMD?
For TMD files, you must use the TMD import script. For PLD files, the EMD script won't work as is, because the PLD files have less sections than EMD files, but the sections contain same data, so modifying the EMD script for PLD import should be easy.
[http://rewiki.regengedanken.de/wiki/.PLD](http://rewiki.regengedanken.de/wiki/.PLD)

I started writing an EMD loader for my viewer. As I already have background image, and camera position, I can display 3D stuff on it. I need some free time to work on it .
## Post #28
- Username: Goomba
- Rank: n00b
- Number of posts: 11
- Joined date: Sun May 20, 2007 5:48 am
- Post datetime: 2008-03-04T21:37:47+00:00
- Post Title: 

I read that PLD has 4 sections and #3 is the same as section #7 in the Emd file. But I do not  know how to rewrite it, I am a intermediate C programmer, so SOmeone Please rewrite the Python script for ME!!!  

I appreciate anyone' s help.
## Post #29
- Username: PmData
- Rank: beginner
- Number of posts: 33
- Joined date: Tue Oct 31, 2006 1:56 am
- Post datetime: 2008-03-05T19:54:02+00:00
- Post Title: 

> Reply from Goomba
>
> I read that PLD has 4 sections and #3 is the same as section #7 in the Emd file. But I do not  know how to rewrite it, I am a intermediate C programmer, so SOmeone Please rewrite the Python script for ME!!!

Ok, I did it 'quick and dirty way'. I took the EMD import script, remove texture image loading, modified to get the proper sections, and it works, for both PLD and PLW files. PLD seem to contain body parts of the player (when it get hurt I think), and PLW contain the hand+weapon. A different PLW file for each weapon. It's on my site now. Note: there are some errors at the end of import, just click on error message, and the model should be displayed. Will have to deal with that later.
## Post #30
- Username: Goomba
- Rank: n00b
- Number of posts: 11
- Joined date: Sun May 20, 2007 5:48 am
- Post datetime: 2008-03-30T23:25:13+00:00
- Post Title: 

If the pld files only have body parts on the psx disks, then where are the whole body parts?? Do you think pmdata that maybe if you work on the pld import code that you can get the whole body of the characters from the pld file? What can I do to figure this out if you are too busy?
## Post #31
- Username: PmData
- Rank: beginner
- Number of posts: 33
- Joined date: Tue Oct 31, 2006 1:56 am
- Post datetime: 2008-04-04T20:20:38+00:00
- Post Title: Re: Resident Evil 2 PC, EMD model format

> Reply from Goomba
>
> If the pld files only have body parts on the psx disks, then where are the whole body parts?? Do you think pmdata that maybe if you work on the pld import code that you can get the whole body of the characters from the pld file? What can I do to figure this out if you are too busy?

I don't remember exactly about PLD, but some EMxxxx.EMD file are for the player character, and the PLW files have the missing parts. Would need to check what exactly is in PLD files.
## Post #32
- Username: Goomba
- Rank: n00b
- Number of posts: 11
- Joined date: Sun May 20, 2007 5:48 am
- Post datetime: 2008-07-01T03:19:01+00:00
- Post Title: Re: Resident Evil 2 PC, EMD model format

Has Anyone updated this plug-in yet? I am curious if there are any new developments on this project. I haven't heard anything about it for about 2 months?
## Post #33
- Username: PmData
- Rank: beginner
- Number of posts: 33
- Joined date: Tue Oct 31, 2006 1:56 am
- Post datetime: 2008-07-05T12:57:30+00:00
- Post Title: Re: Resident Evil 2 PC, EMD model format

> Reply from Goomba
>
> Has Anyone updated this plug-in yet? I am curious if there are any new developments on this project. I haven't heard anything about it for about 2 months?

Sorry I don't have time to work on it.
## Post #34
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2008-07-05T16:59:11+00:00
- Post Title: Re: Resident Evil 2 PC, EMD model format

> Reply from PmData
>
> Goomba wrote:If the pld files only have body parts on the psx disks, then where are the whole body parts?? Do you think pmdata that maybe if you work on the pld import code that you can get the whole body of the characters from the pld file? What can I do to figure this out if you are too busy?
Perhaps this game doesnt use RIGS and its models are made of individual body parts that animate seperatly (a  few games are like that actually).
