## Post #1
- Username: Troopermanaic
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Jul 01, 2011 11:29 pm
- Post datetime: 2011-09-12T05:12:20+00:00
- Post Title: Help plz .DLL file repair for UCGO

OK im not too fluent with coding in general but I am feeling lucky.
Basically I play this game called UCGO and it has a problem with one of its files "SHW32.dll" to be exact.

The problem is that the exports list ".rdata" in that file is messed up somehow, I opened it up with PE explorer and it didnt look right at all.

I been doing alittle research and found out you can make a .DEF file to kinda "proxy" the exports list if you know what I mean. The only problem is that I do not know how to make this file because I literally don't know any coding what so ever, the only reason why I figured this out is because I have strong common sense and allot of luck which led me to where I'M at now.

I been trying to find a tutorial or even an example online but there isn't allot of helpful information about this topic.

By the way I have the full export list the way its supposed to be. Its actually correct in the .DLL file but it doesn't load the functions correctly that's why I wanted to proxy it like I said.

Anyway, does anyone have knowledge on how to do this? Can anyone help me?
it would be GREATLY appreciated =p


Here is some information if its not that hard which I dont expect it to be really I would think that given this information the file probably would come easy to those who understand how to make it.

Library name is 

.idata



and all the exports are

MemAlloc 
MemAllocAligned 
_MemAllocAlignedOffset@20 
MemAllocFS 
MemAllocPtr 
MemCheckPtr 
MemDefaultErrorHandler 
MemDefaultPoolThreadExclusive 
MemErrorUnwind 
MemFix 
MemFree 
MemFreeFS 
MemFreePtr 
MemHandle 
MemIsMoveable 
MemLock 
MemLockCount 
MemPatchProcess 
MemPoolAttachShared 
MemPoolCheck 
MemPoolCount 
MemPoolFirst 
MemPoolFree 
MemPoolInfo 
MemPoolInit 
MemPoolInitFS 
MemPoolInitNamedShared 
MemPoolInitNamedSharedEx 
MemPoolInitRegion 
MemPoolInitRegionEx 
MemPoolLock 
MemPoolNext 
MemPoolPreAllocate 
MemPoolPreAllocateHandles 
MemPoolSetBlockSizeFS 
MemPoolSetCeiling 
MemPoolSetFloor 
MemPoolSetFreeBytes 
_MemPoolSetGrowIncrement@8 
MemPoolSetMaxSubAlloc 
_MemPoolSetMaxSubpools@8 
MemPoolSetPageResizing 
MemPoolSetPageSize 
MemPoolSetSerialization 
MemPoolSetSmallBlockAllocator 
MemPoolSetSmallBlockSize 
MemPoolShrink 
MemPoolSize 
MemPoolUnlock 
MemPoolWalk 
_MemProcessCoelesceSystemAllocs@4 
_MemProcessFlushAll@0 
MemProcessSetFreeBytes 
MemProcessSetGrowIncrement 
_MemProcessSetHeapLimit@4 
MemProcessSetLargeBlockThreshold 
_MemProcessUseMunmap@4 
MemReAlloc 
MemReAllocPtr 
MemRegisterTask 
MemSetErrorHandler 
MemSize 
MemSizePtr 
MemSizeRequested 
MemUnfix 
MemUnlock 
MemUnregisterTask 
MemVersion 
_shi_enterCriticalSection 
_shi_leaveCriticalSection 
shi_MemDefaultPool 
shi_MemFreeDefaultPool 
shi_MemInitDefaultPool 
shi_aligned_malloc 
shi_aligned_offset_malloc 
shi_aligned_offset_realloc 
shi_aligned_offset_recalloc 
shi_aligned_realloc 
shi_aligned_recalloc 
shi_calloc 
shi_calloc_impl 
shi_delete 
shi_deletePtrStdcall 
shi_deleteStdcall 
shi_expand 
shi_free 
shi_freeThreadPools 
shi_freeingDLL 
shi_getThreadPool 
shi_heapadd 
shi_heapchk 
shi_heapmin 
shi_heapset 
shi_heapused 
shi_heapwalk 
shi_loadingDLL 
shi_malloc 
shi_msize 
shi_new 
shi_newStdcall 
shi_notSMP 
_shi_patchDynamicModules@0 
_shi_patchMallocs@0 
shi_realloc 
shi_recalloc 
shi_set_new_handler
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-09-13T16:48:09+00:00
- Post Title: Help plz .DLL file repair for UCGO

I have the tool that does exactly this job:
[http://aluigi.org/mytoolz.htm#dllproxyskel](http://aluigi.org/mytoolz.htm#dllproxyskel)

just launch it as: dllproxyskel.exe c:\SHW32.dll
it will create the def file and a C one ready for the proxy job (tested with mingw so you could require some modifications if you use VC)
## Post #3
- Username: Troopermanaic
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Jul 01, 2011 11:29 pm
- Post datetime: 2011-09-13T20:51:22+00:00
- Post Title: Help plz .DLL file repair for UCGO

thanks this is EXACTLY what im looking for

EDIT
I'm not entirely sure this is working correctly, I know how to edit the .dll with hex editor so I know a certain edit will make the game crash, I wanted to test this with the proxy files to see if the game would crash and it didn't which tells me the .dll isn't using the proxy files. I saw the thing about windows 7 DevOverrideEnable and I have done what I was told to get it to work but im not sure if it did or not. "Restarted my pc and everything"
so im not sure if the proxy files actually work and I have to do something in my registry to fix it or if the registry is right and the proxy files dont work.

EDIT AGAIN
actually I have a question. is there anything im supposed to do the the .dll to make it use the proxy files? I feel like the .dll is still using its own export functions instead of the proxy file.
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-09-26T16:24:16+00:00
- Post Title: Help plz .DLL file repair for UCGO

basicly if it's not a system dll you must rename the original one and modifying the source code to force the loading (proxyfying) of the dll with that name:
original.dll -> backup.dll
replace the "original.dll" text in new.dll with "backup.dll
new.dll -> original.dll
