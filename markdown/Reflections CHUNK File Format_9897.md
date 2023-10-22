## Post #1
- Username: CarLuver69
- Rank: advanced
- Number of posts: 50
- Joined date: Fri Mar 09, 2012 1:17 am
- Post datetime: 2012-11-21T04:28:08+00:00
- Post Title: Reflections CHUNK File Format

Since DRIV3R, Reflections has used a form of this "CHUNK PACKAGE" file format that is basically a unified package containing everything from models to textures, positions in the game world, flags...everything you could possibly think of. It is important to note that the content inside these archives (if they are even archives) are not compressed in any way, shape, or form - one of the major aspects of these files is that there are offsets EVERYWHERE. The very beginning of the files define offsets and block size - there are even sub-chunks inside the big chunk that have offsets as well. Essentially what's going on is each chunk is like a tupperware container with smaller containers inside of it. Once the chunk format is decoded in DRIV3R, we can move onto other games such as DPL or even DSF! The format is exactly the same, the only differences are the new file formats inside of these chunks. Not a big deal, but having chunks out of the way would be nice!

There is no one specific file extension, as it varies depending on what it does. My research here is based on DRIV3R for the PC, and I essentially have no experience in programming myself, which is why I've taken up this project!

Here's some decoding of the CHUNK based file format, using MIAMI_DAY_PC/SuperRegions.pcs as an example:



NOTE: This image has outdated information. To be used for reference only!

CHUNK files have "PCMP" sections that hold DDS textures. It contains complex offsets (to me, at least) describing where each new DDS begins and how long it is. A good friend of mine helped me decode the headers a bit, here's what we came up with (sorry if it's not very specific, I didn't make this picture but will when further documentation arises):



UPDATE 11/22/2012: New organization, more info added.
## Post #2
- Username: CarLuver69
- Rank: advanced
- Number of posts: 50
- Joined date: Fri Mar 09, 2012 1:17 am
- Post datetime: 2012-11-21T07:56:32+00:00
- Post Title: Reflections CHUNK File Format

This post is reserved for an in-depth analysis of each file.

CITIES
The cities of DRIV3R is basically what makes up the whole game - Miami is 390MB, Istanbul is 319MB, and Nice is 286MB. On average, each city has close to over 3,500 textures and an unknown amount of models. According to older work-in-progress screenshots, a program called "Mr. RoadBuilder" was used to create every aspect of the city itself. Here are the only screenshots ever released:




This could give potential reverse engineers an insight into how everything works. Note in the upper-right corner there are references to "Global Regions" and "Super Regions" - these are important to take note of, as they play a crucial part in my observations below. Without further ado...

Legend:

-- = Folder
---- = Inside Folder

city = Name of the city (Miami, Nice, or Istanbul)
timeofday = DAY or NIGHT
platform = I'm assuming what platform it's mean for (in this case, PC = _PC)

.d3c = DRIV3R City. These are known as "Global Regions" that basically make up the whole of the city. The .D3C file interacts with the .PCS file somehow, as there are no models or textures inside.
.pcs = Models and textures for the city. How the .D3C files access these is currently unknown.

--city_timeofday_platform*
----Interiors.pcs**
----SuperRegions.pcs***
city_timeofday_platform.d3c****

* - By default there are 6 folders - Miami with day textures is called "MIAMI_DAY_PC" and with night textures is "MIAMI_NIGHT_PC". The rest is self-explanatory.
** - Definitions for interiors are in here.
*** - Definitions for the outside world you drive in.
**** - For each folder, day or night, there is a .D3C file accompanied by it.

.PCS Files - Last Updated 11/22/2012
.PCS files contain the models and textures that make up the city. The .D3C file uses this file as an index in order to retrieve models amongst other things.

.D3C Files - Last Updated 11/22/2012
These files are very rich in content - these are the biggest CHUNK based files in the whole game. There's so much to a city it's unbelievable. More information will be put here later on.

CONFIGS
Vehicle configurations for every vehicle in the game are in here.

----Vehicles
----BigVO3
----*.b03*

* one for each city

.B03 Files - Last Updated 11/22/2012
While they're not CHUNK based files, they are still a crucial part of the game that need to be documented more. Vehicle handling, colors, etc. for every vehicle in the game.

GUNS
Weapons data located in here.

--Guns.cpr

.CPR Files - Last Updated 11/22/2012
Guess who forgot to document these files? 

MISSIONS
The mission scripting language related files can be found here.

--Personalities
----*.acp
--Recordings
----*.pad
*.dam
*.mpc

.ACP Files - Last Updated 11/22/2012
AI behavior files. Not much is known.

.PAD Files - Last Updated 11/22/2012
Vehicle recording files. These were probably made in a special developer mode that records player movement similar to the Film Director.

.MCP Files - Last Updated 11/22/2012
Exported mission scripts. There was most likely a stage where they were written in a plain-text format and later converted to this special format that uses IDs from locale files.

.DAM Files - Last Updated 11/22/2012
Contains models and textures for each mission. There are a variety of things in here, so its main purpose is unknown. However, it is used to define character models/textures/joints/etc. !

OVERLAYS
I'll update this section at another time.

*.bin
*.gfx
*.map

SFX (Sound Effects)
I'll update this section at another time.

Sfx.pmu

Skies
I'll update this section at another time.

*.d3s

Sounds
I'll update this section at another time.

*.dat
*.vsb

GUI
I'll update this section at another time.

*.mec

Vehicles
I'll update this section at another time.

--city
----CarGlobals[city].vgt

*.VVS
*.VVV
## Post #3
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2012-11-21T20:39:13+00:00
- Post Title: Reflections CHUNK File Format

i found the demo online. there is a description offset in the headers which is most useful .

other notes i made:

Data is chunked with the following header:

uint32 magic ("CHNK")
uint32 fileSize
uint32 chunkCount
uint32 version (3 == Driv3r?)

The minimum size is 16 bytes

Chunks have the following header:

uint32 magic
uint32 chunkOffset
uint32 flags (? based on what you found out)
uint32 descOffset

chunkOffset is relative to the start of the CHNK header
descOffset is relative to the chunkOffset and CHNK header


Chunk data is aligned to 4096 bytes
So are descriptions

Empty memory is filled using the magic DEC015A1h

This is useful when reading the description info:

You can read 4 bytes at a time and xor until you hit 0


Other

Chunks may contain more chunked data (with CHNK magic)

GESR  Super region
GEGR  Global region
GEIR  Interior region
PINF  Mission editor model info
PCSL  Dummy chunk
MDPC  Model package


Files using this structure:

