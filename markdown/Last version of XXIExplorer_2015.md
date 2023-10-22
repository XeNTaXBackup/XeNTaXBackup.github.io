## Post #1
- Username: jasmine
- Rank: VIP member
- Number of posts: 77
- Joined date: Tue May 10, 2005 1:07 pm
- Post datetime: 2006-08-01T01:18:44+00:00
- Post Title: Last version of XXIExplorer

Mr. Mouse, 

Here's the last version of XXIExplorer that you can put host on the website if you would like.  There is nothing new about this version, just the last one I worked on.  Version 1.5.

[http://rapidshare.de/files/27732908/XXI ... p.zip.html](http://rapidshare.de/files/27732908/XXIExplorer1.5Setup.zip.html)

jasmine
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-08-01T05:34:16+00:00
- Post Title: Last version of XXIExplorer

Thanks Jasmine! If possible, you could write a small page at 

[http://wiki.xentax.com/index.php/Game_T ... ia_XXI_.3D](http://wiki.xentax.com/index.php/Game_Tools#WWE_Wrestlemania_XXI_.3D)

In essence, create a small page here? 

[http://wiki.xentax.com/index.php?title= ... ction=edit](http://wiki.xentax.com/index.php?title=XXIExplorer&action=edit)

(see for instance this for reference : [http://wiki.xentax.com/index.php/PICT2BMP](http://wiki.xentax.com/index.php/PICT2BMP) ) 

I will then upload the tool and link it there!
## Post #3
- Username: jasmine
- Rank: VIP member
- Number of posts: 77
- Joined date: Tue May 10, 2005 1:07 pm
- Post datetime: 2006-08-02T05:53:38+00:00
- Post Title: Last version of XXIExplorer

Done.
## Post #4
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-08-02T10:41:33+00:00
- Post Title: Last version of XXIExplorer

Allright, I updated the download link here : [http://wiki.xentax.com/index.php/Game_Tools](http://wiki.xentax.com/index.php/Game_Tools) and also on the page itself: [http://wiki.xentax.com/index.php/XXIExplorer](http://wiki.xentax.com/index.php/XXIExplorer) . 

Cheers mate!
## Post #5
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2006-08-02T15:03:02+00:00
- Post Title: Last version of XXIExplorer

Good thanks
## Post #6
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-08-02T17:31:41+00:00
- Post Title: Last version of XXIExplorer

KorNet! He is back !
## Post #7
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2006-08-03T16:02:32+00:00
- Post Title: Last version of XXIExplorer

Hi Mr.Mouse   And here time appeared decided to visit you
## Post #8
- Username: jasmine
- Rank: VIP member
- Number of posts: 77
- Joined date: Tue May 10, 2005 1:07 pm
- Post datetime: 2006-10-03T03:41:40+00:00
- Post Title: Last version of XXIExplorer

Here is a new version of XXIExplorer.  I finally decoded the texture headers so the program automatically sets the correct dxt type and size and adds the header.  Should make things a lot easier if people are still modding the game.  It's written in C++ using MFC and there is no installation -- just unzip and run.   Here is the information on the texture headers in the .k files if you are interested(the .res files omit unknown1):

```
unsigned short int unknown2; // equals 1
unsigned short int unknown3; // equals 4
unsigned long int unknown4; // equals 0
unsigned long int unknown5; // equals 0
BYTE unknown6; // 0x29
BYTE dxtType; // 0x0C=DXT1 0x0F=DXT5
BYTE widthAndMips; // first nibble=width  second nibble=# of MipMaps
BYTE Length;
unsigned long int unknown6; // equals 0

Width and length are calculated as follows:
Length or Width    Size Dimension
3                         8
4                         16
5                         32
6                         64
7                         128
8                         256
9                         512

```


If you would, please upload it to the appropriate directory and put a link on the Wiki page.  Please leave the older version in case people have a problem with this one.  I tested it as much as I had time to.  I'm going to try and get the models out of the model files.  The offsets are correct now.

Thanks,
jasmine
[XXIExplorer_v2.2.zip](https://xentaxbackup.github.io/file/879_XXIExplorer_v2.2.zip)
## Post #9
- Username: keshire
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Jul 15, 2004 1:15 pm
- Post datetime: 2006-10-03T11:10:07+00:00
- Post Title: Last version of XXIExplorer

> I'm going to try and get the models out of the model files.

Unless you plan on writing a plugin for your app of choice you'll need to figure out what you want to do with the morph targets. I had written down the file specs for the model format on one of the incarnations of NinjaHacker. I've always stated if there was enough interest I'd pick it back up again.
## Post #10
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-10-03T11:32:13+00:00
- Post Title: Last version of XXIExplorer

Ok, link updated at the wiki.
## Post #11
- Username: keshire
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Jul 15, 2004 1:15 pm
- Post datetime: 2006-10-04T10:00:17+00:00
- Post Title: Last version of XXIExplorer

Found an old post via xbox-scene. Not the full spec.

[http://forums.xbox-scene.com/index.php?showtopic=432594](http://forums.xbox-scene.com/index.php?showtopic=432594)
## Post #12
- Username: jasmine
- Rank: VIP member
- Number of posts: 77
- Joined date: Tue May 10, 2005 1:07 pm
- Post datetime: 2006-10-04T18:08:30+00:00
- Post Title: Last version of XXIExplorer

Thanks for the info.  I actually had a previous post of yours saved to a text file.  I'm having a problem understanding the section after the faces.  It is all floats with an integer value but I don't know what determines the size of this section.  Here is the info that I have gotten from the female model sections (by the way, the new version extracts the model.bin correctly now). I still need to find the bones' position and rotation.  It would be nice to write a MilkShape plugin for this.

```
unsigned long int unknown1;
unsigned long int numBones;

// for number of bones//////
unsigned long int nameLength;
char *name;
float x;
float y;
float z;
//////////////////////////

unsigned long int unknown2;

unsigned long int numMeshes;

// for number of meshes/////
unsigned long int nameLength;
char *name;
unsigned long int unknown3;
unsigned long int unknown4;
////////////////////////////

unsigned long int numVerts;

// for number of verts //// I think this is the correct order for verts, normals, uv
float vert[3]; 
float normal[3];
float uv[2];
float unknown5[18];
///////////////////////////

unsigned long int numFaces;

// for number of faces //// Faces appear to be in triangle strips
unsigned short face;
//////////////////////////

unsigned long int unknown6;
unsigned long int unknown7;
unsigned long int unknown8;
unsigned long int unknown9; // 0xFFFF
unsigned long int unknown10; // 0xFFFF
unsigned long int unknown11;
unsigned long int unknown12;
float unknown13[?]; // <--Don't understand what this is or how to calculate size of section

```
## Post #13
- Username: keshire
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Jul 15, 2004 1:15 pm
- Post datetime: 2006-10-05T05:03:33+00:00
- Post Title: Last version of XXIExplorer

Next time I get a chance I'll take a look at it. Glad you got the model extraction corrected.
