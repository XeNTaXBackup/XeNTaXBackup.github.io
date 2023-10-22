## Post #1
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-02-18T15:18:59+00:00
- Post Title: King of Kings III BHL / LPQ

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: ericthered7
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Feb 18, 2012 2:24 am
- Post datetime: 2012-03-23T19:43:48+00:00
- Post Title: King of Kings III BHL / LPQ

Has anyone figured out anything regarding these files?  I'm interested in this game, too.

Thanks,
Eric
## Post #3
- Username: Latency
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Apr 02, 2012 7:56 am
- Post datetime: 2012-04-02T00:14:55+00:00
- Post Title: King of Kings III BHL / LPQ

They are proprietary LZO real-time compressed and more than likely use SHA1/ZLib as its hash.  See Markus Franz Xaver Johannes Oberhumer [markus.oberhumer@jk.uni-linz.ac.at](http://markus.oberhumer@jk.uni-linz.ac.at)     The payload consists of DirectDraw Surface gfx for icons and other things if you look at the headers in the icons.lpq file which are consistent for many of the other in-game related images required for alpha-blending and other sorts of things they are using with DirectX.

Maybe there is a utility that is already out there to uncompress these, but I doubt they would have it available to the public.   It's one way they can conceal the files from people re-producing and using artwork and other sort of proprietary game information without authorization.  Not only that, but the storage space is minimal and they can push updates to the client faster.  These all get decompressed at runtime and are cached into memory upon load.

What is interesting is rather than checking against a version file, they check CRC on all files with an update Login.exe which then exec's the WE.exe.   You can also try the WE_lite.exe version too.  Not sure what the difference in that is.. maybe the profiling information was stripped..  idk?  I tried to bypass the update one.. but received an NPE or unalloc'd reference to something way down when it tried to load the form.  Just decided to give up at that point.  What I am thinking is that the Login.exe is passing an argument of some sort to the WE.exe as it can reuse itself.

The algorithms for the uncompression are going to be found in one of the libraries or integrated within the game binary itself.  Notice they are using dynamic loading of assemblies and embedding cursors and things related in the resources within; having eliminated many of the external files from the distro, exactly what I would do.  The zlib library is in there, so it supports my claims typical to what may occur and adds a bit of security in its overall appearance, possibly used for data Tx's as well looking at the packet encapsulation methods.

Notice there are only a couple proprietary libraries in there.  Start with the BitMapGraphics dynamically linked library and trace that into the PE.  If you can find its entry point and inject a hook to it for dump or just crop it out and inline it into your own assembly.  Look for the .lpq & .bhl file I/O which is an easy marker for its OEP.  It shouldn't be that difficult but if you do get to that point,  verify the ordering of the bits just to be sure.  Nothing is fool-proof but you have work cut out for you.

If you do make headway on your research, be sure to share with us your utility and notify me as I would be interested in taking a look since I am far too busy to do this myself.   PM me in game or email me what project or idea you were thinking of using these for, I might be interested in helping out more if you have skills.

PS.
  When I find out who the idiot is that came out with that [Area] chat bot spammer, I'm going to rape the living *HIT out of you and report you.  Last thing in the world anybody wants is to have you ruin this game like D2.
## Post #4
- Username: ericthered7
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Feb 18, 2012 2:24 am
- Post datetime: 2012-04-02T00:54:43+00:00
- Post Title: King of Kings III BHL / LPQ

Thanks Latency.  I'll try to take a look along these lines.  But I'm guessing I'll be in over my head.

-Eric
## Post #5
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-04-03T15:36:32+00:00
- Post Title: King of Kings III BHL / LPQ

Not anymore needed
## Post #6
- Username: Latency
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Apr 02, 2012 7:56 am
- Post datetime: 2012-07-21T06:44:57+00:00
- Post Title: King of Kings III BHL / LPQ

While you might not have a need for it anymore, I am sure others do.  I will share my research for those who want to know.

One of the things that are being used in conjunction with this is what I believe to be a Partminer Lib file. 
This .bhl file could contain the shared key / password cipher for the data.

Inspected:  .bhl & .lpq files.   While some of the ones from Fairyland game (for example) have some file name references in there, but don't let that fool you.  It is nothing more than a binary array of objects.  This TOC for the packed array is not found anywhere externally, so my guess is it is compiled internally into the PE or ciphered into the .bhl.

Tested:  (un)zpaq102.exe  did not find anything even after removing detection for EOF.
             Peazip - Nothing found either.  I use this, since it supports *PAQ files... however I selected to use the .bhl file as the keyfile, null/anonymous/<guessed a couple> passwords to try & match it. The question is why would the 'BM..' signatures remain with filename target strings visible in raw data?  Also, various layout associations for GUI formatting in plain text also reside in the 'interface.lpq'.  If this was a compressed archive, don't you think those would have been included?  Perhaps some but not all.

Test case:  Assuming only the images where bundled together and used a generic file type + proprietary signature to identify, cut out the block section of each file and save it as its corresponding file type.  Ex.) For .bmp - use [this](http://www.fastgraph.com/help/bmp_header_format.html) as reference.  Find your EOF.   There are .DDS, .ico, and other format types that are in these as well.  Remember, it is just an object array.  Ideally, finding a TOC with the file name associations to the compressed packed array would be nice to have.

Next step:      Disassemble the libraries (did that already) &| PE and write some hooks to dump out the content when loading the game.  Shouldn't be too difficult, just time consuming to trace the binary out and write your patch.

I found there to be a table def for a bunch of constants.
It then goes through and loops $PWD\*.lpq  where it checks also for any *update.lpq of Array[%d].

```
  ecx
  aMesh_stuff ; "MESH_STUFF"
  aMesh ; "mesh"
  aMesh_0 ; "mesh/"
  aInterface_stuf ; "INTERFACE_STUFF"
  aInterface ; "interface"
  aInterface_0 ; "interface/"
  aEffect_path ; "EFFECT_PATH"
  aEffect ; "effect"
  aEffect_0 ; "effect/"
  aMapdata_path ; "MAPDATA_PATH"
  aMapdata ; "mapdata"
  aMapdata_0 ; "mapdata/"
  aMap_path ; "MAP_PATH"
  off_852CD4
  aMap  ; "map/"
  aShore_path ; "SHORE_PATH"
  aShore ; "shore"
  aShore_0 ; "shore/"
  aConfig_path ; "CONFIG_PATH"
  aConfig ; "config"
  aConfig_0 ; "config/"
  aIcons_path ; "ICONS_PATH"
  aIcons ; "icons"
  aIcons_0 ; "icons/"
  aLight_data ; "LIGHT_DATA"
  aLights ; "lights"
  aLights_0 ; "lights/"
  aThread_speed_t ; "THREAD_SPEED_TREE"
  aSpeedtree ; "speedtree"
  aSpeedtree_0 ; "speedtree/"
  aAudio_path ; "AUDIO_PATH"
  aAudio ; "audio"
  aAudio_0 ; "audio/"
  aShader_path ; "SHADER_PATH"
  aShader ; "shader"
  aShader_0 ; "shader/"
  aShadowmap_path ; "SHADOWMAP_PATH"
  aShadowmap ; "shadowmap"
  aShadowmap_0 ; "shadowmap/"
  aCttw_path ; "CTTW_PATH"
  aCttw ; "cttw"
  aCttw_0 ; "cttw/"
}
```


Then it comes to the processing of the types once all the data has been loaded into memory.
loc_61341F:

TextureFromFileInMemory:
Source is in plain view with the virtual file path associated @ 006135AA.
Need to dump the register to a file with the name provided.

'xcptlib.dll' is derived from crashrpt.dll and imports from kernel32.dll.   It then goes to dump the crash report into the necessary files with information used to identify the general area in the game code where the fault happened.  Acts as if it runs in its own process monitor virtual debugger.  It is no wonder that this library is nothing more than a wrapper for everything you can think of for std lib calls, etc... to trap.   E.g. nothing special or of importance in this file.
  After a segfault, it then bundles up all the related files into a .zip archive and is using 'zlib.dll' I am sure for this.   The symbol tables are found on where to export '_s_Crash_s_zip'  = "%s\Crash%s.zip"  where 1st arg specifies the relative game path + dump_folder .. 2nd argument is timestamp-to-text.  

'BMGlib.dll' is just a utility library that has routines for managing image type files, also supports various compression schemas, and conversions to GreyScale, etc.  This is a common file for various games, and is unpacked.   I didn't find anything relating to the pack or assembly of the .lpq file itself.  Just a straight drop in from other games.  This is to be used after you get the binary data out of the array and mapped to its corresponding file name.

See also.. Project64 & Rice Video plugin, MSVCP71.DLL

Manifest for KOK3:
            File:                    WE.exe
            LegalCopyright:     Copyright (C) 2004
            Comments:           Lager
## Post #7
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-07-21T08:20:54+00:00
- Post Title: King of Kings III BHL / LPQ

It's not ZPAQ. For work with LPQ used LagerPacket.dll
## Post #8
- Username: Latency
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Apr 02, 2012 7:56 am
- Post datetime: 2012-07-22T07:24:41+00:00
- Post Title: King of Kings III BHL / LPQ

Yes, I already figured out where in the PE I need to dump, but I don't see the function declarations I need listed in the 'LagerPacket(OMF).dll's.

Closest thing I could come up with is:
 int __cdecl sub_4076E4(int, LPCSTR lpString2)  @ offset [00006CE4]
 int __cdecl sub_402FA4(int, char *src, char, LPCSTR lpFileName, int, int) @ offset [000025A4]

Where arg_0 or 8? = Read or Write
Maybe arg_0 =  fPos_offset  .. ?


Exports:
> sed -e "s/^.*Function: //;/^\/\/.*/d;/^$/d" < lagerpacket.dll.txt

public: __thiscall CLpqPatcher::CLpqPatcher(class CLpqPatcher const &)
public: __thiscall CLpqPatcher::CLpqPatcher(class ILagerPacket *,class ILpqPatchBuilder *)
public: __thiscall ILagerPacket::ILagerPacket(class ILagerPacket const &)
public: __thiscall ILagerPacket::ILagerPacket(void)
public: __thiscall ILpqPatchBuilder::ILpqPatchBuilder(class ILpqPatchBuilder const &)
public: __thiscall ILpqPatchBuilder::ILpqPatchBuilder(void)
public: __thiscall ILpqSystem::ILpqSystem(class ILpqSystem const &)
public: __thiscall ILpqSystem::ILpqSystem(void)
public: virtual __thiscall CLpqPatcher::~CLpqPatcher(void)
public: virtual __thiscall ILagerPacket::~ILagerPacket(void)
public: virtual __thiscall ILpqPatchBuilder::~ILpqPatchBuilder(void)
public: virtual __thiscall ILpqSystem::~ILpqSystem(void)
public: class CLpqPatcher & __thiscall CLpqPatcher::operator=(class CLpqPatcher const &)
public: class ILagerPacket & __thiscall ILagerPacket::operator=(class ILagerPacket const &)
public: class ILpqPatchBuilder & __thiscall ILpqPatchBuilder::operator=(class ILpqPatchBuilder const &)
public: class ILpqSystem & __thiscall ILpqSystem::operator=(class ILpqSystem const &)
const CLpqPatcher::`vftable'
const ILagerPacket::`vftable'
const ILpqPatchBuilder::`vftable'
const ILpqSystem::`vftable'
unsigned long __cdecl CalcLpqCheckSum(void *,unsigned long)
public: virtual int __thiscall CLpqPatcher::CreatePatchFile(void)
public: virtual void __thiscall CLpqPatcher::DeletePatchBlockFile(char *)
public: virtual int __thiscall CLpqPatcher::ExtendPatchFile(void)
public: virtual int __thiscall CLpqPatcher::ProceedPatch(char *)
void __cdecl SetLpqCallback(unsigned long,int (__cdecl*)(class ILagerPacket *,int,int))
int g_nLpqErrCode
class ILpqSystem * g_piLpqSystem


> sed -e "s/^.*Function: //;/^\/\/.*/d;/^$/d" < lagerpacketomf.dll.txt

qualified constructor ILagerPacket::ILagerPacket()
qualified destructor ILagerPacket::~ILagerPacket()
qualified constructor ILagerPacket::ILagerPacket()
qualified destructor ILagerPacket::~ILagerPacket()
function SetLpqCallback(unsigned long, int (*)(ILagerPacket *, int, int))
qualified constructor ILpqSystem::ILpqSystem()
qualified destructor ILpqSystem::~ILpqSystem()
qualified destructor ILagerPacket::~ILagerPacket()
qualified destructor ILpqPatchBuilder::~ILpqPatchBuilder()
qualified constructor CLpqPatcher::CLpqPatcher(ILagerPacket *, ILpqPatchBuilder *)
qualified destructor CLpqPatcher::~CLpqPatcher()
qualified function CLpqPatcher::CreatePatchFile()
qualified function CLpqPatcher::ExtendPatchFile()
qualified function CLpqPatcher::ProceedPatch(char *)
qualified function CLpqPatcher::DeletePatchBlockFile(char *)
qualified constructor ILpqPatchBuilder::ILpqPatchBuilder()
qualified destructor ILpqPatchBuilder::~ILpqPatchBuilder()


Anybody want to give me some help or confirm this?  A dump utility would be great... or I can write one if you can help me figure out what to import.  I just don't see it... and I know the input image files are .dds in array form, minus the file signatures and just the raw binary.   I had thought the index list was embedded in the PE that it maps to.  *scratches head*

I will try to dump the data out of the registers in the PE for now since the breakpoint I posted has already split the array for me at this point.

  Thank you.
## Post #9
- Username: Joebine162
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Mar 17, 2021 5:12 am
- Post datetime: 2021-03-16T21:14:27+00:00
- Post Title: King of Kings III BHL / LPQ

Hello was anyone able to RE this game?
