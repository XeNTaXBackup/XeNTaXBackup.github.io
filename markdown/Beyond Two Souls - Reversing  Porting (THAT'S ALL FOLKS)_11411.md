## Post #1
- Username: deepshit
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-04-12T12:30:28+00:00
- Post Title: Beyond: Two Souls - Reversing | Porting (THAT'S ALL FOLKS?)

____Big Update List

____01/12/2014 We all knew it had to happen some day!
20/10/2014 I talk about scripts and Lua and show some more shit. And eat chips.
10/10/2014 2 scenes ran by NATIVE SCRIPTS ONLY.
18/09/2014 TEXTURES ARE FINALLY COMING!!!
02/09/2014 Exploit found in the actual Lua kernel, let the fun begin!
22/08/2014 Very early demo on CHOICE PATHS!
16/08/2014 KERNEL PART ~2~: Executing multiple byte-code scripts, loading resources and shit actually doing stuff (see vid for more info so tired)
07/08/2014 KERNEL PART ~1~: First real-world test of new engine rewrite, with native kernel.
28/07/2014 MILESTONE: Full sequence playing with scenery, camera's, dialog, music, etc!
27/07/2014 Early progress on area's / scenery!
20/07/2014 Camera keyframe animation figured out + implemented (video link in post)
18/07/2014 Passed final exams, will move out of house!
06/07/2014 Models, now in Mogre, and beginnings of skeleton / bones!
02/07/2014 Models (catalogs) seem to have a bright future!
01/07/2014 Timeline structure figured out, parsing in such a shape that we can now playback sequences (audio only)!
07/06/2014 Announcement new tool "InfraViewer"


Model-to-do-list Disclaimer: list subject to change 
Todo

Make a to-do list   
Doing
Research SCRIPT_ZONE's (ZONE_SHAPE_BOX, ZONE_SHAPE_SPHERE, ZONE_SHAPE_HEXAHEDRON)
Research areas.
Done
I forgot to update this list #lol.
Except for the skeleton & materials everything is done: meshes are parsed, textures decoded.



Sequence-to-do-list Disclaimer: list subject to change 
Todo

Implement MOVIE_VIEWPORT_FADE_FX_ACTION
Implement MOVIE_PAD_VIBRATION_FX_ACTION
Doing

Implement PAR_ELEMENT_STANDARD
Implement PAR_ELEMENT_HOLD
Implement PAR_ELEMENT_LOOP
Implement PAR_ELEMENT_MASH
Implement MPAR_ELEMENT_AXIS_TRANSLATION
Implement MPAR_ELEMENT_AXIS_ROTATION
Implement MPAR_ELEMENT_ABC (?)
Implement MPAR_ELEMENT_STANDARD
Implement MPAR_ELEMENT_HOLD
Implement MPAR_ELEMENT_LOOP
Implement MPAR_ELEMENT_MASH
Implement MOVIE_USER_ACTION_CONDITION
Done

Create a "flexible" interface for playing / controlling sequences.
Implement SEQUENCE_CONTROLLER (SEQ_CHK_), which only defines basic (but important) stuff like the root movie.
Implement MOVIE_SCRIPT_CONDITION
Implement SEQUENCE_CONTROLLER_PLAY[
Rewrite audio streamer for the third time   (this time asynchronous)
Make it better.
Perform first tests!!
Write a custom high-resolution Timer class (using a thread and a stopwatch!)
Implement MOVIE_PLAY_ANIM_ACTION
Implement MOVIE_GO_TO_MOVIE_CONDITION
Implement PLAY_SCRIPT_TOP
Implement MOVIE_PLAY_SHOT_ACTION
Implement MOVIE_WATCH_FX_ACTION
Implement MOVIE_CAMERA_MODIFIER_FX_ACTION
Implement MOVIE_CAMERA_QUAKE_FX_ACTION
Implement MOVIE_PLAY_SOUND_ACTION
Implement MOVIE_DIALOG_GROUP_CONDITION
Implement MOVIE_PLAY_DIALOG_ACTION
Implement MPA_CHK_ and the other entity Communicators (camera shots, sounds, dialog, etc.)
Research camera "sub-shots".
Implement MOV_ELEM (also relies on other stuff)
Implement MOV_MISC
Implement MOV_GUID
Implement MOV_ENT_ (relies on other stuff though)
Find out what PAR/MPAR stands for (Physical Action Reaction / Motion Physical Action Reaction)

Kernel-to-do-list Disclaimer: list subject to change 
Todo

Implement version 2 of CAC_____ (as seen in 0802 The Party Clash -> main scene com).
Check out different DATA_CONTAINER => DC_DATA version formats and implement
Implement SCRIPT_ZONEs
Start my own blog(???)
Check out non-empty SC_FRM_W (in 1802 Hunted Train)
Audio features (stop, pause, resume, seek, insert silence)
Doing

Perform tests to make sure everything works!
Set up MOGRE (now Paradox) environment
Spam XeNTaX with pointless update videos
Done
Research PAR/MPAR events and choice events.
Implement Lua "actions" system (partly completed)
Re-implement dynamic loading for SCRIPT_FUNCTION_CALL.
Proper meta-data reading (needs: SINT_SEC reader rewrite, modification to DC_DATA_ reader and preloader FIX)
FIX: preloading of resources
Partly rewrite, partly port the Sequence parser/player.
Port usable code over from older tools (mainly InfraViewer)
Completely revise attribute reading and data loading.
Finish audio streaming engine (needs minor performance adjustments)
Change FMOD audio engine to BASS audio engine (much better support for custom data streaming and easier DSP mixing)
Research loading of resources.
MILESTONE: Execute -FULL- scene, including sub-scripts, dynamic loading (100% with Broken (scene after Prologue) and Prologue)
Implement SendEvent(...)
Make some sort of Lua execution manager to make sure there are no cross-thread executions. (seems to be fixed using <lock>)
[HIGH PRIORITY] Dynamic loading for LOADING_ZONEs & LOADING_ZONE_TIMERs. (seems to work fine, needs more testing though!)
Implement SCRIPT_FUNCTION and SCRIPT_FUNCTION_CALL (major)
Reorder classes into separate .cs files...
MILESTONE: perform test using scene name, -> load scene loadzone, load scene datacontainer, execute scene (and load resources) -> call <scene>.OnInit().
Research COM_INSTANCE_LIST's
Implement EndVarFreedom()
Converter for PS3 (PPC, big endian) LUAC chunks to PC (little endian) chunks.
Temporary video play management, with threaded pre-loading and threaded playing. Note: needs actual playing! XD
Audio system (FMOD) with global functions, events, and threading. (3D support will be written later)
Implement SCRIPT_DELAY
Implement MESSAGE_LAUNCHER & MESSAGE_CONTROLLER (TESTED)
Proper resource management and properly working clean up functions (stress tested!)
Make multithreaded loading manager with managed stacks and event callbacks
"BinaryCore" for BigFiles (IDM file reading, handle assignments)
Implement runtime.sdat reading
Implement PARAM.SFO reader
Implement Dynamic Communicator system (register, attributes, events, paramaters, actions (partly), unregister, linking)
Implement Lua "variables" system.
Implement Lua "events" system.
Implement Lua "attributes" system.
Neatly working kernel enviroment with easy-to-plug-in features and support.
Create basic "instances" environment.

Support

As you may know, this category of XeNTaX doesn't get as much attention as we'd like it to get!
That's why I made this badge:



```
[url=http://forum.xentax.com/viewtopic.php?f=32&t=11411][img]http://i.imgur.com/EUcneAM.png[/img][/url]
```


So now, you can show your support of this project by putting the badge in your signature!

Donations

Some people have asked me if they can donate somewhere, so I decided to put a PayPal donation thing up here:

[](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=SDC9Y2WSSUNR8)

To anyone who donates: THANK YOU! You're the best.
After you donate, make sure to send the receipt to hugo ~a t~ djek ~d o t~ nl with your nickname, so you can be in the credits once any tools / ports are released.

Where will the money go to? I haven't really thought of any situations where this project would cost money, but it will be primarily spent on this project. This means we could for instance set up a website, or pay people to reverse some assembly for us   It could also be spent on hardware / software (such as the PS4 version of Beyond, when it comes out).

WARNING!!! The info under here is inaccurate and very outdated!



Here's my second tool since joining here!

This tool can extract all data blocks from Beyond: Two Souls, including audio (SFX, Dialog, Music & Ambience (multi channel)), segs entries (and decompress them using QuickBMS), scripts and dialog text (very limited support right now).

It also partly works with Heavy Rain. Let me know if you want me to investigate those formats too.

Here's a screenshot:



What's coming?
Okay, first a little explanation about how Beyond works.
Beyond (and Heavy Rain) store its data in blocks called Communicators.

(The following text is correct for around 60%   )
A Communicator is a table containing data for a certain function in the game. These are formatted as precompiled Lua "function chunks". The values of these "settings" are stored either compressed (as a segs entry, which is a split up ZLIB archive), or uncompressed (as a QZIP entry, which is funny, because "ZIP" normally indicates a compressed file entry). Aside from storing just values as Lua functions, modified versions of Communicators are also used for storing the "actual" scene scripts, model data, animation data, (very small amounts of) audio, video (like the sport scenes and cartoons on the in-game TVs), textures, dialog sequence text, and more.

Right now, I'm working on a universal parser for these blocks. That's basically what the extractor does, but the difference is that this new parser can get useful data out of the blocks, rather than just extracting them.

[>> Download Beyond: Two Souls -Extractor- v1.0](https://mega.co.nz/#!CBVgwS5R!Tb0aBTXTK9LbJC1TGGhSfZk9ycc-zw0i2mD624AhZfw)
ANOTHER NOTE: Even though this is v1.0 it's still very much a beta. Please let me know if you get errors during export!!

So, there you go! I wonder if I will be getting any comments on this one!
## Post #2
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-04-12T17:02:50+00:00
- Post Title: Beyond: Two Souls - Reversing | Porting (THAT'S ALL FOLKS?)

I bow down to you sir good fucken work, I gave up when all those seg blocks were chopped up textures and such. If we can get a decent unpacker for each game asset would be easier to reverse.

-EDIT-

Ok so I tested it on the main BIGFILE


I get this not sure why.
Also BigFile_PS3.d08 throws this 


Have you looked at parsing the model/animation/texture blocks yet?
## Post #3
- Username: mirh
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-04-15T15:44:06+00:00
- Post Title: Beyond: Two Souls - Reversing | Porting (THAT'S ALL FOLKS?)

> Reply from cra0
>
> I bow down to you sir good fucken work, I gave up when all those seg blocks were chopped up textures and such. If we can get a decent unpacker for each game asset would be easier to reverse.

-EDIT-

Ok so I tested it on the main BIGFILE


I get this not sure why.
Also BigFile_PS3.d08 throws this 


Have you looked at parsing the model/animation/texture blocks yet?
Thanks!

Damn, that were some things I forgot to fix... sorry for that! I'll post an update later. Slammed with school stuff right now... 

From your list, I have only been looking at the ANIMDATA blocks. I always first try to reverse engineer the file entries / tab header, etc. but I can't figure it out completely... will post some info below.

About the segs archives: I haven't really looked at them too much, but from what I can see is that we're still missing something. After each(?) segs archive there are more chunks that start with 0x10... these define their own sizes as well... not sure what's up with that, maybe they belong to the segs archives, because every individual file is aligned to 0x800 (2048 bytes), and these only come after the segs stuff, unaligned.

I've been looking through the decrypted version of EBOOT.BIN (EBOOT.ELF), and found some strings that might be able to give us some clues about these archives..
PSST, don't tell anyone: I got the source code for EdgeZlib (it's a special kind of Zlib that can be offloaded to the ?SPU? that comes with the PS3 Edge SDK), will be checking that out soon...

0x00EF86F0: EDGE ZLIB ERROR: outputUncompSkipBeginSize(%d) + outputUncompSkipEndSize(%d) > expectedUncompSize(%d)
0x00EF8760: EDGE ZLIB ERROR: edgeZlibFetchAndInflateLargeRawData failed (%d)
0x00EF87B0: EDGE ZLIB ERROR: edgeZlibInflateRawData failed (%d)
0x00EF87F0: EDGE ZLIB ERROR: DecompressInflateQueueElement returned (%d)
0x00EF8830: EDGE ASSERTION FAILURE: %s(%d)
0x00EF8850: 1.2.3.0-PS3-SPU-EDGE
0x00EF8870: EDGE ZLIB ERROR: inflate error (%d)
0x00EF88A0: incorrect header check
0x00EF88C0: unknown compression method
0x00EF88E0: invalid window size
0x00EF8900: unknown header flags set
0x00EF8920: header crc mismatch
0x00EF8940: invalid block type
0x00EF8960: invalid stored block lengths
0x00EF8980: too many length or distance symbols
0x00EF89B0: invalid code lengths set
0x00EF89D0: invalid bit length repeat
0x00EF89F0: invalid literal/lengths set
0x00EF8A10: invalid distances set
0x00EF8A30: invalid literal/length code
0x00EF8A50: invalid distance code
0x00EF8A70: invalid distance too far back
0x00EF8A90: incorrect data check
0x00EF8AB0: incorrect length check
0x00EF9380: EDGE ZLIB ERROR: inflateEnd error (%d)
0x00EF93B0: EDGE ZLIB ERROR: Stream decompressed to size different from expected (%d != %d)
0x00EF9520: invalid distance code
0x00EF9540: invalid literal/length code
0x00EF9560: invalid distance too far back
0x00EF972C: SPUNAME
0x00EF9734: ..\..\Output\PS3\SPU Release\Ker

0x00D80384: Out of memory while calling edgeZlibAddInflateQueueElement. The game will crash soon !

0x00D84448: Sources\Zlib\EdgeZLib\edgezlib_inflate_queue.cpp:70 (0 == ret)
0x00D84488: Sources\Zlib\EdgeZLib\edgezlib_inflate_queue.cpp:96 CELL_OK == ret
0x00D844CC: Sources\Zlib\EdgeZLib\edgezlib_inflate_queue.cpp:188 (maxNumQueueEntries > 0)
0x00D8451C: Sources\Zlib\EdgeZLib\edgezlib_inflate_queue.cpp:148 (bufferSize == edgeZlibGetInflateQueueSize( maxNumQueueEntries ))
0x00D84594: Sources\Zlib\EdgeZLib\edgezlib_inflate_queue.cpp:149 (bufferSize == (128 + (maxNumQueueEntries * 32)))
0x00D845FC: Sources\Zlib\EdgeZLib\edgezlib_inflate_queue.cpp:150 ((((uint32_t)pBuffer) & 0x7F) == 0)
0x00D8465C: Sources\Zlib\EdgeZLib\edgezlib_inflate_queue.cpp:164 (0 == ret)
0x00D8469C: Sources\Zlib\EdgeZLib\edgezlib_inflate_queue.cpp:167 (0 == ret)
0x00D846DC: EDGE ZLIB ERROR: Input compressed data is on stack (which is illegal)

0x00D84724: Sources\Zlib\EdgeZLib\edgezlib_inflate_queue.cpp:401 (!sys_process_is_stack((void*)pInputCompressedData))
0x00D84794: EDGE ZLIB ERROR: Output uncompressed data is on stack (which is illegal)

0x00D847E4: Sources\Zlib\EdgeZLib\edgezlib_inflate_queue.cpp:404 (!sys_process_is_stack(pOutputUncompPartialBuff))
0x00D8484C: EDGE ZLIB ERROR: outputUncompSkipBeginSize(%d) + outputUncompSkipEndSize(%d) > expectedUncompressedSize(%d)

0x00D848BC: Sources\Zlib\EdgeZLib\edgezlib_inflate_queue.cpp:408 (outputUncompSkipBeginSize + outputUncompSkipEndSize <= expectedUncompressedSize)
0x00D84944: Sources\Zlib\EdgeZLib\edgezlib_inflate_queue.cpp:410 (pWorkToDoCounter)
0x00D8498C: Warning: Compressed data at address 0x%08X is *bigger* than master data (%d > %d).  Pointless?

0x00D849EC: Sources\Zlib\EdgeZLib\edgezlib_inflate_queue.cpp:423 ((((uint32_t)pWorkToDoCounter) & 0x3) == 0)
0x00D84A54: Sources\Zlib\EdgeZLib\edgezlib_inflate_queue.cpp:442 (0 == ret)
0x00D84A9C: Buff))
0x00D84AA4: dSize)
0x00D84AB4: Sources\Zlib\EdgeZLib\edgezlib_inflate_queue.cpp:583 (0 == ret)


Furthermore, here are the different types of Dynamic Communicator blocks I could find, most of them with a description of some sort.
I put them in a nice switch statement (yes, I did this manually...):

NOTE: an asterisk (*) means the description is a guess by me, and where there's just the description it means I haven't found the short name for that one yet. 

```
{
    case "COM_CONT":  // COMMUNICATOR_CONTAINER
    case "LOADCONT": // *LOADING_CONTAINER
    case "LOADZONE":  // LOADING_ZONE
    case "LOADZTIM": // LOADZING_ZONE_TIMER
    case "SINT_SEC": 
    case "SFE_LOAD": 
    case "ANIMDATA": // *ANIMATION_DATA
    case "LOCALIZ_":  // *LOCALIZATION
    case "PARTITIO":  // COMMUNICATOR_PARTITION
    
    case "SFESAV  ": // SCRIPT_FRAMEWORK_ENTITY_CONTROLLER_ABC
    case "SCN_CHK ": 
    case "SINT_SCN": 
    case "VPCCTRL ": // VIDEO_PLAYER_CONTROLLER
    case "MCR_CHK ":
    
    case "SCRIPT  ":
    case "SCPT_DAT":
        
    /* Unknown */
    case "SC_FRM_W": // SCRIPT_FRAMEWORK
    case "SENT_CHK":
    case "MK_INFO_":
    case "LOADZCAM": // LOADING_ZONE_CAMERA
    case "SINT_WLD":
    case "SCSAV   ":
    case "SFESAV  ":
    case "VLACRFC ": // VIEWPORT_LAYOUT_ANIMATION_CONTROLLER_RUN_FROM_CURRENT
    case "VLACR   ": // VIEWPORT_LAYOUT_ANIMATION_CONTROLLER_RUN
    case "VCFOCTRL": // VIEWPORT_CONTROLLER_FADE_OPACITY
    case "VCFCTRL ": // VIEWPORT_CONTROLLER_FADE
    case "CP_ATTR ": // SCRIPT_FRAMEWORK_ENTITY_CONTROLLER_ABC
    case "SCN_CHK ":
    case "SCENE   ":
    case "ADDR_CHK":
    case "SINT_ADR":
    case "VPCCTRL ": // VIDEO_PLAYER_CONTROLLER
    case "MMCSAV  ":
    case "MENUSCPM": // MENUS_MASTER_COM_PARAMETERS
    case "LMCRCTRL": // LOAD_MENU_CONTROLLER_RUN
    case "FADECTRL": // FADE_CONTROLLER
    case "MCRCTRL ": // MENU_CONTROLLER_RUN
    case "SEQ_CHK ":
    case "GEN_SEQ ":
    case "SECSAVE ": // SCRIPT_EVENT_CONTROLLER
    case "SEQUENCE":
    case "SCDLPARA": // SCRIPT_DIALOG_PARAMETERS
    case "SDPARAMS":
    case "SD_PARMS":
    case "GAP_CHK ": // GENERIC_ANIM_PARAMETERS
    case "UA_CHK  ": // USER_ACTION
    case "PAR_CONT": 
    case "UACABC  ": // UA_CONTROLLER_ABC
    case "UAECABC ": // UA_EVENT_CONTROLLER_ABC
    case "EVENTCOM": 
    case "EVNTMPAR":
    case "UAECPAR ": // UA_EVENT_CONTROLLER_PAR
    case "MPARELAD": // MPAR_ELEMENT_AXIS_DIAGONAL
    case "PARELEM ": // MPAR_ELEMENT_NO_EVENT
    case "PARELSHK": // PAR_ELEMENT_BLOCK/HIT
    case "SINT_TPG":
    case "MPCTRL  ": // MAGNETIC_SEGMENT_CONTROLLER
    case "TPGCTRL ": // THIRD_PERSON_GAMEPLAY_CONTROLLER
    case "SINT_GC ":
    case "GCTRLER ": // GAME_CONTROLLER
    case "SINT_GM ":
    case "SINTGM  ":
    case "SINT_GRI": // GAME_RUNTIME_INFO
    case "MAGCON  ": // MAGNETIC_CONNECTION
    case "TPGNP_CK": 
    case "MPASAV  ": // MAGNETIC_PATH
    case "MPCSAV  ": // MAGNETIC_PATH_CONTAINER
    case "SDCTRL  ": // SCRIPT_DELAY
    case "STIM_CHK": 
    case "GMK_COMG": // GMK_MOVEMENT_GRAPH
    case "GMK_ANIM": // GMK_ANIMATION_DATABASE
    case "RBSACTIO":
    case "RBSACTOR":
    case "RBSBRAIN":
    case "MPAREABC": // MPAR_ELEMENT_ABC
    case "PARELABC": // PAR_ELEMENT_ABC
    case "MPARELAR": // MPAR_ELEMENT_AXIS_ROTATION
    case "MPARELAT": // MPAR_ELEMENT_AXIS_TRANSLATION
    case "PARELLOP": // MPAR_ELEMENT_LOOP
    case "PARELMSH": // MPAR_ELEMENT_MASH/PAR_ELEMENT_MASH
    case "PARELHLD": // PAR_ELEMENT_HOLD
    case "PARELLP ": // PAR_ELEMENT_LOOP
    case "PARELSTD": // PAR_ELEMENT_STANDARD
    case "CBSPGP  ":
    case "CBFLWR  ": // ?CAMERA_BEHAVIOR_FOLLOW_VEHICLE
    case "CBFOLWVH": // ?CAMERA_BEHAVIOR_SEQUENCE
    case "ADCI_CHK": 
    case "ADBSAV  ":
    case "GSCCSAV ": // GAME_SAVE_CONTROLLER
    case "GSD_CHK ": // ?GAME_SAVE_DATA
    case "GSDSAV  ":
    case "SRG_CHK ":
    case "AG_SAV  ":
    case "AORSAV  ":
    case "AROSAV  ":
    case "AGNC_CHK": // ANAEL_GAMEPLAY_NAVIGATION_CONFIG
    case "ABCSAV  ": 
    case "AGNC_CHK": // ANAEL_GAMEPLAY_SELECTOR_CONFIG
    case "ANCSAV  ": 
    case "AGNC_CHK": 
    case "ASCSAV  ":
    case "AEMCSAV ": // ANAEL_EASY_MODE_CONTROLLER
    case "AFCSAV  ": // ANAEL_FX_CONTROLLER
    case "PIPO    ": // ?not sure =
    case "AFCCSAV ": // ANAEL_FX_CONTROLLER_CONFIG
    case "AGCSAV  ": // ANAEL_GO_TO_CONTROLLER
    case "AICSAV  ": // ANAEL_INTERACTION_CONTROLLER
                     // ANAEL_ENERGY_MANAGER
                     // ANAEL_ENERGY_SOURCE_CONFIG
                     // COM_ATTRIBUTE_CONTAINER_ABC
    case "AESSAV  ":
    case "AEM_CHK ":
    case "AEMSAV  ":
    case "AFC     ":
    case "ATCSAV  ":
    case "ATFSAV  ":
    case "CARGCSAV": // CAR_GAMEPLAY_CONTROLLER
    case "CARGPIN ": // CTRL_TRAIL_SPEED
    case "IEPSAV  ": // IW_ENTITY_TAIL_SHADER_CONTROLLER
    case "IECSAV  ": // INFRAWORLD_ENTITY_CONFIG
    case "IEP_CHK ": // INFRAWORLD_ENTITY_PACK
    case "IEPSAV  ": // INFRAWORLD_ENTITY_PACK_CONTROLLER
    case "OCSAV   ": // ?PURSUIT_BEHAVIOR
    case "PSSCTCFG": // POSSESSION_CENTRE_CONFIG
    case "PCCSAV  ": // POSSESSION_CENTRE_CONTROLLER
    case "VTSSAV  ": // VIEW_TARGET_SELECTION_CONTROLLER
    
    case "GFCCFG  ": // GROUP_FOLLOW_CONTROLLER_CONFIG
    case "ARRVLPOS": // ARRIVAL_POSE
    case "APSAV   ":
    case "SGCSAV  ": // ?STABILIZE_GAMEPLAY_CONTROLLER
    case "STCTLSV ": // STEALTH_CONTROLLER
    
    case "FSSFCTRL": // FOOTSTEP_SURFACE_CONTROLLER
    
    case "ICCSAV  ": // IK_CONSTRAINT_CONTROLLER
                     // IK_CONSTRAINT_CONTROLLER_EFFECTOR
    case "IQCSAV  ": // IK_QUADRIPED_CONTROLLER
    case "WICSAV  ": // WATCH_ENTITY_CONTROLLER
    case "SUBMGPIN": // SUBMARINE_GAMEPLAY_INPUT
    case "BIKE_CHK": // BIKE_GAMEPLAY
    case "BGCSAV  ": // BIKE_GAMEPLAY_CONTROLLER
    case "PRCANMDT": // PROC_ANIM_COM_DATA
                     // PROJECTILE_MANAGER
    case "VICSAV  ": // VIBRATE_CONTROLLER
    case "LCSAV   ": // LOADING_CONTROLLER
    case "LCFSAV  ": // LOADING_CONTROLLER_FUNCTION
    case "MPST_CHK": // PLAY_SCRIPT_TOP
    case "TSFX_CHK": // MOVIE_TIME_SCALE_FX_ACTION
    case "ACT_CHK ":
    case "COND_CHK":
    case "FX_CHK  ":
    case "CCTSAV  ": // COLLISION_CONTROLLER
    case "TCTSAV  ": // THROW_CONTROLLER
    case "PSESAV  ": // PHYSICS_SPECIAL_EFFECTS
    case "REPSAVE ": // REPULSOR
                     // PHYSICS_LOD_CONFIGURATOR
    case "PHYLC   ":
    case "PLCSAV  ": // CPN_FLMG_CORRECTION
                     // CPN_OBSTACLE_CORRECTION
                     
    case "CDEC_SAV": // CHARACTER_DIALOG_EVENT_CONTROLLER
    case "CEGASAV ": // CONTROLLER_ENTITY_GOTO_ABC
                     // CONTROLLER_ENTITY_GOTO_ADDRESS
    case "CEGAASAV": // CONTROLLER_ENTITY_GOTO_ADDRESS_ABC
    case "CEOTTSV ": // CONTROLLER_ENTITY_ORIENT_TO_TARGET
    case "SECPRANM": // SCRIPT_ENTITY_CONTROLLER_PLAY_PROCEDURAL_ANIM
    case "SSMSAV  ": // SCRIPT_ENTITY_CONTROLLER_SKELETON_MAPPING
    case "SKEL_MAP":
    case "SMCSAV  ": // SKELETON_MAPPING_CONFIG
    case "STZOCTRL": // STAIRS_ZONE_CONTROLLER
    case "SEPSAV  ": // SYNCHRONIZE_ENTITY_POSITIONS_CONTROLLER
    case "PHAD_CHK":
    case "SLSAV   ": // SCRIPT_LOCATOR
    case "FBCSAV  ": // FX_BANK_CONTROLLER
    case "TS_FX   ": // TIME_SCALE_FX
    case "LCALTCFG": // LOCATION_ALERT_CONFIG
    case "LACSAV  ":
                     // LOCATION_ALERT_CONTROLLER
                     // RAISE_EVENT_COUNT_CONTROLLER
                     // RAISE_EVENT_PER_ITEM_CONTROLLER
    case "SWSAV   ": // SCRIPT_WIND
                     // SEQUENCE_INSTANCE
    case "MGCDE   ": // MIX_GROUP_CONTROLLER_DISABLE_EFFECT
    case "MGCEE   ": // MIX_GROUP_CONTROLLER_ENABLE_EFFECT
    case "MGCSFRE ": // MIX_GROUP_CONTROLLER_SET_FDN_REVERB_EFFECT
                     // MIX_GROUP_CONTROLLER_MIX_GROUP
    case "MGCSMCE ": // MIX_GROUP_CONTROLLER_SET_MULTICHANNEL_COMPRESSOR_EFFECT
    case "MGCSPSE ": // MIX_GROUP_CONTROLLER_SET_PITCH_SHIFTER_EFFECT
    case "SSDFFCTL": // SCRIPT_SOUND_CONTROLLER_DISTANCE_FILTER
                     // FOOTSTEP_SOUND_MANAGER
    case "FSMSAV  ": // COLLISION_SOUND_MANAGER
    case "COSOMG  ": 
    case "COSOMGSV": // SCRIPT_SOUND_BANK
    case "SBCSAV  ": // SCRIPT_SOUND_BANK_CONTROLLER
                     // SCRIPT_SOUND_BANK_INSTANCE
                     // SCRIPT_SOUND_MULTITRACK_CONTAINER
    case "S_SND_MC": // SCRIPT_SOUND_RANDOM_CONTAINER
                     // SCRIPT_SOUND_RANDOM_CONTAINER_MODE
    case "S_SND_RC":
    case "S_SND_SC":
    case "AI_AGENT":
    case "AIMSAV  ": // AI_PATH_INTERACTOR_WITH_ZONE
    case "AIPIWZON":
                     // CONTROLLER_AGENT_DELAY_PATH
                     // CONTROLLER_AGENT_FOLLOW
                     // CONTROLLER_AGENT_GOTO_ABC
                     // CONTROLLER_AGENT_GOTO_ADDRESS
                     // CONTROLLER_AGENT_GOTO_ADDRESS_ANIM
                     // CONTROLLER_AGENT_GOTO_AGENT
                     // CONTROLLER_AGENT_GOTO_ZONE
    case "SDCTRL  ": // CONTROLLER_SYNC
    case "GCMCTRL ": // GMK_COMMAND_MESSAGE_CONTROLLER
    case "MKSP_CHK": // ?GMK_SIMULATE_PARAMS
                     // MOTION_GRAPH_TESTER_CONTROLLER
                     // MOTION_GRAPH_PLANNING_CONTROLLER
                     // MOTION_GRAPH_CONTROLLER
                     // QUATERNION_INTERPOLATION_TESTER_CONTROLLER
    case "HDAMCT  ": // HEAD_ANIMO_CONTAINER
    case "WANIMO  ": // WEIGHTED_ANIMO
    case "AREA_CHK":
    case "SINT_ARA":
    case "SINT_CD ":
    case "CSB_CHK ":
    case "SINT_CSB":
    case "CBABC   ": // ?CAMERA_BEHAVIOR_ANAEL
    case "CBSPGP  ": // ?CAMERA_BEHAVIOR_CHASE
    case "CBDCIRC ": // CAMERA_BEHAVIOR_CONTAINER
    case "CBCONTAI": // CAMERA_BEHAVIOR_CROWD_CHASE
                     // CAMERA_BEHAVIOR_FIRST_PERSON
    case "PANIMOCT": // PLAYABLE_ANIMO_CONTROLLER
    case "TGUI_CK ":
    
    case "CATALOG ": // AREA_CATALOG
    case "QFOBJECT": // QPF_COM_CLASS
    
    case "SCPTBANK": // SCRIPT_BANK
    case "GCFG_CHK":
    case "GAME_CFG":
    case "CFG_ELEM": // GAME_CFG_ELEMENT_ABC
    case "RUNT_CFG": // GAME_CFG_RUNTIME_ELEMENT_ABC
    case "STAT_CFG": // GAME_CFG_STATIC_ELEMENT_ABC
    
    case "DLG_CFG ": // DIALOG_CFG
    case "GMG_CFG ": // GAME_MANAGER_CFG
    case "ST_MPAR_":
    case "MPAR_CFG":
    case "RT_ID_  ": 
    case "ID_CFG  ": // INPUT_DEVICE_CFG
    case "RT_LOC_ ":
    case "LOC_CFG ": // LOCALIZATION_CFG
    case "RT_TPG_ ":
    case "TPG_CFG ": // THIRD_PERSON_GAMEPLAY_CFG
    
    case "GENPAT  ": // GENERIC_PATH
    case "GENCON  ": // GENERIC_PATH_CONNECTION
    case "GENSEG  ": // GENERIC_PATH_SEGMENT
    
    case "STORYBRD": // *Storyboard
    case "SINTSTRY":
    case "STBRDELM": // STORYBOARD_ELEMENT
    case "STRBDSCN": // STORYBOARD_SCENE
    case "STBSCELM": // STORYBOARD_SCENE_ELEMENT
    
    case "SF_SAV  ": // SCRIPT_FUNCTION
    case "SFCSAV  ": // SCRIPT_FUNCTION_CALL
    
    case "CMODFXCK": // MOVIE_CAMERA_MODIFIER_FX_ACTION
    case "CQFX_CHK": // MOVIE_CAMERA_QUAKE_FX_ACTION
    case "PADVIB  ": // MOVIE_PAD_VIBRATION_FX_ACTION
    case "PLAVIDFX": // MOVIE_PLAY_VIDEO_FX_ACTION
    case "RVLA_CHK": // MOVIE_RUN_VIEWPORT_LAYOUT_ANIM_ACTION
    case "VPFX_CHK": // MOVIE_VIEWPORT_FADE_FX_ACTION
    case "MDGC_CHK": // MOVIE_DIALOG_GROUP_CONDITION
    case "SCPTCOND": // MOVIE_SCRIPT_CONDITION
    case "MSIC    ": // MOVIE_SOFT_INTERRUPT_CONDITION
    case "MUAC_CHK": // MOVIE_USER_ACTION_CONDITION
    
    case "MOV_ENT_":
    case "MOV_EVT_":
    case "MOV_TOP_":
    case "MOV_FX__":
    case "MOV_GUID":
    case "MOV_MISC":
    case "MOV_COND":
    case "MOV_ELEM":
    
    case "PARDISPL": // UA_ELEMENT_DISPLAY
    case "PARINPUT": // UA_ELEMENT_INPUT
    
    case "MPA_CHK_":
    case "MPABC___": // MOVIE_PLAYABLE_ABC
    case "MCAA_CHK": // MOVIE_COM_ATTRIB_ACTION
    case "MPAA_CHK": // MOVIE_PLAY_ANIM_ACTION
    case "MPDA_CHK": // MOVIE_PLAY_DIALOG_ACTION
    case "NSHA_CHK": // MOVIE_PLAY_SHOT_ACTION
    case "MSA_CHK_": // MOVIE_PLAY_SOUND_ACTION
    
    /* 3D objects */
    case "OBJ_____":
    case "MOV_ENT_":
    case "MESHDATA":
    case "PRIMEDGE":
    case "CLUPSKME":
    case "ENTITY  ":
    case "MESH____":
    case "NODE    ":
    case "STPHDATA": // STATIC_PHYSIC_DATA
    case "DYPHDATA": // DYNAMIC_PHYSIC_DATA
    case "SHADCUST":
    case "FX_EVNT_": // FX_EVENTS
    
    /* Audio */
    case "PARTOFFS": // OFFSET_PARTITION
    case "STREAMAB": // STREAMABLE
    case "HEADER__":
    case "S_SND_E_":
    case "TBOFFSET": 
}

```


About the ANIMDATA, I haven't researched it very deeply, but I did find out some things:

0x8: Block ID (ANIMDATA)
0x4: Unknown identifier (see below)
0x4: Unknown identifier (see below)
0x4: Unknown identifier (see below)
0x4: Unknown identifier (see below)
0x4: Big "tab" entries amount (after the header tab)
0x4: Unknown identifier... (see below)
0x4: Unknown identifier... (see below)
0x4: Header "tab" entries amount

Then the header tab starts, every entry consists of 6 ushorts(?):
0x2: Unknown ushort
0x2: Unknown ushort
0x2: Unknown ushort
0x2: Unknown ushort
0x2: Unknown ushort
0x2: Unknown ushort

Then there's 2 (padding?) bytes, and then the "big" tab thing starts, every entry consisting of 4 ushorts(?):
0x2: Unknown ushort
0x2: Unknown ushort
0x2: Unknown ushort
0x2: Unknown ushort

Then there's some more data... might be the same size as the header entries amount (??????)

So yeah, haven't looked at it very long 

I may have a lead on this one as well though, I found this in the extracted strings from EBOOT.ELF:

0x00D7B0B0: ANIMDATA
0x00D7B0C0: ANIMPARM
0x00D7B0D0: TRACKDAT
0x00D7B0DC: ANIM_DATA
0x00D7B0E8: KEYFRAME_ANIMATION
0x00D7B108: Evt_Foot_Left
0x00D7B118: Evt_Foot_Right
0x00D7B128: Evt_SYNCHstep_Left
0x00D7B140: Evt_SYNCHstep_Right
0x00D7B15C: MBI_SKA
0x00D7B164: STREAMABLE_KEYFRAME_ANIMATION
0x00D7B184: STREAM_ANIMATION_OFFSET
0x00D7B19C: AnimData
0x00D7B1AC: Ref_AnimData
0x00D7B1BC: Ref Frame
0x00D7B1CC: Start Frame
0x00D7B1DC: End Frame
0x00D7B1EC: Blend Time
0x00D7B1FC: Animation Type
0x00D7B20C: Streamable AnimData
0x00D7B224: Ref Streamable AnimData
0x00D7B23C: SetAnimData
0x00D7B24C: GetAnimData
0x00D7B25C: SetStartFrame
0x00D7B26C: GetStartFrame
0x00D7B27C: SetEndFrame
0x00D7B28C: GetEndFrame
0x00D7B29C: SetRefAnimData
0x00D7B2AC: GetRefAnimData
0x00D7B2BC: SetReferenceFrame
0x00D7B2D4: GetRefFrame
0x00D7B2E4: SetStreamableAnimData
0x00D7B2FC: GetStreamableAnimData
0x00D7B314: SetRefStreamableAnimData
0x00D7B334: GetRefStreamableAnimData
0x00D7B354: Main
0x00D7B35C: Idle Frame
0x00D7B36C: Idle Duration Min
0x00D7B384: Idle Duration Offset
0x00D7B39C: Animation Types
0x00D7B3AC: One Shot
0x00D7B3BC: Loop
0x00D7B3C4: Attachment Offset Translation
0x00D7B3E4: Attachment Offset Rotation X
0x00D7B404: Attachment Offset Rotation Y
0x00D7B424: Attachment Offset Rotation Z
0x00D7B444: Attachment Animation
0x00D7B45C: Pause Attachment Anim
0x00D7B474: ANIMMOD
0x00D7B47C: ANIMATION_MODIFIER
0x00D7B490: LeftUpLeg
0x00D7B4A0: LeftLeg
0x00D7B4A8: LeftFoot
0x00D7B4B8: RightUpLeg
0x00D7B4C8: RightLeg
0x00D7B4D8: RightFoot
0x00D7B4E4: LeftToeBase
0x00D7B4F4: RightToeBase
0x00D7B504: LeftArm
0x00D7B50C: LeftForeArm
0x00D7B51C: LeftHand
0x00D7B52C: RightArm
0x00D7B53C: RightForeArm
0x00D7B54C: RightHand
0x00D7B55C: ANIMATION_OPTIONS
0x00D7B570: DisplayMotionKitCommands
0x00D7B590: DisplayInvisiblePlanes
0x00D7B5A8: DisplayMagneticPathConstraints
0x00D7B5C8: DisplayAnimationPoses
0x00D7B5E0: DisplayBoneLock
0x00D7B5F0: DisplayPoseValidityCheck
0x00D7B610: DisplayCanDebug
0x00D7B620: DisplayHierarchyFadeIn
0x00D7B638: EnableRemoteDebugging

And this:

0x00DAC61C: ThisCommunicator
0x00DAC630: None
0x00DAC638: InBounds
0x00DAC648: OnEvent
0x00DAC650: AliasCRC
0x00DAC660: nFrameLowerBound
0x00DAC678: nFrameUpperBound
0x00DAC690: sAnimDataName
0x00DAC6A0: EventNameCRC
0x00DAC6B0: TriggerOnce
0x00DAC6C0: nAnimDataID
0x00DAC6CC: ThisCommunicator
0x00DAC6E0: Invoke
0x00DAC6E8: Success
0x00DAC6F0: AliasCRC
0x00DAC700: EventNameCRC
0x00DAC714: Invoke
0x00DAC71C: Success
0x00DAC724: EventNameCRC
0x00DAC734: EntityCatalogID
0x00DAC744: EntityCatalogName
0x00DAC758: ThisCommunicator
0x00DAC774: Offset_Translation
0x00DAC78C: Offset_Rotation

I don't know if that helps at all, but it could give some hints to what the data means...

By the way, I haven't found any texture blocks yet.... do they start without a Communicator ID? Because I did see a few of those that looked like they could be textures...
## Post #4
- Username: JayK
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-04-16T21:28:23+00:00
- Post Title: Beyond: Two Souls - Reversing | Porting (THAT'S ALL FOLKS?)

Major Update / Find / Thing

Alright, I decided to take a look at (the decrypted version of) BigFile_PS3.sdat first, which starts with the id QUANTICDREAMTABIDMEM.
I suspected this file would give indices into the other BigFile's, and I was right!

The file starts off with a header, which I haven't figured out completely yet, but at least it gives the amount of entries, and the block offset for each block (+ 0x18 for the header).

Then the very first block of entries in the sdat file are indices into BigFile_PS3.dat and are for the LOCALIZ_ blocks (PS3 error codes / Sony messages), the second block is also for BigFile_PS3.dat and this one only has one entry, for the (huge) uncompiled Lua initalization script. 

Then after that there are huge blocks of indices. First up is a tab index I haven't figured out yet   
After that come the indices into the files, each 0x14 in size. They give block offsets, block sizes and the file ID's.

Here's a sample output of 1 of the blocks of BigFile_PS3.sdat (only the first 100 entries of the total of 10,069...):

```
{
    File: G:\Projects\Tools\BeyondTwoSouls\Indexing\BigFile_PS3.(s)dat
    Header ID: QUANTICDREAMTABIDMEM
    Version: 3
}

HEADER TAB
{
    HeaderTabEntries: 7
    UnknownPadding: 0x0
     ----------
    Data Type Entry #1: Unknown: 0x3F8, TypeEntries: 0x2, BlockOffset: 0x60
    Data Type Entry #2: Unknown: 0x1078, TypeEntries: 0x1, BlockOffset: 0x488
    Data Type Entry #3: Unknown: 0x869, TypeEntries: 0x1, BlockOffset: 0x89C
    Data Type Entry #4: Unknown: 0x1D, TypeEntries: 0x2755, BlockOffset: 0xCB0
    Data Type Entry #5: Unknown: 0x897, TypeEntries: 0x15, BlockOffset: 0x32354
    Data Type Entry #6: Unknown: 0x3F2, TypeEntries: 0x3398, BlockOffset: 0x328F8
    Data Type Entry #7: Unknown: 0xFFB, TypeEntries: 0x1FC8, BlockOffset: 0x734D8
}

/* TEMP TEMP TEMP: STARTING ANALYSE @ 0x10C4 */

TEMP FILE OUTPUT
{
    Entry #1: BlockID: 256, BlockOffset: 0xADD4000, BlockSize: 0x77431F, u1: 0x6ACBC7, FileID: 0 -> BigFile_PS3.dat
    Entry #2: BlockID: 1024, BlockOffset: 0x46A46000, BlockSize: 0x68, u1: 0x0, FileID: 4 -> BigFile_PS3.d04
    Entry #3: BlockID: 1792, BlockOffset: 0x12DAE800, BlockSize: 0x12B7D8, u1: 0x0, FileID: 2 -> BigFile_PS3.d02
    Entry #4: BlockID: 2048, BlockOffset: 0x4C783800, BlockSize: 0x29, u1: 0x0, FileID: 0 -> BigFile_PS3.dat
    Entry #5: BlockID: 2560, BlockOffset: 0x240EA800, BlockSize: 0x782A, u1: 0x0, FileID: 2 -> BigFile_PS3.d02
    Entry #6: BlockID: 2816, BlockOffset: 0xBDB3000, BlockSize: 0x4F5B, u1: 0x0, FileID: 2 -> BigFile_PS3.d02
    Entry #7: BlockID: 3584, BlockOffset: 0x5B259800, BlockSize: 0x3B118, u1: 0x3A6CB, FileID: 0 -> BigFile_PS3.dat
    Entry #8: BlockID: 4608, BlockOffset: 0x61F3000, BlockSize: 0x6953B, u1: 0x0, FileID: 0 -> BigFile_PS3.dat
    Entry #9: BlockID: 6400, BlockOffset: 0x7DE5A000, BlockSize: 0x2ADB6A, u1: 0x0, FileID: 0 -> BigFile_PS3.dat
    Entry #10: BlockID: 8192, BlockOffset: 0x4DD74000, BlockSize: 0x120C7, u1: 0x0, FileID: 1 -> BigFile_PS3.d01
    Entry #11: BlockID: 8960, BlockOffset: 0x5985D000, BlockSize: 0x9D14, u1: 0x0, FileID: 2 -> BigFile_PS3.d02
    Entry #12: BlockID: 9984, BlockOffset: 0x2A398000, BlockSize: 0xE59E7, u1: 0xE45C4, FileID: 2 -> BigFile_PS3.d02
    Entry #13: BlockID: 10496, BlockOffset: 0x39932800, BlockSize: 0xBCC1, u1: 0x0, FileID: 3 -> BigFile_PS3.d03
    Entry #14: BlockID: 12032, BlockOffset: 0x551D7000, BlockSize: 0x123AFE, u1: 0x0, FileID: 3 -> BigFile_PS3.d03
    Entry #15: BlockID: 12800, BlockOffset: 0x7DA49800, BlockSize: 0x3CFFD56, u1: 0x3C9F87B, FileID: 3 -> BigFile_PS3.d03
    Entry #16: BlockID: 13568, BlockOffset: 0x12BDB000, BlockSize: 0x1F90A2, u1: 0x0, FileID: 1 -> BigFile_PS3.d01
    Entry #17: BlockID: 13824, BlockOffset: 0xBADE000, BlockSize: 0x29, u1: 0x0, FileID: 1 -> BigFile_PS3.d01
    Entry #18: BlockID: 14592, BlockOffset: 0x4FBEF800, BlockSize: 0x3B3, u1: 0x0, FileID: 0 -> BigFile_PS3.dat
    Entry #19: BlockID: 14848, BlockOffset: 0x6F185800, BlockSize: 0x1EA4D, u1: 0x0, FileID: 0 -> BigFile_PS3.dat
    Entry #20: BlockID: 16128, BlockOffset: 0x64C32800, BlockSize: 0x2B42, u1: 0x0, FileID: 1 -> BigFile_PS3.d01
    Entry #21: BlockID: 16640, BlockOffset: 0x39570800, BlockSize: 0xB8C8A, u1: 0x0, FileID: 0 -> BigFile_PS3.dat
    Entry #22: BlockID: 18176, BlockOffset: 0x1AEE6800, BlockSize: 0xB9D5B, u1: 0x0, FileID: 1 -> BigFile_PS3.d01
    Entry #23: BlockID: 19200, BlockOffset: 0x3094D800, BlockSize: 0x29, u1: 0x0, FileID: 1 -> BigFile_PS3.d01
    Entry #24: BlockID: 19968, BlockOffset: 0x30D5C800, BlockSize: 0x3AE, u1: 0x0, FileID: 1 -> BigFile_PS3.d01
    Entry #25: BlockID: 20992, BlockOffset: 0x5A712000, BlockSize: 0x29, u1: 0x0, FileID: 3 -> BigFile_PS3.d03
    Entry #26: BlockID: 22016, BlockOffset: 0x379F5800, BlockSize: 0x29, u1: 0x0, FileID: 3 -> BigFile_PS3.d03
    Entry #27: BlockID: 22272, BlockOffset: 0x5D2F8800, BlockSize: 0x9C9B, u1: 0x3207, FileID: 1 -> BigFile_PS3.d01
    Entry #28: BlockID: 24064, BlockOffset: 0x2A7D800, BlockSize: 0x247E9B, u1: 0x0, FileID: 4 -> BigFile_PS3.d04
    Entry #29: BlockID: 24576, BlockOffset: 0x396D0000, BlockSize: 0x1A19F4D, u1: 0x19F050E, FileID: 4 -> BigFile_PS3.d04
    Entry #30: BlockID: 27904, BlockOffset: 0x68C5E000, BlockSize: 0x7A6BF, u1: 0x0, FileID: 1 -> BigFile_PS3.d01
    Entry #31: BlockID: 28672, BlockOffset: 0x5D495000, BlockSize: 0xB98BE, u1: 0x0, FileID: 2 -> BigFile_PS3.d02
    Entry #32: BlockID: 29696, BlockOffset: 0x6AF8A800, BlockSize: 0x4F5D2, u1: 0x0, FileID: 2 -> BigFile_PS3.d02
    Entry #33: BlockID: 30208, BlockOffset: 0x52ED3800, BlockSize: 0x22B1D, u1: 0x0, FileID: 2 -> BigFile_PS3.d02
    Entry #34: BlockID: 30976, BlockOffset: 0x31093000, BlockSize: 0x29, u1: 0x0, FileID: 1 -> BigFile_PS3.d01
    Entry #35: BlockID: 31232, BlockOffset: 0x3A18000, BlockSize: 0x2073C, u1: 0x0, FileID: 4 -> BigFile_PS3.d04
    Entry #36: BlockID: 32512, BlockOffset: 0x4E9B800, BlockSize: 0x79CE38, u1: 0x0, FileID: 1 -> BigFile_PS3.d01
    Entry #37: BlockID: 32768, BlockOffset: 0x63FB8000, BlockSize: 0x81448, u1: 0x0, FileID: 0 -> BigFile_PS3.dat
    Entry #38: BlockID: 33024, BlockOffset: 0x4825000, BlockSize: 0x28BF5, u1: 0x0, FileID: 4 -> BigFile_PS3.d04
    Entry #39: BlockID: 35072, BlockOffset: 0x255CD800, BlockSize: 0x29, u1: 0x0, FileID: 4 -> BigFile_PS3.d04
    Entry #40: BlockID: 35840, BlockOffset: 0x3D411800, BlockSize: 0x11C954, u1: 0x0, FileID: 3 -> BigFile_PS3.d03
    Entry #41: BlockID: 36608, BlockOffset: 0x33F23800, BlockSize: 0x5D884C, u1: 0x0, FileID: 0 -> BigFile_PS3.dat
    Entry #42: BlockID: 38912, BlockOffset: 0x372E2800, BlockSize: 0x2ABA9D, u1: 0x0, FileID: 0 -> BigFile_PS3.dat
    Entry #43: BlockID: 39680, BlockOffset: 0x1F782000, BlockSize: 0xE417, u1: 0x0, FileID: 0 -> BigFile_PS3.dat
    Entry #44: BlockID: 40448, BlockOffset: 0x73AAD000, BlockSize: 0x29, u1: 0x0, FileID: 1 -> BigFile_PS3.d01
    Entry #45: BlockID: 40704, BlockOffset: 0xBE20800, BlockSize: 0x7D26, u1: 0x0, FileID: 4 -> BigFile_PS3.d04
    Entry #46: BlockID: 41216, BlockOffset: 0x564DE800, BlockSize: 0xED8A, u1: 0x0, FileID: 0 -> BigFile_PS3.dat
    Entry #47: BlockID: 43520, BlockOffset: 0x2BB60800, BlockSize: 0x2DFC, u1: 0x0, FileID: 4 -> BigFile_PS3.d04
    Entry #48: BlockID: 43776, BlockOffset: 0x6B89000, BlockSize: 0xADF, u1: 0x0, FileID: 4 -> BigFile_PS3.d04
    Entry #49: BlockID: 513, BlockOffset: 0x396000, BlockSize: 0x464, u1: 0x0, FileID: 0 -> BigFile_PS3.dat
    Entry #50: BlockID: 1025, BlockOffset: 0x46A44800, BlockSize: 0x68, u1: 0x0, FileID: 4 -> BigFile_PS3.d04
    Entry #51: BlockID: 1281, BlockOffset: 0x832A000, BlockSize: 0x6957A1, u1: 0x686825, FileID: 2 -> BigFile_PS3.d02
    Entry #52: BlockID: 1537, BlockOffset: 0x235C6800, BlockSize: 0x3F0C9, u1: 0x0, FileID: 2 -> BigFile_PS3.d02
    Entry #53: BlockID: 1793, BlockOffset: 0x12EDA000, BlockSize: 0xC79A, u1: 0x0, FileID: 2 -> BigFile_PS3.d02
    Entry #54: BlockID: 2817, BlockOffset: 0xBDB8000, BlockSize: 0x18201B, u1: 0x0, FileID: 2 -> BigFile_PS3.d02
    Entry #55: BlockID: 3585, BlockOffset: 0x5B295000, BlockSize: 0xFF4C7, u1: 0xA3EFB, FileID: 0 -> BigFile_PS3.dat
    Entry #56: BlockID: 3841, BlockOffset: 0xE388800, BlockSize: 0x70F77, u1: 0x0, FileID: 2 -> BigFile_PS3.d02
    Entry #57: BlockID: 4097, BlockOffset: 0x4DB8B800, BlockSize: 0x41AE2, u1: 0x0, FileID: 0 -> BigFile_PS3.dat
    Entry #58: BlockID: 5121, BlockOffset: 0x4FAA1800, BlockSize: 0x6B137E, u1: 0x6A0839, FileID: 1 -> BigFile_PS3.d01
    Entry #59: BlockID: 7681, BlockOffset: 0x63847800, BlockSize: 0x3067, u1: 0x0, FileID: 2 -> BigFile_PS3.d02
    Entry #60: BlockID: 8193, BlockOffset: 0x4DD86800, BlockSize: 0x29, u1: 0x0, FileID: 1 -> BigFile_PS3.d01
    Entry #61: BlockID: 8961, BlockOffset: 0x59867000, BlockSize: 0x6D704, u1: 0x0, FileID: 2 -> BigFile_PS3.d02
    Entry #62: BlockID: 10497, BlockOffset: 0x3993E800, BlockSize: 0x58BE, u1: 0x0, FileID: 3 -> BigFile_PS3.d03
    Entry #63: BlockID: 11009, BlockOffset: 0x1141E000, BlockSize: 0xBE6, u1: 0x0, FileID: 2 -> BigFile_PS3.d02
    Entry #64: BlockID: 12801, BlockOffset: 0x734AB800, BlockSize: 0x5A3062, u1: 0x58888A, FileID: 0 -> BigFile_PS3.dat
    Entry #65: BlockID: 13825, BlockOffset: 0xBADE800, BlockSize: 0x42B2A, u1: 0x0, FileID: 1 -> BigFile_PS3.d01
    Entry #66: BlockID: 14337, BlockOffset: 0x764FE800, BlockSize: 0x37FAA8, u1: 0x313500, FileID: 0 -> BigFile_PS3.dat
    Entry #67: BlockID: 16385, BlockOffset: 0x65162800, BlockSize: 0x12447A, u1: 0x0, FileID: 1 -> BigFile_PS3.d01
    Entry #68: BlockID: 19201, BlockOffset: 0x3094E000, BlockSize: 0x79A66, u1: 0x0, FileID: 1 -> BigFile_PS3.d01
    Entry #69: BlockID: 19969, BlockOffset: 0x30D5D000, BlockSize: 0x46CB0, u1: 0x0, FileID: 1 -> BigFile_PS3.d01
    Entry #70: BlockID: 20481, BlockOffset: 0x3CD5D000, BlockSize: 0x76FD0, u1: 0x0, FileID: 1 -> BigFile_PS3.d01
    Entry #71: BlockID: 20993, BlockOffset: 0x7251E000, BlockSize: 0x1BD8BD, u1: 0x0, FileID: 1 -> BigFile_PS3.d01
    Entry #72: BlockID: 22017, BlockOffset: 0x379F6000, BlockSize: 0x29, u1: 0x0, FileID: 3 -> BigFile_PS3.d03
    Entry #73: BlockID: 24065, BlockOffset: 0x2CC5800, BlockSize: 0x2602F, u1: 0x0, FileID: 4 -> BigFile_PS3.d04
    Entry #74: BlockID: 30209, BlockOffset: 0x53F21800, BlockSize: 0xF4D, u1: 0x0, FileID: 2 -> BigFile_PS3.d02
    Entry #75: BlockID: 30977, BlockOffset: 0x31093800, BlockSize: 0x29, u1: 0x0, FileID: 1 -> BigFile_PS3.d01
    Entry #76: BlockID: 31745, BlockOffset: 0x5EE4F800, BlockSize: 0x60066, u1: 0x0, FileID: 2 -> BigFile_PS3.d02
    Entry #77: BlockID: 32257, BlockOffset: 0x46CA800, BlockSize: 0x3B1, u1: 0x0, FileID: 4 -> BigFile_PS3.d04
    Entry #78: BlockID: 32769, BlockOffset: 0x64039800, BlockSize: 0x2F2B9, u1: 0x0, FileID: 0 -> BigFile_PS3.dat
    Entry #79: BlockID: 35073, BlockOffset: 0x255CE000, BlockSize: 0x2D872, u1: 0x0, FileID: 4 -> BigFile_PS3.d04
    Entry #80: BlockID: 35841, BlockOffset: 0x3D52E800, BlockSize: 0xED651, u1: 0x0, FileID: 3 -> BigFile_PS3.d03
    Entry #81: BlockID: 37633, BlockOffset: 0xD529800, BlockSize: 0x1964, u1: 0x0, FileID: 3 -> BigFile_PS3.d03
    Entry #82: BlockID: 37889, BlockOffset: 0x116C0000, BlockSize: 0x71E3, u1: 0x0, FileID: 0 -> BigFile_PS3.dat
    Entry #83: BlockID: 39681, BlockOffset: 0x1F790800, BlockSize: 0x41D28, u1: 0x0, FileID: 0 -> BigFile_PS3.dat
    Entry #84: BlockID: 40193, BlockOffset: 0x22F54000, BlockSize: 0x1A616, u1: 0x0, FileID: 0 -> BigFile_PS3.dat
    Entry #85: BlockID: 40449, BlockOffset: 0x73AAD800, BlockSize: 0x29, u1: 0x0, FileID: 1 -> BigFile_PS3.d01
    Entry #86: BlockID: 41217, BlockOffset: 0x564ED800, BlockSize: 0x1DC63, u1: 0x0, FileID: 0 -> BigFile_PS3.dat
    Entry #87: BlockID: 41729, BlockOffset: 0x61035800, BlockSize: 0x14044, u1: 0x0, FileID: 2 -> BigFile_PS3.d02
    Entry #88: BlockID: 43777, BlockOffset: 0x69D0800, BlockSize: 0x5BE12, u1: 0x0, FileID: 4 -> BigFile_PS3.d04
    Entry #89: BlockID: 258, BlockOffset: 0x8FA2000, BlockSize: 0x7CBC5D, u1: 0x72BFB2, FileID: 0 -> BigFile_PS3.dat
    Entry #90: BlockID: 770, BlockOffset: 0x5305C000, BlockSize: 0x241422B, u1: 0x237FBD7, FileID: 1 -> BigFile_PS3.d01
    Entry #91: BlockID: 1026, BlockOffset: 0x46A45000, BlockSize: 0x464, u1: 0x0, FileID: 4 -> BigFile_PS3.d04
    Entry #92: BlockID: 1538, BlockOffset: 0x23606000, BlockSize: 0x29, u1: 0x0, FileID: 2 -> BigFile_PS3.d02
    Entry #93: BlockID: 2818, BlockOffset: 0xBF3A800, BlockSize: 0x7EA1, u1: 0x0, FileID: 2 -> BigFile_PS3.d02
    Entry #94: BlockID: 3586, BlockOffset: 0x5B394800, BlockSize: 0xAE8F9, u1: 0x79511, FileID: 0 -> BigFile_PS3.dat
    Entry #95: BlockID: 8450, BlockOffset: 0x39708800, BlockSize: 0x3CEB, u1: 0x0, FileID: 1 -> BigFile_PS3.d01
    Entry #96: BlockID: 8962, BlockOffset: 0x598D4800, BlockSize: 0x20EBB, u1: 0x0, FileID: 2 -> BigFile_PS3.d02
    Entry #97: BlockID: 10242, BlockOffset: 0x265C2800, BlockSize: 0xF3203, u1: 0xBE680, FileID: 0 -> BigFile_PS3.dat
    Entry #98: BlockID: 11010, BlockOffset: 0x1141F000, BlockSize: 0x138212, u1: 0x0, FileID: 2 -> BigFile_PS3.d02
    Entry #99: BlockID: 12034, BlockOffset: 0x552FB000, BlockSize: 0xA5FB2, u1: 0x0, FileID: 3 -> BigFile_PS3.d03
    Entry #100: BlockID: 12802, BlockOffset: 0x7F43C000, BlockSize: 0xE2CC2, u1: 0xB8880, FileID: 0 -> BigFile_PS3.dat
}

```


There are a few things to note here:
1. The thing that I called "BlockID" (which I'm not sure of if that's what it actually is) gets bigger every entry but then suddenly gets smaller again. I'm suspecting these are "groups" of assets that belong to each other.
2. The u1 stands for Unknown1. No idea what this indicates yet, but it's only non-0x0 for some entries...

So, that's it for now!
## Post #5
- Username: mirh
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-04-17T21:19:15+00:00
- Post Title: Beyond: Two Souls - Reversing | Porting (THAT'S ALL FOLKS?)

The "groups" inside BigFile_PS3.(s)dat seem to be neatly ordered by content! There's a group that indexes just .bik files (video) of the different BigFile's, then there's a group that seems to be indexing only the audio files, and there are groups that index all over the place (BigFile_PS3.dat - .d04). Then, within the big content groups, there seem to be 255 subgroups (always that number for some reason), that's the tab thing I didn't understand in my previous post. These subgroups are defined before the actual file indices start of that content group. I'm not sure if these groups actually mean something or not right now. Today I made a pretty good parser for the index sdat with basic GUI / treeview of the individual entries of every BigFile, together with sorting per content group / subgroup. Will port some of the better code of the extractor over tomorrow so I can check if these groups are actual groups.
## Post #6
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2014-04-18T11:11:52+00:00
- Post Title: Beyond: Two Souls - Reversing | Porting (THAT'S ALL FOLKS?)

I have some files taken from the ps3s cache whilst the game is running, I can send them to you if you think they may help.
## Post #7
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-04-18T14:13:38+00:00
- Post Title: Beyond: Two Souls - Reversing | Porting (THAT'S ALL FOLKS?)

> Reply from HugoPeters
>
> 
PSST, don't tell anyone: I got the source code for EdgeZlib
hehehe XD nice! hope that comes in handy


> Reply from HugoPeters
>
> 
Furthermore, here are the different types of Dynamic Communicator blocks I could find, most of them with a description of some sort.
Ah nice yeah those look about right

 case "MESHDATA":
 case "OBJ_____":

seem interesting most likely OBJ would be the static objects in the scenes.


> Reply from HugoPeters
>
> 
By the way, I haven't found any texture blocks yet.... do they start without a Communicator ID? Because I did see a few of those that looked like they could be textures...
The textures are in DXT1 DXT5 (DXTATI2N - NORMALS), if I recall the segs script EKEY wrote dumped some texture files.


> Reply from JayK
>
> I have some files taken from the ps3s cache whilst the game is running, I can send them to you if you think they may help.
Someone's mentioned this to me before would you mind if I took a look at the ram dump as well to at least see how there model formats are stored and hopefully
figure them out for when Hugo's finished his parser tool?

Oh lastly great job HugoPeters
## Post #8
- Username: mirh
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-04-18T15:29:13+00:00
- Post Title: Beyond: Two Souls - Reversing | Porting (THAT'S ALL FOLKS?)

> Reply from JayK
>
> I have some files taken from the ps3s cache whilst the game is running, I can send them to you if you think they may help.
Yeah, that would be very useful! That could help with identifying the different groups of files the game defines, or what to expect from the decompressed file entries. Btw, cache dump = RAM dump?

> Reply from cra0
>
> HugoPeters wrote:
HugoPeters wrote:
Furthermore, here are the different types of Dynamic Communicator blocks I could find, most of them with a description of some sort.

Ah nice yeah those look about right

 case "MESHDATA":
 case "OBJ_____":

seem interesting most likely OBJ would be the static objects in the scenes.

From what I can tell the objects are very complex. Here's some strings related to the model structure:

0x00DCA3FC: hkVersionPatchManager
0x00DCA414: hk_2011.1.0-r1
0x00DCA424: hk.DataObjectType
0x00DCA438: The object of class 
0x00DCA451: is about to be removed and all references to it will be invalid.
However, the object is referenced (
0x00DCA4B8: ) from outside the world and it will lead to unexpected behavior or crash.
0x00DCA508: d:/Perforce/Main/Havok2011/Source/Common/Serialize/Data/Dict/hkDataObjectDict.cpp
0x00DCA55C: typeName
0x00DCA610: hk.PostFinish
0x00DCA654: __classnames__
0x00DCA664: variant
0x00DCA66C: memSizeAndFlags
0x00DCA67C: value
0x00DCA684: name
0x00DCA68C: time
0x00DCA694: namedVariants
0x00DCA6A4: className
0x00DCA6B4: hkRootLevelContainer
0x00DCA6CC: hkRootLevelContainerNamedVariant
0x00DCA6F4: hkReferencedObject
0x00DCA70C: hkBaseObject
0x00DCA71C: type
0x00DCA724: data
0x00DCA72C: hkxMaterial
0x00DCA73C: floatData
0x00DCA74C: floatStride
0x00DCA75C: uint8Stride
0x00DCA76C: hkxIndexBuffer
0x00DCA77C: userChannels
0x00DCA78C: mapping
0x00DCA794: hkxMaterialTextureStage
0x00DCA7AC: uint8Data
0x00DCA7BC: decls
0x00DCA7C4: hkxMeshSection
0x00DCA7D4: attributes
0x00DCA7E4: hkxVertexDescriptionElementDecl
0x00DCA804: numVerts
0x00DCA814: subMaterials
0x00DCA824: length
0x00DCA82C: indexBuffers
0x00DCA83C: annotations
0x00DCA84C: indexType
0x00DCA85C: uint16Data
0x00DCA86C: hkxMesh
0x00DCA874: uint32Stride
0x00DCA884: vectorData
0x00DCA894: attributeGroups
0x00DCA8A4: ambientColor
0x00DCA8B4: byteOffset
0x00DCA8C4: hkxVertexBufferVertexData
0x00DCA8E4: indices16
0x00DCA8F4: indices32
0x00DCA904: hkpSphereMotion
0x00DCA914: hkxVertexDescription
0x00DCA92C: hkxAttributeGroup
0x00DCA944: texture
0x00DCA94C: diffuseColor
0x00DCA95C: material
0x00DCA96C: stages
0x00DCA974: usage
0x00DCA97C: userChannelInfos
0x00DCA994: specularColor
0x00DCA9A4: mesh
0x00DCA9AC: vectorStride
0x00DCA9BC: byteStride
0x00DCA9CC: sections
0x00DCA9DC: hkxAttribute
0x00DCA9EC: uint32Data
0x00DCA9FC: desc
0x00DCAA04: uint16Stride
0x00DCAA14: tcoordChannel
0x00DCAA24: hkxAttributeHolder
0x00DCAA3C: vertexBuffer
0x00DCAA4C: emissiveColor
0x00DCAA5C: hkxVertexBuffer
0x00DCAA6C: vertexBaseOffset
0x00DCAA84: hkxAnimatedVector
0x00DCAA9C: vectors
0x00DCAAA4: hkxMeshUserChannelInfo
0x00DCAABC: usageHint
0x00DCAACC: isHierarchicalCompound
0x00DCAAE4: extraData
0x00DCAAF4: hkpShapeInfo
0x00DCAB04: childShapeNames
0x00DCAB14: localFrame
0x00DCAB24: childTransforms
0x00DCAB34: hkdShapesCollected
0x00DCAB4C: hkLocalFrame
0x00DCAB64: children
0x00DCAB74: floats
0x00DCAB7C: parent
0x00DCAB84: hkMemoryResourceHandleExternalLink
0x00DCABAC: hkMemoryResourceHandle
0x00DCABC4: hkResourceContainer
0x00DCABDC: references
0x00DCABEC: hkResourceHandle
0x00DCAC04: memberName
0x00DCAC14: hkMemoryResourceContainer
0x00DCAC34: hkResourceBase
0x00DCAC44: externalId
0x00DCAC54: resourceHandles
0x00DCAC64: near
0x00DCAC6C: materials
0x00DCAC7C: leftHanded
0x00DCAC8C: hkxTextureInplace
0x00DCACA4: angle
0x00DCACAC: selectedNodes
0x00DCACBC: position
0x00DCACCC: hkxScene
0x00DCACDC: cameras
0x00DCACE4: rootNode
0x00DCACF4: filename
0x00DCAD04: modeller
0x00DCAD14: bindPose
0x00DCAD24: selected
0x00DCAD34: hkxNodeAnnotationData
0x00DCAD4C: fileType
0x00DCAD5C: asset
0x00DCAD64: far
0x00DCAD6C: object
0x00DCAD74: meshes
0x00DCAD7C: userProperties
0x00DCAD8C: hkxNode
0x00DCAD94: externalTextures

There's a lot more, but I don't know if that has to do with the actual model file...
What's interesting is that (some of) the physics data is also stored in the model file.
It looks like the mesh data is stored in chunks... not sure if one chunk equals one primitive, but it's worth considering...

Btw, here's a screenshot from the output of the data as how it's stored in the BigFile indices file (BigFile_PS3.sdat):

It's the beginning of my all-in-one parser tool thingy :3

> Reply from cra0
>
> 
HugoPeters wrote:
By the way, I haven't found any texture blocks yet.... do they start without a Communicator ID? Because I did see a few of those that looked like they could be textures...

The textures are in DXT1 DXT5 (DXTATI2N - NORMALS), if I recall the segs script EKEY wrote dumped some texture files.
Do the texture files start with a Communicator ID? like COM_CONT, ANIMDATA, PARTITIO_, etc?
Can you attach a sample texture file? So I'm not "groping in the dark"?
## Post #9
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2014-04-19T00:23:18+00:00
- Post Title: Beyond: Two Souls - Reversing | Porting (THAT'S ALL FOLKS?)

Nah the cache dump is different to the ram dump, but I dumped the ram as well soI can give you that also. The cache dump has the scene and and index and DAT file etc, like TheEmbassy.idx TheEmbassy.DAT there's lots of Segs and other stuff insid. I became less interested as time went on but I still have the files. I'll send them to you both soon
## Post #10
- Username: RunaWhite
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-04-27T22:56:03+00:00
- Post Title: Beyond: Two Souls - Reversing | Porting (THAT'S ALL FOLKS?)

Update!
Alright, got quite a lot of stuff going on!
cra0 and I are working on the ultimate Beyond tool!

I'm doing most of the tool itself, the GUI, parser, structure, base features, decompressor, extractor, etc. while cra0 is reversing the model format! And another big thing for me: I've made the switch from GameMaker to C# in Visual Studio..... and damn. It's like heaven. I really want to thank cra0 for helping we with all my noob questions, I'm already getting the hang of it!

Here are some screenshots from the tool in its current form (which is: very unfinished / very early):


Left is where you select the main entries group. The entries are defined from the decrypted BigFile_PS3.sdat file. Then once you loaded the entries group, you get a nice display of all the entries in that group!


Before you can actually begin looking in the entries to see what data they contain you must first Inspect them. You can Inspect every individual entry manually by selecting it, then going to the Inspector tab and then clicking the Inspect button, but you can also Inspect all entries at once by clicking the Tools menu.
Once entries have been Inspected you can do things like searching the entries for types of content (Communicators). The filter can be set by selecting the "Filter" tab on the left... you can also choose between two filter modes: the entry must contain all Communicators in the filter, or the entry must contain one or more of the Communicators in the filter! When you click "Add Communicator" you get a nice popup with a combo box consisting of all known Communicators.


You can also filter the currently loaded entries on offset!


This is the Inspector tab. On the Inspector's Base tab, you can see an overview of all Communicators found within the entries. As you can see in this example, it contains both Communicators set in the filter!


This is a feature in a very early stage: an output of how the entry is constructed.


Here's a neat one: when you double click a Communicator in the Inspector's Base tab, you will be taken to the Hex Viewer, and the selected offset will be automatically set to the offset of that Communicator!

Also, don't forget the decompressor! I found out more about how these files are built, and most of them consist of more than one segs archive!

So yeah, let me know what you guys think! If you have any suggestions, please let me know!
## Post #11
- Username: JayK
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-05-01T20:50:50+00:00
- Post Title: Beyond: Two Souls - Reversing | Porting (THAT'S ALL FOLKS?)

another huge update with a title in a huge font

Thanks to JayK's files I reverse engineered the DC_INFO sections in Beyond's file structure.

Too tired for an explanation now and since no one ever replies here I'm not going to bother posting the structure until someone asks me too   

Here's a sample:
## Post #12
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2014-05-02T22:07:11+00:00
- Post Title: Beyond: Two Souls - Reversing | Porting (THAT'S ALL FOLKS?)

Nice, glad them files came in handy.
## Post #13
- Username: mirh
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-05-04T22:28:05+00:00
- Post Title: Beyond: Two Souls - Reversing | Porting (THAT'S ALL FOLKS?)

Alrighty, I now partly understand the way the game accesses its content.
Again, not going to explain too deeply because I suck at explaining and this is pretty complicated xD

Here's a quick look though:



This is for dialog. For example, the first red square gives an index into the FLOW_DIALOG content group, which is included in these:



The enum value for FLOW_DIALOG(_OFFSET) is 0xffc / 0xffb.
Then, the File ID is the next int, in this example it's 0x131a.

Using my tool I can quickly seek to the file bound to that ID, and then hear the audio, and it matches the sentence! 

This ID, 0x3f2 stands for AUDIO_DATA. This is from one of JayK's files, The Party.dat or something like that. When I go to the file with that ID, surprise surprise, it's the "Beautiful Body" song!
## Post #14
- Username: mono24
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-05-06T10:50:30+00:00
- Post Title: Beyond: Two Souls - Reversing | Porting (THAT'S ALL FOLKS?)

I've made a video demonstrating the tool and how I find matching audio with text dialog (FLOW_DIALOG):

[https://www.youtube.com/watch?v=vunRjVMVXY0](https://www.youtube.com/watch?v=vunRjVMVXY0)
## Post #15
- Username: mirh
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-05-06T14:25:35+00:00
- Post Title: Beyond: Two Souls - Reversing | Porting (THAT'S ALL FOLKS?)

Texture format is reversed!
## Post #16
- Username: mirh
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-05-06T17:23:48+00:00
- Post Title: Re: [PS3] Beyond: Two Souls -Extractor- + Beginnings of pars

BOOM.
## Post #17
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2014-05-07T03:37:33+00:00
- Post Title: Re: [PS3] Beyond: Two Souls -Extractor- + Beginnings of pars

are you planning to obtain 3d models in the future?
## Post #18
- Username: mirh
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-05-07T09:01:23+00:00
- Post Title: Re: [PS3] Beyond: Two Souls -Extractor- + Beginnings of pars

> Reply from luxox18
>
> are you planning to obtain 3d models in the future?
Why does everyone keep asking me that...

Cra0 is working on the models, I help him with that whenever I can, but I don't know as much of 3D stuff as he does.
I'm mostly working on reversing the main structure, compression, audio, textures, the communicators and their attributes, Lua scripts, variables, data containers, etc. I'm also in charge of development of the tool.

I'm planning to reverse the whole thing. With animation and all. But if I ever get to that..... is a big question.
It is however a big relief that cra0 and me are working together. It would've been way too much to do alone.

I don't like that whenever I get a comment on here (which is not often at all) it's never like "thanks!"
## Post #19
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2014-05-07T19:58:24+00:00
- Post Title: Re: [PS3] Beyond: Two Souls -Extractor- + Beginnings of pars

Im surprised there aren't more people speaking in the topic, but I honestly think that's because of the forum it's in, if this were in game archive research for example I think it would have a lot more attention, people rarely visit this subforum. I think people keep asking about the mesh as that's what they mainly want and fail to realise how much greater a feat it is to have done what you have in managing to find the connection between each of the files, structure, and how they talk to each other, I'm sure you feel greatly rewarded in yourself for doing so.

I think because some people that visit these forums are just interested in getting 3d models they don'treally reverse themselves  they don't really understand, I wouldn't really worry about those people. But if the game is using edge's byte compression for the models then I think its going to be a really hard task to parse them. So these people might be asking for a while. But yeah, don't be disheartened by them, ive looked at the files before so i know theyre very complex. You're doing some great work.
## Post #20
- Username: JayK
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-05-07T20:15:22+00:00
- Post Title: Re: [PS3] Beyond: Two Souls -Extractor- + Beginnings of pars

It is using edge compression. it looks standard tho unlike uncharted.
## Post #21
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-05-07T21:06:40+00:00
- Post Title: Re: [PS3] Beyond: Two Souls -Extractor- + Beginnings of pars

> Reply from chrrox
>
> It is using edge compression. it looks standard tho unlike uncharted.
Theres a magic meshdata which is followed by a vertex structure of some sort then another magic primeedge which looks like tristrips. Still trying to figure it out though since there is random face indices scattered around
## Post #22
- Username: JayK
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-05-07T21:26:09+00:00
- Post Title: Re: [PS3] Beyond: Two Souls -Extractor- + Beginnings of pars

> Reply from JayK
>
> Im surprised there aren't more people speaking in the topic, but I honestly think that's because of the forum it's in, if this were in game archive research for example I think it would have a lot more attention, people rarely visit this subforum. I think people keep asking about the mesh as that's what they mainly want and fail to realise how much greater a feat it is to have done what you have in managing to find the connection between each of the files, structure, and how they talk to each other, I'm sure you feel greatly rewarded in yourself for doing so.

I think because some people that visit these forums are just interested in getting 3d models they don'treally reverse themselves  they don't really understand, I wouldn't really worry about those people. But if the game is using edge's byte compression for the models then I think its going to be a really hard task to parse them. So these people might be asking for a while. But yeah, don't be disheartened by them, ive looked at the files before so i know theyre very complex. You're doing some great work.

Thank you! Yes, I actually do feel rewarded! It's awesome when something works out the way you think it does!
## Post #23
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2014-05-08T01:46:01+00:00
- Post Title: Re: [PS3] Beyond: Two Souls -Extractor- + Beginnings of pars

> Reply from JayK
>
> Im surprised there aren't more people speaking in the topic, but I honestly think that's because of the forum it's in, if this were in game archive research for example I think it would have a lot more attention, people rarely visit this subforum. I think people keep asking about the mesh as that's what they mainly want and fail to realise how much greater a feat it is to have done what you have in managing to find the connection between each of the files, structure, and how they talk to each other, I'm sure you feel greatly rewarded in yourself for doing so.

I think because some people that visit these forums are just interested in getting 3d models they don'treally reverse themselves  they don't really understand, I wouldn't really worry about those people. But if the game is using edge's byte compression for the models then I think its going to be a really hard task to parse them. So these people might be asking for a while. But yeah, don't be disheartened by them, ive looked at the files before so i know theyre very complex. You're doing some great work.

I'm reversing killzone models  but anyway I want to know if is possible to obtain meshes and cra0 is working on this.
## Post #24
- Username: RunaWhite
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-05-11T22:12:21+00:00
- Post Title: Re: [PS3] Beyond: Two Souls -Extractor- + Beginnings of pars

i can confirm its standard edge format.
## Post #25
- Username: mono24
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-05-11T22:35:37+00:00
- Post Title: Re: [PS3] Beyond: Two Souls -Extractor- + Beginnings of pars

Good job on the mesh!



Here's something completely different!
[http://youtu.be/NfqOkZnVfg0](http://youtu.be/NfqOkZnVfg0)

You can see it uses Edge Geometry and more in the end of the video.
## Post #26
- Username: oyunceviri
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-05-13T20:02:57+00:00
- Post Title: Re: [PS3] Beyond: Two Souls -Extractor- + Beginnings of pars

Not that interesting for others for now, but here's the complete debug dialog output of "Hunted", together with all file ID's.

2106.32s-[DART]Finished loading scene
2192.63s-[DART][LOC][23] : {S}{*1}OH!
2194.43s-[DART][LOC][23] : {S}{*2}Back off, Aiden.
2196.87s-[DART][LOC][23] : {S}{*3}C'mon! I haven't slept in like three days,
2199.91s-[DART][LOC][23] : {S}{*4}okay? I'm tired...
2261.86s-[DART][LOC][68031] : {S}{*1}Goddamn rain,
2264.60s-[DART][LOC][68031] : {S}{*2}don't look like it's ever gonna let up.
2265.83s-[DART][LOC][35] : {S}{*3}Aiden!
2267.14s-[DART][LOC][35] : {S}{*4}Look, I told you that&
2271.08s-[DART][LOC][37] : {S}{*1}Crap&
2284.13s-[DART][LOC][30] : {S}{*1}Evening.
2284.34s-[DART][LOC][45] : {S}{*2}Ma'am! Return to your seat, please!
2289.27s-[DART][LOC][42] : {S}{*1}Shit, that's her! THAT'S HER!
2301.08s-[DART][LOC][55] : {S}{*1}Freeze! Police!
2306.96s-[DART][LOC][67] : {S}{*1}Hey! What's going on?
2317.33s-[DART][LOC][63] : {S}{*1}Hey, watch out!
2319.38s-[DART][LOC][62] : {S}{*1}Grab her!
2328.33s-[DART][LOC][65] : {S}{*1}Hey, you crazy?!
2339.61s-[DART][LOC][76] : {S}{*5}Quick, Aiden!
2340.85s-[DART][LOC][76] : {S}{*6}Blast the window!
2442.32s-[DART][LOC][91] : {S}{*1}Got you!
2444.02s-[DART][LOC][90] : {S}{*1}End of the line, lady.
2445.79s-[DART][LOC][90] : {S}{*2} Keep your hands where we can see em!
2448.90s-[DART][LOC][92] : {S}{*1}GET HER!
2451.36s-[DART][LOC][23709] : {S}{*TC:1380|2570}HELP ME, AIDEN!!!!
2451.68s-[DART][LOC][95] : {S}{*1}Fuck!
2454.34s-[DART][LOC][96] : {S}{*1}We need back-up! She's getting away!
2479.78s-[DART]Finished loading scene
2510.03s-[DART][LOC][97] : {S}{*1}Yeah, I know.
2512.34s-[DART][LOC][97] : {S}{*2}We gotta get out of here before they come back.
2524.30s-[DART][LOC][118] : {S}{*1}Over there!
2526.29s-[DART][LOC][121] : {S}{*1}Go around the other side!
2529.30s-[DART][LOC][114] : {S}{*1}Oh, fuck!
2536.53s-[DART][LOC][110] : {S}{*1}Watch your footing! It's fucking slippery&
2547.76s-[DART][LOC][101] : {S}{*1}This girl is dangerous, so be careful!
2558.42s-[DART][LOC][105] : {S}{*1}I think I see her!
2569.09s-[DART][LOC][100] : {S}{*1}Fan out! 10 foot gaps&
2589.95s-[DART][LOC][116] : {S}{*1}There!
2591.05s-[DART][LOC][116] : {S}{*2}She's in the river!
2593.48s-[DART][LOC][117] : {S}{*1}Travis, go to the rocks!
2595.79s-[DART][LOC][117] : {S}{*2}Move!
2613.33s-[DART][LOC][111] : {S}{*1}Go around there!
2617.98s-[DART][LOC][102] : {S}{*1}I can't see a damn thing!
2622.93s-[DART][LOC][107] : {S}{*1}Control those fucking dogs!
2628.54s-[DART][LOC][115] : {S}{*1}Keep your eyes peeled!
2633.28s-[DART][LOC][103] : {S}{*1}I just saw her, she can't be that far!
2639.95s-[DART][LOC][113] : {S}{*1}Over here!
2707.28s-[DART][LOC][98] : {S}{*1}Where the hell did she go?
2712.84s-[DART][LOC][112] : {S}{*1}See anything yet?
2734.60s-[DART][LOC][106] : {S}{*1}We need more light over here, I can't see a damn thing!
2754.34s-[DART][LOC][122] : {S}{*1}You see anything?
2756.99s-[DART][LOC][123] : {S}{*1}Nothing but rock.
2759.65s-[DART][LOC][123] : {S}{*2}And she'd never be able to make it up there&
2767.27s-[DART][LOC][124] : {S}{*1}Shit!
2768.36s-[DART][LOC][124] : {S}{*2}We musta' missed her!
2769.59s-[DART][LOC][124] : {S}{*3}Travis!
2770.57s-[DART][LOC][124] : {S}{*4}Bring back those goddamn dogs!
2795.14s-[DART]Finished loading scene
2813.27s-[DART][LOC][23243] : {S}{*1}Go for it, Aiden.
2822.71s-[DART][LOC][23636] : {S}{*1}Goddamn rain,
2825.46s-[DART][LOC][23636] : {S}{*2}don't look like it's ever gonna let up.
2830.85s-[DART][LOC][23637] : {S}{*1}I hope to hell she gets here soon&
2833.74s-[DART][LOC][23637] : {S}{*2}Just clap irons on the bitch and we can all go back to bed.
2841.84s-[DART][LOC][23638] : {S}{*1}That copter back there&
2844.21s-[DART][LOC][23638] : {S}{*2}it looked like it was down by the river.
2848.82s-[DART][LOC][23639] : {S}{*1}Could have been&
2859.38s-[DART][LOC][23197] : {S}{*1}A motorbike,
2861.22s-[DART][LOC][23197] : {S}{*2}just what I need.
2895.11s-[DART][LOC][129] : {S}{*1}Where are you goin' Mike?
2897.40s-[DART][LOC][136] : {S}{*1}Hey,
2898.41s-[DART][LOC][136] : {S}{*2}what the fuck are you doin'?!
2907.05s-[DART][LOC][127] : {S}{*1}All right Mike, that's enough! You out of your fuckin mind?!
2910.73s-[DART][LOC][127] : {S}{*2}Jesus Christ!
2914.66s-[DART][LOC][139] : {S}{*1}Jesus, Mike!
2916.08s-[DART][LOC][139] : {S}{*2}What the fuck?!
2930.95s-[DART]Finished loading scene
3013.54s-[DART][LOC][68698] : {S}{*1}Hold your positions.
3021.57s-[DART][LOC][146] : {S}{*1}No choice.
3023.77s-[DART][LOC][146] : {S}{*2}We're going straight through.
3025.72s-[DART][LOC][146] : {S}{*3}Are you ready, Aiden?
3034.03s-[DART][LOC][147] : {S}{*2}Let's go!!!
3035.30s-[DART][LOC][23255] : {S}{*1}Aiden, I need you NOW!
3045.36s-[DART][LOC][177] : {S}{*1}Take cover!
3057.47s-[DART][LOC][68708] : {S}{*1}Hold your fire!
3059.00s-[DART][LOC][68721] : {S}{*1}I said HOLD YOUR FIRE!
3061.05s-[DART][LOC][149] : {S}{*1}This is Roadblock Tango.
3063.25s-[DART][LOC][149] : {S}{*2}We missed her.
3064.90s-[DART][LOC][149] : {S}{*3}I repeat, we missed her. She's headed for Bakertown!
3089.85s-[DART]Finished loading scene
3116.22s-[DART][LOC][186] : {S}{*1}Move in! Move in!
3132.97s-[DART][LOC][190] : {S}{*1}Group 3, in position.
3135.73s-[DART][LOC][152] : {S}{*1}You're surrounded! Come out with your hands up and you will not be harmed!
3139.77s-[DART][LOC][151] : {S}{*7}If theyre looking for trouble,
3141.74s-[DART][LOC][151] : {S}{*8}that's what theyre gonna get&
3145.58s-[DART][LOC][151] : {S}{*10}Take care of them, Aiden!
3170.24s-[DART][LOC][167] : {S}{*1}Take cover!
3189.72s-[DART][LOC][164] : {S}{*1}What the hell is goin' on?
3195.48s-[DART][LOC][23693] : {S}{*1}Hold your fire!
3199.67s-[DART][LOC][23662] : {S}{*1}We need an ambulance! Call a fucking ambulance!
3200.90s-[DART][LOC][23674] : {S}{*1}We can't just stand here like this!
3201.18s-[DART][LOC][184] : {S}{*1}Have you got a visual?!
3202.77s-[DART][LOC][23690] : {S}{*1}Hold your positions.
3203.36s-[DART][LOC][23688] : {S}{*1}Don't move.
3212.67s-[DART][LOC][23694] : {S}{*1}I said HOLD YOUR FIRE!
3213.10s-[DART][LOC][166] : {S}{*1}I don't get it. Its fucked up!
3220.24s-[DART][LOC][23675] : {S}{*1}We need to do something!
3225.89s-[DART][LOC][23672] : {S}{*1}She won't surrender!
3227.82s-[DART][LOC][23695] : {S}{*1}Stop Shooting!
3231.24s-[DART][LOC][192] : {S}{*1}What the fuck are we supposed to do?!
3231.71s-[DART][LOC][23661] : {S}{*1}He's choking!
3233.14s-[DART][LOC][23661] : {S}{*2}Christ, he's choking!
3233.48s-[DART][LOC][23692] : {S}{*1}What are you doing? Hold your position!
3238.52s-[DART][LOC][23696] : {S}{*1}Get her! Now!
3240.94s-[DART][LOC][197] : {S}{*1}Aiden, theyre coming! Keep them off me!!!
3250.66s-[DART][LOC][207] : {S}{*1}The door, Aiden! I can't get in! Open the door!
3279.65s-[DART][LOC][198] : {S}{*1}They're getting closer. You've gotta help me!
3317.58s-[DART][LOC][231] : {S}{*2}Tell them to leave me the fuck alone, because next time,
3322.19s-[DART][LOC][231] : {S}{*3}I'll kill everyone.
3329.11s-[DART][LOC][231] : {S}{*4}Come on, Aiden.
3331.02s-[DART][LOC][231] : {S}{*5}I think they get the message.
## Post #27
- Username: mirh
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-05-14T18:00:39+00:00
- Post Title: Re: [PS3] Beyond: Two Souls -Extractor- + Beginnings of pars

Here's something pretty cool, made a basic parser for the variables in the SINT_SEC attribute:
## Post #28
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2014-05-18T15:00:27+00:00
- Post Title: Re: [PS3] Beyond: Two Souls -Extractor- + Beginnings of pars

Thank you very much for all the progress on this! 
I'm sure it's utterly hard to do this >< But really thanks!
## Post #29
- Username: Hamers
- Rank: beginner
- Number of posts: 21
- Joined date: Fri Jul 22, 2011 11:39 pm
- Post datetime: 2014-05-20T21:04:55+00:00
- Post Title: Re: [PS3] Beyond: Two Souls -Extractor- + Beginnings of pars

OMG, this is absolutely fantastic. Thank you SO much for your hard work   I'm a very big fan of both Heavy Rain and Beyond and currently look for glitches to speedrun the game. So this will come in very handy, especially to satisfy my general curiosity about how the game and their engine works. Taking a look at the lua files will take up my time for sure 

THANKS!!!
## Post #30
- Username: mirh
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-05-20T21:10:13+00:00
- Post Title: Re: [PS3] Beyond: Two Souls -Extractor- + Beginnings of pars

> Reply from Hamers
>
> OMG, this is absolutely fantastic. Thank you SO much for your hard work   I'm a very big fan of both Heavy Rain and Beyond and currently look for glitches to speedrun the game. So this will come in very handy, especially to satisfy my general curiosity about how the game and their engine works. Taking a look at the lua files will take up my time for sure 

THANKS!!!
Thanks!

If you by any chance get a decompiler working on the precompiled ones, let me know... 



Big Update!

So I decided to start from the beginning, and see how the game links the files together.

So it starts with file 0x0 of course. It's defined in its own content group with only 1 entry in it. It's labeled as "LOADING_ZONE".

0x0 redirects us to 0x151.
This entry is a data container, and contains the complete storyboard of Beyond.

The DC_INFO section defines the ID's to the content in the DC_DATA section.
The DC_DATA section consists of a LOT of LOADING_ZONES, which link to other files.

Then there's the "STORYBOARD" attribute, which gives paramaters, like the name, trophy database, and some more variables to the scene, and then the scene
defines its scene elements. The scene elements on their turn define which earlier LOADING_ZONE links to that element (remember that each loading zone has its own linked entry).

When going to the entry in the loading zone of that scene element I can clearly see that it matches with the name of the scene.

This entry is the main "init" script of that scene, and based on the complexity of the scene this file defines its own LOADING_ZONE's, SCENE's, AREA's, etc.

These LOADING_ZONES can consist of multiple things. If the scene has multiple "jobs" / sequences these link to the other communicators containing the necessary scripts, animation data, audio data (linked), etc. If it's a simple scene, let's say the Prologue, the main entry (as linked by the storyboard) links to one other file, containing the dialog, links to the models (which also include the textures), audio and more. Perfectly matches! 


Here's a demo of this system: https://www.youtube.com/watch?v=z74J_icVS7I.

Another update: I just made the parser much better, I can now just fill in any scene name, it will go through -all- linked entries (which are A LOT), and will play the music as it finds it.
I've found all music that matches to all scenes already
## Post #31
- Username: Hamers
- Rank: beginner
- Number of posts: 21
- Joined date: Fri Jul 22, 2011 11:39 pm
- Post datetime: 2014-05-20T21:30:50+00:00
- Post Title: Re: [PS3] Beyond: Two Souls -Extractor- + Beginnings of pars

This is so awesome and completely made my day. Pretty much exactly what I needed. I never thought I would see the day of this happening haha
I've got some experience in C++, Java and VB actually and would love to help, but I absolutely suck at everything related to file structures. I've studied the uncompiled lua file as well and extracted some concept art using a file inspector, but not much beyond that. If you need support with anything I might be able to do feel free to ask (testing for example).

Take all the time you need. Just don't disappear from the face of the earth before releasing the individual file extractor  
In case I get the lua files decompiled I will let you know immediately ^^ 

Like some never included gameplay features (Aiden being called Amael and being able to drain energy from plankton and people's emotions according to some lua variables?) Beyond also has some deleted chapters I'm pretty sure you can find some leftovers in the files. Curious learning about them as well. Only know the codenames from concept art that may or may not be accurate. Chapters that apparently got the axe: First Steps, Opening Credits, The Senator, New Agent, Shaman. Also an unreleased chapter that may be set in France and/or Kuala Lumpur.

Will definitely use your tool to try to find something out about them
## Post #32
- Username: Hamers
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-05-20T22:16:18+00:00
- Post Title: Re: [PS3] Beyond: Two Souls -Extractor- + Beginnings of pars

> Reply from Hamers
>
> This is so awesome and completely made my day. Pretty much exactly what I needed. I never thought I would see the day of this happening haha
I've got some experience in C++, Java and VB actually and would love to help, but I absolutely suck at everything related to file structures. I've studied the uncompiled lua file as well and extracted some concept art using a file inspector, but not much beyond that. If you need support with anything I might be able to do feel free to ask (testing for example).

Take all the time you need. Just don't disappear from the face of the earth before releasing the individual file extractor  
In case I get the lua files decompiled I will let you know immediately ^^ 

Like some never included gameplay features (Aiden being called Amael and being able to drain energy from plankton and people's emotions according to some lua variables?) Beyond also has some deleted chapters I'm pretty sure you can find some leftovers in the files. Curious learning about them as well. Only know the codenames from concept art that may or may not be accurate. Chapters that apparently got the axe: First Steps, Opening Credits, The Senator, New Agent, Shaman. Also an unreleased chapter that may be set in France and/or Kuala Lumpur.

Will definitely use your tool to try to find something out about them
Haha, thanks again!

Yeah, trying to load First Steps will crash the game. I tried, lol.
There might be some leftovers of The Senator, as I did see that being mentioned deeper in the game's structure. As for other unused things.... I already found a few, somewhat unsettling, pieces of unused audio dialog that were intended for a scene at The Bar (Like Other Girls), and I recently found this....



And, well... yeah.



And I've also found some epic unused music intended for a (unused??) scene in Hunted, will try to get that up soon.
## Post #33
- Username: Hamers
- Rank: beginner
- Number of posts: 21
- Joined date: Fri Jul 22, 2011 11:39 pm
- Post datetime: 2014-05-21T00:17:23+00:00
- Post Title: Re: [PS3] Beyond: Two Souls -Extractor- + Beginnings of pars

Yeah I have seen your entry on The Cutting Room Floor (that was my first WTF where is this suddenly coming from moment). Pretty messed up, especially the subtitles you just showed. Seems like you were originally supposed to take control over Aiden in that scene and make the choice of interrupting or just watching, which is pretty crazy. Would have made the revenge scene a lot more intense, but hearing the dialogue alone makes me uncomfortable already. They likely wanted to avoid a huge controversy, especially since not even movies go that far most of the time. Not to mention the rating boards, so they probably made the right call in the end.

The changed dialogue in general is pretty interesting as well. I watched your videos on YT and the prologue dialogue you played is almost completely different from the one that's actually used in the game. Much longer too.

Too bad you can't load First Steps. Apparently you play Jodie as a baby in that scene. Sounds pretty interesting, but considering that's a lot different from the main game scripting wise I'm not surprised it crashes. Interesting that you actually found something on Senator.

The Hunted music has a high chance of being the leftover music from the Beta. Hunted was the first scene they build and showed at E3 2012, so they included some early music that wasn't composed by the actual composer. The scene is probably still in there considering you found the "Broken" chapter as well from E3 2012 featuring the uncut scene of the cop talking to Jodie.

FunnyML (I think he is registered here as well) managed to extract all of the music before (but only in small unnamed chunks) and went through the effort of putting everything together again. He released the entire album over at FFShrine and I uploaded some of the Beta music to my channel. So maybe you are referring to one of these tracks?

[https://www.youtube.com/watch?v=nSizbVG1S0o](https://www.youtube.com/watch?v=nSizbVG1S0o)
[https://www.youtube.com/watch?v=CKEh2yOAwlk](https://www.youtube.com/watch?v=CKEh2yOAwlk)

If not, then it would be pretty interesting if you found even more music
## Post #34
- Username: mirh
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-05-21T07:31:50+00:00
- Post Title: Re: [PS3] Beyond: Two Souls -Extractor- + Beginnings of pars

> Reply from Hamers
>
> Yeah I have seen your entry on The Cutting Room Floor (that was my first WTF where is this suddenly coming from moment). Pretty messed up, especially the subtitles you just showed. Seems like you were originally supposed to take control over Aiden in that scene and make the choice of interrupting or just watching, which is pretty crazy. Would have made the revenge scene a lot more intense, but hearing the dialogue alone makes me uncomfortable already. They likely wanted to avoid a huge controversy, especially since not even movies go that far most of the time. Not to mention the rating boards, so they probably made the right call in the end.

The changed dialogue in general is pretty interesting as well. I watched your videos on YT and the prologue dialogue you played is almost completely different from the one that's actually used in the game. Much longer too.

Too bad you can't load First Steps. Apparently you play Jodie as a baby in that scene. Sounds pretty interesting, but considering that's a lot different from the main game scripting wise I'm not surprised it crashes. Interesting that you actually found something on Senator.

The Hunted music has a high chance of being the leftover music from the Beta. Hunted was the first scene they build and showed at E3 2012, so they included some early music that wasn't composed by the actual composer. The scene is probably still in there considering you found the "Broken" chapter as well from E3 2012 featuring the uncut scene of the cop talking to Jodie.

FunnyML (I think he is registered here as well) managed to extract all of the music before (but only in small unnamed chunks) and went through the effort of putting everything together again. He released the entire album over at FFShrine and I uploaded some of the Beta music to my channel. So maybe you are referring to one of these tracks?

https://www.youtube.com/watch?v=nSizbVG1S0o
https://www.youtube.com/watch?v=CKEh2yOAwlk

If not, then it would be pretty interesting if you found even more music

Small unnamed chunks... that's correct, the music is formatted like this:

uint: channel amount (always 3?)

uint: channel 1 chunk size
uint: channel 2 chunk size
uint: channel 3 chunk size

< channel 1 chunk >
< channel 2 chunk >
< channel 3 chunk >

Then relative alignment to 0x800  and then another block of these chunks.
This goes on until the end of the PARTITIO attribute.

You've probably already seen it, but I did already release a (poorly made lol) file extractor that also exports the audio to .mp3.

Anyways here is one fucking epic (unused) track, which I can't remember of where it came from:
http://www.djek.nl/shit/beyond/EB89.mp3

Then there's the chapter 1803 Hunted Bike... In the game the bike part is called 1802B Hunted Barricade. Then 1804 is Hunted Town... so I'm thinking Hunted Bike is
completely unused! EDIT: actually I don't think the -whole- chapter is unused :A that audio is though!

Here's some audio from it:

http://www.djek.nl/shit/beyond/1BBE.mp3 (love this track)
http://www.djek.nl/shit/beyond/1953.mp3
## Post #35
- Username: mono24
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-05-21T08:27:01+00:00
- Post Title: Re: [PS3] Beyond: Two Souls -Extractor- + Beginnings of pars

Here's a better demo video! 

http://youtu.be/D59SAbFSIoU
## Post #36
- Username: Hamers
- Rank: beginner
- Number of posts: 21
- Joined date: Fri Jul 22, 2011 11:39 pm
- Post datetime: 2014-05-21T14:21:14+00:00
- Post Title: Re: [PS3] Beyond: Two Souls -Extractor- + Beginnings of pars

> Reply from HugoPeters
>
> Small unnamed chunks... that's correct, the music is formatted like this:

uint: channel amount (always 3?)

uint: channel 1 chunk size
uint: channel 2 chunk size
uint: channel 3 chunk size

< channel 1 chunk >
< channel 2 chunk >
< channel 3 chunk >

Then relative alignment to 0x800  and then another block of these chunks.
This goes on until the end of the PARTITIO attribute.

You've probably already seen it, but I did already release a (poorly made lol) file extractor that also exports the audio to .mp3.

Anyways here is one fucking epic (unused) track, which I can't remember of where it came from:
http://www.djek.nl/shit/beyond/EB89.mp3

Then there's the chapter 1803 Hunted Bike... In the game the bike part is called 1802B Hunted Barricade. Then 1804 is Hunted Town... so I'm thinking Hunted Bike is
completely unused! EDIT: actually I don't think the -whole- chapter is unused :A that audio is though!

Here's some audio from it:

http://www.djek.nl/shit/beyond/1BBE.mp3 (love this track)
http://www.djek.nl/shit/beyond/1953.mp3
I think the EB89 one is actually used in Dragon's Hideout near the end if you wait too long or something. I certainly remember it. But the other two are completely new to me and weren't included in FunnyML's release ([http://forums.ffshrine.org/f72/2013-|-l ... nd-164892/](http://forums.ffshrine.org/f72/2013-%7C-lorne-balfe-va-%7C-beyond-164892/)). They might also be from the Beta version of the Bike scene though. I'm not sure as I don't have CFW installed, but I think 1802B Hunted Barricade is the part where you have to steal the bike while 1803 Hunted Bike is the actual bike part. They definitely load another scene after you escaped the forest and then again after you take off with the bike, so that would make sense.


> Reply from HugoPeters
>
> Here's a better demo video! 

http://youtu.be/D59SAbFSIoU
Really great work with the storyboard parsing. I assume this means you could at some point extract all the assets and scripts used by a chapter, which would be really helpful considering the game has so many assets apparently all over the place. To find something specific it certainly is a lot easier to just search in the related chapter instead of the entire game.
## Post #37
- Username: JayK
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-05-27T10:21:09+00:00
- Post Title: Re: [PS3] Beyond: Two Souls -Extractor- + Beginnings of pars

Alright, EPIC UPDATE

JayK helped me with decompiling the Luac scripts, and guess what, perfect match!



So the music we get is: [http://www.djek.nl/shit/beyond/MusicMenu_1653D.mp3](http://www.djek.nl/shit/beyond/MusicMenu_1653D.mp3)!!!


hehe.

I've been trying to get Mogre to work, and finally I'm getting some results. I remade the loading / splash screen of Beyond!

Code for making the splashscreen appear:


And to make it fade-in / out:

(if there's a better way of doing that, please let me know!)

Result:


Thought I'd brag about that a little bit
## Post #38
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2014-05-27T20:03:05+00:00
- Post Title: Re: [PS3] Beyond: Two Souls -Extractor- + Beginnings of pars

Great work, is Mogre any good?
## Post #39
- Username: mono24
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-05-27T20:31:51+00:00
- Post Title: Re: [PS3] Beyond: Two Souls -Extractor- + Beginnings of pars

> Reply from JayK
>
> Great work, is Mogre any good?
I'm liking it thusfar (though getting it to work was a pain)! Getting framerates of around 6000 while just having the splash screen fading in/out on a GTX 770, so pretty good!
I've only done a splash screen so far, the code behind it first didn't make a lot of sense but while making it I began to understand how Mogre / Ogre works, and I like it! But for real 3D stuff I can't really share a solid opinion yet as I haven't done anything of that kind yet.
## Post #40
- Username: mono24
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-05-27T20:37:07+00:00
- Post Title: Re: [PS3] Beyond: Two Souls -Extractor- + Beginnings of pars

Check it out, unused loading screen audio!
[http://www.djek.nl/shit/beyond/LoadingScreenAudio.mp3](http://www.djek.nl/shit/beyond/LoadingScreenAudio.mp3)
## Post #41
- Username: Hamers
- Rank: beginner
- Number of posts: 21
- Joined date: Fri Jul 22, 2011 11:39 pm
- Post datetime: 2014-05-28T09:57:47+00:00
- Post Title: Re: [PS3] Beyond: Two Souls -Extractor- + Beginnings of pars

Great fucking work! Glad someone else is interested in the LUA scripts
## Post #42
- Username: mirh
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-05-28T10:55:13+00:00
- Post Title: Re: [PS3] Beyond: Two Souls -Extractor- + Beginnings of pars

> Reply from Hamers
>
> Great fucking work! Glad someone else is interested in the LUA scripts
Well, to be honest, my goal is to get them to actually execute on my PC.

The files JayK sent me before contained a lot of function "outputs" and were to source to finding the Communicators and their ID's.
Now, in the decrypted main executable, I can see the templates of these functions and that they're just strings where the Communicator names and ID's are filled in to. Because I already generated a complete enum of the Communicators I can easily remake the generation of these functions.

An example:

function QDT.GAME_MANAGER.GetType() return 4222 end (not sure if this is valid Lua, not on my PC right now :A)

That's the simplest function, there's also {Communicator}.NewPlaced, {Communicator}.NewPlacedCtx, {Communicator}.New, etc.

I use DynamicLua to use Lua in C#, and it's pretty dope.

To initialize this "dynamic database", I loop through the whole Communicator enum, getting the name and the ID of that Communicator.
Then I generate the functions as strings in a string array, just like the main executable seems to do.
After that I loop through the string array, executing them on the Lua instance.

It's really neat, to define a function I just have to do something like IW.Lua("function QDT.GAME_MANAGER.GetType() return 4222 end"); (IW being my main "glue" of all settings, sub-classes, etc.), and IW.Lua being the DynamicLua instance.

After that I just do this: IW.Lua.QDT.GAME_MANAGER.GetType()! Because it's generated on runtime I can use it like a native method 
To get a correct output is a bit different though (not 100% sure, but it works).
To make it display on a message box I do: MessageBox.Show(IW.Lua("return QDT.GAME_MANAGER.GetType()").ToString());.
Still, that's pretty fucking neat 

So once I have all of Beyond's kernel functions figured out I can call the Game Manager (which is a huge uncompiled Lua script which takes care of all game-related variables, a ton of game-related functions and also the functions which start the storyboard).

Beyond isn't actually that complicated, the whole system is pretty minimalistic, but there are two things that still twist my mind:

Why are the names of the Communicator attributes-"attributes" (the ones you see in the data containers, like COM_CONT, MESHDATA, PARTITIO, LOADCONT, etc.) still present? Isn't it much more efficient to just have a uint of the type of the attribute?? What's the advantage of having these strings still in there? Using uints would save a huge space considering all of these attribute names are 0x8 in size, every data container has a lot of 'em, and there are more than 30000 data containers!
The way the DC_DATA section is formatted makes no sense, there are no offsets, just sizes before each Communicator attribute (so not the attribute-attributes like COM_CONT, but the blocks that contain them). I'm suspecting these tables are Lua tables of some kind. That would make sense, as Lua tables can contain their own functions, and a lot of these data containers have compiled scripts in them. Then still, the only way of parsing these DC_DATA tables is to go through each and every attribute and either skip the size of them to go to the next one or parse the whole thing, which would take up too much memory for a PS3 I think, however, the bigger data containers that contain textures have a "head" and "tail", the head being one segs archive containing the DC_INFO and DC_DATA section, and the the tail being the (compressed) texture.
## Post #43
- Username: Hamers
- Rank: beginner
- Number of posts: 21
- Joined date: Fri Jul 22, 2011 11:39 pm
- Post datetime: 2014-05-28T12:12:05+00:00
- Post Title: Re: [PS3] Beyond: Two Souls -Extractor- + Beginnings of pars

Whoa. So you could potentially directly (or at least partially) send commands to the game engine while running and call functions? That would be incredible
## Post #44
- Username: mirh
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-05-28T12:19:16+00:00
- Post Title: Re: [PS3] Beyond: Two Souls -Extractor- + Beginnings of pars

> Reply from Hamers
>
> Whoa. So you could potentially directly (or at least partially) send commands to the game engine while running and call functions? That would be incredible

What I'm doing now is basically tying to remake Beyond's engine, but sending commands to the PS3's engine would be possible, yeah.
How that would work:

First, figure out a script that we want to put our own things in.

Then to patch it:
1. If compressed, decompress the data container
2. Decompile the function
3. Add our own stuff
4. Recompile it
5. Write it to the data container, modifiying sizes and such (not sure if there's any CRC's, but eventually recalculate those)
6. If it was compressed, recompress it
7. Write it to the game's files
8. Update the defined size in the SDAT file (decrypt first and eventually modify the ExSize if that entry has stuff like textures the re-encrypt) 

This is pretty limited though I'm afraid, as the functionality depends on how much Lua can do, but sure we could use the native functions of the engine.

Though I'm more interested in remaking the engine
## Post #45
- Username: Hamers
- Rank: beginner
- Number of posts: 21
- Joined date: Fri Jul 22, 2011 11:39 pm
- Post datetime: 2014-05-28T12:58:49+00:00
- Post Title: Re: [PS3] Beyond: Two Souls -Extractor- + Beginnings of pars

Well that would be the best thing ever probably. But how? I mean the renderer is obviously pretty advanced and custom tailored to the SPUs right? How would you make that running on PC? Or do you plan to write an emulator specifically for Beyond
## Post #46
- Username: mono24
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-05-28T18:20:43+00:00
- Post Title: Re: [PS3] Beyond: Two Souls - Extractor | Reversing | Portin

> Reply from Hamers
>
> Well that would be the best thing ever probably. But how? I mean the renderer is obviously pretty advanced and custom tailored to the SPUs right? How would you make that running on PC? Or do you plan to write an emulator specifically for Beyond
I'm not going to use their renderer, I'm only using the main executable as reference (the disassembled output is very useful).
If I can remake the way the game parses content I can make a new renderer using Mogre.
## Post #47
- Username: mirh
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-05-28T20:39:13+00:00
- Post Title: Re: [PS3] Beyond: Two Souls - Extractor | Reversing | Portin

Update! Been looking into Lua, and been porting / understanding Beyond's kernel code, and I can almost safely say the communicators are just Lua metatables of the inidivudal communicator tables. These tables have their own functions, variables, etc. Those functions look like they're just wrappers of C++ engine/kernel level methods.

Aaaanyhooow, here's some ported shit:



In the region "game manager test" is around the first 400 lines of the actual Game Manager, using that as temp until I build the parser.

Here's the debug output...



Not that much to see, but everything works just as expected and seems to work exactly like the game's (decompiled) source does.
## Post #48
- Username: Hamers
- Rank: beginner
- Number of posts: 21
- Joined date: Fri Jul 22, 2011 11:39 pm
- Post datetime: 2014-05-28T22:33:29+00:00
- Post Title: Re: [PS3] Beyond: Two Souls - Extractor | Reversing | Portin

> Reply from HugoPeters
>
> Hamers wrote:Well that would be the best thing ever probably. But how? I mean the renderer is obviously pretty advanced and custom tailored to the SPUs right? How would you make that running on PC? Or do you plan to write an emulator specifically for Beyond  
I'm not going to use their renderer, I'm only using the main executable as reference (the disassembled output is very useful).
If I can remake the way the game parses content I can make a new renderer using Mogre.
Wow  Well, if you can really do this, that probably would be indeed the best thing ever. Good luck
## Post #49
- Username: lion589
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-06-07T11:33:22+00:00
- Post Title: Re: [PS3] Beyond: Two Souls - Extractor | Reversing | Portin

Coming Soon... a brand new tool for viewing Beyond's files. Much more user friendly and intuitive.

I decided to do a complete rewrite as I know so much more now that I can make a much, much better and more stable core, a richer feature set and of course that more intuitive and user friendly layout.

To give a small example of the improved core: the total amount of lines used for reading the IDM files (encrypted to SDAT) used to be 273 in InfraTool.
In this new tool, there are just 50 lines spend on that!
That's a reducement of 82%!

Here's a screenshot from the debugger of a tiny part of the parser that doesn't really say anything at all but does kinda give a little clue of how I want to "order" the files in this new tool.




And yeah, of course I made a logo.
## Post #50
- Username: lion589
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2014-06-09T09:57:17+00:00
- Post Title: Re: [PS3] Beyond: Two Souls - Extractor | Reversing | Portin

Looking good.
## Post #51
- Username: mirh
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-06-22T22:55:54+00:00
- Post Title: Re: [PS3] Beyond: Two Souls - Extractor | Reversing | Portin

PLOT TWIST #1.

=====> http://youtu.be/aVO_eiPiRuY

I have (partially) reversed the sequence / movie timeline format, demo at around 2/5 of the video.

And also: new tool is pretty neat.
## Post #52
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2014-06-23T06:34:57+00:00
- Post Title: Re: [PS3] Beyond: Two Souls - Extractor | Reversing | Portin

Glad to see an update from you, the progress you've made on your tool is really amazing, it looks very well constructed. Keep it up and good luck.
## Post #53
- Username: mirh
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-06-23T08:59:02+00:00
- Post Title: Re: [PS3] Beyond: Two Souls - Extractor | Reversing | Portin

> Reply from JayK
>
> Glad to see an update from you, the progress you've made on your tool is really amazing, it looks very well constructed. Keep it up and good luck.
Thanks. The "movies" in Beyond are basically cutscenes like the Prologue, but are also the things that contain choices, button-press-events, etc. As you can see in the video, I can get the the Prologue's audio to play together with all dialog. It's all separate pieces of dialog, with time indices into the dialog audio. I also found the indices of the subtitles (which is an array of start - end floats) and the localization text gives indices into these floats, so not everything is used.
I can also already parse the camera shots, so I know what camera shot starts when and what properties it has (thanks QD for leaving the property names in there  ).
If we can get the textures out, it should be just a matter of time before we can get whole sequences and parts of the game to play.

If anyone knows anything about JPEG / DXT / DDS / compression, please check out: viewtopic.php?f=21&t=11607
## Post #54
- Username: mono24
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-06-25T16:49:55+00:00
- Post Title: Re: [PS3] Beyond: Two Souls - Extractor | Reversing | Portin

-
        -
           -
Just in before the weekly update, this should clear things up (or not)
      -
        -
           -

edit: you may have noticed the audio is a bit off and the dialog is a bit choppy, this has been corrected now.
## Post #55
- Username: mirh
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-06-27T08:57:24+00:00
- Post Title: Re: [PS3] Beyond: Two Souls - Extractor | Reversing | Portin

Spoilers!!!
See here, what's possible right now: https://www.youtube.com/watch?v=4ikhbv4xkGk
Dialog is still off here and there, will try to fix today. Also the loop points are incorrect so is the volume of some parts.
## Post #56
- Username: mirh
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-07-01T11:04:53+00:00
- Post Title: Re: [PS3] Beyond: Two Souls - Extractor | Reversing | Portin

Here's a nice extended demo video of the parsed timeline: https://www.youtube.com/watch?v=tW9b_UE9Pd4

chrrox and I are working on models as we speak, and I can confirm it's exactly as how I would expect them to do it.

<catalog>
skeleton
_____particles
_____nodes
_____mesh table
__________<link to compressed mesh files>
__________meshdata
_______________shaders
____________________textures
_______________edge data

So catalogs only have one skeleton which links to meshes, etc. All models have 1 skeleton only so it serves as the root entity (thanks debug strings ). Area's have more then one skeleton (for all static objects) so the dev would have to specify the root entity (again, thanks debug strings!)

Soon more?  But no textures unless we manage to figure out the texture format/compression. Anyone who knows PPC/elf assembly?
## Post #57
- Username: RunaWhite
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-07-02T18:00:02+00:00
- Post Title: Re: [PS3] Beyond: Two Souls - Extractor | Reversing | Portin

PLOT TWIST #2

Surprise.
## Post #58
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2014-07-02T23:32:29+00:00
- Post Title: Re: [PS3] Beyond: Two Souls - Extractor | Reversing | Portin

OMG so are the models possible?? This is awesome. I hope it'll be possible to get them also with bones and weights... and that it's going to be the same format as Heavy Rain (so I read). I've been waiting for those models for ages.

Thank you very much for all the hard work you guys do on this stuff!
## Post #59
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2014-07-04T09:51:32+00:00
- Post Title: Re: [PS3] Beyond: Two Souls - Extractor | Reversing | Portin

Wow thanks so much for all the work on this  This is amazing ;_;
## Post #60
- Username: RunaWhite
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-07-06T11:26:47+00:00
- Post Title: Re: [PS3] Beyond: Two Souls - Extractor | Reversing | Portin

Models Update!

Big thanks to chrrox and howfie for helping me getting this working!!

I ported chrrox's PSA edge index decompression over to C#, and when I finally got my hand on a working bitreader and getting the normals correct (really big thanks to chrrox and howfie for that!) I succeeded in getting the models to show up!

I will be using Mogre as my graphics rendering engine (and it's fucking awesome).

 
 
(the arm missing is because there's cloth physics there)





And here's a glimpse into the future...
## Post #61
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2014-07-06T16:37:29+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (UPDATE: Models 

Question about Jodie's hair: is the mesh totally missing because of the physics? Other games still have a static mesh in that case, but I suppose that depends on the way a game was made...
## Post #62
- Username: mirh
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-07-06T17:27:25+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (UPDATE: Models 

> Reply from RunaWhite
>
> Question about Jodie's hair: is the mesh totally missing because of the physics? Other games still have a static mesh in that case, but I suppose that depends on the way a game was made...
The hair (and dynamic clothes) is done through nodes, which I'm working on now. Those nodes have Havok physics data and a set of geometry data.
## Post #63
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2014-07-06T22:13:21+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (UPDATE: Models 

Thank you for your answer! Keep up the great work ^_^
## Post #64
- Username: lion589
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-07-11T16:07:20+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (UPDATE: Models 

Update on the skeleton:


And some nice LOD meshes:
## Post #65
- Username: zubren
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Apr 07, 2013 2:25 pm
- Post datetime: 2014-07-15T10:37:59+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (UPDATE: Models 

Dude, this is fucking sweet. Keep it up!
## Post #66
- Username: zubren
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-07-15T16:39:27+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (UPDATE: Models 

Something fun in between:

Here's the chapter select image for the removed "First Steps" scene:
## Post #67
- Username: mono24
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-07-18T12:17:10+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (UPDATE: Models 

I'm very proud to announce I passed my finals exams! This means I will be moving to Breda (The Netherlands) and will start a bachelor on Indie Game Development!

Fun fact: did you know that in the time I was supposed to prepare for my finals I did most of the work on reversing Beyond? This lead to the fact that I didn't... quite... prepare well for the finals...
But I'm so fucking happy right now!
## Post #68
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2014-07-19T08:47:37+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (UPDATE: Models 

Congrats Hugo! ^_^
## Post #69
- Username: Hamers
- Rank: beginner
- Number of posts: 21
- Joined date: Fri Jul 22, 2011 11:39 pm
- Post datetime: 2014-07-19T18:42:53+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (UPDATE: Models 

Congrats dude!!! I was on vacation, so I couldn't check this thread in a while. Seems like you made some amazing progress
## Post #70
- Username: Hamers
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-07-19T18:52:05+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (UPDATE: Models 

> Reply from Hamers
>
> Congrats dude!!! I was on vacation, so I couldn't check this thread in a while. Seems like you made some amazing progress
Glad to see you're back! You're gonna love this: [https://www.youtube.com/watch?v=tW9b_UE9Pd4](https://www.youtube.com/watch?v=tW9b_UE9Pd4)
## Post #71
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2014-07-20T02:07:14+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (UPDATE: Models 

> Reply from HugoPeters
>
> I'm very proud to announce I passed my finals exams! This means I will be moving to Breda (The Netherlands) and will start a bachelor on Indie Game Development!

Fun fact: did you know that in the time I was supposed to prepare for my finals I did most of the work on reversing Beyond? This lead to the fact that I didn't... quite... prepare well for the finals...
But I'm so fucking happy right now!

Congratulations! 

good luck with your projects!
## Post #72
- Username: lion589
- Rank: beginner
- Number of posts: 26
- Joined date: Thu Oct 13, 2011 12:48 am
- Post datetime: 2014-07-20T13:14:15+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (UPDATE: Models 

> Reply from HugoPeters
>
> I'm very proud to announce I passed my finals exams! This means I will be moving to Breda (The Netherlands) and will start a bachelor on Indie Game Development!

Fun fact: did you know that in the time I was supposed to prepare for my finals I did most of the work on reversing Beyond? This lead to the fact that I didn't... quite... prepare well for the finals...
But I'm so fucking happy right now!

Congratulations, btw Would your tool work on Heavy Rain?
## Post #73
- Username: Hamers
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-07-20T13:17:14+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (UPDATE: Models 

> Reply from lion589
>
> HugoPeters wrote:I'm very proud to announce I passed my finals exams! This means I will be moving to Breda (The Netherlands) and will start a bachelor on Indie Game Development!

Fun fact: did you know that in the time I was supposed to prepare for my finals I did most of the work on reversing Beyond? This lead to the fact that I didn't... quite... prepare well for the finals...
But I'm so fucking happy right now!

Congratulations, btw Would your tool work on Heavy Rain?
I haven't looked at Heavy Rain yet, but I know the base is the same, however, the actual data is probably very different at many points, because the new features Beyond uses.
Once I played Heavy Rain, and I got more free time, I will try to make it compatible with Heavy Rain as well (which is probably much easier than Beyond...)
## Post #74
- Username: mono24
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2014-07-20T13:38:15+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (UPDATE: Models 

Hi Hugo,

What exactly is your goal in here mate ? Are you actually want to make it work and render on PC ? Include controller functionality ?
## Post #75
- Username: mirh
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-07-20T13:43:48+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (UPDATE: Models 

> Reply from michalss
>
> Hi Hugo,

What exactly is your goal in here mate ? Are you actually want to make it work and render on PC ? Include controller functionality ?
Well, I haven't set an exact goal, but I am trying to make it work on PC, yes.
As long as I don't get 100% stuck with something I'm just going to keep on reversing it and making it work on PC!

Note that Quantic Dream has been using this format since Fahrenheit, and they're probably not going to give up on it, so with a bit of luck all of their future games are going
to be playable on PC at some point!
## Post #76
- Username: Hamers
- Rank: beginner
- Number of posts: 21
- Joined date: Fri Jul 22, 2011 11:39 pm
- Post datetime: 2014-07-20T15:18:31+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (UPDATE: Models

> Reply from HugoPeters
>
> Hamers wrote:Congrats dude!!! I was on vacation, so I couldn't check this thread in a while. Seems like you made some amazing progress 
Glad to see you're back! You're gonna love this: https://www.youtube.com/watch?v=tW9b_UE9Pd4
Wow, that's utterly amazing that you can "hear" the entire scene like that already. I especially love all the additional info you already get like animation names, camera shots and effects synchronized to the scene, controller vibration and some script stuff like when to pre-load the next scene, change time of day etc.

Keep up the great work!
## Post #77
- Username: mono24
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-07-20T15:34:04+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (UPDATE: Models

> Reply from Hamers
>
> HugoPeters wrote:Hamers wrote:Congrats dude!!! I was on vacation, so I couldn't check this thread in a while. Seems like you made some amazing progress 
Glad to see you're back! You're gonna love this: https://www.youtube.com/watch?v=tW9b_UE9Pd4
Wow, that's utterly amazing that you can "hear" the entire scene like that already. I especially love all the additional info you already get like animation names, camera shots and effects synchronized to the scene, controller vibration and some script stuff like when to pre-load the next scene, change time of day etc.

Keep up the great work!
Thanks, yeah it's really neat! You have no idea how hard it was to get subtitles working though! XD
Anyways, got something really cool coming up!
## Post #78
- Username: Hamers
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-07-20T21:09:56+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (UPDATE: Models

Update!

Alrighty, finally gotten around to take a look at the camera keyframe system, figured it out, and implemented it! Yay for camera keyframe animation!

[https://www.youtube.com/watch?v=NKManMXr-M4](https://www.youtube.com/watch?v=NKManMXr-M4)
## Post #79
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2014-07-24T19:51:02+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (UPDATE: Models

This is one of the best projects i've seen on Xentax, keep it up.
## Post #80
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-07-25T05:45:19+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (UPDATE: Models

Wow shit thats cool great work PC port coming soon
## Post #81
- Username: RunaWhite
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-07-26T22:04:13+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (UPDATE: Models

Update!

Alright, I'm now on vacation in Austria, but still going on Beyond!
So here's some early progress on area's!
## Post #82
- Username: Hamers
- Rank: beginner
- Number of posts: 21
- Joined date: Fri Jul 22, 2011 11:39 pm
- Post datetime: 2014-07-27T03:24:31+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (UPDATE: Models

Holy shit you actually did it. That's extremely impressive. So I guess soon you will be able to replay the Broken chapter with full audio, the rough environment, static character models (?) and the cutscene camera all linked together using the timeline. Even without any characters at all this would be a pretty huge milestone, to actually see the rough scene in front of you and the camera moving through like it does in the final game
## Post #83
- Username: Hamers
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-07-28T14:07:24+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (UPDATE: Models

> Reply from Hamers
>
> Holy shit you actually did it. That's extremely impressive. So I guess soon you will be able to replay the Broken chapter with full audio, the rough environment, static character models (?) and the cutscene camera all linked together using the timeline. Even without any characters at all this would be a pretty huge milestone, to actually see the rough scene in front of you and the camera moving through like it does in the final game
TADAAAAA

Here it is! [https://www.youtube.com/watch?v=Zfe22G5cxXI](https://www.youtube.com/watch?v=Zfe22G5cxXI)
EDIT: here's a better one: [https://www.youtube.com/watch?v=HM9AqzbBhOg](https://www.youtube.com/watch?v=HM9AqzbBhOg)

So this is what they call a milestone?

What you see in the video is my program, loading in 2 areas (the "road" part isn't supported yet, sorry!),  and then 8 "movies" (timeline things), which are then played after each other.

Everything you see and hear is coming from my program, no edits whatsoever.

THINGS TO NOTE:
+ It's very rough. No textures, no game defined lights, etc. Also, sorry for the z-buffer clipping spasts, not sure what's going on with that.
+ The camera is still a bit off
+ No correct measurement when a timeline has finished (especially visible in the "I know... They're coming." part).
+ Etc.

I'm going to experiment with Lua, and will probably end up doing another full rewrite, this time with the Lua engine implemented.
## Post #84
- Username: mono24
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2014-07-28T14:13:48+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (UPDATE: Models

impressive work Hugo, i hope you gonna finnish it
## Post #85
- Username: lion589
- Rank: beginner
- Number of posts: 26
- Joined date: Thu Oct 13, 2011 12:48 am
- Post datetime: 2014-07-29T13:38:46+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (UPDATE: Models

That was impressive work you've done.
## Post #86
- Username: Hamers
- Rank: beginner
- Number of posts: 21
- Joined date: Fri Jul 22, 2011 11:39 pm
- Post datetime: 2014-07-29T23:48:42+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (UPDATE: Models

That is indeed a milestone. Congratz    I figure animated objects are handled quite a bit differently compared to the static scene (lack of door, chair and cup)? Also I noticed that at 0:45-0:50 your camera is missing a shot (maybe it's tied to the character?)  

Also what do you think about the street car scene? Is it on the same map as the police station or swapped in and out with the loading happening in the background? It also wouldn't surprise me if the street is very short and they just loop the one segment over and over again, they definitely do that in Hunted.
## Post #87
- Username: lion589
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-07-30T07:47:49+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (UPDATE: Models

> Reply from Hamers
>
> That is indeed a milestone. Congratz    I figure animated objects are handled quite a bit differently compared to the static scene (lack of door, chair and cup)? Also I noticed that at 0:45-0:50 your camera is missing a shot (maybe it's tied to the character?)  

Also what do you think about the street car scene? Is it on the same map as the police station or swapped in and out with the loading happening in the background? It also wouldn't surprise me if the street is very short and they just loop the one segment over and over again, they definitely do that in Hunted.

Thanks! The animated objects are handeled as characters. The static scenery is all in one big mesh collection, the "characters" (so also doors, chairs, etc.) can have animation, sounds, etc. They are added by the scene Lua script.

The shot that's missing is a bit hard to explain. If you look before the missing shot you see the camera is facing Jodie. Then in the game the shot facing the chief cop comes, and then it's back to Jodie. That shot of Jodie (before / after the cop) is one shot. As you may have noticed, the road part starts later in my version than in the game. That is because at the end of the scene you can see the camera shot that was the missing one. That one works as a "sub shot", it appears over another shot. Since I haven't implemented that yet, you can see missing shots here and there that then appear after the scene is over.

The street car scene is a separate area. The chapter "Broken" has one scene and three areas (POLICE_STATION, POLICE_STATION_ROAD and POLICE_STATION_BREAK). In the video I did it so that it loads the first and lasts area, but only activates the first one for all but the last "movie" (that's how one part of a sequence is called internally). When the last one starts (the "Too Late" part), it deactivates the first area and activates the last one. I had some trouble loading in the road part so I didn't bother fixing it before the video 
Here is the code to load and play the movies/areas, so you can see just how hacky it is xD [http://pastebin.com/67Lns7mU](http://pastebin.com/67Lns7mU)
## Post #88
- Username: mirh
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-07-31T10:32:53+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (UPDATE: Models

Okay, I fixed a lot of things in the engine, including the z-buffer fighting, lighting, but I also removed the last 2 camera shots from the interrogation part, and fixed the check
if the timeline is playing (at the "I know... they're coming" part), so now it matches perfectly with the audio!

Here's a new demo of the sequence playing, along with a nice "flythrough" of the area:

https://www.youtube.com/watch?v=HM9AqzbBhOg

SPOILER: making a lot of progress on the Lua engine. It's looking promising!


And please, we need textures! If you know anyone who's good at that stuff (or if you're good at it) or at PPC / ELF disassembly, please let me know!
## Post #89
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-08-02T21:02:00+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (UPDATE: Models

> Reply from HugoPeters
>
> And please, we need textures! If you know anyone who's good at that stuff (or if you're good at it) or at PPC / ELF disassembly, please let me know!
What with textures wrong?
## Post #90
- Username: mirh
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-08-02T21:28:28+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (UPDATE: Models

> Reply from Ekey
>
> HugoPeters wrote:And please, we need textures! If you know anyone who's good at that stuff (or if you're good at it) or at PPC / ELF disassembly, please let me know!
What with textures wrong?
Nobody has found the texture compression format yet. Cra0, chrrox, howfie and a few others have looked at it already, but no luck.
I made a topic about them a little while ago: [viewtopic.php?f=21&t=11607](http://forum.xentax.com/viewtopic.php?f=21&t=11607)
If you want I can send you a few samples!

[update]
Forget that last pic I posted, I remade it -again-, and this time I have something that's actually working!
## Post #91
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-08-03T07:13:10+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (UPDATE: SEQUENC

Send me eboot and a few textures.
## Post #92
- Username: mono24
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-08-03T08:02:29+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (UPDATE: SEQUENC

> Reply from Ekey
>
> Send me eboot and a few textures.
Sent a PM, it's still in my Outbox but it should arrive soon. Thanks!
## Post #93
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2014-08-03T12:02:11+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (UPDATE: SEQUENC

go ekey!
## Post #94
- Username: Hamers
- Rank: beginner
- Number of posts: 21
- Joined date: Fri Jul 22, 2011 11:39 pm
- Post datetime: 2014-08-04T15:39:51+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (UPDATE: SEQUENC

> Reply from HugoPeters
>
> Thanks! The animated objects are handeled as characters. The static scenery is all in one big mesh collection, the "characters" (so also doors, chairs, etc.) can have animation, sounds, etc. They are added by the scene Lua script.
Ah what I suspected. They do build all their scenes in Maya apparently, so it doesn't surprise me they are exported as one big collection.

> Reply from HugoPeters
>
> The shot that's missing is a bit hard to explain. If you look before the missing shot you see the camera is facing Jodie. Then in the game the shot facing the chief cop comes, and then it's back to Jodie. That shot of Jodie (before / after the cop) is one shot. As you may have noticed, the road part starts later in my version than in the game. That is because at the end of the scene you can see the camera shot that was the missing one. That one works as a "sub shot", it appears over another shot. Since I haven't implemented that yet, you can see missing shots here and there that then appear after the scene is over.
Makes a lot of sense.

> Reply from HugoPeters
>
> The street car scene is a separate area. The chapter "Broken" has one scene and three areas (POLICE_STATION, POLICE_STATION_ROAD and POLICE_STATION_BREAK). In the video I did it so that it loads the first and lasts area, but only activates the first one for all but the last "movie" (that's how one part of a sequence is called internally). When the last one starts (the "Too Late" part), it deactivates the first area and activates the last one. I had some trouble loading in the road part so I didn't bother fixing it before the video 
Here is the code to load and play the movies/areas, so you can see just how hacky it is xD http://pastebin.com/67Lns7mU

```
if (i == 7)  // TooLate
```

I see what you did there  

EDIT: Hopefully someone figures out the texture format and wow at dat lua output. I'm not mistaken in the assumption that "fAidenLookAt" is an actual function that is probably a part of their node based scripting system which the level designers used to create the scene scripting?
## Post #95
- Username: mirh
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-08-04T16:00:25+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (UPDATE: SEQUENC

> Reply from Hamers
>
> HugoPeters wrote:
EDIT: Hopefully someone figures out the texture format and wow at dat lua output. I'm not mistaken in the assumption that "fAidenLookAt" is an actual function that is probably a part of their node based scripting system which the level designers used to create the scene scripting?
fAidenLookAt is a Dynamic Communicator, which means the function itself is stored elsewhere, and by adding attributes, events and actions they can call this script in a "tool-efficient" manner.
The normal Communicators have their scripts, attributes, events, etc. stored in the executable, while these are created on runtime.

fAidenLookAt is defined in the GameManager:

```
if (QDT.fAidenLookAt == nil) then
	local nDynType = CreateDynCommunicator("fAidenLookAt", 4411)
		AddDynAttribute(nDynType, "ANAEL_GAMEPLAY", "AnaelGameplay", 0)
		AddDynAttribute(nDynType, "float", "BlendDuration", 0)
		AddDynAttribute(nDynType, "string", "BonesName", 6)
		AddDynAttribute(nDynType, "SCRIPT_ENTITY_ABC", "EntityToLook", 0)
		AddDynAttribute(nDynType, "bool", "StopAtEnd", 0)
	RegisterDynCommunicator(nDynType)
end
```


This is how I implemented the kernel's main way of dealing with functions, etc.:


It works pretty well!

And I also already implemented the whole Dynamic Communicator thing:
## Post #96
- Username: mirh
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-08-06T22:51:57+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (UPDATE: SEQUENC

Kernel!

Here's my first real-world test of my kernel interface.
The scripts playing the audio are copy-pasted from the game!

https://www.youtube.com/watch?v=CtRO0hcNOE4
## Post #97
- Username: mirh
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-08-07T21:21:15+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (UPDATE: SEQUENC

OMFG
I made a Luac bytecode converter for Beyond's chunks, the issue was endianness in the end! So I now read in the function, and convert BE ints to LE ints, and also change the floats into doubles.
AND IT WORKS SO I CAN NOW FINALLY EXECUTE BEYOND'S LUAC SCRIPTS
## Post #98
- Username: mirh
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-08-11T21:14:14+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (UPDATE: SEQUENC

During loading research:

- Disabled caching
- Disabled usage of setup files
- Since I run the game through the ProDG target manager I can change the load speed by changing my ethernet port Speed & Duplex, so set it to 10 Mb/s.

Result:
## Post #99
- Username: Hamers
- Rank: beginner
- Number of posts: 21
- Joined date: Fri Jul 22, 2011 11:39 pm
- Post datetime: 2014-08-13T00:50:18+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (UPDATE: SEQUENC

Not surprised in the slightest lol Poor console games rely a lot on caching and fast streaming of assets on the fly. Still funny to see the LODs though xD 
Awesome news about the lua functions!
## Post #100
- Username: mirh
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-08-15T10:52:11+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (UPDATE: SEQUENC

Small update: proper audio streaming has been build!
## Post #101
- Username: Hamers
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-08-16T21:53:03+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (UPDATE: SEQUENC

Kernel Part ~2~!

'Right guys, more shit!

https://www.youtube.com/watch?v=o8HnAjksFMc

I'm getting to a point where I find it extremely difficult to explain what the fuck I'm even doing XD
So I might need to start with stuff like voice overs where I can quickly explain the contexts of everything, but for now I've done it through subtitles.
## Post #102
- Username: Hamers
- Rank: beginner
- Number of posts: 21
- Joined date: Fri Jul 22, 2011 11:39 pm
- Post datetime: 2014-08-17T12:44:23+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (UPDATE: SEQUENC

> Reply from HugoPeters
>
> Kernel Part ~2~!

'Right guys, more shit!

https://www.youtube.com/watch?v=o8HnAjksFMc

I'm getting to a point where I find it extremely difficult to explain what the fuck I'm even doing XD
So I might need to start with stuff like voice overs where I can quickly explain the contexts of everything, but for now I've done it through subtitles.
Yeah, seems like this starts to go into the territory where you have to reverse engineer and implement the actual game scripting, which sounds pretty complicated. Good luck man, props to you for keeping at it!
## Post #103
- Username: mirh
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-08-17T18:33:00+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (UPDATE: SEQUENC

> Reply from Hamers
>
> HugoPeters wrote:Kernel Part ~2~!

'Right guys, more shit!

https://www.youtube.com/watch?v=o8HnAjksFMc

I'm getting to a point where I find it extremely difficult to explain what the fuck I'm even doing XD
So I might need to start with stuff like voice overs where I can quickly explain the contexts of everything, but for now I've done it through subtitles.
Yeah, seems like this starts to go into the territory where you have to reverse engineer and implement the actual game scripting, which sounds pretty complicated. Good luck man, props to you for keeping at it!
It's funny, because I've already implemented around 40% of their "kernel"/interface.
I've basically completed the basic environment, and now it's only a matter of making the functions actually do something, I've already passed the hardest part by far.
## Post #104
- Username: Hamers
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-08-22T01:10:17+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (UPDATE: SEQUENC

Choices??

Here's a very, very, VERY early demo of choice paths!
There's dialog audio starting / ending at wrong times, dialog text isn't parsed, and a TON more things wrong, but it kinda gives an idea of how far I am right now.
All the stuff wrong are just minor touch-ups.

https://www.youtube.com/watch?v=lAEm632Ordc

Please keep in mind, what seems like a glitch isn't a glitch, it's just because I haven't implemented this or that yet.
## Post #105
- Username: Hamers
- Rank: beginner
- Number of posts: 21
- Joined date: Fri Jul 22, 2011 11:39 pm
- Post datetime: 2014-08-22T13:05:02+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (UPDATE: SEQUENC

Regardless how rough it is, I refresh the thread every day in anticipation of an update   Really love how you document your progress!
## Post #106
- Username: mirh
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-08-22T13:10:07+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (CHOICE PATHS!?!

> Reply from Hamers
>
> Regardless how rough it is, I refresh the thread every day in anticipation of an update   Really love how you document your progress!
Thanks, it's really fun to keep track of it all! I suppose you've already seen the "to-do"-lists on the first page?

I've also forgot to mention this, but I started my own blog, with currently only one lonely post, but should be an interesting read: [http://heap.djek.nl/](http://heap.djek.nl/)

Also, I'm pretty fucking excited right now, because I finally figured out how the game gets the exact localization part from a container.
It's really stupid.
It provides a key like IW_0801_JUSTIN_FLIRT_JHO14_C00097, then it takes the CRC32 of that, and that turns out to be the key stored in the localization container.
I was first doing all sorts of crazy stuff to get to the correct localization bit, but this is so much easier
## Post #107
- Username: mirh
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-08-22T18:07:47+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (CHOICE PATHS!?!

This is a title

Cleaned up everything quite a bit, fixed a lot of things, and made a lot of "boring" but important things.
And I also included the execution of the radio script now, so yeah:

https://www.youtube.com/watch?v=S-2OvPOZ2QM
## Post #108
- Username: aagems
- Rank: advanced
- Number of posts: 75
- Joined date: Thu May 31, 2012 1:07 am
- Post datetime: 2014-09-01T17:15:20+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (CHOICE PATHS!?!

Great job Hugo
## Post #109
- Username: deepshit
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-09-02T00:32:06+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (CHOICE PATHS!?!

LOL!

Alright, a biggie for y'all.

I first wanted to do a post on Script Zones (I still have a tab open for that), but then I discovered an exploit in the game.
The Game Manager (the uncompiled Lua script which initializes a bunch of stuff for the game) has some print commands and comments scattered around.
I noticed the function "RunLuaFile" in my ELF string output.
So I replaced a print command with NewOS("Infraworld", 4216, 0):RunLuaFile("EXECUTE_ME.lua") (NewOS gets the Game Manager instance) and I was shocked to see that the game was then indeed trying to open the file EXECUTE_ME.lua.
Then I created that file in the file serving directory, and sure enough, the game runs the fucking file.

So what can I do now?

Everything.

I can swap models, set their position, unload them, unload graphics, remove motion kits, call script functions, trigger events (also FX events for characters), remove triggers (thus remove things like restrictions where you can walk), enable wireframe, remove objects, change audio, open the PSN store (lolwut), force low / high def LODs, and the list goes on and on. I basically have direct access and control over the kernel and engine. I wrote a script that launches another RunLuaFile when the user clicks square on the controller. This means I can modify my code on the go and do some fun shit!

Proof:

List of all "instances" in the "The Party" scene:


Wireframe enabled:


Jodie's character model swapped with Matt's:



Matt's character model set to null:


Jodie's char.. this should explain itself:


This too:


And this might:


Havok doesn't like it when I lock the FPS to 400000:


The game has LOADS of print() functions everywhere, so I made a function that overrides the print() and made my own:



Will you release a patch?
Possibly, I'm a person that only likes to release finished things, so when I have time to finish it, I probably will.

Will this work with Heavy Rain too?
Probably, yeah.

A little snip from my custom code to launch the RunLuaFile when the square button is pressed:


More stuff soon!
## Post #110
- Username: lion589
- Rank: beginner
- Number of posts: 26
- Joined date: Thu Oct 13, 2011 12:48 am
- Post datetime: 2014-09-02T14:01:50+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (CHOICE PATHS!?!

is this running on pc?
## Post #111
- Username: lion589
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-09-02T14:32:53+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (CHOICE PATHS!?!

> Reply from lion589
>
> is this running on pc?
Haha, that post was concerning the PS3 version. But when we get the textures out, it could very well look like that on PC as well soon enough!
## Post #112
- Username: lion589
- Rank: beginner
- Number of posts: 26
- Joined date: Thu Oct 13, 2011 12:48 am
- Post datetime: 2014-09-02T14:57:18+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (CHOICE PATHS!?!

> Reply from HugoPeters
>
> lion589 wrote:is this running on pc?
Haha, that post was concerning the PS3 version. But when we get the textures out, it could very well look like that on PC as well soon enough!
Nice!
## Post #113
- Username: Meguido
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Sep 07, 2014 8:33 pm
- Post datetime: 2014-09-07T13:23:00+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (CHOICE PATHS!?!

OMG what an amazing job you're doing here!

Didn't know about a "deleted" scene in that sequence (all i knew was about Jodie with Matt in Jodie's room had 7 seconds cutted in the eu version to get a low PEGI...) but that' look really cool    

Btw just a not-related-to-the-main-subject question xD. Have you used game maker to make the Beyond: Two Souls -Extractor- v1.0? I ask because of this shot:

that's the ussual window you get in gm when any error of unknown "resources" used arises.
Just wondering, sorry if its offtopic.
## Post #114
- Username: mono24
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-09-07T13:31:11+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (CHOICE PATHS!?!

> Reply from Meguido
>
> OMG what an amazing job you're doing here!

Didn't know about a "deleted" scene in that sequence (all i knew was about Jodie with Matt in Jodie's room had 7 seconds cutted in the eu version to get a low PEGI...) but that' look really cool    

Btw just a not-related-to-the-main-subject question xD. Have you used game maker to make the Beyond: Two Souls -Extractor- v1.0? I ask because of this shot:

that's the ussual window you get in gm when any error of unknown "resources" used arises.
Just wondering, sorry if its offtopic.
Yup, I did use Game Maker for that, but since then I've (luckily) switched to C# and Visual Studio!
## Post #115
- Username: lion589
- Rank: beginner
- Number of posts: 26
- Joined date: Thu Oct 13, 2011 12:48 am
- Post datetime: 2014-09-11T09:17:03+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (CHOICE PATHS!?!

Is there any updates? I am dying to see more from you
## Post #116
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-09-11T09:40:05+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (CHOICE PATHS!?!

I'm going to contribute more when I get my new pc next week especially for those bone joints and UVs
## Post #117
- Username: lion589
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-09-11T20:18:34+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (CHOICE PATHS!?!

> Reply from lion589
>
> Is there any updates? I am dying to see more from you
Thanks!!
I've been really busy with university, instead of boring homework such as economy and so forth I now get way more fun assignments like Maya stuff, concept design, using game engines, using SVN, making games as a team and much more, so fun and quite easy!

I've just completed Heavy Rain, and even though I like the fight scenes over Beyond's in some ways I do still prefer Beyond over Heavy Rain.

About updates... I got one major thing coming up.
I'll give a clue:
textures

Also I'm happy to announce flatz is helping out! He has made some very impressive tools, like this PS3 EID Root Key Dumper: [http://www.maxconsole.com/maxcon_forums ... z-released](http://www.maxconsole.com/maxcon_forums/threads/197759-EID-Root-Key-Dumper-by-flatz-released).
## Post #118
- Username: lion589
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-09-14T14:01:26+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (CHOICE PATHS!?!

Made a super simple mesh exporter to do some research on normals. Unfortunately I am probably not going to share the models (legal reasons) 



(parts of body are missing because of clothes being stored in different meshes)
## Post #119
- Username: lion589
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-09-18T00:37:22+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (CHOICE PATHS!?!

Big shout out to flatz for finding and reverse engineering the texture decoding module!!

Ladies and gentlemen. It is time. (the corrupted pieces scattered throughout some textures have been fixed now). For some reason some Jodies have blue arms, will figure out why.







(chrrox made me do this   )
## Post #120
- Username: lion589
- Rank: beginner
- Number of posts: 26
- Joined date: Thu Oct 13, 2011 12:48 am
- Post datetime: 2014-09-18T12:38:55+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (CHOICE PATHS!?!

Wow  This is great, now the models came to life.
## Post #121
- Username: Hamers
- Rank: beginner
- Number of posts: 21
- Joined date: Fri Jul 22, 2011 11:39 pm
- Post datetime: 2014-09-19T19:44:01+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (!!!TEXTURES!!!)

Welp I forget to check this thread for 2 weeks and another set of huge updates    Awesome work! Really nice to see the collaborated effort paying off. I sense fully textured environments coming soon   

@Hugo
If you have some spare time (and if it's not asking too much) could you maybe check something for me in "1902 Homeless Miracles" ? Since you can now remove/disable triggers (that feature would be sick to have in your MOD btw) I'm curious what happens if you go back on the street and try to advance the story (supermarket/house/baby) without going through the part where you have to eat with the homeless gang. Normally there is a trigger before the street turning you back, but I'm wondering if the game logic is activated behind it. I told you a while ago I'm trying to break Beyond a little bit for speedrunning purposes and there is a glitch that allows you to make Jodie walk through some triggers without activating them (by calling Aiden at the right moment while doing a turn around). It's pretty fucking hard to do in some spots though, so it would be nice to know if it's even worth the effort xD
## Post #122
- Username: HugoPeters
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-09-19T20:25:17+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (!!!TEXTURES!!!)

> Reply from Hamers
>
> Welp I forget to check this thread for 2 weeks and another set of huge updates    Awesome work! Really nice to see the collaborated effort paying off. I sense fully textured environments coming soon   

@Hugo
If you have some spare time (and if it's not asking too much) could you maybe check something for me in "1902 Homeless Miracles" ? Since you can now remove/disable triggers (that feature would be sick to have in your MOD btw) I'm curious what happens if you go back on the street and try to advance the story (supermarket/house/baby) without going through the part where you have to eat with the homeless gang. Normally there is a trigger before the street turning you back, but I'm wondering if the game logic is activated behind it. I told you a while ago I'm trying to break Beyond a little bit for speedrunning purposes and there is a glitch that allows you to make Jodie walk through some triggers without activating them (by calling Aiden at the right moment while doing a turn around). It's pretty fucking hard to do in some spots though, so it would be nice to know if it's even worth the effort xD
Hmm... *sniff* *sniff*, yeah, I can smell it. It's close by. 

I disabled the trigger zone, and I was able to walk through the whole scene, but the other triggers are disabled, so nothing happens.
Btw, if you want I can add you on Skype so I can help you break the game?
## Post #123
- Username: Hamers
- Rank: beginner
- Number of posts: 21
- Joined date: Fri Jul 22, 2011 11:39 pm
- Post datetime: 2014-09-20T07:55:26+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (!!!TEXTURES!!!)

Do I want? Yeah I think I do   Will send you a PM
## Post #124
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2014-09-21T10:11:35+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (!!!TEXTURES!!!)

Hugo, I just wanted to thank you for the hard work on the models! Good to see the textures are finally available too! Keep up the good work
## Post #125
- Username: Hamers
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-09-23T02:31:09+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (!!!TEXTURES!!!)

Stuff!

https://www.youtube.com/watch?v=fUqPOOoC8xU

Spoiler: got clothing (and thus hair) working too finally.
## Post #126
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2014-09-24T04:53:44+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (!!!TEXTURES!!!)

> Reply from HugoPeters
>
> Stuff!

https://www.youtube.com/watch?v=fUqPOOoC8xU

Spoiler: got clothing (and thus hair) working too finally.

Lol good news!!!
## Post #127
- Username: lion589
- Rank: beginner
- Number of posts: 26
- Joined date: Thu Oct 13, 2011 12:48 am
- Post datetime: 2014-09-26T13:57:17+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (!!!TEXTURES!!!)

I have a question about the game exploit, Can you model swap Jodie with any character in the game or is it limited to the playable chapter?
## Post #128
- Username: lion589
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-09-27T12:07:35+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (!!!TEXTURES!!!)

> Reply from lion589
>
> I have a question about the game exploit, Can you model swap Jodie with any character in the game or is it limited to the playable chapter?
I can swap any model with any model, as long as they are available in the same scene. For instance, in Navajo, I can swap Jodie's model with the dog's model (hilarious btw), but I can't swap Jodie's model in say The Dinner with the Navajo dog model.
## Post #129
- Username: octaviousrex
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-09-27T18:08:48+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (!!!TEXTURES!!!)

Some more screenshots!

Beware! My lighting sucks! My normals suck! My anti-aliasing sucks! I'm moving to a new renderer atm!
## Post #130
- Username: Jodan
- Rank: n00b
- Number of posts: 17
- Joined date: Fri Jul 02, 2010 11:12 am
- Post datetime: 2014-09-30T07:52:22+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (!!!TEXTURES!!!)

It has been forever since I've been on this site... love the 3d world but have not had any time as of late.  So I was just curious if any new things have come about and I found this thread (because of your post in the 3d/2d models thread... think your right about it being mostly unnoticed..made me laugh).  

This is some outstanding work, saw the videos of the scripts in action, very cool developments.  I have to say seeing how they can create these very believable people and places is just amazing.  More and more realism everyday... motion capture/3d scanning just brings these games to life and the details they can bring into people now... it was not long ago that this was unimaginable.  Thanks for the glimpse behind the curtain... certainly can't wait to see more. Some seriously talent was needed to bring all these many and different nuances together always a Wow.QuanticDream and all those who make this type of artwork definitely do this for love the craft.
## Post #131
- Username: lion589
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-10-05T08:49:45+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (!!!TEXTURES!!!)

Support

As you may know, this category of XeNTaX doesn't get as much attention as we'd like it to get!
That's why I made this badge:



```
[url=http://forum.xentax.com/viewtopic.php?f=32&t=11411][img]http://i.imgur.com/EUcneAM.png[/img][/url]
```


So now, you can show your support of this project by putting the badge in your signature!

Let's take over XeNTaX, one signature at the time!
## Post #132
- Username: Gruselgurke
- Rank: advanced
- Number of posts: 72
- Joined date: Sat Mar 31, 2012 1:15 am
- Post datetime: 2014-10-05T18:24:31+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (!!!TEXTURES!!!)

This is nuts! Would be huge if you can actually pull that port of, looking really good so far.
## Post #133
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2014-10-06T03:51:38+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (!!!TEXTURES!!!)

I want in
## Post #134
- Username: deepshit
- Rank: advanced
- Number of posts: 76
- Joined date: Wed Feb 01, 2012 4:43 am
- Post datetime: 2014-10-06T08:15:12+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (!!!TEXTURES!!!)

I like the idea for support.
## Post #135
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2014-10-07T05:41:00+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (!!!TEXTURES!!!)

Ok already supporting this crap
## Post #136
- Username: Naroax
- Rank: beginner
- Number of posts: 30
- Joined date: Sun Aug 31, 2014 1:44 am
- Post datetime: 2014-10-07T10:09:18+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (!!!TEXTURES!!!)

Supporting this too!
## Post #137
- Username: lion589
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-10-10T00:07:07+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (!!!TEXTURES!!!)

We hit 10,000 topic views everyone!
So it's time for an update!!!!

Been working on my script kernel, and making some huge progress!
What you're about to witness are 2 scenes (Prologue and Broken) being run COMPLETELY by Beyond's native scripts.
No more hacky code, no manual ordering. EVERYTHING is run by the scripts. The scripts call other scripts, etc.

Note that this proves that my whole kernel is working, now it's just a matter of adding features.

>> https://www.youtube.com/watch?v=w0p_MGTfN8M

Also, happy one year anniversary Beyond!
## Post #138
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2014-10-10T04:34:53+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (!!!TEXTURES!!!)

Great work!
## Post #139
- Username: zubren
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Apr 07, 2013 2:25 pm
- Post datetime: 2014-10-10T05:57:58+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (!!!TEXTURES!!!)

Jesus, this actually wildly interesting. Keep up the great work man!
## Post #140
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2014-10-10T14:40:08+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (!!!TEXTURES!!!)

Good!!!! Keep it up!!!
## Post #141
- Username: mirh
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-10-11T13:13:51+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (!!!TEXTURES!!!)

Thanks for all the support everyone!

Since my kernel is almost complete now, I can start adding features!
First off are area's! The loading is now completely dynamic, no more ugly manual shit.
What you see in this video are area's being loaded in, and then shown when the script calls the <areainstance>.ShowCatalog() and hidden when it calls the .HideCatalog() function.

This is pretty freaking awesome if I may say so myself.

https://www.youtube.com/watch?v=G_CRtX67zU0
## Post #142
- Username: lion589
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-10-13T06:29:56+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (!!!TEXTURES!!!)

Hooray for triangles

Ok, got camera shot's working (again), this time much better of course!
Also got dynamic area loading in there now, along with some Hide() and Show() functions.

Check it out, this engine's a keeper!

https://www.youtube.com/watch?v=2Yaut1ScuSA

Btw, for the ones who have been following the to-do list, I have just quickly updated them (gotta do a better update though), but I've now also finally implemented "actions" (custom events set by the developer) in my script engine. This means it's sorta... complete? At least for the core scripting engine.

More spam soon!
## Post #143
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2014-10-13T07:06:22+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (!!!TEXTURES!!!)

Sadly, the video is 'private'. Can't view it.
## Post #144
- Username: mono24
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2014-10-13T07:48:37+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (!!!TEXTURES!!!)

Mr. Mouse is right can you please unlock it ?? Thx
## Post #145
- Username: mono24
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-10-13T08:31:25+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (!!!TEXTURES!!!)

> Reply from Mr.Mouse
>
> Sadly, the video is 'private'. Can't view it.

> Reply from michalss
>
> Mr. Mouse is right can you please unlock it ?? Thx

Sorry, forgot to put it on Unlisted.

Should be fixed now!
## Post #146
- Username: lion589
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-10-14T09:54:07+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (!!!TEXTURES!!!)

The best UV test map of All Time

Look! It's another video!

Note the fading, it's done by my engine, not post editing effects!

https://www.youtube.com/watch?v=rNz3gBDROi0

Note that the z-buffer fighting is just because normally there would be a more complicated shader applied to there or that part wouldn't even be visible.
## Post #147
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2014-10-14T14:28:17+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (!!!TEXTURES!!!)

Very nice dude !!

Its exactly what my project was (porting some xbox classic games to pc [like DOA, project gotham, midtown madness etc..]) and even re-mastering some old psx games ([ff, saga frontier, front mission etc...]).


Too bad, never get any help, and I'm too busy right now with my own game to continue.......



But, like I said in a pm to Mr.Mouse, it will be a good idea to make a subforum for porting/remastering games, I know a lot of people who try to port maps/gameplay or free dlc to PC (like some sonic unleashed maps [only on console] to sonic generation in PC]...)
## Post #148
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2014-10-14T23:39:58+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (!!!TEXTURES!!!)

Lot of progress since I last checked in, keep up the good work Hugo
## Post #149
- Username: Hamers
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-10-20T14:44:50+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (!!!TEXTURES!!!)

> Reply from zaykho
>
> Very nice dude !!
Its exactly what my project was (porting some xbox classic games to pc [like DOA, project gotham, midtown madness etc..]) and even re-mastering some old psx games ([ff, saga frontier, front mission etc...]).
Too bad, never get any help, and I'm too busy right now with my own game to continue.......
But, like I said in a pm to Mr.Mouse, it will be a good idea to make a subforum for porting/remastering games, I know a lot of people who try to port maps/gameplay or free dlc to PC (like some sonic unleashed maps [only on console] to sonic generation in PC]...)
Thanks! To be honest though, this isn't the same as porting console-specific maps to PC versions, this is about getting the whole game on there! 

> Reply from JayK
>
> Lot of progress since I last checked in, keep up the good work Hugo
It's pretty insane 

(kinda)

I made even more progress on my scripting kernel, and also made a little window so I can directly input commands.
This time, I made a video on it while I TALK about it!! 

Let me know what you guys think!

http://youtu.be/RfLbLTIe7sI

spoiler: physics / triggers coming in?
## Post #150
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2014-10-20T18:59:15+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (!!!TEXTURES!!!)

Er..what you say?  



featured-img.png (76.14 KiB) Viewed 225 times
## Post #151
- Username: HugoPeters
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-10-20T19:04:36+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (I CAN TALK!?!?

> Reply from Mr.Mouse
>
> Er..what you say?  
featured-img.png
I hope it was semi-understandable
## Post #152
- Username: Hamers
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2014-10-20T22:13:11+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (I CAN TALK!?!?

> Reply from HugoPeters
>
> I'm very proud to announce I passed my finals exams! This means I will be moving to Breda (The Netherlands) and will start a bachelor on Indie Game Development!

Fun fact: did you know that in the time I was supposed to prepare for my finals I did most of the work on reversing Beyond? This lead to the fact that I didn't... quite... prepare well for the finals...
But I'm so fucking happy right now!

Can't believe I missed this. Congrats...belatedly... but nevertheless!   

   

So you moved to Breda now huh! Great! I live in Emmen nowadays for about 4 years, after having lived for 14 years in Groningen and then 3 years in Elst (near Arnhem). Job's still in Arnhem though. 

Keep up this port work, looking to be amazing.
## Post #153
- Username: d875j
- Rank: advanced
- Number of posts: 52
- Joined date: Sun Jun 17, 2012 10:32 am
- Post datetime: 2014-10-21T03:24:37+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (I CAN TALK!?!?

Just shocked i just heard about this today looks awesome.
## Post #154
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2014-10-21T06:59:21+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (I CAN TALK!?!?

Hugo --> Very great progress, im actually looking forward to see textures on scene in action 

Question : can you say on 100%, that you are now able to replicate that Game on PC?

Thx
## Post #155
- Username: mirh
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-10-21T12:25:08+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (I CAN TALK!?!?

> Reply from Mr.Mouse
>
> HugoPeters wrote:I'm very proud to announce I passed my finals exams! This means I will be moving to Breda (The Netherlands) and will start a bachelor on Indie Game Development!

Fun fact: did you know that in the time I was supposed to prepare for my finals I did most of the work on reversing Beyond? This lead to the fact that I didn't... quite... prepare well for the finals...
But I'm so fucking happy right now!

Can't believe I missed this. Congrats...belatedly... but nevertheless!   

   

So you moved to Breda now huh! Great! I live in Emmen nowadays for about 4 years, after having lived for 14 years in Groningen and then 3 years in Elst (near Arnhem). Job's still in Arnhem though. 

Keep up this port work, looking to be amazing.
Thanks!!! I really love Breda, and also living separately from my parents is pretty fun actually! I still go to my parents' home in the weekends, which is more in the western area, but that's only for the first few months.

> Reply from michalss
>
> Hugo --> Very great progress, im actually looking forward to see textures on scene in action 

Question : can you say on 100%, that you are now able to replicate that Game on PC?

Thx
Not for a 100%. We're still missing important things such as animation, and chapter-specific gameplay such as a bike, submarine and horse. But, I'm currently working on triggers, and the basics are already working thanks to the amazing [Paradox](http://paradox3d.net/features)!!!

Triggers are looking really good
## Post #156
- Username: KaoruKasuga
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed May 02, 2012 2:48 am
- Post datetime: 2014-10-21T17:57:50+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (I CAN TALK!?!?

So I discovered this topic a few minutes ago, I was getting more and more excited, and then:

> Reply from HugoPeters
>
> Made a super simple mesh exporter to do some research on normals. Unfortunately I am probably not going to share the models (legal reasons)  

Anyway this is an awesome project you're doing here and I wish you the best ! 
And good luck for the uv mapping :'D

Last question: What will you do when the game will be fully ported ? Are you going to sell it ?
## Post #157
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2014-10-21T18:28:30+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (I CAN TALK!?!?

> Reply from HugoPeters
>
> Mr.Mouse wrote:

So you moved to Breda now huh! Great! I live in Emmen nowadays for about 4 years, after having lived for 14 years in Groningen and then 3 years in Elst (near Arnhem). Job's still in Arnhem though. 

Keep up this port work, looking to be amazing.   
Thanks!!! I really love Breda, and also living separately from my parents is pretty fun actually! I still go to my parents' home in the weekends, which is more in the western area, but that's only for the first few months.

Yeah, I know I wanted to leave my parents' home as soon as I could. No offence to them, but I had to be on my own. 'Course that was in 1993 when I started to study in Groningen.
## Post #158
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2014-10-21T19:14:48+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (I CAN TALK!?!?

> Reply from HugoPeters
>
> zaykho wrote:Very nice dude !!
Its exactly what my project was (porting some xbox classic games to pc [like DOA, project gotham, midtown madness etc..]) and even re-mastering some old psx games ([ff, saga frontier, front mission etc...]).
Too bad, never get any help, and I'm too busy right now with my own game to continue.......
But, like I said in a pm to Mr.Mouse, it will be a good idea to make a subforum for porting/remastering games, I know a lot of people who try to port maps/gameplay or free dlc to PC (like some sonic unleashed maps [only on console] to sonic generation in PC]...)
Thanks! To be honest though, this isn't the same as porting console-specific maps to PC versions, this is about getting the whole game on there!

Yeah I know, this is what I was doing, I was porting the whole game, physics, models, sound, etc....
I wanted to play on pc those "exclusive console game", and more, I wanted to them being playable directly in the web browser without some OS dependencies.....

Right now, even a game like BEYOND two souls can be ported to Three.js.  :p
## Post #159
- Username: lion589
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-10-21T23:03:12+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (I CAN TALK!?!?

> Reply from KaoruKasuga
>
> So I discovered this topic a few minutes ago, I was getting more and more excited, and then:
HugoPeters wrote:Made a super simple mesh exporter to do some research on normals. Unfortunately I am probably not going to share the models (legal reasons)   

Anyway this is an awesome project you're doing here and I wish you the best ! 
And good luck for the uv mapping :'D

Last question: What will you do when the game will be fully ported ? Are you going to sell it ?
UV mapping is already done! 

What I will do with it.. well I've already gotten tons of requests for a model exporter, so that's what I'm probably NOT going to release XD (just for the plain reason that there are many perverts out there and I think it's illegal)

It really depends on what's legal and what's not. I want to avoid trouble with Sony and Quantic Dream as much as I can, so I'm keeping it at video updates for now... but who knows what the future will bring 

> Reply from Mr.Mouse
>
> HugoPeters wrote:Mr.Mouse wrote:

So you moved to Breda now huh! Great! I live in Emmen nowadays for about 4 years, after having lived for 14 years in Groningen and then 3 years in Elst (near Arnhem). Job's still in Arnhem though. 

Keep up this port work, looking to be amazing.   
Thanks!!! I really love Breda, and also living separately from my parents is pretty fun actually! I still go to my parents' home in the weekends, which is more in the western area, but that's only for the first few months.

Yeah, I know I wanted to leave my parents' home as soon as I could. No offence to them, but I had to be on my own. 'Course that was in 1993 when I started to study in Groningen.
wow, I wasn't even born back then XD

But yeah it's the same for me, even though I'm still 17 so it's only half-legal to live on my own, which causes tons of troubles registering everywhere 
I must say I don't know if I would have left if I didn't find the NHTV @ Breda, I didn't have a real "urge" to leave, but it did seem like a good option from the beginning.


Small Update
You might have noticed the weird vertices from the wireframe video's, there were ones exceeding 10000 in on the XYZ axises. I finally figured out the problem: some are HALF FLOATS instead of singles / floats. Oh Quantic Dream... I love how they're literally wasting data at one point, and at another being careful with it (even though it's probably a standard Edge SDK thing).

So here's a tree that consists entirely from half-floats!


And here are some flowers (don't mind the green thing)!


MORE TREES.


And high poly GRASS.


Soon... integrated in the area's.
## Post #160
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2014-10-22T05:17:37+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (I CAN TALK!?!?

> Reply from HugoPeters
>
> 
What I will do with it.. well I've already gotten tons of requests for a model exporter, so that's what I'm probably NOT going to release XD (just for the plain reason that there are many perverts out there and I think it's illegal)

Of course, there's no point in creating a conversion if nobody can play it.  I'm sure XeNTaX will be able to host some alpha or beta demo versions of it at some point somewhere. Meanwhile, by the time it reaches advanced beta stage you may want to contact Sony directly to see if they are willing to publish it / endorse it.  As for the model exporter, there would be no harm if there was one, or for instance in the form of support for Noesis. Talk to Rich Whitehouse about that (MrAdults).
## Post #161
- Username: lion589
- Rank: beginner
- Number of posts: 26
- Joined date: Thu Oct 13, 2011 12:48 am
- Post datetime: 2014-10-22T15:34:12+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (I CAN TALK!?!?

> Reply from Mr.Mouse
>
> HugoPeters wrote:
What I will do with it.. well I've already gotten tons of requests for a model exporter, so that's what I'm probably NOT going to release XD (just for the plain reason that there are many perverts out there and I think it's illegal)

Of course, there's no point in creating a conversion if nobody can play it.  I'm sure XeNTaX will be able to host some alpha or beta demo versions of it at some point somewhere. Meanwhile, by the time it reaches advanced beta stage you may want to contact Sony directly to see if they are willing to publish it / endorse it.  As for the model exporter, there would be no harm if there was one, or for instance in the form of support for Noesis. Talk to Rich Whitehouse about that (MrAdults).

Contacting Sony about this project it's really a bad idea because they'll stop this work immediately, and as for the model I really wish if he could release it.
## Post #162
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2014-10-22T19:56:58+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (I CAN TALK!?!?

That is why I said contacting Sony when there's a version that is playable only (like a beta version). Not before. And also making sure a lot of people have already tested it. (it is public).
## Post #163
- Username: Hamers
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-10-22T22:31:29+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (I CAN TALK!?!?

> Reply from Mr.Mouse
>
> That is why I said contacting Sony when there's a version that is playable only (like a beta version). Not before. And also making sure a lot of people have already tested it. (it is public).
Hmm, no, Sony would probably not like it for a couple of reasons...
1) They own copyright to Beyond (in fact, they own the IP and trademark by a 100%)
2) They're very serious about their exclusives (and haven't released a single exclusive on any non-PS platform)
3) Quantic Dream probably has a "build for PC" button somewhere, so why take a non-official version?
4) There's a PS4 version coming out with new scenes, this could heavily impact sales
5) Windows is owned by Microsoft... Microsoft & Sony aren't exactly friends...

Nah, contacting Sony would probably be the worst idea honestly, I'd rather send a direct email to David Cage (CEO & Writer of Quantic Dream).
But even he could easily sue me.

I need to give it some thought.
Currently I do not like the idea of releasing a separate model exporter, making it Noesis compatible would be like rewriting my whole project (currently the whole thing consists of over 500 C# files (partly auto generated so I can fill them in later on), and three core files with a total of over 20,000 lines of code.) 
The models are split up into pieces, those are split up into pieces, and the contents for those piece-pieces aren't even in the main file, and sometimes pieces from another mesh are found in the same file as another piece, and so forth.... To get to models in the first place requires kind of a set up.
And another reason: I've seen what can happen with game models... and especially because there are naked models in Beyond, I know I will see them back at some places where I'd rather not see them.

And another issue is decompilers.
C# is easily decompilable, even obfuscated. I could add that only the non-naked models can be exported, but it would take only minutes for people to remove the restriction.

I dunno, I do not want to sound selfish, but I gotta make sure I don't end up in prison... XD that being said, I love releasing stuff like this. I think the decisions on what to release and what not to release should be given more time until there's an actual thing that can largely play the game.
## Post #164
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2014-10-23T05:28:45+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (I CAN TALK!?!?

Well, you can see this as an assignment for yourself, certainly, and not release anything. But dismissing Sony is assuming too much up front based on no knowledge. It's about taking leadership of the project and bringing it to another level. It all depends on the way communication with a party like that is happening. Release a port in hiding, or release it in public. Alternatively, don't release it at all. Nobody goes to prison just like that, and as said, it is what you communicate is what is important. Be authentic with your intentions. Be that is it may, it is your call. Not mine. Sometimes you simply must look beyond that which you think you know. Go bold, because frankly people mostly know nothing at all. And still don't even know that they don't know. And the part they don't know they don't know is by far the largest of all.
## Post #165
- Username: figuresculptor
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Jan 07, 2011 4:08 am
- Post datetime: 2014-10-26T14:58:03+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (I CAN TALK!?!?

> Reply from Mr.Mouse
>
> Well, you can see this as an assignment for yourself, certainly, and not release anything. But dismissing Sony is assuming too much up front based on no knowledge. It's about taking leadership of the project and bringing it to another level. It all depends on the way communication with a party like that is happening.

He's not making this decision with "no knowledge". Sony has a long history of being antagonistic toward hackers of the PlayStation platform. They have, more than once, sued hacking projects targeting different generations of the PlayStation. Even when the law's not on their side, they are still known to sue because they have enormous financial resources and they know most of the peole they sue won't have the money to defend themselves.

In reality, they probably wouldn't go after Hugo in court over a game that's a few years old on a console that's not the current generation… but it's definitely a possibility based on their past behavior, especially if his work can be applied to decompile games on the PS4. At very least, Sony is likely to issue a takedown notice if they become aware of the project.

> Reply from Mr.Mouse
>
> Go bold, because frankly people mostly know nothing at all. And still don't even know that they don't know.

"Go bold" is easy advice to give when you're not the one facing the risk.   

That being said, I hope Hugo decides to release. This is some stellar work and I would love access to his work. I love looking through game assets and seeing how they were built.
## Post #166
- Username: odrin
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Mon May 23, 2011 9:43 am
- Post datetime: 2014-10-28T05:44:45+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (I CAN TALK!?!? 

first of all, i doubt this will end up as more than a glorified content extractor. just being realistic.

secondly, don't contact them, let them contact you. the risk of them putting the kibosh on this is 100 percent for all the reasons you listed yourself. so delay their knowing about this as long as possible. then proliferate it all over the internet. this way, when you get the cease and desist, the mirrors are up, and everyone has the file and can reupload anytime.
## Post #167
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2014-10-29T04:07:19+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (I CAN TALK!?!? 

> Reply from odrin
>
> first of all, i doubt this will end up as more than a glorified content extractor. just being realistic.

secondly, don't contact them, let them contact you. the risk of them putting the kibosh on this is 100 percent for all the reasons you listed yourself. so delay their knowing about this as long as possible. then proliferate it all over the internet. this way, when you get the cease and desist, the mirrors are up, and everyone has the file and can reupload anytime.

A better idea, release this with a tor joint "anonymously".
## Post #168
- Username: SkacikPL
- Rank: advanced
- Number of posts: 53
- Joined date: Tue Oct 28, 2014 2:51 pm
- Post datetime: 2014-10-29T12:58:41+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (I CAN TALK!?!? 

> Reply from Darko
>
> odrin wrote:first of all, i doubt this will end up as more than a glorified content extractor. just being realistic.

secondly, don't contact them, let them contact you. the risk of them putting the kibosh on this is 100 percent for all the reasons you listed yourself. so delay their knowing about this as long as possible. then proliferate it all over the internet. this way, when you get the cease and desist, the mirrors are up, and everyone has the file and can reupload anytime.

A better idea, release this with a tor joint "anonymously".

When it comes to releasing anything that's legally undesirable for certain individuals, just find someone who lives in russia/china to upload it to russian/chinese server for you.
Neither of those care about copyrights and such.
## Post #169
- Username: mirh
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-10-29T13:13:36+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (I CAN TALK!?!? 

> Reply from odrin
>
> i doubt this will end up as more than a glorified content extractor. just being realistic.
Excuse me, but...



It's funny because this engine won't be able to extract a single resource.
I'd have to make another program purely for extracting resources.
Have you even seen the video updates I posted??


I'm glad to hear people are excited over this project and want me to release it, but shall we now put down this topic for a while and return to the project itself?
## Post #170
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2014-10-30T06:36:43+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (I CAN TALK!?!? 

> Reply from HugoPeters
>
> odrin wrote:i doubt this will end up as more than a glorified content extractor. just being realistic.
Excuse me, but...



It's funny because this engine won't be able to extract a single resource.
I'd have to make another program purely for extracting resources.
Have you even seen the video updates I posted??


I'm glad to hear people are excited over this project and want me to release it, but shall we now put down this topic for a while and return to the project itself?

The fact I'm entering here is to see any progress of your project, not any legal or ethics discussions, so you can continue 

For legal issues, worry about that when the project is finished and you'll see what's more convenient for you.
## Post #171
- Username: d875j
- Rank: advanced
- Number of posts: 52
- Joined date: Sun Jun 17, 2012 10:32 am
- Post datetime: 2014-10-30T07:08:44+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (I CAN TALK!?!? 

I say keep it up and please allow us to run from pc and have adjustable graphics settings and ect. I like to play this on my beast rig.
## Post #172
- Username: Darko
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-11-07T01:40:10+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (I CAN TALK!?!? 

swag yolo

Been really busy with university lately, had two exams this week so didn't really have time to work on the project, BUT I did refine a lot of things.
Biggest thing is the updated MeshConstructor. I already spotted that quite a bit of the area meshes seemed to be missing, and I now figured out why.
Not going into the details, but I added support for that, which results in much more complete scenery.

And today I added quite a few general functions to my kernel, and also used a little trick to display Bink videos: the official viewer.
I just launch a process of the player using the video requested by the script, so now I can kinda see the video.

It's hacky, but it works for the time. I'm actually waiting on cra0 (wink) to provide me with something to make everything way easier.

Here's a vid: https://www.youtube.com/watch?v=JtcnL9PuOII

NOTE: because of the updated MeshConstructor, you can see all of the planes the "wind effect" is projected on in the Apocalypse scene (first one in the video).
NOTE 2:I tried to make this 60 FPS, but after 4 corrupted conversions I gave up and used Camtasia's standard shit. I'll post a video made using Fraps some time later... maybe. Also I have no fucking clue why it's lagging at certain points, it was smooth when I recorded it. ~_~ If anyone has any suggestions for good, reliable 60 FPS desktop recording..... please let me know!
NOTE 3: Did y'all know there's a subscribe button for the topic? That way you get an email when there's a new reply. Might be something to check out for those who want to stay up to date
## Post #173
- Username: d875j
- Rank: advanced
- Number of posts: 52
- Joined date: Sun Jun 17, 2012 10:32 am
- Post datetime: 2014-11-07T04:53:08+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (I CAN TALK!?!? 

> Reply from HugoPeters
>
> swag yolo

Been really busy with university lately, had two exams this week so didn't really have time to work on the project, BUT I did refine a lot of things.
Biggest thing is the updated MeshConstructor. I already spotted that quite a bit of the area meshes seemed to be missing, and I now figured out why.
Not going into the details, but I added support for that, which results in much more complete scenery.

And today I added quite a few general functions to my kernel, and also used a little trick to display Bink videos: the official viewer.
I just launch a process of the player using the video requested by the script, so now I can kinda see the video.

It's hacky, but it works for the time. I'm actually waiting on cra0 (wink) to provide me with something to make everything way easier.

Here's a vid: https://www.youtube.com/watch?v=JtcnL9PuOII

NOTE: because of the updated MeshConstructor, you can see all of the planes the "wind effect" is projected on in the Apocalypse scene (first one in the video).
NOTE 2:I tried to make this 60 FPS, but after 4 corrupted conversions I gave up and used Camtasia's standard shit. I'll post a video made using Fraps some time later... maybe. Also I have no fucking clue why it's lagging at certain points, it was smooth when I recorded it. ~_~ If anyone has any suggestions for good, reliable 60 FPS desktop recording..... please let me know!
NOTE 3: Did y'all know there's a subscribe button for the topic? That way you get an email when there's a new reply. Might be something to check out for those who want to stay up to date

Wonderful work man.
## Post #174
- Username: mirh
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-11-07T23:41:09+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (I CAN TALK!?!? 

Small experiment:

A kernel access indicator viewer thingy.

Fhun.
## Post #175
- Username: lion589
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-11-08T16:20:38+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (I CAN TALK!?!? 

Did some cleaning to the debugger, and added trophies!
## Post #176
- Username: d875j
- Rank: advanced
- Number of posts: 52
- Joined date: Sun Jun 17, 2012 10:32 am
- Post datetime: 2014-11-11T23:25:35+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (I CAN TALK!?!? 

Nice work really love it.
## Post #177
- Username: mirh
- Rank: n00b
- Number of posts: 19
- Joined date: Wed Nov 19, 2014 3:05 am
- Post datetime: 2014-11-19T22:12:15+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (I CAN TALK!?!? 

> Reply from HugoPeters
>
> 
You've probably already seen it, but I did already release a (poorly made lol) file extractor that also exports the audio to .mp3.

Anyways here is one fucking epic (unused) track, which I can't remember of where it came from:
http://www.djek.nl/shit/beyond/EB89.mp3Why not plain .wav? Isn't lossless supposed to be better (and more flexible)? :p
Besides, I remember a similar music was played in the ending credits

> Reply from HugoPeters
>
> michalss wrote:Hi Hugo,

What exactly is your goal in here mate ? Are you actually want to make it work and render on PC ? Include controller functionality ?
Well, I haven't set an exact goal, but I am trying to make it work on PC, yes.
As long as I don't get 100% stuck with something I'm just going to keep on reversing it and making it work on PC!

Note that Quantic Dream has been using this format since Fahrenheit, and they're probably not going to give up on it, so with a bit of luck all of their future games are going
to be playable on PC at some point!This make me remember [that guy](http://www.moddb.com/mods/fahrenheit-indigo-prophecy-hd-mod-1080p) that really went heavy with Fahrenheit reverse engineering. He could even find a set of tools called Quantic Dream Tools

> Reply from HugoPeters
>
> Mr.Mouse wrote:That is why I said contacting Sony when there's a version that is playable only (like a beta version). Not before. And also making sure a lot of people have already tested it. (it is public).
Hmm, no, Sony would probably not like it for a couple of reasons...
1) They own copyright to Beyond (in fact, they own the IP and trademark by a 100%)
2) They're very serious about their exclusives (and haven't released a single exclusive on any non-PS platform)
3) Quantic Dream probably has a "build for PC" button somewhere, so why take a non-official version?
4) There's a PS4 version coming out with new scenes, this could heavily impact sales
5) Windows is owned by Microsoft... Microsoft & Sony aren't exactly friends...1) I bought the game. So I guess you did. 0 copyright problems since you aren't sharing any QD file. Just your [original work](http://en.wikipedia.org/wiki/Clean_room_design).  It's no different from pcsx2 status. 
I couldn't find the exact post where one of the developers said that they had already got in touch with SCEE, but I remember the only thing sony required was: no BIOS (and of course no illegal ISOs) and we'll be fine. 

2) Of course they are. Though, I think it's more like "fuck xbox", "pc, who cares?" thing. Even though I believe any [XDev](http://en.wikipedia.org/wiki/SCE_Worldwide_Studios#XDev) partner can suspend their "benefit" at any time (as demonstrated by developer Housemarque)

3) Well, actually QD even promised [2 games](http://web.archive.org/web/20051031120514/http://www.quanticdream.com/pages/frameset_pub.php?lg=us) in 2005, without console biases. Even heavy rain was [coming to pc](http://web.archive.org/web/20070101044829/http://www.quanticdream.com/downloads/news/HR_PR1_050706.pdf#page=2). This until the "[partnership](http://web.archive.org/web/20070928010136/http://www.quanticdream.com/)". 
And indeed... in all fairness.. I think it was a wise move after all.. What other publisher could give you 30milllion dollars for a third person game without gunfires around every corner and a rambo-style protagonist ?
They could have even avoided to [say](http://www.officialplaystationmagazine.co.uk/2013/03/22/beyond-two-souls-ps3-preview-a-last-hurrah-for-current-gen/) some [BS](http://www.gamespot.com/articles/quantic-ps4-like-the-pc-of-2014-or-2015/1100-6407724/) notwithstanding, imo. 

4) Again, this is not supposed to be piracy (i.e. diminish sales)

5) Lol. Really: if there's a company hating gaming on windows, that's microsoft. Seriously, no shit. 
Just look at the last E³.. At least sony had some co-developed indie games that are even available even on PC. 
Moreover I don't remember MS allowing cross-platform multiplayer like it happens with the PS3 versions of final fantasy 14 and portal 2...

> Reply from HugoPeters
>
> 
What I will do with it.. well I've already gotten tons of requests for a model exporter, so that's what I'm probably NOT going to release XD (just for the plain reason that there are many perverts out there and I think it's illegal)
> Reply from HugoPeters
>
> And another reason: I've seen what can happen with game models... and especially because there are naked models in Beyond, I know I will see them back at some places where I'd rather not see them.I perfectly see your point. After all I'm pretty sure everybody in here had heard about [this](http://www.polygon.com/2013/10/22/4865768/report-sony-cracking-down-on-beyond-two-souls-nude-leak). 
Though I don't think you'd questioned about what legal issues a texture dumped from your own game could arise. 
And indeed that was a lapse, a mistake. Just some [too zealous](http://web.archive.org/web/20131106175950/http://eskimopress.com/news/games/item/431-ellen-page-not-suing-for-leaked-nude-pictures) PR guys. There's nothing different from the usual modding process

> Reply from lion589
>
> Mr.Mouse wrote:

Of course, there's no point in creating a conversion if nobody can play it.  I'm sure XeNTaX will be able to host some alpha or beta demo versions of it at some point somewhere. Meanwhile, by the time it reaches advanced beta stage you may want to contact Sony directly to see if they are willing to publish it / endorse it.  As for the model exporter, there would be no harm if there was one, or for instance in the form of support for Noesis. Talk to Rich Whitehouse about that (MrAdults).Contacting Sony about this project it's really a bad idea because they'll stop this work immediately, and as for the model I really wish if he could release it.
> Reply from HugoPeters
>
> 
Nah, contacting Sony would probably be the worst idea honestly, I'd rather send a direct email to David Cage (CEO & Writer of Quantic Dream).
But even he could easily sue me.I don't actually think we are doing something illegal. We shouldn't neither act likewise. 
I'm not saying I'd die to know Sony/QD opinion, though we shouldn't certainly hide like burglars. 

Even though, who knows.. mr. cage could even be secretly a fan of God Gabe.if you know what I mean
In this case consequences might range from a simple good work boy, to a consecration on mount Olympus. 
Otherwise, at least my heart will be able to know if it's the case to rest, forever, in piece. I wonder when I'll be able to play next QD pearl. 


Nevertheless, thank you again for your work. It's magnificent.
## Post #178
- Username: mono24
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-11-19T22:44:39+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (I CAN TALK!?!? 

Holy shit. Okay this is a big one.
I'm not really in the mood to talk about the legal stuff, so I'm going to leave most of that aside (for the moment) 

> Reply from mirh
>
> HugoPeters wrote:
You've probably already seen it, but I did already release a (poorly made lol) file extractor that also exports the audio to .mp3.

Anyways here is one fucking epic (unused) track, which I can't remember of where it came from:
http://www.djek.nl/shit/beyond/EB89.mp3
Why not plain .wav? Isn't lossless supposed to be better (and more flexible)? :p
Besides, I remember a similar music was played in the ending credits
Because Beyond actually stores all audio as MP3! (split up into 1 second chunks)

> Reply from mirh
>
> 1) I bought the game. So I guess you did. 0 copyright problems since you aren't sharing any QD file. Just your original work.  It's no different from pcsx2 status. 
I couldn't find the exact post where one of the developers said that they had already got in touch with SCEE, but I remember the only thing sony required was: no BIOS (and of course no illegal ISOs) and we'll be fine.
Of course I bought the game. I own two copies even. But hmm. The license does say "no unauthorized use on any system other than PS3"... but I guess that entails the main executable.

> Reply from mirh
>
> Nevertheless, thank you again for your work. It's magnificent.
Thank you =)


Unfortunately I've been really busy lately with university (and am at the moment), so I don't have the time to write an extensive reply, but thanks for your huge and interesting post, that must have been a hell to write 

[Edit].........................................................did you actually "thank" all of my posts? O_______O That's INSANE. XD but really awesome!!!!!!!!!!!
## Post #179
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2014-11-19T22:54:44+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (I CAN TALK!?!? 

Assumptions kill ambition. Sony isn't some Demon Hell Hole that is stuffed to the brim with everything but humans that will swallow you whole the moment you step on their doorstep (or Hell Portal) to show them your excellent game conversion that everybody's playing on the PC. Seriously. You have to start thinking out of the box, and get rid of your assumptions.
## Post #180
- Username: mirh
- Rank: n00b
- Number of posts: 19
- Joined date: Wed Nov 19, 2014 3:05 am
- Post datetime: 2014-11-19T23:21:11+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (I CAN TALK!?!? 

> Reply from HugoPeters
>
> 
Because Beyond actually stores all audio as MP3! (split up into 1 second chunks)Oh, that's ok then. 

> Reply from HugoPeters
>
> 
Of course I bought the game. I own two copies even. But hmm. The license does say "no unauthorized use on any system other than PS3"... but I guess that entails the main executable.License may even say that but, again, if [pcsx2 still is alive](http://forums.pcsx2.net/Thread-Admin-or-Mod-please-email-me-about-this?page=5) (and that's trying to emulate every game, not just one!) I don't even see the furthest possibility of legal problems. 
Especially when I think you did this with a "common" open source game engine and C#   

And besides, yes I actually did. It took me the whole afternoon to read (and thanks almost) every freaking message, but I'm absolutely thrilled about this. 
Really, when I first played the game.. I started at 2pm.. and I was with zoey starring at thunders at about 2am. I did even feel Aiden floating above me for the entire following day..   

And this was on my PS3 which I don't really love (cmon, couches are for pussies with downscaled graphics).
On PC.. good god

EDIT: and I still cannot believe the game that I liked more than every other... it's exactly the object of your unique work...
## Post #181
- Username: jadentheman
- Rank: n00b
- Number of posts: 18
- Joined date: Fri Oct 24, 2014 7:21 am
- Post datetime: 2014-11-20T02:43:43+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (I CAN TALK!?!?

This project is great and all, but I do have a few questions. Why Beyond Two Souls? and would you also reverse (if its comes) the PS4 game? It would have x86 coding, higher res textures, and maybe other bells and whistles.

Also does this open the door to reversing other PS3 exclusive games to PC? I mean wwe can talk about that later, but I just found this tiopic and all this info is shown to me at once.
## Post #182
- Username: mirh
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-11-20T02:56:43+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (I CAN TALK!?!?

> Reply from mirh
>
> HugoPeters wrote:
Because Beyond actually stores all audio as MP3! (split up into 1 second chunks)Oh, that's ok then. 
HugoPeters wrote:
Of course I bought the game. I own two copies even. But hmm. The license does say "no unauthorized use on any system other than PS3"... but I guess that entails the main executable.License may even say that but, again, if pcsx2 still is alive (and that's trying to emulate every game, not just one!) I don't even see the furthest possibility of legal problems. 
Especially when I think you did this with a "common" open source game engine and C#   

And besides, yes I actually did. It took me the whole afternoon to read (and thanks almost) every freaking message, but I'm absolutely thrilled about this. 
Really, when I first played the game.. I started at 2pm.. and I was with zoey starring at thunders at about 2am. I did even feel Aiden floating above me for the entire following day..   

And this was on my PS3 which I don't really love (cmon, couches are for pussies with downscaled graphics).
On PC.. good god

EDIT: and I still cannot believe the game that I liked more than every other... it's exactly the object of your unique work...
C# is actually the best programming language of All Time.   
That aside, I must admit Beyond made me depressed for around 4 days.

I like consoles (including the PS3) because developers can easily optimize for it in comparison to PC (for example, Edge SDK).

Now the only thing we need is Depth of Field... Wait what's that? The Paradox 3D team is working on it??

> Reply from jadentheman
>
> Why Beyond Two Souls?
Because I fucking love it!

> Reply from jadentheman
>
> would you also reverse (if its comes) the PS4 game?
I'm definitely going to take a look at it once it comes out and it can be dumped.

> Reply from jadentheman
>
> Also does this open the door to reversing other PS3 exclusive games to PC?
Other PS3 exclusive games developed by Quantic Dream: yes.
Most other companies do not store literally everything in the game's external data like Quantic Dream does. As soon as any important part is in the main executable it suddenly gets a million times more difficult as that would require assembly to be decompiled, which for example I can't do.
So... as long as this project doesn't inspire other people, probably no. I've gotten some "requests" to do the same with The Last Of Us as what I'm doing with Beyond, but there's a high chance that's already impossible. Let's just say I got lucky with Beyond.

> Reply from jadentheman
>
> I just found this tiopic and all this info is shown to me at once.
Have fun reading/watching/listening! There is indeed a lot already!
## Post #183
- Username: jadentheman
- Rank: n00b
- Number of posts: 18
- Joined date: Fri Oct 24, 2014 7:21 am
- Post datetime: 2014-11-22T14:32:05+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (I CAN TALK!?!?

I wonder also since it's your build, that if you get far enough you can add something like TressFX or PhysX?
## Post #184
- Username: mirh
- Rank: n00b
- Number of posts: 19
- Joined date: Wed Nov 19, 2014 3:05 am
- Post datetime: 2014-11-22T16:28:25+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (I CAN TALK!?!?

> Reply from jadentheman
>
> I wonder also since it's your build, that if you get far enough you can add something like TressFX or PhysX?
You mad?
The game is already using Havok.. no way physics engine could be changed
TressFX would require adjustments to models I think (in addition to shaders and engine things..)

It has already been used with [unity](http://kennux.net/wordpress/?p=13) but this project has OGRE... and porting code from radeon SDK would be yet another hassle (assuming it may even be vaguely possible)
## Post #185
- Username: mono24
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-11-22T16:31:51+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (I CAN TALK!?!?

> Reply from mirh
>
> jadentheman wrote:I wonder also since it's your build, that if you get far enough you can add something like TressFX or PhysX?
You mad?
The game is already using Havok.. no way physics engine could be changed
TressFX would require adjustments to models I think (in addition to shaders and engine things..)

It has already been used with unity but this project has OGRE... and porting code from radeon SDK would be yet another hassle (assuming it may even be vaguely possible)
I'm not using OGRE anymore but Paradox, which has BulletPhysics built-in. If I were to implement it, that's what I would probably use.

But, I've got an update coming up that everyone may or may not like.

Also, this is my 100th post, which I actually wanted to spend on something else... but kinda can't. XD
More soon, I guess?
## Post #186
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2014-11-24T21:14:14+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (I CAN TALK!?!?

100th post or not, your progress this far is quite impressive   

now you've looked at most of the data formats and created a lua kernel are you aiming for features (textures, etc) or compatability (more lua hooks)?

also, you should absolutely create a blog - [https://ghost.io/](https://ghost.io/)
## Post #187
- Username: mirh
- Rank: n00b
- Number of posts: 19
- Joined date: Wed Nov 19, 2014 3:05 am
- Post datetime: 2014-11-25T15:03:02+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (I CAN TALK!?!?

> Reply from WRS
>
> also, you should absolutely create a blog - https://ghost.io/
[http://heap.djek.nl/](http://heap.djek.nl/)
## Post #188
- Username: zubren
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-12-01T00:38:16+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (I CAN TALK!?!?

We all knew it had to happen some day!

:(
I was recently approached by the co-CEO of Quantic Dream. He told me that he is aware of this project and would like me to stop working on it. He and the rest were amused by it though!

:)
I was also contacted by the CTO of Quantic Dream. We are currently in talk about some things...

But yeah, the inevitable happened. I'm afraid I can't continue on the port / tools. Sorry everybody, it's been a blast. A big thanks to everybody who supported / helped me with the project :D
Even though the port might be legal, I want to keep everyone at Quantic Dream as allies, so I'm not going to be disobedient.

To be continued...?
## Post #189
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2014-12-01T21:16:28+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (I CAN TALK!?!?

thats too bad for us - but good for you for complying    hopefully they offered you a job!

with an engine built around lua, i'd expect a pc port!
## Post #190
- Username: mono24
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-12-01T21:19:03+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (I CAN TALK!?!?

> Reply from WRS
>
> hopefully they offered you a job!
Maybe...
## Post #191
- Username: jadentheman
- Rank: n00b
- Number of posts: 18
- Joined date: Fri Oct 24, 2014 7:21 am
- Post datetime: 2014-12-02T00:09:57+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (I CAN TALK!?!?

Shame you can't finish, but also a possibility is open for an official PC release? May or may not happen though as Quantic Dream is a Sony 2nd Party and the rumored PS4 release is coming, but hey.

Well maybe someday someone will continue your work lol. Good luck for future endeavors
## Post #192
- Username: zubren
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Apr 07, 2013 2:25 pm
- Post datetime: 2014-12-02T02:10:00+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (I CAN TALK!?!?

> Reply from HugoPeters
>
> I was recently approached by the co-CEO of Quantic Dream. He told me that he is aware of this project and would like me to stop working on it. He and the rest were amused by it though!It was bound to happen some day. No worries, you showed off a ton of cool stuff, not to mention skills.

> Reply from HugoPeters
>
> I was also contacted by the CTO of Quantic Dream. We are currently in talk about some things...]Best possible outcome IMO. Congrats
## Post #193
- Username: mirh
- Rank: n00b
- Number of posts: 19
- Joined date: Wed Nov 19, 2014 3:05 am
- Post datetime: 2014-12-04T23:02:41+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (I CAN TALK!?!?

Good God.   

My heart is bleeding....I would have sold my ass to see Jodie on PC one day..
I hope you may reach a deal... 

Best regards. Respect.
## Post #194
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2014-12-06T22:13:18+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (I CAN TALK!?!?

Perhaps now we can work on a model viewer for Omikron: The Nomad Soul. David Cage might not like any of us extracting naked Ellen Page, but I don't think Quantic Dream would mind us ripping the Cybernetic Ghost of David Bowie.
## Post #195
- Username: d875j
- Rank: advanced
- Number of posts: 52
- Joined date: Sun Jun 17, 2012 10:32 am
- Post datetime: 2014-12-07T03:23:04+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (I CAN TALK!?!?

> Reply from Mirrorman95
>
> Perhaps now we can work on a model viewer for Omikron: The Nomad Soul. David Cage might not like any of us extracting naked Ellen Page, but I don't think Quantic Dream would mind us ripping the Cybernetic Ghost of David Bowie.
Not to sure naked Ellen Page be great in GTA IV or some game.
## Post #196
- Username: d875j
- Rank: advanced
- Number of posts: 52
- Joined date: Sun Jun 17, 2012 10:32 am
- Post datetime: 2014-12-07T03:23:26+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (THAT'S ALL FOLK

> Reply from Mirrorman95
>
> Perhaps now we can work on a model viewer for Omikron: The Nomad Soul. David Cage might not like any of us extracting naked Ellen Page, but I don't think Quantic Dream would mind us ripping the Cybernetic Ghost of David Bowie.
Not to sure naked Ellen Page be great in GTA IV or some game.
## Post #197
- Username: mirh
- Rank: n00b
- Number of posts: 19
- Joined date: Wed Nov 19, 2014 3:05 am
- Post datetime: 2014-12-07T11:54:11+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (THAT'S ALL FOLK

> Reply from Mirrorman95
>
> Perhaps now we can work on a model viewer for Omikron: The Nomad Soul. David Cage might not like any of us extracting naked Ellen Page, but I don't think Quantic Dream would mind us ripping the Cybernetic Ghost of David Bowie.
Quantic Dream [neither care](http://web.archive.org/web/20131106175950/http://eskimopress.com/news/games/item/431-ellen-page-not-suing-for-leaked-nude-pictures) if you rip Ellen's vulva texture..

EDIT: yes, perhaps I said it in a harsh way. But the point is that since the dawn of time users modded games (that they bought and legally own, of course). Why this should be now a problem? Because it's a PS3 game? Because there are textures depicting skin? You could even use a 3D printer to make a replicant of Jodie/Ellen but then? That's still not Ms. Page.
## Post #198
- Username: ngovandang
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-12-07T13:22:44+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (THAT'S ALL FOLK

> Reply from Mirrorman95
>
> Perhaps now we can work on a model viewer for Omikron: The Nomad Soul. David Cage might not like any of us extracting naked Ellen Page, but I don't think Quantic Dream would mind us ripping the Cybernetic Ghost of David Bowie.

> Reply from d875j
>
> Mirrorman95 wrote:Perhaps now we can work on a model viewer for Omikron: The Nomad Soul. David Cage might not like any of us extracting naked Ellen Page, but I don't think Quantic Dream would mind us ripping the Cybernetic Ghost of David Bowie.
Not to sure naked Ellen Page be great in GTA IV or some game.

> Reply from mirh
>
> Mirrorman95 wrote:Perhaps now we can work on a model viewer for Omikron: The Nomad Soul. David Cage might not like any of us extracting naked Ellen Page, but I don't think Quantic Dream would mind us ripping the Cybernetic Ghost of David Bowie.
Quantic Dream neither care if you rip Ellen's vulva texture..
Can we please stop this discussion right now? If you guys are really that obsessed over some fake textures, go discuss it somewhere else. It's disrespectful towards Ellen, she has put some amazing work into Beyond: Two Souls, and the only thing everyone is talking about is a texture that isn't even her's. Btw, this is exactly why I didn't want to release a model extractor from the beginning.
## Post #199
- Username: mono24
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2014-12-08T09:02:26+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (THAT'S ALL FOLK

Project is over no need to come back to it! LOCK
## Post #200
- Username: WRS
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2014-12-09T21:09:30+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (THAT'S ALL FOLK

Actually, I would say the op owns the right in this case to stop posting in this thread or continue, not us.

Back open.
## Post #201
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2014-12-10T02:05:38+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (THAT'S ALL FOLK

i'm glad this is back open!

staying on track - after re-reading your research and videos i went and bought the game (so far i think the narrative works well and the acting really incredible). but your progress was inspirational. someone else said they started porting a game - but its a huge technical challenge to reimagine the whole engine.

would love to know how far you got rendering the characters with your new engine. you posted the textured models, but how far off was the skeleton/animation research? obviously with some of the rendered scenes, inclusion of the characters in the intro sequence would make a fantastic demo.

edit

so i'm also pretty amazed at how quickly you made the switch from gamemaker (original exporter tool) to c# - particularly with threading. is that something you picked up for this project?
## Post #202
- Username: mirh
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-12-10T09:10:01+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (THAT'S ALL FOLK

> Reply from WRS
>
> i'm glad this is back open!

staying on track - after re-reading your research and videos i went and bought the game (so far i think the narrative works well and the acting really incredible). but your progress was inspirational. someone else said they started porting a game - but its a huge technical challenge to reimagine the whole engine.
Could you link me to that topic? 

> Reply from WRS
>
> 
would love to know how far you got rendering the characters with your new engine. you posted the textured models, but how far off was the skeleton/animation research? obviously with some of the rendered scenes, inclusion of the characters in the intro sequence would make a fantastic demo.
Aside from some rotation issues I pretty much completely reversed the skeleton format, however, not vertex skinning, this would've been the next step towards animation. I took a few brief looks at the animation data, but I couldn't get any sensical data out of it, so it's most likely compressed.

My engine already has support to load in models when the game's script calls for it, so you can see the models appear at (0, 0, 0), but without animation it's pretty boring 

> Reply from WRS
>
> 
so i'm also pretty amazed at how quickly you made the switch from gamemaker (original exporter tool) to c# - particularly with threading. is that something you picked up for this project?
Yup, I was up and running in about 2 days. All of my C# knowledge that I have now is indeed because of this project. Every time I didn't know how to do something I just googled it or asked someone, and then moved on.
## Post #203
- Username: Ndidi
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Dec 11, 2014 1:19 pm
- Post datetime: 2014-12-11T05:27:53+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (THAT'S ALL FOLK

Can't wait for INFRA Viewer
## Post #204
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2014-12-13T04:43:59+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (THAT'S ALL FOLK

I'm sorry to bump this again but I'm curious, What did you talk about with the CTO of Quantic Dream?? Did they offer you a job?? Or it's a secret .
## Post #205
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2014-12-19T09:23:02+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (THAT'S ALL FOLK

Which lua decompiler do you use?
## Post #206
- Username: jadentheman
- Rank: n00b
- Number of posts: 18
- Joined date: Fri Oct 24, 2014 7:21 am
- Post datetime: 2014-12-30T23:39:11+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (THAT'S ALL FOLK

This thread got mentioned on NeoGAF
[http://www.neogaf.com/forum/showthread.php?t=962176](http://www.neogaf.com/forum/showthread.php?t=962176)

You have arrived OP!!
## Post #207
- Username: mono24
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-12-31T00:43:04+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (THAT'S ALL FOLK

> Reply from jadentheman
>
> This thread got mentioned on NeoGAF
http://www.neogaf.com/forum/showthread.php?t=962176

You have arrived OP!!
Wow, that's awesome, thanks for linking me that.
I'll post a comment on there as soon as my account gets activated...
## Post #208
- Username: Ndidi
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Dec 11, 2014 1:19 pm
- Post datetime: 2014-12-31T18:52:56+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (THAT'S ALL FOLK

> Reply from HugoPeters
>
> Wow, that's awesome, thanks for linking me that.
I'll post a comment on there as soon as my account gets activated...
  Happy New Year! Make a gift to us, release extractor for B:TS models!
## Post #209
- Username: ngovandang
- Rank: veteran
- Number of posts: 121
- Joined date: Sun Aug 10, 2014 5:33 pm
- Post datetime: 2015-03-17T20:42:36+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (THAT'S ALL FOLK

Hello, anyone can share to me  Jodie Holmes model?
## Post #210
- Username: mono24
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2015-03-17T23:26:25+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (THAT'S ALL FOLK

> Reply from ngovandang
>
> Hello, anyone can share to me  Jodie Holmes model?
No.
## Post #211
- Username: ngovandang
- Rank: veteran
- Number of posts: 121
- Joined date: Sun Aug 10, 2014 5:33 pm
- Post datetime: 2015-03-18T09:07:52+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (THAT'S ALL FOLK

> Reply from HugoPeters
>
> ngovandang wrote:Hello, anyone can share to me  Jodie Holmes model? 
No.

Why? T.T)
## Post #212
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2015-03-18T10:05:28+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (THAT'S ALL FOLK

> Reply from ngovandang
>
> HugoPeters wrote:ngovandang wrote:Hello, anyone can share to me  Jodie Holmes model? 
No.

Why? T.T)

If you want it rip it yourself, this forum doesn't rip models and share them with eachother, its against forum rules to share content we do not own, especially if we've no idea if the requesting party owns them. Its simply copyright law, don't share.
## Post #213
- Username: d875j
- Rank: advanced
- Number of posts: 52
- Joined date: Sun Jun 17, 2012 10:32 am
- Post datetime: 2015-03-25T10:03:34+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (THAT'S ALL FOLK

Kinda confused so does this mean the port still can happen. i heard PS4 port is coming and after that then said they wouldn't care after they get their profit.
## Post #214
- Username: patloonytoon
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Mar 15, 2012 8:39 am
- Post datetime: 2015-06-13T22:09:11+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (THAT'S ALL FOLK

Pretty bummed about all this great work not going to be released. Noticed it seems impossible to even get older versions. I really like QuanticDreams but wish they were a bit more accepting of fan creations. Back to the drawing board I guess :/
## Post #215
- Username: mono24
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2015-06-14T16:25:07+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (THAT'S ALL FOLK

> Reply from patloonytoon
>
> Pretty bummed about all this great work not going to be released. Noticed it seems impossible to even get older versions. I really like QuanticDreams but wish they were a bit more accepting of fan creations. Back to the drawing board I guess :/
To be fair, I took down most of what I released online voluntarily, Quantic Dream never forced me to anything, they only asked me to stop working on it. I removed the content because I wanted to sustain a healthy relation with QD.
## Post #216
- Username: mirh
- Rank: n00b
- Number of posts: 19
- Joined date: Wed Nov 19, 2014 3:05 am
- Post datetime: 2015-06-15T12:29:17+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (THAT'S ALL FOLK

> Reply from HugoPeters
>
> cause I wanted to sustain a healthy relation with QD.Implying there's a relation with QD atm?
## Post #217
- Username: odrin
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Mon May 23, 2011 9:43 am
- Post datetime: 2015-08-29T22:45:33+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (THAT'S ALL FOLK

qd only cares about keeping their ip safe and secure. if it was possible to do it through diplomacy and implied future support(aka lies), then even better.

don't expect them to give fuck all to the pc community. beyond two souls will never see the light of existence on the pc platform.

and you delete loads of hard work for nothing.

ps whoever notified qd, shame on you for dashing this poor boy's dreams and efforts.
## Post #218
- Username: mirh
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2015-08-29T23:24:05+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (THAT'S ALL FOLK

> Reply from odrin
>
> qd only cares about keeping their ip safe and secure. if it was possible to do it through diplomacy and implied future support(aka lies), then even better.

don't expect them to give fuck all to the pc community. beyond two souls will never see the light of existence on the pc platform.

and you delete loads of hard work for nothing.

ps whoever notified qd, shame on you for dashing this poor boy's dreams and efforts.
No worries or hate towards QD... I'm still in contact with them, and have at least got an internship once I reach that point in my bachelor, and possibly a job after that!
And I bet they would "give a fuck" about the PC community if Sony wasn't paying them good money to keep the games exclusive to their platform  
[Edit] Btw, QD was notified from within the company. Someone inside found this thread, then linked it through to the Co-CEO, who contacted me.
## Post #219
- Username: mirh
- Rank: n00b
- Number of posts: 19
- Joined date: Wed Nov 19, 2014 3:05 am
- Post datetime: 2015-08-30T21:09:51+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (THAT'S ALL FOLK

> Reply from HugoPeters
>
> And I bet they would "give a fuck" about the PC community if Sony wasn't paying them good money to keep the games exclusive to their platformTo be honest, the [official rationale](http://www.ign.com/articles/2013/03/23/heavy-rain-dev-to-remain-playstation-exclusive) is that «Sony provides so much creative freedom that the studio isn’t even thinking of partnering with anyone else» 
and that «[they] wouldn’t be working with Sony as a publisher [by going multi-platform]». 

Which technically can either simply imply Sony is not going to publish on other platforms (in which case QD is free to use, let's say their [GOG](http://www.gog.com/games&#35devpub=quantic_dream) and [Steam](http://store.steampowered.com/search/?developer=Quantic%20Dream) accounts)
or that they are the evil and oblige the lock down to the single platform.

And for as odd as it sounds, it's not like there ain't already lots of [games](https://en.wikipedia.org/wiki/List_of_PlayStation_4_games#List) sponsored by Sony with "console exclusive" tagline. 
So imo, this is a pretty big unknown

They also say that «sticking with PlayStation allows the team to focus on one platform and get the best out of it» and that's imo the most possibly concrete argument, but I believe that your work somewhat question this assertion (and I mean.. kudos to their engine for this pretty high level abstraction). 
... deep down I feel they already know these things, be it PC [hardware](http://www.gamespot.com/articles/quantic-ps4-like-the-pc-of-2014-or-2015/1100-6407724/) or [modding](http://www.neogaf.com/forum/showthread.php?t=964900) capabilities. Hopefully with time there'll be more people recognizing this ( ͡° ͜ʖ ͡°) 


> Reply from HugoPeters
>
> [Edit] Btw, QD was notified from within the company. Someone inside found this thread, then linked it through to the Co-CEO, who contacted me.I feel like having shared this on reddit and PCSX2 boards may have helped just a little bit to raise attentions
## Post #220
- Username: hoang vinh
- Rank: n00b
- Number of posts: 13
- Joined date: Sun Nov 22, 2015 3:54 pm
- Post datetime: 2015-11-25T06:42:10+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (THAT'S ALL FOLK

The ps4 remastered is released today, we have 2 option from the start: play original way or chronicle order. It seem the work of  your made them to do that.
 sorry my bad english
## Post #221
- Username: Fr4gMovi3
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Dec 12, 2015 6:36 pm
- Post datetime: 2015-12-12T11:12:57+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (THAT'S ALL FOLK

Please release model/texture extractor
## Post #222
- Username: U+0300l
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Mar 31, 2016 7:58 pm
- Post datetime: 2016-03-31T12:04:58+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (THAT'S ALL FOLK

> Reply from HugoPeters
>
> patloonytoon wrote:Pretty bummed about all this great work not going to be released. Noticed it seems impossible to even get older versions. I really like QuanticDreams but wish they were a bit more accepting of fan creations. Back to the drawing board I guess :/
To be fair, I took down most of what I released online voluntarily, Quantic Dream never forced me to anything, they only asked me to stop working on it. I removed the content because I wanted to sustain a healthy relation with QD.

So let me get this straight - You just scrapped every progress made so far, for a pat on the back and non-existent, one-way relation with QD? Wow, good job there, son.    

I know C# but not much about 3D, but maybe I can try do it myself. Open sourced. At least it's worth trying. If  somebody have older versions stored somewhere on their drives so I could pick them up and do faster research, please PM me.
## Post #223
- Username: mono24
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2016-03-31T12:31:46+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (THAT'S ALL FOLK

> Reply from U+0300l
>
> HugoPeters wrote:patloonytoon wrote:Pretty bummed about all this great work not going to be released. Noticed it seems impossible to even get older versions. I really like QuanticDreams but wish they were a bit more accepting of fan creations. Back to the drawing board I guess :/
To be fair, I took down most of what I released online voluntarily, Quantic Dream never forced me to anything, they only asked me to stop working on it. I removed the content because I wanted to sustain a healthy relation with QD.

So let me get this straight - You just scrapped every progress made so far, for a pat on the back and non-existent, one-way relation with QD? Wow, good job there, son.    

I know C# but not much about 3D, but maybe I can try do it myself. Open sourced. At least it's worth trying. If  somebody have older versions stored somewhere on their drives so I could pick them up and do faster research, please PM me.
"Non-existent, one-way relation with QD", meanwhile I'm having technical discussions with them and my internship is set.
## Post #224
- Username: U+0300l
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Mar 31, 2016 7:58 pm
- Post datetime: 2016-03-31T16:15:29+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (THAT'S ALL FOLK

> Reply from HugoPeters
>
>  meanwhile I'm having technical discussions with them and my internship is set.

That may or may not be true. They could hire you after your internship ends, not hire you at all, or fire after a month. I don't really care.

 I guess all of this was your work so you had the full right to remove it. That doesn't change the fact that it was a selfish move, and now this project is fully dead. You could just leave it somewhere, remove all your references to it (like email/credits) and somebody else would happily pick it up  where it ended. Especially when QD didn't  even wanted you to remove it.  
Just look at your signature. What's the point in advertising something/getting donations for it and then simply canceling it? There, I said it. I'm just pissed how it all went down.
## Post #225
- Username: mono24
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2016-03-31T16:40:48+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (THAT'S ALL FOLK

> Reply from U+0300l
>
> HugoPeters wrote: meanwhile I'm having technical discussions with them and my internship is set.

That may or may not be true. They could hire you after your internship ends, fire you after a month. I don't really care.

 I guess all of this was your work so you had the full right to remove it. That doesn't change the fact that it was selfish, and now this project is fully dead. You could just leave it somewhere, remove all your references to it (like name/redits) and somebody else would happily pick it up  where it ended. Especially when QD didn't  even wanted you to remove it.  Just look at your signature. What's the point in advertising something and then simply canceling it? There, I said it. Best of luck in your new job. I'm just pissed how it all went down.
You know what is selfish? If QD asked me to stop porting and I kept the assets up. 
You know what else is selfish? Venting to someone who decided to cancel their own project which means that you can't have it for your own benefit.

For the record, I haven't taken down the videos, which were the only things I released of the port in the first place lol, no one has the source or builds of it (except some people close to me, but those are deeply obfuscated and they wouldn't share them anyways).

Your anger and arrogance are quite misplaced here, I understand you might be disappointed that the project is off the table for now, but you completely seem to ignore my perspective, and since this was my own project that is the only thing that matters.

Also the banner in my signature I simply didn't bother to remove, I think it looks quite nice : )
## Post #226
- Username: U+0300l
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Mar 31, 2016 7:58 pm
- Post datetime: 2016-03-31T20:31:00+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (THAT'S ALL FOLK

> Reply from HugoPeters
>
> 
You know what is selfish? If QD asked me to stop porting and I kept the assets up.

That would be just plain ignorance and violation of copyright, but:
1. I'm not talking about in-game assets
2. They didn't asked you.

> Reply from HugoPeters
>
> 
You know what else is selfish? Venting to someone who decided to cancel their own project which means that you can't have it for your own benefit.
You mean for public benefit? Cuz no, again, your way of thinking is selfish. You just prove that all of this was made for a showcase, for your personal gain, not for people.  Thank god Linus Torvalds didn't thinked like that, I mean, this guy gave up so many times in the past, if he decided to scrap everything, we wouldn't have Linux today. 

> Reply from HugoPeters
>
> 
no one has the source or builds of it (except some people close to me, but those are deeply obfuscated

What was the point of obfuscating it. Was not it mean to be public? C# is easy to decompile  and deobfuscate anyway. 

Looks like all of  it was just a showcase for your own benefit. I was so hyped up in the recent months, I just hope that nobody gave you any donations, because they would be even more pissed off that I am now. And with that, I'm done in this topic.
## Post #227
- Username: Loomy
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Sep 12, 2015 9:16 am
- Post datetime: 2016-04-20T04:49:26+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (THAT'S ALL FOLK

Its truly amazing what Hugo & comrades pulled off, sad im so late to the party, but my sincere thx Hugo for leaving some crumbs behind ^^ scattered about, and YT stuff.  What hurts though is all the input & contributions by others that in a sense were lost to the world,or at least anyone outside the circle, alot of it could be used and is even needed for a good couple other games, both current  future.  Id like to think QD wouldnt mind casual & private poking about, within reason.  asset extraction while not impossible was always doomed from the start being A-List actors, and livemocap, its more than just their likeness, at least in public.  Still, even today, B2S  was then & still has some the highest visual fidelity out there on the PS3, while HR not so much, it was still groundbreaking in other aspects.  for aspiring devs & casual hobbyists with too much free time such as I, it makes for a great case study.  Also now that Ps4 versions out, and as time goes on, discussion & research on the topic will hopefully be less of a threat to their bottom line.
## Post #228
- Username: AnonBaiter
- Rank: veteran
- Number of posts: 82
- Joined date: Fri Oct 16, 2015 3:15 am
- Post datetime: 2016-05-06T18:21:20+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (THAT'S ALL FOLK

HugoPeters, just what exactly was your intention on working with this one? Couldn't you have just researched the files and be done with it?
Oh you say you want a PC version? If so, then why didn't you leave the PC porting work to Quantum Dream instead of yourself?
## Post #229
- Username: mono24
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2016-05-06T18:26:25+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (THAT'S ALL FOLK

> Reply from AnonBaiter
>
> HugoPeters, just what exactly was your intention on working with this one? Couldn't you have just researched the files and be done with it?
Oh you say you want a PC version? If so, then why didn't you leave the PC porting work to Quantum Dream instead of yourself?
Not sure what you're trying to say here, QD was never going to make a PC version
## Post #230
- Username: WRS
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2016-07-10T12:09:10+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (THAT'S ALL FOLK

Hi everyone, I finally got to unveil the thing I've been working on as lead programmer / tech lead for the past few months   

Please check it out! [https://www.youtube.com/watch?v=CXBGa5J9VbI](https://www.youtube.com/watch?v=CXBGa5J9VbI)

Also if you want to stay updated you can like our FB page! [https://www.facebook.com/SoulKnightOfficial](https://www.facebook.com/SoulKnightOfficial)
## Post #231
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2016-07-10T13:57:48+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (THAT'S ALL FOLK

> Reply from HugoPeters
>
> Hi everyone, I finally got to unveil the thing I've been working on as lead programmer / tech lead for the past few months   

Please check it out! https://www.youtube.com/watch?v=CXBGa5J9VbI

Also if you want to stay updated you can like our FB page! https://www.facebook.com/SoulKnightOfficial

Hey congratulations! The trailer looks fantastic - what engine are you using?
## Post #232
- Username: mono24
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2016-07-10T18:47:50+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (THAT'S ALL FOLK

> Reply from WRS
>
> HugoPeters wrote:Hi everyone, I finally got to unveil the thing I've been working on as lead programmer / tech lead for the past few months   

Please check it out! https://www.youtube.com/watch?v=CXBGa5J9VbI

Also if you want to stay updated you can like our FB page! https://www.facebook.com/SoulKnightOfficial

Hey congratulations! The trailer looks fantastic - what engine are you using?
Thanks a lot, glad you like it  We're using a slightly modified Unreal Engine 4.
## Post #233
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2016-07-21T22:52:50+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (THAT'S ALL FOLK

Excellent!!         
[https://www.facebook.com/permalink.php? ... 8469022795](https://www.facebook.com/permalink.php?story_fbid=1092960247405941&id=143458469022795)
## Post #234
- Username: U+0300l
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Mar 31, 2016 7:58 pm
- Post datetime: 2016-10-04T22:39:41+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (THAT'S ALL FOLK

> I've been working on as lead programmer / tech lead for the past few months

It's funny, especially when you stated that you were hired by the QD.

Mods, please lock this thread as the project is dead anyway.
## Post #235
- Username: Kett
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2016-10-04T23:56:59+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (THAT'S ALL FOLK

> Reply from U+0300l
>
> I've been working on as lead programmer / tech lead for the past few months 

It's funny, especially when you stated that you were hired by the QD.

Mods, please lock this thread as the project is dead anyway.
Welcome back!   

Must say, interesting to hear that I was working at QD.... DID I LIE??? Actually no I never said that lol. I was offered a position when I was 17, which was made into an internship.
If you actually read my posts you'd know I'm still doing my bachelor game dev... I'm tech lead of the project I'm doing for my university... in my 3rd year atm actually so next year the internship is happening.

Surprise, I'm a mod and this thread is not going to be locked.   

Also stop being so salty I don't own you anything, it was my own project dude
Contrary to your other statement on the top, QD did ask me, nicely I must say, to stop and not release anything - otherwise I wouldn't have stopped...
## Post #236
- Username: mono24
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-10-05T13:44:34+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (THAT'S ALL FOLK

Hi, just a friendly reminder. Please keep things civil, no need to become provocative and rude. I'll be keeping an eye on this thread.

Cheers
## Post #237
- Username: haskegasdodaske
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Apr 07, 2018 1:25 pm
- Post datetime: 2018-04-07T15:59:14+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (THAT'S ALL FOLK

> Reply from HugoPeters
>
> U+0300l wrote:I've been working on as lead programmer / tech lead for the past few months 

It's funny, especially when you stated that you were hired by the QD.

Mods, please lock this thread as the project is dead anyway.
Welcome back!   

Must say, interesting to hear that I was working at QD.... DID I LIE??? Actually no I never said that lol. I was offered a position when I was 17, which was made into an internship.
If you actually read my posts you'd know I'm still doing my bachelor game dev... I'm tech lead of the project I'm doing for my university... in my 3rd year atm actually so next year the internship is happening.

Surprise, I'm a mod and this thread is not going to be locked.   

Also stop being so salty I don't own you anything, it was my own project dude
Contrary to your other statement on the top, QD did ask me, nicely I must say, to stop and not release anything - otherwise I wouldn't have stopped...

FOR MORE YOU CAN SEE THIS LINK They are already ported models to pc 
https://crazy31139.deviantart.com/gallery/
## Post #238
- Username: mono24
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2018-04-19T00:17:35+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (THAT'S ALL FOLK

> Reply from haskegasdodaske
>
> 
FOR MORE YOU CAN SEE THIS LINK They are already ported models to pc 
https://crazy31139.deviantart.com/gallery/

<snip>

Hope you enjoy them I guess!  
Interesting how everyone is so focused on the models. I wonder why.   

While I'm here I suppose I can give a little status update on what I'm doing: I now work at Ubisoft, where I'm working on a mix of animation tech, gameplay and AI for a major unrevealed title.
It's super fun, lots of amazing people and I'm learning things every day. 
This project was definitely a major factor in getting through the door.  

So for people wondering why I'm not at QD, it honestly was not a good idea as I don't speak French  
And they were kind of like, "yeah you shouldn't come if you don't already live in Paris". Can't wait to play Detroit next month tho!
## Post #239
- Username: Unlimitedskills
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri May 04, 2018 4:50 pm
- Post datetime: 2018-07-06T16:36:08+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (THAT'S ALL FOLK

Beyond two Souls is a very fun game. Like everyone else i was looking to see where all this research led. But alas its dead. I'm starting to notice this HugoPeters doesnt finish the projects he starts. He did the same thing with Star Fox Adventures E3 2002 prototype (looking for dinosaur planet remnants) over at [http://jul.rustedlogic.net/thread.php?id=16384&page=0](http://jul.rustedlogic.net/thread.php?id=16384&page=0)

It started in 2013. 5 years and 40 pages later and god knows how many man hours wasted he creates a tool everyones been waiting for then vanishes without releasing it. Then does the most absurd thing ever. A random guy with a youtube channel pops up out of a cave asking if he can show off his new tool. Hugo shares his tool to this random stranger because of the attention he will bring on youtube. 

All the research that kcat and everyone else did,he took all thier knowledge and built a tool to view models/assets from the game. piggy backing off others work. Instead of releasing the tool to all the visitors/fans/dedicated followers who have been following that thread for years a random dude comes along with no interest in the game,never been to rustedlogic and could care less about dinosaur planet and this is the fool Hugo decides to send his tools to for attention? The youtuber was so lost 2 guys  kett and kokorogensou  had to explain to him what the models represent,what hes looking at,what the game is about etc....Im like dude what are you doing? Like someone else said its like Hugo is doing it for attention. No one wants to see 50 pictures of new models you found. Everyone wants to use the tool themselves and see what they can discover and these are legit dinosaur planet fans who have been studying/researching the game that was never released for god knows how many years. Can't stand to see peoples research go to waste for 1 person's insecurity.
## Post #240
- Username: mirh
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2018-07-07T13:31:30+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (THAT'S ALL FOLK

> Reply from Unlimitedskills
>
> Beyond two Souls is a very fun game. Like everyone else i was looking to see where all this research led. But alas its dead. I'm starting to notice this HugoPeters doesnt finish the projects he starts. He did the same thing with Star Fox Adventures E3 2002 prototype (looking for dinosaur planet remnants) over at http://jul.rustedlogic.net/thread.php?id=16384&page=0

If you'd have read the thread you'd know that HugoPeters was asked by the developers to cease work on these tools.

> Reply from Unlimitedskills
>
> 
It started in 2013. 5 years and 40 pages later and god knows how many man hours wasted he creates a tool everyones been waiting for then vanishes without releasing it. Then does the most absurd thing ever. A random guy with a youtube channel pops up out of a cave asking if he can show off his new tool. Hugo shares his tool to this random stranger because of the attention he will bring on youtube.

Don't be so entitled, if someone doesn't want to release the tools they wrote they don't have to.

> Reply from Unlimitedskills
>
> 
All the research that kcat and everyone else did,he took all thier knowledge and built a tool to view models/assets from the game. piggy backing off others work. Instead of releasing the tool to all the visitors/fans/dedicated followers who have been following that thread for years a random dude comes along with no interest in the game,never been to rustedlogic and could care less about dinosaur planet and this is the fool Hugo decides to send his tools to for attention? The youtuber was so lost 2 guys  kett and kokorogensou  had to explain to him what the models represent,what hes looking at,what the game is about etc....Im like dude what are you doing? Like someone else said its like Hugo is doing it for attention. No one wants to see 50 pictures of new models you found. Everyone wants to use the tool themselves and see what they can discover and these are legit dinosaur planet fans who have been studying/researching the game that was never released for god knows how many years. Can't stand to see peoples research go to waste for 1 person's insecurity.

Then write your own tools.
## Post #241
- Username: Kett
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2018-07-14T00:38:05+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (THAT'S ALL FOLK

> Reply from Unlimitedskills
>
> Beyond two Souls is a very fun game. Like everyone else i was looking to see where all this research led. But alas its dead. I'm starting to notice this HugoPeters doesnt finish the projects he starts. He did the same thing with Star Fox Adventures E3 2002 prototype (looking for dinosaur planet remnants) over at http://jul.rustedlogic.net/thread.php?id=16384&page=0

It started in 2013. 5 years and 40 pages later and god knows how many man hours wasted he creates a tool everyones been waiting for then vanishes without releasing it. Then does the most absurd thing ever. A random guy with a youtube channel pops up out of a cave asking if he can show off his new tool. Hugo shares his tool to this random stranger because of the attention he will bring on youtube. 

All the research that kcat and everyone else did,he took all thier knowledge and built a tool to view models/assets from the game. piggy backing off others work. Instead of releasing the tool to all the visitors/fans/dedicated followers who have been following that thread for years a random dude comes along with no interest in the game,never been to rustedlogic and could care less about dinosaur planet and this is the fool Hugo decides to send his tools to for attention? The youtuber was so lost 2 guys  kett and kokorogensou  had to explain to him what the models represent,what hes looking at,what the game is about etc....Im like dude what are you doing? Like someone else said its like Hugo is doing it for attention. No one wants to see 50 pictures of new models you found. Everyone wants to use the tool themselves and see what they can discover and these are legit dinosaur planet fans who have been studying/researching the game that was never released for god knows how many years. Can't stand to see peoples research go to waste for 1 person's insecurity.

Hey, Unlimitedskills, if you really have unlimited skills you could easily do this work yourself, like Gh0stBlade suggested 

Alright, I feel like addressing this properly once and for all, as you're definitely not the only one with this opinion.

Let's put one thing up front: My goal is and has been to have a career in the games industry. 
Just for that reason, it would be dumb to release projects like B2S, as it would only harm my reputation within the industry.
There's a fine line between a "cool project" and "illegal" in this case. When I visited a certain developer in Amsterdam they were extremely impressed with the B2S project but reassured it's good I didn't release any of it, or I would not have been invited.   
Selfish? Maybe, but people seem so self entitled, it really confuses me. What makes you think you automatically should have the right to own what I make?
I put in the hours, I get to decide what to do with it, right? Nobody is paying me, I don't owe anything to you...
I understand it sucks to see cool stuff and then not get it for yourself, but I ask you to have some respect for my decisions.

Unfortunately this stuff can be controversial, so I'm extremely hesitant to release anything. There's many reasons that should be self explanatory in regards to this.
That being said, I did release a similar project, a model viewer for No Man's Sky models, which got featured a ton:
[https://www.youtube.com/watch?v=kDG3visCxlk](https://www.youtube.com/watch?v=kDG3visCxlk)

B2S I obviously can't release as I was asked to stop working on it by QD.
Because I did that I now have a good relation with them and talk to some of the devs from time to time, and it's all on good terms.
Some people who worked at QD who are aware of the project are now at the company I'm at and so, it's a small industry where you have to protect your reputation - is the point I'm trying to make I guess.

Dinosaur Planet, you got it wrong I'm afraid!
First of all, I use bits of other people's research that have been released, so I'm not keeping anything from anyone that's done by others.
Second of all, I don't use "all" of their research, and I'm not bragging when I say most of the stuff I show I've done myself, without help from others.
I am actually very much working on it as we speak and got some awesome things coming soon, I just like to post/release things on forums when there's a good amount to show instead of doing it gradually, that way it's a lot more noteworthy when it drops 
I've announced on a few places already that I am working on a web-based model viewer using my own engine (for everyone, not just tech-savvy people), with the goal to faithfully recreate parts of a scene from DP with the data that we have.

The H4G video - I don't release crap, so that's why I thought this was a good (temporary) way of allowing a larger audience to see the cool bits 

Also, releasing tools individually requires a lot of work to just make them usable for the community, and at that point the amount of people that can actually use them is very small, whereas I like to create something standalone and user friendly, so everyone can enjoy it. 
See it as a tribute to the game, rather than just hacking tools 
Besides, there's only so much data to DP and I've covered about 99% of it already anyway!

So, I hope this makes sense to you and you understand my perspectives a bit better now.

One last note, Kett and Kokorogensou are actually friends of mine and ask not to be involved in your trashing of me, so if you plan on writing any more messages keep them out of your argumentation please
## Post #242
- Username: NeoNull80
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jun 12, 2018 5:06 am
- Post datetime: 2019-03-30T16:52:58+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (THAT'S ALL FOLK

I might be a bit late but I thought id post this here anyways.

[https://www.polygon.com/2019/3/20/18274 ... -exclusive](https://www.polygon.com/2019/3/20/18274142/detroit-become-human-heavy-rain-epic-games-store-pc-exclusive)
## Post #243
- Username: nightride
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue May 07, 2019 10:03 am
- Post datetime: 2019-05-07T02:06:15+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (THAT'S ALL FOLK

I don't suppose there's some way of finding out which point in the game that certain audio is from?
## Post #244
- Username: Anthony7890050
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat May 11, 2019 4:58 am
- Post datetime: 2019-05-19T16:54:28+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (THAT'S ALL FOLK

hello I can have more than two souls PS3 files please
## Post #245
- Username: Alvare
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Feb 28, 2017 3:45 pm
- Post datetime: 2019-08-12T04:14:54+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (THAT'S ALL FOLK

Erm.. did anyone ever figure out why the arm texture is blue?


I mean, that's some otherworldly looking arm right there.
## Post #246
- Username: darkbabe2
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jul 01, 2015 4:27 am
- Post datetime: 2019-09-06T06:40:50+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (THAT'S ALL FOLK

Anyone haw the Ryan Clayton model?.If so can someone send it to me pls its the only model i need from this game
## Post #247
- Username: gamer1977
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Feb 28, 2019 1:23 pm
- Post datetime: 2020-02-02T05:23:07+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (THAT'S ALL FOLK

Hello friends Someone can upload Beyond Two Souls -Extractor- v1.0 Deleted download link
## Post #248
- Username: Funnybizness
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Nov 15, 2019 10:03 am
- Post datetime: 2020-02-11T20:51:49+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (THAT'S ALL FOLK

I know this is thread is basically dead but just wanted to say thanks. This tool allowed me to extract all the audio I needed for my creations. And I was fortunate to convert them all. I'm very grateful. Thank you again.
## Post #249
- Username: wesernameX93
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Mar 16, 2020 9:14 pm
- Post datetime: 2020-03-19T11:47:20+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (THAT'S ALL FOLK

Hello everyone, i know this post is too old, but when i use the b2s extractor i don't %100 it'll stuck at %50. anyone have a solution for that ?
[stuck.png](https://xentaxbackup.github.io/file/17738_stuck.png)
## Post #250
- Username: zeaofsuos
- Rank: beginner
- Number of posts: 28
- Joined date: Fri Apr 19, 2019 10:07 pm
- Post datetime: 2020-03-19T14:54:04+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (THAT'S ALL FOLK

ADMIN, PLEASE DELETE.
## Post #251
- Username: wesernameX93
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Mar 16, 2020 9:14 pm
- Post datetime: 2020-03-19T15:22:59+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (THAT'S ALL FOLK

> Reply from zeaofsuos ↑Thu Mar 19, 2020 10:54 pm at Thu Mar 19, 2020 10:54 pm
>
> 
wesernameX93 wrote: ↑Thu Mar 19, 2020 7:47 pm
Hello everyone, i know this post is too old, but when i use the b2s extractor i don't %100 it'll stuck at %50. anyone have a solution for that ?


Does that also work for the PC Versions of Quantic Dream Games? Or is it specifically for the game files of the console versions? Could I maybe test that tool off of you? It would be appreciated.

it's only work with B2S PS3 version, and here is the test it and tell me if its working or not

[blog/?p=1166](https://forum.xentax.com/blog/?p=1166)
## Post #252
- Username: ProGamer
- Rank: veteran
- Number of posts: 98
- Joined date: Thu Sep 05, 2019 4:44 pm
- Post datetime: 2020-05-15T07:57:32+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (THAT'S ALL FOLK

hi there is an extraction tool for animations beyond two souls,
## Post #253
- Username: Faithfullfaun
- Rank: advanced
- Number of posts: 79
- Joined date: Mon Nov 28, 2016 4:12 pm
- Post datetime: 2020-07-30T10:19:05+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (THAT'S ALL FOLK

Possible update for PC versions of Heavy Rain and Beyond: Two Souls?
## Post #254
- Username: mahbod
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Oct 04, 2019 8:20 pm
- Post datetime: 2020-10-14T01:35:38+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (THAT'S ALL FOLK

Could anyone reupload this tool again please?
## Post #255
- Username: Raq
- Rank: beginner
- Number of posts: 22
- Joined date: Sun Nov 17, 2019 1:04 am
- Post datetime: 2022-10-14T23:55:03+00:00
- Post Title: Re: Beyond: Two Souls - Reversing | Porting (THAT'S ALL FOLK

I hope I'm not bothering anyone by bumping this thread or something, but I just wanted to know if there is any "solution" or workaround regarding the diffuse textures having a very weird color. While extracting Jodie's different outfits I noticed that a lot of them have weird blue hand textures, blue face textures or very pale face textures. I thought it was something to do with the RGB channels of the texture but it is not, no combination gives out a result that looks even remotely correct.

Some of these textures look correct in some outfits, but in others, Jodie's teen punk-phase outfit for example, they don't. And it's quite frustrating because that outfit has an unique face texture with makeup, which cannot be found in any other outfit therefore there's no way to get the "correct" diffuse texture for it. Is there some kind of weird process the game does in runtime (like material files) to change the color of the texture? And if so, why do they do this only on a certain amount of outfits/models? It feels kinda inconsistent.





EDIT:

I found out about this litterally seconds after posting this, and it really helps fixing this issue. I use Photoshop so the steps might be slightly different depending on the photo editing software you use but essentially what you need to do is go to the Channel Mixer and increase the Green channel by something like 30%. Here's the result:



It would be cool to know exactly by how much the green channel is being increased in-game to have the most accurate result possible, but oh well, if it works it works.
## Post #256
- Username: relight
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Aug 16, 2010 10:52 am
- Post datetime: 2023-05-25T00:48:13+00:00
- Post Title: Re: Beyond: Two Souls

I know it's an old thread, I was just curious if the tool was still around, since the original link doesn't work anymore.

No worries if not, and I apologize in advance for the bump
## Post #257
- Username: QuasarNebula
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Mar 04, 2023 5:13 am
- Post datetime: 2023-10-13T14:58:25+00:00
- Post Title: Re: Beyond: Two Souls

please reupload
