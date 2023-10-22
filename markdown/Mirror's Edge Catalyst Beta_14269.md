## Post #1
- Username: OriginOfWaves
- Rank: beginner
- Number of posts: 38
- Joined date: Wed Jun 08, 2011 8:58 pm
- Post datetime: 2016-04-25T16:38:31+00:00
- Post Title: Mirror's Edge Catalyst Beta

hello there other xentax folks. i've been digging through the files of the Mirror's Edge Catalyst Beta trying to extract some files. Unfortunately i had no success using the BF4 dumper or the DAI tools. I think it's because the folder structure is quite a bit different than BF4 or DAI. For instance, both Battlefield 4 and Dragon Age have all of their .cas and .cat files together in the "Data" folder, while MEC had all of it's .cat and .cas files separated into individual folders inside the "Data\Win32\gameconfigurations\" folder.

here are some screen grabs for easier understanding of my problem.


as you can see, the Data folder has no .cat or .cas files on the MEC side, while the Win32 folder is mostly similar with .sb and .toc files on both sides. the biggest difference is in the Gameconfigurations folders which are inside completely different folders and contain different file types.

I tried to edit the bf4 dumper script to point to these .cat and .cas files but it still fails, probably 'cause the .cas and .cat files are all separated and not together in one folder. Using DAI tools i can read some of the .sb files but loading .cat or .cas files always fails and gives out errors. so there are probably some changes in those files as well.

anyways, any sort of help i could get here is greatly appreciated. so let me know if you need me to upload any of the game files. thanks in advance.
## Post #2
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-04-26T21:19:21+00:00
- Post Title: Mirror's Edge Catalyst Beta

It can be unpacked with StarWars Battlefront unpacker / decoder

