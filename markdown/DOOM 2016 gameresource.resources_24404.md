## Post #1
- Username: newc22
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Aug 27, 2021 4:58 am
- Post datetime: 2021-08-26T21:06:17+00:00
- Post Title: DOOM 2016 gameresource.resources

I use DOOMExtract.exe and I get the english.bfile file where the text out there. I translate it but if i repack the file i get 11 GB gameresources.resources file not the original 5 GB and the game doesn't run well i get this massage: ( I try to run in dev mode enabled but doesn' t help me...) Any idea what will i do?! Thanx the reply! (In DoomEternal i edit DOOMEternalx64vk.exe file by HxD  to read the english.blang files)

Configured log listener print-redirect tags
Added structured log listener print-redirect
Added structured log listener mp-cloud-gobbler
2021-08-26T23:02:40.963+02:00 LOG: Process started
Winsock Initialized
------ Initializing File System ------
Current search path:
    - C:/Users/NewC/Saved Games/id Software/DOOM/base/
    - E:/Games/Dooom/base/
------ File System initialized.
------ Command Line ------
 "E:\Games\Dooom\DOOMx64.exe" 
2021-08-26T23:02:40.980+02:00 LOG: Command Line: "E:\Games\Dooom\DOOMx64.exe" 
------ CPU Information ------
    1 CPU package, 6 physical cores, 12 logical cores
    3200 MHz    AMD CPU with MMX & SSE & SSE2 & SSE3 & SSSE3 & SSE41 & SSE42 & AVX & HTT
    65536 kB 1st level cache, 524288 kB 2nd level cache, 8388608 kB 3rd level cache
    16336 MB System Memory