Overlays/*.map
Overlaps/*.gfx
Cities/*.d3c
Cities/ (see op) /*.pcs
## Post #4
- Username: CarLuver69
- Rank: advanced
- Number of posts: 50
- Joined date: Fri Mar 09, 2012 1:17 am
- Post datetime: 2012-11-22T03:34:19+00:00
- Post Title: Reflections CHUNK File Format

UPDATE 11/22/2012:

Lots of new info today. Wrote a small BMS script (see below) and took the time to document every single file type in the game. Without further ado, here are my huge ass research documents!

I'm not quite sure what I was going for with this one, but it seems to be useless since the one below this one is almost the exact same.

```
	- Archive-like tendencies:
		- Defines size of chunk
		- Defines # of packages inside
	- Always has an unknown LONG at the end; "03 00 00 00" (3 in little endian)
		- Possibly version number (credits go to user WRS)
	- Package offsets begin on the line of the CHNK header:
		- For example, let's say "BLAH" has offset of "00 10 00 00" (or 1000). This means the beginning of "BLAH" is offset 1000 from the CHNK header. Got all that?
		- Offsets are 4096 byte-aligned (credits go to XeNTaX)
	- Files inside CHUNK's are uncompressed ASCII format, however they are not common file formats and are not meant to be used as external files. Files inside chunks need to be extracted, modified, and have offsets/checksums recalculated - a relatively easy process once everything is totally understood.
	- Acts as a container
		- Nesting capabilities:
	
			CHNK
			[parent]
				CHNK
				[child/parent]
					CHNK
					[child/parent]
						CHNK
						[child/parent]
						...
				[child]
				[child]
			[parent]
			
		- Think of the chunk as a big tupperware container; You can put other smaller containers inside, as well as a couple of other things on the side.

"Unified Package"
	- The result of a package having no specific name assigned (all 00's)
	- Acts as a container that holds another chunk inside of it, most likely so the main chunk itself can access it and then start doing sub-routines. Why this is necessary is unknown, maybe just for organization.
	- No further information.
	
-------------------------
%CITY%.D3C
------------------------- 
GESR (Global Region)
----GEPM (Building Physics Data)
----PMLD (Building Physics Lookup Data)
----GWTR (Water Instance Data)
----GEBI (Global Building Instance Data)
----GERD (Spline Road Data)
--------AIEX (AIExport)
----ANOD (Animated Object Data)
----SCND (Global Scene Data)
----GEPD (Prop Data Container)
--------HRDT (Prop Hiearchy Information)

GEIR (Region %0d)
----GWRD (Water Region Data)
----GEBI (Building Instance Data)
----GRTD (Region Terrain)
----GEBR (Building Routefind Data)
----JNR! (Broadphase Data)
----ATRD (Attractor Data)
----SCND (Region SceneData Data ?)
----OCGD (Occluder Game Data)

IRCT (External file link + External?)
----ATRD (Interior Attractor Object Data)
----ANOD (Interior Animated Object Data)
----GEBI (Interior Instance Data)
----IRDT (Interior Scene Data )
----GEPM (Interior Physics Model Data)
----PMLD (Interior Physics Lookup Data)
----JNR! (Interior Broadphase Data)
----ISHM (Interior Lighting Data)
--------PROBv1.0 (unknown format - unused?)
GESR (again?) (External file link + Internal?)
----GEPD (Prop Data Container)
--------HRDT (Internal Interior Prop Hierarchy Prop-Data Container)

PINF (Model Information for Mission Editor)
----PIND (Model Data for Mission Editor)
----PINS (Model Strings for Mission Editor)

GEGL (Grandiose Lookup?)
----GESI (Super Region Info)
----GILH (Lookup Header)
----GSIL (Super Region Lookup )
----GRIL (Region Lookup)
----IRLU (Interior Lookup Info)

PCSL (Specific Region? "NORTH DOWNTOWN")
----GEPM (Building Physics Data)
----PMLD (Building Lookup Physics Data)
----ANOD (Animated Object Data)
	
-------------------------
MISSION%0d.MPC
------------------------- 
"Exported Mission Root"
Description: Basically a "shrink wrap" for the exported mission data.

----EM__ (Exported Mission)
	Description: Holds all mission-related data. Nested multiple times (rare).
	
--------EMOB (Exported Mission Objects)
--------EMPR (Exported Mission Prop Handles)

--------LELD (Logic Export Data)
------------LESC (String Collection)
------------LESB (Sound Bank)

------------LEAC (Actors)
--------------------LEAD (Actor Definitions)
--------------------LEPR (Actor Properties Table)

------------LENC (Logic Nodes)
--------------------LEND (Logic Node Definitions Table)
--------------------LEPR (Logic Node Properties Table)

------------LEAS (Actor Set Table)
------------LEWC (Wire Collection)
------------LECO (Script Counter)

-------------------------
MISSION%0d.DAM
------------------------- 
"Unified Packager"
Description: Presumably stuff related to models and characters for each specific mission.

----MDPC (Renderer Model Package)
----UPXD (Extra Character Data Package)
----UPCB (Skelton Package)

EMMS (Mission Summary)
Description: Probably used for locale purposes.

-------------------------
%CITY%.MAP
------------------------- 
"Unified Packager"
Description: The HUD map.

----MDPC (Renderer Model Package)

-------------------------
*.GFX
-------------------------
"Unified Packager"
Description: Packaged graphics, each with a different purpose.

----UPST (Standalone Textures)
----MDPC (Renderer Model Package)

-------------------------
SFX.PMU
-------------------------
"Unified Packager"
Description: No idea what these are for...sound effects need textures?

----UPST (Standalone Textures)
----MDPC (Renderer Model Package)

-------------------------
*.MEC
-------------------------
RDMP (Reflections Menu Data Package)
Description: Contains menu data chunks

----RMDL (Reflections Menu Data Chunk)
----MDPC (Reflections Menu Material Chunk)

-------------------------
FONT.BNK
-------------------------
FONT (Font Container)
Description: Holds information regarding fonts for DRIV3R. Universal.

----UPST (Standalone Textures [lContainerPa?])
----MDPC (Renderer Model Package)
----FBNK (Font Data)

-------------------------
CARGLOBALS%CITY%.VGT
-------------------------
"Unified Packager"
Description: Contains global content used for vehicles, such as interiors, brakelights, etc.

----UPST (Standalone Textures)
----MDPC (Renderer Model Package)

-------------------------
%CITY%.VVS
-------------------------
"Individual Model"
Description: Each individual car model, along with textures, is contained in here. UPVH has an unknown LONG at the beginning in place of the usual magic numbers - this should be noted.

----UPVH (Vehicle Hiearchy)*
--------AWHF (Unknown Format)

MDPC (Renderer Model Package)*

-------------------------
%CITY%.VVV
%CITY%_ARTIC_TRUCK.VVV
%CITY%_BOAT.VVV
%CITY%_BIKE.VVV
MISSION%0d.VVV
-------------------------
"Unified Packager"
Description: This is an interesting one. There's a .VVV file for the city, the semi truck, boats, motorcycles, and individual missions. Could this be vehicle selection?

----UPVH (Vehicle Hiearchy)*
--------AWHF (Unknown Format)
----MDPC (Renderer Model Package)*

* means multiple instances
```


This one is similar to above, but it mimics the exact format of the files:

```

	../[CITY]_[TIMEOFDAY]_[PLATFORM]
	*.PCS
	
	CHNK
	MDPC - ModelPackage_PC

*.D3C

CHNK
GESR - Global Region
	CHNK
	GEPM - Building Physics Data
	PMLD - Building Physics Lookup Data
	GWTR - Water Instance Data
	GEBI - Global Building Instance Data 
	GERD - Spline Road Data
		CHNK
		AIEX - AIExport
	ANOD - Animated Object Data
	SCND - Global Scene Data
	GEPD - Prop Data Container
		HRDT - Prop Hiearchy Information
GEIR - Region
	CHNK
	GWRD - Water Region Data
	GEBI - Building Instance Data
	GRTD - Region Terrain
	GEBR - Building Routefind Data
	JNR! - Broadphase Data
	ATRD - Attractor Data
	SCND - Region SceneData Data ?
	OCGD - Occluder Game Data
IRCT - External file link + External?
	CHNK
	ATRD - Interior Attractor Object Data
	ANOD - Interior Animated Object Data
	GEBI - Interior Instance Data
	IRDT - Interior Scene Data 
	GEPM - Interior Physics Model Data
	PMLD - Interior Physics Lookup Data
	JNR! - Interior Broadphase Data
	ISHM - Interior Lighting Data
		PROBv1.0 (unknown format - unused?)
GESR (again?) - External file link + Internal?
	CHNK
	GEPD - Prop Data Container
		CHNK
		HRDT - Internal Interior Prop Hierarchy Prop-Data Container
		
PINF - Model Information for Mission Editor
	CHNK
	PIND - Model Data for Mission Editor
	PINS - Model Strings for Mission Editor
GEGL - Grandiose Lookup?
	CHNK
	GESI - Super Region Info
	GILH - Lookup Header
	GSIL - Super Region Lookup 
	GRIL - Region Lookup
	IRLU - Interior Lookup Info
PCSL - "NORTH DOWNTOWN" ?
	CHNK
	GEPM - Building Physics Data
	PMLD - Building Lookup Physics Data
	ANOD - Animated Object Data

/MISSIONS
*.MPC

CHNK
[blank] - Exported Mission Root
	CHNK
	EM__ - Exported Mission
		CHNK
		EMOB - Exported Mission Objects
		EMPR - Exported Mission Prop Handles
		LELD - Logic Export Data
			CHNK
			LESC - String Collection
			LESB - Sound Bank
			LEAC - Actors
				CHNK
				LEAD - Actor Definitions
				LEPR - Actor Properties Table
			LENC - Logic Nodes
				CHNK
				LEND - Logic Node Definitions Table
				LEPR - Logic Node Properties Table
			LEAS - Actor Set Table
			LEWC - Wire Collection
			LECO - Script Counters
EMMS - Mission Summary
	
*.DAM

CHNK
[blank] - Unified Packager
	CHNK
	MDPC - Renderer Model Package
	UPXD - Extra Character Data Package
	UPCB - Skelton Package
	
/OVERLAYS
*.MAP

CHNK
[blank] - Unified Packager
	CHNK
	MDPC

*.GFX

CHNK
[blank] - Unified Packager
	CHNK
	UPST - Standalone Textures
	MDPC - Renderer Model Package
	
/SFX

*.PMU

CHNK
[blank] - Unified Packager
	UPST - Standalone Textures
	MDPC - Renderer Model Package
	
/TERRITORY/[LOCALE]

	../GUI
	*.MEC
	
	CHNK
	RDMP - Reflections Menu Data Package
		CHNK
		RMDL - Reflections Menu Data Chunk
		MDPC - Reflections Menu Material Chunk
	
	../LOCALE/[LANGUAGE]..

		../FONTS
		*.BNK
		
		CHNK
		FONT - Font Container
			CHNK
			UPST - Standalone Textures (lContainerPa?)
			MDPC - Renderer Model Package
			FBNK - Font Data
		
/VEHICLES

	../[CITYNAME]
	*.VGT
	
	CHNK
	[blank] - Unified Packager
		CHNK
		UPST - Standalone Textures
		MDPC - Renderer Model Package
	
*.VVS

CHNK
[UNKNOWN long] - Individual Model
	CHNK
	UPVH - Vehicle Hiearchy
		AWHF (Unknown Format)
MDPC - Renderer Model Package

*.VVV

CHNK
[blank] - Unified Packager
	CHNK
	UPVH - Vehicle Hiearchy
		AWHF (Unknown Format)
	MDPC - Renderer Model Package

```
## Post #5
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2012-11-22T03:35:49+00:00
- Post Title: Reflections CHUNK File Format

alright, my turn to bump

i've written a rough bms script to dump the dds textures from the GFX files (for now)

overlays.gfx - gui stuff; weapon highlights
loading.gfx - the spinning disk icon and the driv3r logo (attached)

```
# v0.01 - rough recursive script based on demo filedata
# WRS (xentax.com)

set OFFSET long 0
callfunction ParseChunk 1
cleanexit


startfunction ParseChunk
  getdstring BLOCKTYPE 4
  get BLOCKSIZE long
  get CHUNKS long
  get VERSION long

  if BLOCKTYPE != "CHNK"
    print "Unknown chunk header"
    cleanexit
  endif

  if VERSION != 3
    print "Unknown version"
    cleanexit
  endif

  for CHUNK = 1 to CHUNKS
    getdstring CHUNKTYPE 4
    get CHUNKOFF long
    get CHUNKUNKNOWN long
    get CHUNKSIZE long

    if CHUNKTYPE = "MDPC"
      print "Found info header"
      math LOCALOFF = CHUNKOFF
      math LOCALOFF += OFFSET
      math LOCALOFF += 4096  ## unknown heading
      goto LOCALOFF
      idstring "PCMP"
      get VER long # 3 again
      get FILES long
      getdstring IGNORE 32
      get HEADERINFO long
      math HEADERINFO -= 48 # we read 4+4+4+32+4 bytes
      savepos POS
      math POS += HEADERINFO
      goto pos
      ## now we have our headers
      math LOCALOFF += 4096 # again, assumptions
      for F = 1 to FILES 
        get FUNKNOWN long # 01010101h (no idea)
        get FCHECKSUM long # CRC32 of the DDS data
        get FOFFSET long # relative to LOCALOFF for now
        get FSIZE long
        getdstring FIGNORED 16 # ignorable data

        math FOFFSET += LOCALOFF
        string FNAME p= "%i_%08X.dds" F FCHECKSUM
        log FNAME FOFFSET FSIZE

      next F
      print "Done!"
      cleanexit
    endif

  next CHUNK

  if CHUNKTYPE = "" and CHUNKS = 1
    math LOCALOFF = CHUNKOFF
    math LOCALOFF += OFFSET
    math OFFSET = LOCALOFF
    #save CURPOS
    goto OFFSET
    print "Next level down.."
    callfunction ParseChunk 1
  endif

endfunction

```


more to come   
[savedas.png](https://xentaxbackup.github.io/file/6020_savedas.png)
## Post #6
- Username: CarLuver69
- Rank: advanced
- Number of posts: 50
- Joined date: Fri Mar 09, 2012 1:17 am
- Post datetime: 2012-11-22T03:41:15+00:00
- Post Title: Reflections CHUNK File Format

I actually wasn't expecting anyone to try and help out, this is quite unexpected. Here's a BMS script of my own (my very first one, I'm working on a more advanced one)

```
# © CarLuver69
# This code is experimental and may not even work properly in some case.
# Use at your own discretion.

	#Define what a CHUNK is, duh
	set EDMONDSON "Reflections CHUNK"

# CHUNK loading
	
	getdstring CHNKNM 0x04
	
#If it's not a Reflections CHUNK, don't load it!	
	if CHNKNM = CHNK
		set TYPE 0
	else
		print "\nERROR: Not a %EDMONDSON% File!\nHeader is %CHNKNM%, please correct this."
		cleanexit
	endif
	
#If it's a Reflections CHUNK, go ahead and load it!
	if TYPE = 0
			get CHNKSZ long
			get NUMPAKS long
			get DUMMY long
			print "\nType: 	%EDMONDSON%\nSize: 	%CHNKSZ%kb\n# Packages: 	%NUMPAKS%\n"
	endif

# Load the packages

goto 0x10
		
for i = 0 < NUMPAKS

	getdstring PAKNAME 0x04
	get PAKOFFSET long
	get PAKTYPE short
	get DUMMY short
	get PAKSIZE long
	
	# Files need a unique identifier and extension

	set DOMATH long
	set SUFFIX ".CHUNK" #Assign .CHUNK as file extension
	
	math DOMATH += PAKOFFSET #get offset
	string PAKNAME += DOMATH #assign offset to filename
	string PAKNAME += SUFFIX #assign .CHUNK to end of file ;)
	
	log PAKNAME PAKOFFSET PAKSIZE
	
next i

```


It lists all of the primary "packages" inside of the CHUNK. The new one will be able to dig deeper down into the files, and be able to expose parents and children - still working on my research document(s) so I'll hold off on that.
## Post #7
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2012-11-22T03:46:48+00:00
- Post Title: Reflections CHUNK File Format

if you're just posting a work-in-progress of your own i will leave you to it    if you need a hand send me a pm or something
## Post #8
- Username: CarLuver69
- Rank: advanced
- Number of posts: 50
- Joined date: Fri Mar 09, 2012 1:17 am
- Post datetime: 2012-11-22T04:16:37+00:00
- Post Title: Reflections CHUNK File Format

No no WRS, I'm actually quite excited you're looking into this stuff. I'm working on research and practicing BMS because I want to take up programming and stuff, so I gotta start somewhere. You're more than welcome to post research here, it'll help get the format cracked faster! 

I didn't mean "quite unexpected" in a bad way now that I read it again. I just meant that it came to me as a shock that people were actually willing to help out, which is pretty neat.

Maybe you could take a stab at the more complex files? The most I can do is decode how everything is stored, cracking the formats is nearly impossible for someone like me. For example, open one of the .VVS files inside the "Vehicles" folder and look for "AWHF" - this is all the data for an individual vehicle, stored in some type of .X file format that's been modified to work differently.
## Post #9
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2012-11-24T01:30:30+00:00
- Post Title: Reflections CHUNK File Format

i started writing a small program to explore the chunks a little better - [https://github.com/x1nixmzeng/Explor3r](https://github.com/x1nixmzeng/Explor3r)

it essentially does what you documented here: [viewtopic.php?p=81162#p81162](http://forum.xentax.com/viewtopic.php?p=81162#p81162) using recursion to identify which CHNK blocks are themselves CHNK blocks
## Post #10
- Username: CarLuver69
- Rank: advanced
- Number of posts: 50
- Joined date: Fri Mar 09, 2012 1:17 am
- Post datetime: 2012-11-24T07:15:02+00:00
- Post Title: Reflections CHUNK File Format

This program is pretty much exactly what I had in mind! Excellent work!

Just a quick note, that unknown long that's at the end of the "CHNK" line isn't the version number - it's the same in Parallel Lines and San Francisco. I wonder what it's meant for.
## Post #11
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2012-11-27T00:43:00+00:00
- Post Title: Reflections CHUNK File Format

minor update

slow progress with the model data

the renderer model package chunks (MDPC) contain the models (faces indices, vertex data and textures) but i'm stuck on reconstructing them. all i think i've found is the normal data:
## Post #12
- Username: CarLuver69
- Rank: advanced
- Number of posts: 50
- Joined date: Fri Mar 09, 2012 1:17 am
- Post datetime: 2012-11-27T02:36:09+00:00
- Post Title: Reflections CHUNK File Format

That's definitely impressive. I think it may help to know that the model format is very similar to an .X file.
## Post #13
- Username: RacingFreak
- Rank: veteran
- Number of posts: 136
- Joined date: Fri Feb 11, 2011 5:44 pm
- Post datetime: 2012-11-27T07:52:34+00:00
- Post Title: Reflections CHUNK File Format

Awesome! It will be simply awesome if there would be an import function aswell. Explor3r works perfect, kudos WRS 

PS
Just one thing - can you rather make it extract to .DDS or .TGA format which is more comfortable for us modders?
## Post #14
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2012-11-27T17:31:17+00:00
- Post Title: Reflections CHUNK File Format

@WRS is that from Driv3r or DriverSF?
## Post #15
- Username: CarLuver69
- Rank: advanced
- Number of posts: 50
- Joined date: Fri Mar 09, 2012 1:17 am
- Post datetime: 2012-11-27T18:21:21+00:00
- Post Title: Reflections CHUNK File Format

Chipicao it's pretty obvious it's from DRIV3R, since he has no access to a copy of Driver: San Francisco (as far as I'm aware of).
## Post #16
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2012-11-27T20:54:13+00:00
- Post Title: Re: Reflections CHUNK File Format

Well I have no idea what he has access to and what not :p

But thanks, I asked because I've been researching DSF for some time and the format is similar except for some chunk names.
## Post #17
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2012-11-27T23:30:01+00:00
- Post Title: Re: Reflections CHUNK File Format

> Reply from Chipicao
>
> But thanks, I asked because I've been researching DSF for some time and the format is similar except for some chunk names.

what research can you share with us on dsf? have you looked at the model data?

also for the moment i'm just curious what driv3r does with its data as i used to play the xbox version and really enjoyed it    but it sounds like there are enough similarities to make something more generic if possible
## Post #18
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2012-11-28T07:38:24+00:00
- Post Title: Re: Reflections CHUNK File Format

I'm not sure about Driv3r (didn't have time to analyze your research thoroughly, sorry) but I'll tell you what I know about DSF .sp files
- every file is split into one or more chunks, identified by a header name called CHNK
- first long is the total chunk size starting from the beginning of CHNK
- second long is the number of sub-sections (sub-chunks)
- third long is the number of parameters (longs) for each sub-section; there are usually 3, but you should always keep count of this number.

The sub-sections start immediately after this. They are actually sub-section headers; their actual data starts after every sub-section header is parsed, and is identified with offsets.
- every sub-section header starts with a 4-character name (example: MDXN - model data, NONR - "non-resources" like car sounds)
- the first parameter is an offset to the sub-section data/contents; this offset is relative to the beginning of the "parent" CHNK header
- the second parameter is unknown at this time
- the third parameter is the sub-section data size, starting from where the offset takes you

The contents of each sub-section may be actual data, or it may be another CHNK, in which case the above applies all over again.

The model data is in specific section names, for example DXTC for DDS textures, or VXDT for vertex data.
## Post #19
- Username: CarLuver69
- Rank: advanced
- Number of posts: 50
- Joined date: Fri Mar 09, 2012 1:17 am
- Post datetime: 2012-11-28T08:05:57+00:00
- Post Title: Re: Reflections CHUNK File Format

> Reply from Chipicao
>
> - third long is the number of parameters (longs) for each sub-section; there are usually 3, but you should always keep count of this number.

Ah, so that explains the mysterious long we've been trying to figure out. WRS thought it was a version number, I thought it was just unknown, but thanks for clearing that up. The formats are 100% similar.
## Post #20
- Username: Axsis
- Rank: advanced
- Number of posts: 48
- Joined date: Fri Oct 21, 2011 7:55 pm
- Post datetime: 2012-11-28T23:57:20+00:00
- Post Title: Re: Reflections CHUNK File Format

I did some research in D:SF too. About a year ago... so I don't remember any details about format, but then I've wrote a script for chunks unpacking. Not sure if it would work with DRIV3R, but if you think that formats are similar you may try it.
As I remember, it unpacks all chunks recursively, as result giving LOTS of small files in LOTS of folders (messy...) But maybe it'll be useful for someone...
Good luck in further research!

```
Get NAME basename
CallFunction ChunkParser

################################
StartFunction ChunkParser
 String FULLNAME += \
 String FULLNAME += NAME
 GetDString HDR 4
 If HDR != "CHNK"
  String FULLNAME += ".bin"
  Log FULLNAME RECOFFSET RECSIZE
 Else
  SavePos CHNKOFFSET
  Math CHNKOFFSET -= 4
  Get CHNKSIZE long
  Get NUMREC long
  Get DUMMY long
  For REC = 0 < NUMREC
   GetDString RECID 4
   Get RECOFFSET long
   Math RECOFFSET += CHNKOFFSET
   Get DUMMY byte
   Get RECNAMESIZE byte
   Get DUMMY short
   Get RECSIZE long
   SavePos POS1
   Math RECNAMEOFFSET = RECOFFSET
   Math RECNAMEOFFSET += RECSIZE
   GoTo RECNAMEOFFSET
   GetDString RECNAME RECNAMESIZE
   String NAME p= "%04u_%s_[%s]" REC RECID RECNAME
   Goto RECOFFSET
   CallFunction ChunkParser
   GoTo POS1
  Next REC
 EndIf
EndFunction
################################
```
## Post #21
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2012-11-29T23:07:09+00:00
- Post Title: Re: Reflections CHUNK File Format

its interested that a few people have managed the chunk parsing but nobody has gotten much further
## Post #22
- Username: CarLuver69
- Rank: advanced
- Number of posts: 50
- Joined date: Fri Mar 09, 2012 1:17 am
- Post datetime: 2012-11-30T16:44:32+00:00
- Post Title: Re: Reflections CHUNK File Format

The easiest part is "unchunking" the files. The hardest part is actually making use of the files inside the chunks, which tend to be formats none of us have experience with.
## Post #23
- Username: Antares666
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Apr 03, 2010 12:10 am
- Post datetime: 2013-01-09T01:19:16+00:00
- Post Title: Re: Reflections CHUNK File Format

Hi, this topic is quite interesting, as a driv3r fan, i am following it with great interest. Any progress since your last post ?

However, WRS, did you use a max script to visualize the normal data ? If so, would you be willing to share the script please ? Because i would like to see the normal datas in Max ( i have tested your tool Explor3r, nice work ). Thank you  

By the way, good job guys.

> Reply from WRS
>
> minor update

slow progress with the model data

the renderer model package chunks (MDPC) contain the models (faces indices, vertex data and textures) but i'm stuck on reconstructing them. all i think i've found is the normal data:
## Post #24
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2013-01-09T03:12:36+00:00
- Post Title: Re: Reflections CHUNK File Format

when i last worked on this i was looking for face indexes

instead of the 3d wheel rims i was looking at the maps (which are stored with 3d geometry but are 2d). i started by using 3d ripper dx to save the meshes in the scene, then deleting all but the map.

obviously the vertex info isn't the same due to projects and whatever, but i got nowhere looking for face details.

the maxscript was written on the fly. i found a chunk of data which looked like a vertex buffer (the 32-bit values were all valid floats) and created a rough mesh based on it.

i then decided got distracted writing a 3d model data explorer: [https://github.com/x1nixmzeng/luaexpose](https://github.com/x1nixmzeng/luaexpose)

i have since been distracted by something else  

edit, i've attached the map i mentioned


[ex.zip](https://xentaxbackup.github.io/file/6121_ex.zip)
## Post #25
- Username: RacingFreak
- Rank: veteran
- Number of posts: 136
- Joined date: Fri Feb 11, 2011 5:44 pm
- Post datetime: 2013-01-09T16:04:46+00:00
- Post Title: Re: Reflections CHUNK File Format

Holy crap! Fantastic
## Post #26
- Username: CarLuver69
- Rank: advanced
- Number of posts: 50
- Joined date: Fri Mar 09, 2012 1:17 am
- Post datetime: 2013-01-09T21:31:56+00:00
- Post Title: Re: Reflections CHUNK File Format

I think what you seek is not a face index, but an indice index. Try looking in the .MAP files at offset 0x3360, there's a common header of 
```
01 00 00 00 A0 86 01 00
```
 which seems to be a header, further down a little there's a bunch of indicies.

I think I found some kind of index, it's just before the indices I talk about:
## Post #27
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2013-01-10T11:45:27+00:00
- Post Title: Re: Reflections CHUNK File Format

wip 010 binary template for mdpc chunks (explor3r can save these for you)

edit
this clearly wasn't helpful. if anyone needs it, pm me
## Post #28
- Username: CarLuver69
- Rank: advanced
- Number of posts: 50
- Joined date: Fri Mar 09, 2012 1:17 am
- Post datetime: 2013-01-10T19:40:03+00:00
- Post Title: Re: Reflections CHUNK File Format

That template is pretty useful for the most part. However I think it would be better to just document the actual MDPC format rather than make an 010 template, since from what I can see, it doesn't do much good other than allow you to visually jump to each section in the header. It also skipped a section of bytes near the "partA" section and messed up the offsets. It's pretty cool otherwise.
## Post #29
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2013-01-11T00:22:22+00:00
- Post Title: Re: Reflections CHUNK File Format

> Reply from CarLuver69
>
> That template is pretty useful for the most part. However I think it would be better to just document the actual MDPC format rather than make an 010 template, since from what I can see, it doesn't do much good other than allow you to visually jump to each section in the header. It also skipped a section of bytes near the "partA" section and messed up the offsets. It's pretty cool otherwise.

i have no idea what the actual MDPC format looks like.. this template is the result of guesswork working from a chunk i dumped. what do you mean "document the actual MDPC format"?
## Post #30
- Username: CarLuver69
- Rank: advanced
- Number of posts: 50
- Joined date: Fri Mar 09, 2012 1:17 am
- Post datetime: 2013-01-11T01:59:13+00:00
- Post Title: Re: Reflections CHUNK File Format

You made some pretty accurate guesses on the MDPC format, so instead of making a 010 template, take notes on the format and post them here kinda like how I did when I first started the thread. I made a pretty cool discovery regarding vehicle hierarchies, here's the result of messing around -









The method I used was the equivalent of swapping vehicle IDs. I documented every vehicle ID in the game -

```
				
0x02	Miami		Flamingo Taxi
0x06	Miami		'69 Bruiser
0x09	Miami		Police Prowler
0x0A	Miami		El Toro GT500
0x13	All			Packer Big Daddy
0x14	All			Packer Big Daddy (Trailer)
0x16	Miami		Dart Retaliator
0x17	Miami		Scout Cargo Van
0x18	Miami		G-750 Pickup
0x1F	Miami		Antilli VO9s
0x20	Miami		Scout Chaser
0x21	Miami		Hunter 313-T
0x22	Miami		V-8
0x23	Miami		Patriarch Tycoon
0x24	Miami		Packer Transport (Dump Truck)
0x25	Miami		'80 Redline V-8
0x26	Miami		Grande Spedizione
0x27	Miami		Miami Bus
0x28	Miami		Adams Liberty
0x2B	Miami		Go-kart
0x2C	Miami		Farley FLH Whole Hog
0x2D	Miami		Cigarette 38 Top Gun
0x2E	Miami		Sea-King Cormorant
0x2F	Miami		Surf Craft
0x31	Miami		Monorail
0x40	Miami		Sobe Packer Truck
0x42	Miami		Velocity Turbo
0x50	Miami		TT Cuatro Superpower
0x59	Miami		Miami Dade Police Boat
		
0x0D	Nice		Benissimo 74 Turbo
0x10	Nice		Prontezza Freddo
0x11	Nice		Le Compact Rapporter
0x19	Nice		Vitesse Moyenne 72X
0x1B	Nice		Dolch Schub
0x2A	Nice		Dagger Type-S
0x32	Nice		Le Compact Taxicab
0x33	Nice		Dagger Type-T
0x34	Nice		Le Chariot Transport 6
0x35	Nice		Le Chariot Klein
0x36	Nice		Forklift
0x37	Nice		Conquest Motors Dominance
0x39	Nice		Vitesse Moyenne 94 Police
0x3A	Nice		Le Autobus
0x3B	Nice		Lastwagon Kasten
0x3C	Nice		Dolva 8M8
0x3D	Nice		LTS V-8
0x3E	Nice		Le Chariot Cinq
0x41	Nice		Camper Van
0x43	Nice		Sun Runner
0x44	Nice		Moped
0x45	Nice		Cigarette 42 Tiger
0x46	Nice		Sea-King Cormorant
0x47	Nice		Sea-King Silverfish
0x5A	Nice		Nice Polis Boat
0x5C	Nice		Vitesse Moyenne 94LE
0x5D	Nice		Le Compact XS
0x5E	Nice		Prontezza Brezza
		
0x0E	Istanbul	Le Chariot Douze Polis
0x0F	Istanbul	Cargo Van
0x15	Istanbul	'54 Taxi
0x1C	Istanbul	Santun TTZ
0x1D	Istanbul	'54 Classic
0x1E	Istanbul	'71 Pickup
0x29	Istanbul	Speedster
0x48	Istanbul	'73 Classic
0x49	Istanbul	Otobus
0x4A	Istanbul	Le Chariot A1
0x4B	Istanbul	Canyon Wagonaire
0x4C	Istanbul	Packer Transport (Flatbed)
0x4D	Istanbul	Jager Roadster LS28
0x4E	Istanbul	Roadster
0x4F	Istanbul	Racer GT
0x51	Istanbul	Beast
0x52	Istanbul	Moped
0x53	Istanbul	Yeni Golata
0x54	Istanbul	St. Michael Mariner
0x55	Istanbul	Sport Fisher
0x56	Istanbul	Tram
0x57	Istanbul	Train Engine
0x5B	Istanbul	Istanbul Polis Boat
0x5F	Istanbul	Train car
```


Doing this allowed me to finally figure out how to locate vehicle-specific handling in BO3 files using the big header up top, the hex number represents the position in BO3 header so it can be assigned proper handling and vehicle colors. I've decoded BO3 file format 50%, the biggest part of it was finding car colors (they're just little-endian hexidecimal). Now to figure out what everything else does, which seems to be mostly performance related. I cannot confirm or deny if the BO3 files control wheel position since swapping vehicle IDs resulted in proper wheel placement, so I am thinking wheel placement is in AWHF format.

I'll try to get some documentation up soon.
## Post #31
- Username: CarLuver69
- Rank: advanced
- Number of posts: 50
- Joined date: Fri Mar 09, 2012 1:17 am
- Post datetime: 2013-03-10T07:45:50+00:00
- Post Title: Re: Reflections CHUNK File Format

Well now I know how to reads vertices. Too bad faces aren't as easy...



Since this is the file research topic, I will post a snippet of code that may or may not serve a purpose to anyone who sees it.

```

-Offset-|-- MDPC PART DEF --|-- HEXADECIMAL ----|-- WORD ---|
0x56F00C| UNK_LIST_OFFSET	| 80 00 00 00 		| 80		|
0x56F014| UNK_LIST2_OFFSET	| 80 28 00 00 		| 2880		|
0x56F028| DDS_TEX_START		| 00 60 08 00 		| 86000		|
0x56F02C| PCMP_OFFSET 		| 00 50 08 00 		| 85000		|
0x56F034| FACES_LENGTH 		| F8 6B 00 00 		| 6BF8 		|
0x56F038| FACES_OFFSET 		| 9C 53 00 00 		| 539C 		|
0x56F040| UNK_HEADER01 		| 80 53 00 00 		| 5380 		|

Vertex List begin: 	57AF94
Vertex list end: 	5F35D7
Vertex list length: 78644	(44 86 07 00)

Faces List begin:	57439C 	(9C 43 57 00)
Faces List end:		57AF93 	(93 AF 57 00)
Faces List length:	6BF8	(F8 6B 00 00)

INTERIOR
Vertices Offset:	57AF94 	(94 AF 57 00)
Vertices End:		58C453 	(53 C4 58 00)
Vertices Length:	114C0	(C0 14 01 00)
Faces Offset:		???
Faces End:			???

BF94


Minimum Start: 57B000
Maximum Start: 5DCAD0

Minimum End: 57C67F
Maximum End: 5E1683

-- INTERIOR ---------------|--MAX.--|
57B000 - 585ED7 (MESH_0640)| 57C67F |
57B564 - 585DE7 (MESH_0646)| 57FCDF |
57BEC4 - 57FCDF (MESH_0634)| 584AEB |
57C2C0 - 57C67F (MESH_0657)| 5852E3 |
57C771 - 585E9B (MESH_0662)| 585DE7 |
57E0FC - 584AEB (MESH_2970)| 585E9B |
581DEC - 5852E3 (MESH_0669)| 585ED7 |
------------------------------------|
Real length: 57B000 - 58C453 (11454)
------------------------------------|
-- LOD MODEL --------------|--------|
58C454 - 59152F (MESH_0678)| 5914F3 |
58C9B8 - 592CDB (MESH_0668)| 59152F |
58D9A8 - 5914F3 (MESH_2972)| 59242F |
58E86C - 592B37 (MESH_0639)| 59273B |
58FA00 - 59273B (MESH_0645)| 592B37 |
58FAB4 - 59336B (MESH_0650)| 592CDB |
591698 - 59242F (MESH_0683)| 59336B |
-- REAR CLIP --------------|--------|
595FF4 - 5A0CAF (MESH_0638)| 59C0BF |
596FA8 - 59F17F (MESH_0666)| 59F17F |
598A60 - 5A1597 (MESH_0675)| 5A0CAF |
5994EC - 59C0BF (MESH_0643)| 5A10AB |
5A0CEC - 5A10AB (MESH_2971)| 5A1597 |
-- TRUNK ------------------|--------|
5A92FC - 5A9DC3 (MESH_0667)| 5A9DC3 |
5A9680 - 5A9EB3 (MESH_0677)| 5A9EB3 |
5A9EF0 - 5AA4CB (MESH_0644)| 5AA4CB |
-- BUMPER -----------------|--------|
5AAB20 - 5ABFFB (MESH_0676)| 5ABFFB |
-- RIGHT DOOR -------------|--------|
5AEE64 - 5B1B9F (MESH_0674)| 5B082B |
5AEF90 - 5B082B (MESH_0665)| 5B0E07 |
5B0868 - 5B0E07 (MESH_0637)| 5B1203 |
5B0E44 - 5B1203 (MESH_0649)| 5B1B9F |
-- LEFT DOOR --------------|--------|
5B4198 - 5B6FFF (MESH_0673)| 5B62DF |
5B42C4 - 5B62DF (MESH_0664)| 5B6717 |
5B613C - 5B6717 (MESH_0636)| 5B6AD7 |
5B6754 - 5B6AD7 (MESH_0648)| 5B6FFF |
-- ENGINE BAY -------------|--------|
5B9670 - 5BF4E3 (MESH_0635)| 5BC54F |
5BC118 - 5BC54F (MESH_0641)| 5BF4E3 |
-- FRONT CLIP -------------|--------|
5C55B0 - 5C758F (MESH_0672)| 5C758F |
5C9354 - 5CB3AB (MESH_0671)| 5CB3AB |
5CCFCC - 5D22C3 (MESH_0670)| 5D22C3 |
-- HOOD -------------------|--------|
5D521C - 5D7A6B (MESH_0663)| 5D7A6B |
5D7A6C - 5D946F (MESH_0642)| 5D946F |
-- STEERING WHEEL ---------|--------|
5DB270 - 5DC1E7 (MESH_0647)| 5DC1E7 |
-- WHEEL MODEL ------------|--------|
5DC788 - 5E1683 (3D WHEEL) | 5DD33F |
5DCAD0 - 5DD33F (WHL TREAD)| 5E1683 |
---------------------------|--------|

```


Here is the heavily-WIP MaxScript I made to accomplish the pictures seen above. The code is provided as-is and will not be updated unless something significant happens.

```

if (heapSize < 200000) do (
	heapSize = 2000000
)

--vF = GetOpenFileName caption:"Choose VVS File:" \
--types:"DRIV3R Vehicles (*.VVS)|*.VVS|"

vF = "C:\Program Files (x86)\Atari\DRIV3R\Vehicles\miami.vvs"

f = fopen vF "rb"

readFaces = true
readVerts = true

face_array = #()

if readFaces == true do (
	fseek f 5718940 #seek_set
	
	format "Faces begin: 0x%\n" ((bit.intAsHex(ftell f)) as string)
	--format "%\n" "---------------------------------"
	
	for k = 1 to 304 do (
		--format "%\n" ("Indice Idx: "+k as string)
		
		i0 = ReadShort f #unsigned+1
		i1 = ReadShort f #unsigned+1
		i2 = ReadShort f #unsigned+1
		
		append Face_array[i0,i1,i2]
			
		--format "indicies: [%,%,%]\n"\
			--((i0+1) as string)\
			--((i1+1) as string)\
			--((i2+1) as string)
		
		--format "%\n" ("---------------------------------")
		windows.processPostedMessages()
	)
	format "Faces end: 0x%\n" ((bit.intAsHex(ftell f)) as string)
)

if readVerts == true do (
	fseek f 5750468 #seek_set

	vx = 0.0
	vy = 0.0
	vz = 0.0
	nx = 0.0
	ny = 0.0
	nz = 0.0
	tu = 0.0
	tv = 0.0

	
	vert_array = #()
	norm_array = #()
	uv_array = #()

	debugStuff = 0
	format "Vertices Begin: 0x%\n" ((bit.intAsHex(ftell f)) as string)
	
	for i = 1 to 6910 do (
		if debugStuff == 1 do format "Current Position: 0x%\n" ((bit.intAsHex(ftell f)) as string)
		
		vx = ReadFloat f
		vy = ReadFloat f
		vz = ReadFloat f
		
		nx = ReadFloat f
		ny = ReadFloat f
		nz = ReadFloat f
		
		tu = ReadFloat f
		tv = ReadFloat f
		
		junk1 = ReadLong f #unsigned
		junk2 = ReadLong f #unsigned
		junk3 = ReadLong f #unsigned
		junk4 = ReadLong f #unsigned
		junk5 = ReadLong f #unsigned
		junk6 = ReadLong f #unsigned
		junk7 = ReadLong f #unsigned
		
		--The format is vx, vy, vz, nx, ny, nz, tu, tv, junk1, junk2, junk3, junk4, junk5, junk6, junk7...
		
		append vert_array[vx*100,-vz*100,vy*100]
		append norm_array[nx,ny,nz]
		append uv_array[tu,tv,0]
		
		if debugStuff == 1 do (
			format "\nvx: %\nvy:\t%\nvz:\t%\nnx:\t%\nny:\t%\nnz:\t%\ntu:\t%\ntv:\t%"\
				(vx as string)\
				(vy as string)\
				(vz as string)\
				(nx as string)\
				(ny as string)\
				(nz as string)\
				(tu as string)\
				(tu as string)
			format "\n----------------------------------------------------------------------\n"
		)

	windows.processPostedMessages()
	)
	format "Vertices End: 0x%\n" ((bit.intAsHex(ftell f)) as string)

	msh = mesh vertices:vert_array faces:face_array
		setNumTVerts msh uv_array.count
			
		for i = 1 to uv_array.count do (setTVert msh i uv_array[i]) 
		buildTVFaces msh false
		for i = 1 to face_array.count do (setTVFace msh i face_array[i])
			
		select msh
)

fclose f
```
## Post #32
- Username: CarLuver69
- Rank: advanced
- Number of posts: 50
- Joined date: Fri Mar 09, 2012 1:17 am
- Post datetime: 2013-04-01T09:49:10+00:00
- Post Title: Re: Reflections CHUNK File Format

I'm back, and this time, I've got significant progress:



Expect to see a fully imported vehicle in 3DS Max sometime in April, if not May (but why would it take another month? )
## Post #33
- Username: Antares666
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Apr 03, 2010 12:10 am
- Post datetime: 2013-04-01T14:21:09+00:00
- Post Title: Re: Reflections CHUNK File Format

Awesome.
## Post #34
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-04-01T15:34:20+00:00
- Post Title: Re: Reflections CHUNK File Format

"Mr. RoadBuilder" released? Google don't know this tool
## Post #35
- Username: Antares666
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Apr 03, 2010 12:10 am
- Post datetime: 2013-04-01T18:10:34+00:00
- Post Title: Re: Reflections CHUNK File Format

It's an internal tool from Reflections Interactive.
## Post #36
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-04-01T19:14:35+00:00
- Post Title: Re: Reflections CHUNK File Format

Oh lol okay
## Post #37
- Username: CarLuver69
- Rank: advanced
- Number of posts: 50
- Joined date: Fri Mar 09, 2012 1:17 am
- Post datetime: 2013-04-02T00:36:54+00:00
- Post Title: Re: Reflections CHUNK File Format

It's a shame Mr. RoadBuilder is an internal tool...it looks so advanced for 2002/2003...they probably could've made a lot of money selling that tool!
## Post #38
- Username: CarLuver69
- Rank: advanced
- Number of posts: 50
- Joined date: Fri Mar 09, 2012 1:17 am
- Post datetime: 2013-04-03T08:25:44+00:00
- Post Title: Re: Reflections CHUNK File Format

And on the second day...
## Post #39
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2013-04-19T14:10:27+00:00
- Post Title: Re: Reflections CHUNK File Format

Any progress here? Did you find the texture normals?
## Post #40
- Username: CarLuver69
- Rank: advanced
- Number of posts: 50
- Joined date: Fri Mar 09, 2012 1:17 am
- Post datetime: 2013-04-19T18:02:16+00:00
- Post Title: Re: Reflections CHUNK File Format

Yeah, there's progress alright. 

Working on the final version of MDPCEdit, needs a lot of cleaning up and proper PCMP/DDS loading. As for normals, 3DS Max won't handle them properly, so that's out of the question. Exporting meshes shouldn't affect normals too bad...
















What the hell is that?
## Post #41
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2013-07-05T14:28:12+00:00
- Post Title: Re: Reflections CHUNK File Format

I have just finished the maxscript I've been working on with vagos21 for DriverSF. Well actually it's been ready for a very long time, but we had some trouble decoding normals from the game files.
If anyone's interested it can be downloaded [here (click)](http://kotschopshop.com/topic/5175609/).

It supports only vehicles for now and will load all UV coordinates, vertex normals and materials. It also extracts and assigns textures.
[](http://www.imagebam.com/image/5d5f69263972910) [](http://www.imagebam.com/image/f95e9e263972944)
## Post #42
- Username: Antares666
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Apr 03, 2010 12:10 am
- Post datetime: 2013-08-07T11:01:33+00:00
- Post Title: Re: Reflections CHUNK File Format

Downloaded, tested, awesome.
## Post #43
- Username: CarLuver69
- Rank: advanced
- Number of posts: 50
- Joined date: Fri Mar 09, 2012 1:17 am
- Post datetime: 2013-11-27T04:44:20+00:00
- Post Title: Re: Reflections CHUNK File Format

Lots of progress has been made since my last post here. There's so much progress, in fact, that all of it cannot be listed. So instead, I leave these pictures here:














There's also some significant progress on mission scripts as well:




Other news:

- Chunk loading routines completed
- Chunk exporter complete
- Ability to read/write data to chunks (including nested chunks and regular block data)
- Antilli can export models to .obj format

Just thought I'd update this since I got my start here.