[viewtopic.php?f=10&t=13584](http://forum.xentax.com/viewtopic.php?f=10&t=13584)
## Post #3
- Username: OriginOfWaves
- Rank: beginner
- Number of posts: 38
- Joined date: Wed Jun 08, 2011 8:58 pm
- Post datetime: 2016-04-27T11:59:37+00:00
- Post Title: Mirror's Edge Catalyst Beta

thanks for pointing me to it. i'll try it out.

Update: unfortunately after setting up the directories for the dumper script, it only manages to dump 8 GB out of 12 GB. there are a lot of empty folders and the mesh and chunk management tool was only able to find a few matching chunks. i tried importing some meshes with corresponding chunks into 3ds max with BF4 script but it does nothing on import. looks like they made some changes from the SW Battlefield. so maybe all the tools and scripts need some updating to be able to work with MEC.
## Post #4
- Username: dainazinas
- Rank: advanced
- Number of posts: 40
- Joined date: Wed Feb 01, 2012 3:32 am
- Post datetime: 2016-05-01T20:27:52+00:00
- Post Title: Mirror's Edge Catalyst Beta

> Reply from OriginOfWaves
>
> thanks for pointing me to it. i'll try it out.

Update: unfortunately after setting up the directories for the dumper script, it only manages to dump 8 GB out of 12 GB. there are a lot of empty folders and the mesh and chunk management tool was only able to find a few matching chunks. i tried importing some meshes with corresponding chunks into 3ds max with BF4 script but it does nothing on import. looks like they made some changes from the SW Battlefield. so maybe all the tools and scripts need some updating to be able to work with MEC.

Can you share your dumper script and main python folder. As I only get 4257 empty folders and 0 files when I use the above mentioned BF4 dumper. If I get mesh and chunk files I might adjust my maxscripts to work with these, thx.
## Post #5
- Username: StreamThread
- Rank: beginner
- Number of posts: 27
- Joined date: Tue Mar 22, 2016 4:58 am
- Post datetime: 2016-05-01T21:19:09+00:00
- Post Title: Mirror's Edge Catalyst Beta

i'm extract with all standard settings and have only 2,89 gb of extracted data - no more .ebx files and textures with names, and 2,57 gb of chunks.
## Post #6
- Username: dainazinas
- Rank: advanced
- Number of posts: 40
- Joined date: Wed Feb 01, 2012 3:32 am
- Post datetime: 2016-05-01T22:12:26+00:00
- Post Title: Mirror's Edge Catalyst Beta

1. adding/replacing(swbf) these lines to row 23 seems to help the extractor a bit

> cat1Path       = r"Data\Win32\gameconfigurations\downtownnorthinstallpackage\cas.cat"
>
> cat2Path       = r"Data\Win32\gameconfigurations\prisonexteriorinstallpackage\cas.cat"
>
> cat3Path       = r"Data\Win32\gameconfigurations\releaseinstallpackage\cas.cat"
>
> cat4Path       = r"Data\Win32\gameconfigurations\downtownsouthinstallpackage\cas.cat"
>
> cat5Path       = r"Data\Win32\gameconfigurations\backinthegameinstallpackage\cas.cat"
>
> cat6Path       = r"Data\Win32\gameconfigurations\cityglobalinstallpackage\cas.cat"
>
> cat7Path       = r"Data\Win32\gameconfigurations\cityrevealinstallpackage\cas.cat"
>
> cat8Path       = r"Data\Win32\gameconfigurations\initialinstallpackage\cas.cat"

2. Here is updated version of Mesh and chunk file tool
[https://dl.dropboxusercontent.com/u/881 ... Reader.exe](https://dl.dropboxusercontent.com/u/88155050/Mirrors%20Edge%20Catalyst%20CB/Chunk%20and%20Mesh%20Tool/Bf3_MeshFile_Type_Reader.exe)
## Post #7
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-05-02T15:05:43+00:00
- Post Title: Mirror's Edge Catalyst Beta

> Reply from dainazinas
>
> Can you share your dumper script and main python folder. As I only get 4257 empty folders and 0 files when I use the above mentioned BF4 dumper.

Because you DON'T have to use BF4 dumper. Use Star Wars dumper. The link is up there.
## Post #8
- Username: kkdf2
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Oct 24, 2010 4:26 pm
- Post datetime: 2016-07-02T13:16:32+00:00
- Post Title: Mirror's Edge Catalyst Beta

> Reply from daemon1
>
> It can be unpacked with StarWars Battlefront unpacker / decoder

viewtopic.php?f=10&t=13584
Thanks, it succeeded to export 14,863 chunks (6.20GB!), and 8,557 (4.75GB!) wav files from retail version of Mirror's Edge Catalyst (Origin PC)! fyi, game's Data&Patch folder contain 22.8GB

And, anyone is trying to extract more data like modelling data from raw chunk files? If you have, please share it...
## Post #9
- Username: lolbas
- Rank: beginner
- Number of posts: 28
- Joined date: Wed Nov 18, 2015 11:59 pm
- Post datetime: 2016-07-09T13:47:41+00:00
- Post Title: Mirror's Edge Catalyst Beta

> Reply from kkdf2
>
> Thanks, it succeeded to export 14,863 chunks (6.20GB!), and 8,557 (4.75GB!) wav files from retail version of Mirror's Edge Catalyst (Origin PC)!
Excuse me, but how do you use that tool? I seem to miss some tutorial on that app
## Post #10
- Username: kkdf2
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Oct 24, 2010 4:26 pm
- Post datetime: 2016-07-11T15:35:57+00:00
- Post Title: Mirror's Edge Catalyst Beta

> Reply from lolbas
>
> kkdf2 wrote:Thanks, it succeeded to export 14,863 chunks (6.20GB!), and 8,557 (4.75GB!) wav files from retail version of Mirror's Edge Catalyst (Origin PC)!
Excuse me, but how do you use that tool? I seem to miss some tutorial on that app
Hi.
We can try it but I'm not sure whether we can acquire satisfied output from extraction for now...

What I have tried:
- Obtain swbf.rar from [viewtopic.php?f=10&t=13584](http://forum.xentax.com/viewtopic.php?f=10&t=13584)
- Explode it.
- Edit swbf_dump/sw_dumper.py

Line 5-7:

```
bf4Directory=r"H:\Program Files (x86)\Origin Games\Mirrors Edge Catalyst"
targetDirectory = r"H:\MEC" 
```


Line21-30: (Updated 2016/08/29)

```
#Although in that case you could just as well use an invalid path, i.e. not change anything.
cat1Path = r"Data\Win32\gameconfigurations\anchorinstallpackage\cas.cat"
cat2Path = r"Data\Win32\gameconfigurations\backinthegameinstallpackage\cas.cat"
cat3Path = r"Data\Win32\gameconfigurations\cityglobalinstallpackage\cas.cat"
cat4Path = r"Data\Win32\gameconfigurations\cityrevealinstallpackage\cas.cat"
cat5Path = r"Data\Win32\gameconfigurations\defaultinstallpackage\cas.cat"
cat6Path = r"Data\Win32\gameconfigurations\downtownnorthinstallpackage\cas.cat"
cat7Path = r"Data\Win32\gameconfigurations\downtownsouthinstallpackage\cas.cat"
cat8Path = r"Data\Win32\gameconfigurations\initialinstallpackage\cas.cat"
cat9Path = r"Data\Win32\gameconfigurations\prisonexteriorinstallpackage\cas.cat"
cat10Path = r"Data\Win32\gameconfigurations\releaseinstallpackage\cas.cat"
cat11Path = r"Data\Win32\gameconfigurations\rezoninginstallpackage\cas.cat"
#updateCatPath = r"Update"

```


around line 274 (Added 2016/08/29)

```
for path in "cat1Path", "cat2Path", "cat3Path", "cat4Path", "cat5Path", "cat6Path", "cat7Path", "cat8Path", "cat9Path", "cat10Path", "cat11Path", "updateCatPath", "tocRoot", "tocRoot2":
  if path in locals():
  locals()[path]= os.path.normpath(bf4Directory+"\\"+locals()[path])

```


around line 291 (Added 2016/08/29)

```
try: readCat(cat, cat1Path)
except: print "cat1Path cat not found."
try: readCat(cat, cat2Path)
except: print "cat2Path cat not found."
try: readCat(cat, cat3Path)
except: print "cat3Path cat not found."
try: readCat(cat, cat4Path)
except: print "cat4Path cat not found."
try: readCat(cat, cat5Path)
except: print "cat5Path cat not found."
try: readCat(cat, cat6Path)
except: print "cat6Path cat not found."
try: readCat(cat, cat7Path)
except: print "cat7Path cat not found."
try: readCat(cat, cat8Path)
except: print "cat8Path cat not found."
try: readCat(cat, cat9Path)
except: print "cat9Path cat not found."
try: readCat(cat, cat10Path)
except: print "cat10Path cat not found."
try: readCat(cat, cat11Path)
except: print "cat11Path cat not found."

if "tocRoot" in locals(): dumpRoot(tocRoot)
if "tocRoot2" in locals(): dumpRoot(tocRoot2)

```


- Launch sw_dumper.py thru IDLE (Python GUI) of Python 2.7

For some .wav files extraction:
- Edit fb3decoder/fb3decoder.py.

Line20-25:

```
dumpDirectory = r"H:\MEC"
targetDirectory = r"H:\MEC\snd"

#Download Zench's tool so the script can handle EALayer3.
ealayer3Path=r"H:\DL\swbf\fb3decoder\ealayer3.exe" 
```


around line 294, add 0xc11d:("q",8) to numDict: (Added 2016/08/30)

```
  0xC12D:("Q",8),
  0xc0cd:("B",1),
  0x0035:("I",4),
  0xc10d:("I",4),
  0xc14d:("d",8),
  0xc0ad:("?",1),
  0xc0fd:("i",4),
  0xc0bd:("b",1),
  0xc0ed:("h",2),
  0xc0dd:("H",2),
  0xc13d:("f",4),
  0xc11d:("q",8), #unknown
  }

```


- Launch fb3decoder/fb3decoder.py. Using IDLE (Python GUI) of Python 2.7 is useful for printing export progress.
- We will get some wav files. But I think many sounds are still unextracted in current status. We can get most wav files including game music. 61,415 files in 28GB. It took 3 days for extraction. (Updated 2016/09/04)

For texture (.dds, direct draw surface?) extraction: (2016/09/06 Updated)
- Obtain Batch_Itexture_Converter.exe from somewhere.
- [Select Itexture] H:\MEC\bundles 2330 6433 or such
- [Select Chunk] H:\MEC\chunks 14863 53239 or such
- [Get DDS Files] 2330 6433 or such
- We will get some dds files. However most of them are unreadable with my usual tools.

I have tested some tools to preview DX10 dds texture files: (2016/09/06 Added)

 DirectX Texture Tool (64-Bit) in Microsoft DirectX SDK (June 2010)\DirectX Utilities (64-Bit)
 → An error occurred trying to open that file.
 DDS Viewer from ddsviewer.com
 → DDS Viewer has stopped working
 NVIDIA Corporation\DDS Utilities\readdxt.exe
 → generates transparent tga. is it correct?
 Windows Texture Viewer from nvidia.com
 → show nothing.
 PicoPixel-0.6.11-x86-installer.exe from pixelandpolygon.com
 → can preview!
 texconv.exe from github.com Microsoft/DirectXTex
 → can convert!

texconv.exe usage sample:

```
Microsoft (R) DirectX 11 Texture Converter (DirectXTex version)
Copyright (C) Microsoft Corp. All rights reserved.

reading H:\MEC\bundles\res\characters\enemy\drone_hunter\t_drone_hunter_d d3286deeb3eca4ed 0b000000010000000000000000000000.dds (2048x2048 BC1_UNORM_SRGB 2D) as (2048x2048 R8G8B8A8_UNORM_SRGB 2D)
writing C:\Users\Sola\Desktop\t_drone_hunter_d d3286deeb3eca4ed 0b000000010000000000000000000000.PNG
```
## Post #11
- Username: OriginOfWaves
- Rank: beginner
- Number of posts: 38
- Joined date: Wed Jun 08, 2011 8:58 pm
- Post datetime: 2016-07-28T16:39:45+00:00
- Post Title: Mirror's Edge Catalyst Beta

phew finally found some time to share my progress on this front. these are some of the meshes and textures that i was able to obtain form the Demo, thanks to the edited BF4 dumper script and Shakotay's Hex2Obj app (thanks a bunch Shakotay for all the help you provided).
## Post #12
- Username: redspike474
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Feb 05, 2016 2:24 am
- Post datetime: 2016-07-28T21:03:45+00:00
- Post Title: Mirror's Edge Catalyst Beta

Looking awesome, any idea if shaders accessible in any of these recent dice games?
I sure would like to take a look.
I guess its rare that games come with uncompiled shaders these days, but the recent doom, division and watchdogs did!
## Post #13
- Username: OriginOfWaves
- Rank: beginner
- Number of posts: 38
- Joined date: Wed Jun 08, 2011 8:58 pm
- Post datetime: 2016-07-29T13:32:48+00:00
- Post Title: Mirror's Edge Catalyst Beta

not to my knowledge. the Frostbite engine is pretty locked up. i remember having to go through multiple hoops just to mod a tiny bit of Dragon Age Inquisition. but i can tell you the basics about how Frostbite shaders handle different materials like cotton, metal, leather. they use color mask maps to identify different materials. they look something like this.

in this example the red parts are where the shader applies a shiny leather material, green is for a simple cotton material and blue is for a faux leather material. these color maps are always red, green and blue and sometimes with an alpha layer for further control, but which material they represent differs from example to example.
## Post #14
- Username: OriginOfWaves
- Rank: beginner
- Number of posts: 38
- Joined date: Wed Jun 08, 2011 8:58 pm
- Post datetime: 2016-08-15T13:46:32+00:00
- Post Title: Mirror's Edge Catalyst Beta

uploaded Faith models and drones to dropbox. they are .obj's with textures, no bones.

[https://www.dropbox.com/sh/qolc2o7tt5y4 ... U3IHa?dl=0](https://www.dropbox.com/sh/qolc2o7tt5y4z2p/AABR1wefS56vmwTVo_7NU3IHa?dl=0)
## Post #15
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2016-08-16T00:10:28+00:00
- Post Title: Mirror's Edge Catalyst Beta

Great work, dude! Can't wait to see how this goes!
## Post #16
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2016-10-01T20:41:37+00:00
- Post Title: Re: Mirror's Edge Catalyst Beta

@OriginOfWaves thank you! I was really hoping to get the models from this game but I didn't know if it was already possible or not.
## Post #17
- Username: Irastris
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Sep 21, 2015 12:28 pm
- Post datetime: 2016-10-21T06:36:08+00:00
- Post Title: Re: Mirror's Edge Catalyst Beta

Did anyone ever figure out how to get models with rigging from MEC? I'm really desperate for Faith but I have no idea how to go about rigging the OBJ that was previously posted.
## Post #18
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2016-10-24T15:39:43+00:00
- Post Title: Re: Mirror's Edge Catalyst Beta

The game uses the Frostbite engine like Dragon Age Inquisition... so technically it is possible since with the DAI Tools we can get rigged models. However, the programmer is already working hard on the new tools for that game, thus I doubt she will try to also implement a MEC support. Maybe someone else can figure out another way at some point, who knows.
## Post #19
- Username: kkdf2
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Oct 24, 2010 4:26 pm
- Post datetime: 2016-11-09T16:21:11+00:00
- Post Title: Re: Mirror's Edge Catalyst Beta

I'm working on a mesh converter: mesh→blenderPy script.

faith has 10 parts and we need to combine them into one body...
[blender.jpg](https://xentaxbackup.github.io/file/11893_blender.jpg)
## Post #20
- Username: kkdf2
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Oct 24, 2010 4:26 pm
- Post datetime: 2016-11-11T14:15:24+00:00
- Post Title: Re: Mirror's Edge Catalyst Beta

I have a sample tool, in development status, in order to extract mesh data: writing down .py or .h2o formats. [http://kkdf2.sakura.ne.jp/MEC/DecMECMesh-0.1.7z](http://kkdf2.sakura.ne.jp/MEC/DecMECMesh-0.1.7z)  pass MEC

- Launch "Run-gui.bat"
- Require .NET Framework 4.0 or later

Use [ILSpy](http://ilspy.net/) to obtain source code. enjoy!
[ss.jpg](https://xentaxbackup.github.io/file/11899_ss.jpg)
## Post #21
- Username: kkdf2
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Oct 24, 2010 4:26 pm
- Post datetime: 2016-11-15T11:42:50+00:00
- Post Title: Re: Mirror's Edge Catalyst Beta

MEC's skeleton data is partially decoded. Export will be available in near future...
e.g. bundles\ebx\characters\skeletons\skeleton_faith.ebx

The decoding code sample:

```
            MemoryStream siSkel = new MemoryStream(File.ReadAllBytes(fpebx));
            BinaryReader brSkel = new BinaryReader(siSkel);

            SkelFileHeader fileHeader = new SkelFileHeader {
                Data64 = brSkel.ReadBytes(64),
            };
            siSkel.Position = fileHeader.OffsetStrBlock1 + fileHeader.LengthStrBlock1;

            brSkel.ReadBytes(16 * fileHeader.EntryCount1);
            brSkel.ReadBytes(16 * fileHeader.EntryCount2);

            SkelHeader header = new SkelHeader {
                Data160 = brSkel.ReadBytes(160),
            };

            var strBlk2 = Encoding.ASCII.GetString(brSkel.ReadBytes(fileHeader.LengthStrBlock2));
            brSkel.ReadBytes(16); //GUID?
            brSkel.ReadBytes(0x30); //?

            List<Bone> bones = new List<Bone>();
            {
                int countBones = brSkel.ReadInt32();
                Debug.Assert(countBones == header.CountBones);
                for (int x = 0; x < countBones; x++) {
                    int relativeOffsetName = brSkel.ReadInt32();
                    bones.Add(new Bone {
                        index = x,
                        name = strBlk2.Substring(relativeOffsetName).Split('\0')[0],
                    });
                }
            }
            {
                int countBones = brSkel.ReadInt32();
                Debug.Assert(countBones == header.CountBones);
                for (int x = 0; x < countBones; x++) {
                    brSkel.ReadInt32();//?
                }
            }
            {
                int countBones = brSkel.ReadInt32();
                Debug.Assert(countBones == header.CountBones);
                for (int x = 0; x < countBones; x++) {
                    bones[x].parentIndex = brSkel.ReadInt32();
                }
            }
            {
                siSkel.Position += 12 - (int)(siSkel.Position & 15);
                int countBones = brSkel.ReadInt32();
                Debug.Assert(countBones == header.CountBones);
                for (int x = 0; x < countBones; x++) {
                    bones[x].matrix1 = new float[9];

                    bones[x].matrix1[0] = brSkel.ReadSingle();
                    bones[x].matrix1[1] = brSkel.ReadSingle();
                    bones[x].matrix1[2] = brSkel.ReadSingle();
                    brSkel.ReadSingle();

                    bones[x].matrix1[3] = brSkel.ReadSingle();
                    bones[x].matrix1[4] = brSkel.ReadSingle();
                    bones[x].matrix1[5] = brSkel.ReadSingle();
                    brSkel.ReadSingle();

                    bones[x].matrix1[6] = brSkel.ReadSingle();
                    bones[x].matrix1[7] = brSkel.ReadSingle();
                    bones[x].matrix1[8] = brSkel.ReadSingle();
                    brSkel.ReadSingle();

                    bones[x].vector1 = new float[3];
                    bones[x].vector1[0] = brSkel.ReadSingle();
                    bones[x].vector1[1] = brSkel.ReadSingle();
                    bones[x].vector1[2] = brSkel.ReadSingle();
                    brSkel.ReadSingle();
                }
            }
            {
                siSkel.Position += 12 - (int)(siSkel.Position & 15);
                int countBones = brSkel.ReadInt32();
                Debug.Assert(countBones == header.CountBones);
                for (int x = 0; x < countBones; x++) {
                    bones[x].matrix2 = new float[9];

                    bones[x].matrix2[0] = brSkel.ReadSingle();
                    bones[x].matrix2[1] = brSkel.ReadSingle();
                    bones[x].matrix2[2] = brSkel.ReadSingle();
                    brSkel.ReadSingle();

                    bones[x].matrix2[3] = brSkel.ReadSingle();
                    bones[x].matrix2[4] = brSkel.ReadSingle();
                    bones[x].matrix2[5] = brSkel.ReadSingle();
                    brSkel.ReadSingle();

                    bones[x].matrix2[6] = brSkel.ReadSingle();
                    bones[x].matrix2[7] = brSkel.ReadSingle();
                    bones[x].matrix2[8] = brSkel.ReadSingle();
                    brSkel.ReadSingle();

                    bones[x].vector2 = new float[3];
                    bones[x].vector2[0] = brSkel.ReadSingle();
                    bones[x].vector2[1] = brSkel.ReadSingle();
                    bones[x].vector2[2] = brSkel.ReadSingle();
                    brSkel.ReadSingle();
                }
            }

            siSkel.Position = fileHeader.OffsetStrBlock2;
            String fullName = Util.ReadStr(brSkel);

            String fpJson = Path.ChangeExtension(fpebx, ".json");
            using (StreamWriter writer = new StreamWriter(fpJson, false, Encoding.ASCII)) {
                JsonSerializer.CreateDefault(new JsonSerializerSettings { Formatting = Formatting.Indented }).Serialize(writer, new SkelJson {
                    fullName = fullName,
                    name = Path.GetFileNameWithoutExtension(fullName),
                    bones = bones.ToArray(),
                });
            }

            String fpTxt = Path.ChangeExtension(fpebx, ".skel.txt");
            using (StreamWriter writer = new StreamWriter(fpTxt, false, Encoding.ASCII)) {
                for (int y = 0; y < bones.Count; y++) {
                    writer.WriteLine("0x{0:X2},{0,4},{1,4}, {2}", y, bones[y].parentIndex, bones[y].name);
                }
            }
        }

    public class SkelFileHeader {
        public byte[] Data64;

        public int OffsetStrBlock2 { get { return BitConverter.ToInt32(Data64, 0x04); } }

        public int EntryCount2 { get { return BitConverter.ToUInt16(Data64, 0x16); } }

        public int EntryCount1 { get { return BitConverter.ToUInt16(Data64, 0x18); } }

        public int LengthStrBlock1 { get { return BitConverter.ToUInt16(Data64, 0x1A); } }

        public int LengthStrBlock2 { get { return BitConverter.ToInt32(Data64, 0x1C); } }

        public int OffsetStrBlock1 { get { return BitConverter.ToInt32(Data64, 0x24); } }
    }

    public class SkelHeader {
        public byte[] Data160;

        public int CountBones { get { return BitConverter.ToInt32(Data160, 0x20); } }
    }

```

[skel.jpg](https://xentaxbackup.github.io/file/11919_skel.jpg)
## Post #22
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2016-11-16T22:37:50+00:00
- Post Title: Re: Mirror's Edge Catalyst Beta

This is amazing news  Thanks for your hard work!
## Post #23
- Username: MisterPrawn
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Jan 30, 2014 12:36 pm
- Post datetime: 2016-11-17T04:29:06+00:00
- Post Title: Re: Mirror's Edge Catalyst Beta

I would just like to say that the DecMECMesh tool seems really good! However, when I try to use it on a Plants vs Zombies Garden Warfare 2 .mesh file, it gives me this error:

```
   at System.IO.BinaryReader.FillBuffer(Int32 numBytes)
   at System.IO.BinaryReader.ReadInt32()
   at DecMECMesh.Program.Conv(String fpMesh, String dirConvTo, String dirChunks, Boolean ExportPy, Boolean ExportH2O, Boolean ExportOnlyFirstLOD)
   at DecMECMesh.ConvMeshForm.bwConv_DoWork(Object sender, DoWorkEventArgs e)

```


It'd be really nice if it could work with PvZGW2, just saying.
## Post #24
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-12-02T15:19:45+00:00
- Post Title: Re: Mirror's Edge Catalyst Beta

> Reply from kkdf2
>
> MEC's skeleton data is partially decoded. Export will be available in near future...

So how is it going. In my experience, binding model to skeleton may be the hardest part because of so many ways devs are doing this. Bone remaps, submeshes, groups, all of that stuff.
## Post #25
- Username: kkdf2
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Oct 24, 2010 4:26 pm
- Post datetime: 2016-12-03T13:59:23+00:00
- Post Title: Re: Mirror's Edge Catalyst Beta

> It'd be really nice if it could work with PvZGW2, just saying.
sorry, currently I don't have much time to work on other game...

> Reply from daemon1
>
> kkdf2 wrote:MEC's skeleton data is partially decoded. Export will be available in near future...

So how is it going. In my experience, binding model to skeleton may be the hardest part because of so many ways devs are doing this. Bone remaps, submeshes, groups, all of that stuff.
Skeleton exporter is ready on 0.2, pass MEC:
[http://kkdf2.sakura.ne.jp/MEC/DecMECMesh-0.2.7z](http://kkdf2.sakura.ne.jp/MEC/DecMECMesh-0.2.7z)

But it is not fully automated yet. It needs some procedures even if we convert faith's mesh and bones:

- Convert dds textures to png

- Turn on [Export .json].

- Convert all .mesh files in MEC\bundles\res\characters\faith. Drag faith's folder and drop it into [Drop file(s) or folder(s) ...] button.

- Convert MEC\bundles\ebx\characters\skeletons\skeleton_faith.ebx
You will get required file skeleton_faith.json

- Edit attached Faith.py
Modify the path:

```
bundlesDirectory = r"H:\MEC\bundles";
```


- Tweak importTables in Faith.py
Each jsonMeshFile is valid, but diffuseMap may be incorrect for most sub meshes. Please trial and error for better result!

```
    {
        "jsonMeshFile": r"res\characters\faith\armgear\magrope\magrope_skin_mesh\magrope_skin-lod1.json",
        "diffuseMap":   r"res\characters\faith\armgear\magrope\t_magrope_d ec6cb90b09fef721 0b000000010000000000000000000000.PNG"
    },
    {
        "jsonMeshFile": r"res\characters\faith\arms\faith_arms_mesh\faith_arms-lod1.json"
    },
    {
        "jsonMeshFile": r"res\characters\faith\gridlink\faith_gridlink_mesh\faith_gridlink-lod1.json"
    },
    {
        "jsonMeshFile": r"res\characters\faith\hair\faith_hair_3pcloth_ingame_mesh ba25d653909762f1 3005000070a404006800000090003001-lod1.json",
        "diffuseMap":   r"res\characters\faith\hair\t_alphahair_a 98be69afce0ddd0b 0b000000010000000000000000000000.PNG"
    },
    {
        "jsonMeshFile": r"res\characters\faith\head\faith_head_mesh 9bd03e0f689c56d9 002c190020050800f800000090003001-lod1.json",
        "diffuseMap":   r"res\characters\faith\head\t_faithhead_dao b99b387e03207ab7 0b000000010000000000000000000000.PNG"
    },
    {
        "jsonMeshFile": r"res\characters\faith\headparts\faith_headparts_mesh\faith_headparts-lod1.json"
    },
    {
        "jsonMeshFile": r"res\characters\faith\lowerbody\faith_lowerbody_mesh\faith_lowerbody-lod1.json",
        "diffuseMap":   r"res\characters\faith\lowerbody\t_lowerbody_dao fc8450880b45f12b 0b000000010000000000000000000000.PNG"
    },
    {
        "jsonMeshFile": r"res\characters\faith\toolbag\faith_toolbag_mesh\faith_toolbag-lod1.json",
        "diffuseMap":   r"res\characters\faith\toolbag\faith_pickupbag_dao 6206caa6286b3edb 0b000000010000000000000000000000.PNG"
    },
    {
        "jsonMeshFile": r"res\characters\faith\upperbody\faith_upperbody_mesh\faith_upperbody-lod1.json",
        "diffuseMap":   r"res\characters\faith\upperbody\t_arms_dao a97c9a442565aba7 0b000000010000000000000000000000.PNG"
    }
]
```


- Launch Faith.py like other exported py scripts.

```
# Runs great on Blender 2.77a
# How to:
# - Launch Blender 2.77a
# - Press Shift+[F11] to open Text Editor
# - Press Alt+O to open this script
# - Press Alt+P to run this script
# - Press Shift+[F5] to get back initial perspective view

```
## Post #26
- Username: desperado
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Aug 21, 2014 2:54 am
- Post datetime: 2017-01-07T18:10:41+00:00
- Post Title: Re: Mirror's Edge Catalyst Beta

Hello, great job. Is anyone know where is texts of the game and how can i replace them?
## Post #27
- Username: slayer983
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Jun 30, 2012 4:26 am
- Post datetime: 2017-01-14T22:44:41+00:00
- Post Title: Re: Mirror's Edge Catalyst Beta

only lark. why are these doing if not to be used in game? where repack it, replace it, import it. Files open and extract but there is no rest.

It will be more useful a thousand times than these if made a translation tool. these are only make an appearance.

Everyone can not do what you do, it also takes skill, I respect them. but it not works for me. it not works for who ones will make a difference.
## Post #28
- Username: keku645
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jan 18, 2017 6:25 pm
- Post datetime: 2017-01-18T10:36:54+00:00
- Post Title: Re: Mirror's Edge Catalyst Beta

Do you guys find out a way to extract the animations?

If someone asks who i am, I'm a Mirror's Edge modder (1st game) that we are still waiting to someone manages a way to mod MEC, until that at least me, i'm still in the first game, and i tried to export stuff from MEC into the original game, but ninja ripper worked really bad, didnt even extracted UV channels well so i gave up until i noticed this topic. Thank you so much for the tool.

At the moment my project was to "recreate" MEC into the first game, at least the city.
## Post #29
- Username: keku645
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jan 18, 2017 6:25 pm
- Post datetime: 2017-04-17T21:32:38+00:00
- Post Title: Re: Mirror's Edge Catalyst Beta

Is this topic still up?

I can't figure out a way to get models, i dont care about bones but i'd like to get the rest, i already have everything except models.
## Post #30
- Username: ximik163
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Sep 01, 2018 8:58 pm
- Post datetime: 2018-09-01T19:16:09+00:00
- Post Title: Re: Mirror's Edge Catalyst Beta

little question. all textures have a diffuse (_d) channel and normal map (_n). but what is _rsm?
## Post #31
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2018-09-01T22:44:51+00:00
- Post Title: Re: Mirror's Edge Catalyst Beta

> Reply from ximik163
>
> little question. all textures have a diffuse (_d) channel and normal map (_n). but what is _rsm?

if I had to guess it's Roughess/specular/metallic maps combined into rgb channels.