initializing resource container gameresources.resources
initializing resource container gameresources.patch
initializing resource container gameresources_002.patch
idLib::SetProduction( PROD_PRODUCTION )
------- Initializing renderSystem --------
PreliminaryRenderSetup
---registered window class
---registered fake window class
---registered context window class
created OpenGL 4.3 context
created OpenGL 4.3 context
----- GL_Init -----
----- GPU Details -----
Vendor : ATI Technologies Inc.
GPU    : Radeon(TM) RX 460 Graphics
Driver : 4.3.14757 Compatibility Profile Context 20.12.1 27.20.14501.28009
dedicated video memory :     3543MB
total video memory     :     3543MB
available video memory :     3543MB
OpenGL version 4.3
GLSL version 4.6
X..GL_ARB_shader_clock not found
X..GL_NVX_multigpu_info not found
Number of GPUs  : 1
RENDER THREAD STACK SIZE: 4194304
created OpenGL 4.3 context
Initializing OpenGL subsystem
ShowGameWindow: (0, 0) 1920 x 1080, full screen
Using mega2 chunk file E:\Games\Dooom/virtualtextures/_vmtr_sq9.mega2
Using mega2 chunk file E:\Games\Dooom/virtualtextures/_vmtr_q1.mega2
Using mega2 chunk file E:\Games\Dooom/virtualtextures/_vmtr_q2.mega2
Using mega2 chunk file E:\Games\Dooom/virtualtextures/_vmtr_q3.mega2
Using mega2 chunk file E:\Games\Dooom/virtualtextures/_vmtr_q4.mega2
Read vmtrs from E:\Games\Dooom/virtualtextures/_vmtr.vmtr
Read vmtrs from E:\Games\Dooom/virtualtextures/_vmtr_dlc1.vmtr
Could not open E:\Games\Dooom/virtualtextures/_vmtr_dlc2.vmtr, all vmtrs will be re-created
Could not open E:\Games\Dooom/virtualtextures/_vmtr_dlc3.vmtr, all vmtrs will be re-created
Could not open E:\Games\Dooom/virtualtextures/_vmtr_dlc4.vmtr, all vmtrs will be re-created
Read a total of 3322 vmtrs
Executing default.cfg for device #0...
Executing default.cfg for device #1...
Executing default.cfg for device #2...
Executing default.cfg for device #3...
Unknown command 'build_packageParent'
------ Build Information ------
    Cheat Mode: OFF
    Host Name: DESKTOP-DDCH2DN
    Binary Build:
        Version: 6.1.1
        Target: shippingretail
        Name: 20160808-123534-peach-almond
        Requestor: user:evan.eubanks:137c7
        URL: [http://www.eden.idsoftware.com/builds/b ... ach-almond](http://www.eden.idsoftware.com/builds/binaries/20160808-123534-peach-almond)
        Relevant CLs: 434135
    Package:
        Name: 20160727-184944-quartzite-wrench
        Map Set: BFG Playtest, SP Campaign back up, SP Campaign, SP Beta Test, Demo, sp_min_unified, SP Playtest, sp_campaign, Unified IHV SP, First 3
        Requestor: user:ben.miles:c4c76
        URL: [http://www.eden.idsoftware.com/builds/p ... ite-wrench](http://www.eden.idsoftware.com/builds/packages/20160727-184944-quartzite-wrench)
        Relevant CLs: 431538
    Disc Layout:
        Name: 20160808-123639-cerium-masala
    Candidate:
        Name: 20160808-124023-puny-parrot
        Disc Number: 1
2021-08-26T23:02:48.882+02:00 LOG: Retrieved build information
reading 5878 sound events
reading 54 sound busses
reading 55 sound states
reading 5 sound switches
done reading 5 sound events longest is 59
----- Initializing Decls -----
330 types, 0 declSource in 1 ms
------------------------------
Failed to read remaplist.md6remap
Reading strings/english.lang as UTF-8
24879 strings read
Initializing class hierarchy

------- Input Initialization -------
Initializing DirectInput...
mouse: DirectInput initialized.
keyboard: DirectInput initialized.
------------------------------------
EnumerateDownloadableContent: E:\Games\Dooom\dlc
NetGetVersionChecksum - checksum  : 146807551
DownloadPlatformTitleStorage: Loaded
NetGetVersionChecksum - no change
idMPServerCloudInstance is disabled
  0: Hangszórók (Realtek High Definition Audio)
     2 channels, 48000 Hz
     Default Console Device, Multimedia Device, Communications Device, and Game Device
Using audio device for voice 0
----- Initializing Sound System ------
initial.pck stream package loaded
audio bank 'doom_mp.bnk' excluded based on game mode SP
audio bank 'doom_weapon_mp.bnk' excluded based on game mode SP
streamed_sfx.pck stream package loaded
async load success id -2103502525 : doom_initial.bnk
streamed_sfx_dlc1.pck stream package loaded
streamed_sfx_dlc2.pck stream package loaded
streamed_sfx_dlc3.pck stream package loaded
English(US)/streamed_vo.pck stream package loaded
English(US)/streamed_vo_dlc1.pck stream package loaded
  sound system initialized.
--------------------------------------
---------- ResetPersistHeap ----------
Global heap: Can't HeapWalk() in this configuration
Map heap   : GlobalMemoryStatus: 15.95GB dwTotalPhys
GlobalMemoryStatus: 8.86GB dwAvailPhys
GlobalMemoryStatus: 7.09GB used phys
GlobalMemoryStatus: 6.90GB used virtual
0.0 seconds to start load screen video
0.0 seconds to init the hdc
0.0 seconds to prep vts
0.0 seconds to figure out container
0.2 seconds to read 12334k table header
Resources skipped by layer tests: 0
0.0 seconds to determine and prepare  1249 resources need loaded
0.0 seconds was durango PLM Events
0.0 seconds to allocate and defer load  1294 resources
Load 1249 resources using 1294 of 75045 total resource files, 1 streamed
0.0 seconds to start the BGL
DOOMx64.exe @ 0x59cd256d(  ) +  bytes () : GetGameSystemInterface(  )
DOOMx64.exe @ 0x59c33320(  ) +  bytes () : GetGameSystemInterface(  )
DOOMx64.exe @ 0x59c235fd(  ) +  bytes () : GetGameSystemInterface(  )
DOOMx64.exe @ 0x59c9acef(  ) +  bytes () : GetGameSystemInterface(  )
DOOMx64.exe @ 0x59a4f677(  ) +  bytes () : GetGameSystemInterface(  )
DOOMx64.exe @ 0x59a39bac(  ) +  bytes () : GetGameSystemInterface(  )
DOOMx64.exe @ 0x599efb8e(  ) +  bytes () : GetGameSystemInterface(  )
DOOMx64.exe @ 0x59a13e54(  ) +  bytes () : GetGameSystemInterface(  )
DOOMx64.exe @ 0x59a45689(  ) +  bytes () : GetGameSystemInterface(  )
DOOMx64.exe @ 0x59a40af5(  ) +  bytes () : GetGameSystemInterface(  )
DOOMx64.exe @ 0x59a01c3f(  ) +  bytes () : GetGameSystemInterface(  )
DOOMx64.exe @ 0x584e50ab(  ) +  bytes () : __glewVertexAttrib2fvARB(  )
DOOMx64.exe @ 0x59c8839b(  ) +  bytes () : GetGameSystemInterface(  )
KERNEL32.DLL @ 0x2a017c24(  ) +  bytes () : BaseThreadInitThunk(  )
ntdll.dll @ 0x2af0d4d1(  ) +  bytes () : RtlUserThreadStart(  )
FATAL ERROR: Loading unverified resource. Verify files with Steam or set 'devMode_enable' to allow unverified resources: index file E:\Games\Dooom\base\gameresources.index
Set cvar 'devMode_enable' to enable Dev Mode.
zlib inflate error
Dumped console text to C:\Users\NewC\Saved Games\id Software\DOOM\base\ErrorLog_08-26-2021__11-02-52pm.txt.

idRenderSystem::Shutdown()
Shutting down OpenGL subsystem

***************************
FATAL ERROR: Loading unverified resource. Verify files with Steam or set 'devMode_enable' to allow unverified resources: index file E:\Games\Dooom\base\gameresources.index
Set cvar 'devMode_enable' to enable Dev Mode.

***************************
