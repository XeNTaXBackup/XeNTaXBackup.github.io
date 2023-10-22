## Post #1
- Username: LoopyNoopy
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jun 10, 2016 8:28 pm
- Post datetime: 2016-06-10T12:53:27+00:00
- Post Title: Ninja ripper and GW2 problem

Hey there, a while ago Ninja Ripper used to work on GW2 for me but quite recently it's stopped.

I've tried using the 86 and 64 bit versions of ninja ripper and both don't work. 
the 64 bit version causes GW2 to crash, leaving this error message from the game:

> *--> Crash <--*
>
> Assertion: Coherent host crashed 
>
> File: ..\..\..\Engine\ArenaWeb\CoherentUi\AwCohContext.cpp(240)
>
> App: Gw2-64.exe 
>
> Pid: 10044
>
> Cmdline: 
>
> BaseAddr: 000000013FB80000
>
> ProgramId: 101
>
> Build: 62624
>
> When: 2016-06-10T12:34:24Z 2016-06-10T13:34:24+01:00
>
> Uptime:   0 days  0:00:15
>
> Flags: 0

Whereas the 86 bit version allows the game to load, and freezes the game on the character selection screen for a few seconds but doesn't rip anything. Beyond the character screen it doesn't work. But it actually leaves a log which is the following:

> 0610/132940 [055C] Ninja Ripper 1.5.1 x86
>
> 0610/132940 [055C] © 2004-2015 black_ninja
>
> 
>
> 0610/132940 [055C] LOG START
>
> 0610/132940 [055C] Inject mode: "intruder"
>
> 
>
> 0610/132940 [055C] Texture downscale max width : 4096
>
> 0610/132940 [055C] Texture downscale max height: 4096
>
> 0610/132940 [055C] Texture downscale value: 2
>
> 
>
> 0610/132940 [055C] LdrLoadDll hooked. Target: 0x7707C99D
>
> 0610/132940 [055C] LdrUnloadDll hooked. Target: 0x7707C0F0
>
> 0610/132940 [055C] CreateProcessA hooked. Target: 0x75821072
>
> 0610/132940 [055C] CreateProcessW hooked. Target: 0x7582103D
>
> 0610/132940 [055C] CreateProcessAsUserW hooked. Target: 0x7536C512
>
> 0610/132940 [055C] CreateProcessWithLogonW hooked. Target: 0x753A55E1
>
> 0610/132940 [055C] CreateProcessWithTokenW hooked. Target: 0x753A5617
>
> 0610/132941 [055C] D3D9.DLL loaded
>
> 0610/132941 [055C] D3D9 ripper init
>
> 0610/132941 [055C] Direct3DCreate9 hooked. Target: 0x60A10A62
>
> 0610/132941 [055C] Direct3DCreate9(32) return: 0x04BE07E0
>
> 0610/132941 [055C] IDirect3D9_CreateDevice hooked. Target: 0x609D2E0E
>
> 0610/132941 [055C] D3D9.DLL unloaded
>
> 0610/132941 [055C] D3D9 ripper uninit
>
> 
>
> 0610/132941 [055C] DDRAW.DLL loaded
>
> 0610/132941 [055C] DDRAW init
>
> 0610/132941 [055C] DirectDrawCreateEx hooked. Target: 0x554DEBC6
>
> 0610/132941 [055C] DirectDrawCreate hooked. Target: 0x554D859D
>
> 0610/132941 [055C] DirectDrawCreate() ret: 0x00000000
>
> 0610/132941 [055C] IDirectDraw_QueryInterface hooked. Target: 0x554D8AD0
>
> 0610/132941 [055C] IDirectDraw_CreateSurface hooked. Target: 0x554D617E
>
> 0610/132941 [055C] IUnknown_QueryInterface(IID_IDirectDraw7) HRESULT: 0x00000000
>
> 0610/132941 [055C] IDirectDraw_CreateSurface hooked. Target: 0x55502A62
>
> 0610/132941 [055C] DDRAW.DLL unloaded
>
> 0610/132941 [055C] DDRAW uninit
>
> 
>
> 0610/132943 [055C] CreateProcessW("D:\Games\Guild Wars 2\Gw2-64.exe") return: 1
>
> 0610/132943 [055C] Injecting to child process. Status: QueueUserApc() error.Win32 error code: 0x00000006
>
> 0610/132943 [055C] Loaded Modules List
>
> 0610/132943 [055C] --------------------------------
>
> 0610/132943 [055C] BaseAddr    Size         Module
>
> 0610/132943 [055C] --------------------------------
>
> 0610/132943 [055C] 0x01010000 (0x01C22000)  D:\Games\Guild Wars 2\Gw2.exe
>
> 0610/132943 [055C] 0x77040000 (0x00180000)  C:\Windows\SysWOW64\ntdll.dll
>
> 0610/132943 [055C] 0x75810000 (0x00110000)  C:\Windows\syswow64\kernel32.dll
>
> 0610/132943 [055C] 0x752E0000 (0x00047000)  C:\Windows\syswow64\KERNELBASE.dll
>
> 0610/132943 [055C] 0x750F0000 (0x00100000)  C:\Windows\syswow64\USER32.dll
>
> 0610/132943 [055C] 0x74B80000 (0x00090000)  C:\Windows\syswow64\GDI32.dll
>
> 0610/132943 [055C] 0x75230000 (0x0000A000)  C:\Windows\syswow64\LPK.dll
>
> 0610/132943 [055C] 0x756D0000 (0x0009D000)  C:\Windows\syswow64\USP10.dll
>
> 0610/132943 [055C] 0x749F0000 (0x000AC000)  C:\Windows\syswow64\msvcrt.dll
>
> 0610/132943 [055C] 0x75360000 (0x000A1000)  C:\Windows\syswow64\ADVAPI32.dll
>
> 0610/132943 [055C] 0x757F0000 (0x00019000)  C:\Windows\SysWOW64\sechost.dll
>
> 0610/132943 [055C] 0x769C0000 (0x000F0000)  C:\Windows\syswow64\RPCRT4.dll
>
> 0610/132943 [055C] 0x74990000 (0x00060000)  C:\Windows\syswow64\SspiCli.dll
>
> 0610/132943 [055C] 0x74980000 (0x0000C000)  C:\Windows\syswow64\CRYPTBASE.dll
>
> 0610/132943 [055C] 0x748B0000 (0x00009000)  C:\Windows\system32\VERSION.dll
>
> 0610/132943 [055C] 0x752A0000 (0x00035000)  C:\Windows\syswow64\WS2_32.dll
>
> 0610/132943 [055C] 0x76B40000 (0x00006000)  C:\Windows\syswow64\NSI.dll
>
> 0610/132943 [055C] 0x71BD0000 (0x0000D000)  C:\Windows\system32\WTSAPI32.dll
>
> 0610/132943 [055C] 0x700F0000 (0x00032000)  C:\Windows\system32\WINMM.dll
>
> 0610/132943 [055C] 0x75330000 (0x0002F000)  C:\Windows\syswow64\WINTRUST.dll
>
> 0610/132943 [055C] 0x75560000 (0x00121000)  C:\Windows\syswow64\CRYPT32.dll
>
> 0610/132943 [055C] 0x756A0000 (0x0000C000)  C:\Windows\syswow64\MSASN1.dll
>
> 0610/132943 [055C] 0x74F80000 (0x0015D000)  C:\Windows\syswow64\ole32.dll
>
> 0610/132943 [055C] 0x74EF0000 (0x0008F000)  C:\Windows\syswow64\OLEAUT32.dll
>
> 0610/132943 [055C] 0x75BD0000 (0x00C4C000)  C:\Windows\syswow64\SHELL32.dll
>
> 0610/132943 [055C] 0x74E90000 (0x00057000)  C:\Windows\syswow64\SHLWAPI.dll
>
> 0610/132943 [055C] 0x72780000 (0x00014000)  C:\Windows\system32\MSACM32.dll
>
> 0610/132943 [055C] 0x60D30000 (0x00190000)  C:\Windows\WinSxS\x86_microsoft.windows.gdiplus_6595b64144ccf1df_1.1.7601.23407_none_5c02a2f5a011f9be\gdiplus.dll
>
> 0610/132943 [055C] 0x70130000 (0x00084000)  C:\Windows\WinSxS\x86_microsoft.windows.common-controls_6595b64144ccf1df_5.82.7601.18837_none_ec86b8d6858ec0bc\COMCTL32.dll
>
> 0610/132943 [055C] 0x75920000 (0x00005000)  C:\Windows\syswow64\PSAPI.DLL
>
> 0610/132943 [055C] 0x60D20000 (0x00005000)  C:\Windows\system32\MSIMG32.dll
>
> 0610/132943 [055C] 0x6D090000 (0x00007000)  C:\Windows\system32\WSOCK32.dll
>
> 0610/132943 [055C] 0x719F0000 (0x00008000)  C:\Windows\system32\Secur32.dll
>
> 0610/132943 [055C] 0x75240000 (0x00060000)  C:\Windows\system32\IMM32.DLL
>
> 0610/132943 [055C] 0x74AA0000 (0x000CC000)  C:\Windows\syswow64\MSCTF.dll
>
> 0610/132943 [055C] 0x0F8D0000 (0x000C1000)  D:\Programs\newNinjaRipper\x86\intruder.dll
>
> 0610/132943 [055C] 0x6D5C0000 (0x000EB000)  C:\Windows\system32\dbghelp.dll
>
> 0610/132943 [055C] 0x04BF0000 (0x00207000)  C:\Windows\system32\d3dcompiler_43.dll
>
> 0610/132943 [055C] 0x0FC40000 (0x001FF000)  C:\Windows\system32\d3dx9_43.dll
>
> 0610/132943 [055C] 0x71B00000 (0x00080000)  C:\Windows\system32\uxtheme.dll
>
> 0610/132943 [055C] 0x76820000 (0x0019D000)  C:\Windows\syswow64\SETUPAPI.dll
>
> 0610/132943 [055C] 0x75990000 (0x00027000)  C:\Windows\syswow64\CFGMGR32.dll
>
> 0610/132943 [055C] 0x74C10000 (0x00012000)  C:\Windows\syswow64\DEVOBJ.dll
>
> 0610/132943 [055C] 0x5D710000 (0x00151000)  C:\Windows\system32\nvspcap.dll
>
> 0610/132943 [055C] 0x6FF50000 (0x00058000)  C:\Windows\system32\WINHTTP.dll
>
> 0610/132943 [055C] 0x6FF00000 (0x00050000)  C:\Windows\system32\webio.dll
>
> 0610/132943 [055C] 0x5D3B0000 (0x0035F000)  C:\Windows\system32\nvapi.dll
>
> 0610/132943 [055C] 0x75220000 (0x0000B000)  C:\Windows\syswow64\profapi.dll
>
> 0610/132943 [055C] 0x699D0000 (0x00017000)  C:\Windows\system32\CRYPTSP.dll
>
> 0610/132943 [055C] 0x69990000 (0x0003B000)  C:\Windows\system32\rsaenh.dll
>
> 0610/132943 [055C] 0x751F0000 (0x0002B000)  C:\Windows\syswow64\imagehlp.dll
>
> 0610/132943 [055C] 0x67E00000 (0x00039000)  C:\Windows\system32\ncrypt.dll
>
> 0610/132943 [055C] 0x68520000 (0x00017000)  C:\Windows\system32\bcrypt.dll
>
> 0610/132943 [055C] 0x67DC0000 (0x0003D000)  C:\Windows\SysWOW64\bcryptprimitives.dll
>
> 0610/132943 [055C] 0x74E70000 (0x00017000)  C:\Windows\syswow64\USERENV.dll
>
> 0610/132943 [055C] 0x67DA0000 (0x00016000)  C:\Windows\system32\GPAPI.dll
>
> 0610/132943 [055C] 0x71B80000 (0x0004C000)  C:\Windows\system32\apphelp.dll
>
> 0610/132943 [055C] LOG END

My question is what's happening and how do I get ninja ripper to work? I'm pretty sure it's to do with the 64 bit exe that runs but I'm not sure how to stop it running to check
