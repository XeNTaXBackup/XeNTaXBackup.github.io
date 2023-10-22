## Post #1
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-17T15:51:06+00:00
- Post Title: [Request] 9 Dragons

Hello guys!!! well a game called 9 Dragons have format .XP, the exe's are protected so maybe somebody can take a look into files and unpack it.

C:\9Dragons\binkw32.dll	::	Nothing found *
C:\9Dragons\dbghelp.dll	::	Microsoft Visual C++ 7.0 DLL Method 3
C:\9Dragons\fmod.dll	::	UPX 0.80 - 1.24 DLL -> Markus & Laszlo
C:\9Dragons\GameGuard.des	::	UPX 0.89.6 - 1.02 / 1.05 - 2.90 -> Markus & Laszlo [Overlay]
C:\9Dragons\msvcp60.dll	::	Nothing found *
C:\9Dragons\MSVCP60D.DLL	::	Microsoft Visual C++ 5.0 [Debug]
C:\9Dragons\MSVCRTD.DLL	::	Microsoft Visual C++ 5.0 [Debug]
C:\9Dragons\NDLAUNCHER.EXE	::	Microsoft Visual C++ 6.0
C:\9Dragons\NDLauncher2.exe	::	Microsoft Visual C++ 6.0
C:\9Dragons\NINEDRAGONS.EXE	::	yoda's cryptor 1.x / modified
C:\9Dragons\ogg.dll	::	Microsoft Visual C++ 6.0 DLL
C:\9Dragons\QHTM.dll	::	Microsoft Visual C++ 6.0 DLL
C:\9Dragons\SpeedTreeRT.dll	::	Microsoft Visual C++ 6.0 DLL
C:\9Dragons\unicows.dll	::	Nothing found [Overlay] *
C:\9Dragons\vorbis.dll	::	Microsoft Visual C++ 6.0 DLL
C:\9Dragons\vorbisfile.dll	::	Microsoft Visual C++ 6.0 DLL
C:\9Dragons\XEraser.exe	::	Microsoft Visual C++ 6.0
C:\9Dragons\XFCONTROL.DLL	::	Microsoft Visual C++ 6.0 DLL
C:\9Dragons\XFileTransfer.exe	::	yoda's cryptor 1.x / modified
C:\9Dragons\XWebPage.dll	::	Microsoft Visual C++ 6.0 DLL



[9 Dragons XP Archive Research](http://www.mediafire.com/download.php?e458g943rszxg6f)
[9Dragons Exe's yoda's cryptor 1.x](http://www.mediafire.com/download.php?1wb1vi5hj3tafan)
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-02-17T16:10:04+00:00
- Post Title: [Request] 9 Dragons

Another request [here](http://forum.xentax.com/viewtopic.php?f=10&t=5214)
Unpacked executable [here](http://www.progamercity.net/other-mmo/3072-release-9dragons-unpacked.html)

For coders  

```
#define _HEADERINDICATOR_PACKAGEFILEVERSION      0xA001

typedef struct 
{

   WORD HeaderIndicator;
   WORD FileVersion;   
   int  PackedFileCount;

} _PACKAGEFILE_HEADER;


#define _ENCODEKEY      0xEF

void _EncodeData( LPSTR string, BYTE key )
{
   if( !string ) return;
   ASSERT( string );

   int length = strlen( string );

   LPSTR tptr = string;

   for( int i = 0; i < length; i++ )
   {
      *tptr ^= key;
      tptr++;
   }
}
```
## Post #3
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-17T16:14:56+00:00
- Post Title: [Request] 9 Dragons

> Reply from Ekey
>
> Another request here
Unpacked executable here

For coders  
Code: Select all#define _HEADERINDICATOR_PACKAGEFILE            0xFEFA
#define _HEADERINDICATOR_PACKAGEFILEVERSION      0xA001

typedef struct 
{

   WORD HeaderIndicator;
   WORD FileVersion;   
   int  PackedFileCount;

} _PACKAGEFILE_HEADER;


#define _ENCODEKEY      0xEF

void _EncodeData( LPSTR string, BYTE key )
{
   if( !string ) return;
   ASSERT( string );

   int length = strlen( string );

   LPSTR tptr = string;

   for( int i = 0; i < length; i++ )
   {
      *tptr ^= key;
      tptr++;
   }
}
ummm thanks a lot Ekey, any chance for learn how unpack EXE? can you give me a small tutorial via private message? grateful for your support.
## Post #4
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-02-17T16:51:53+00:00
- Post Title: [Request] 9 Dragons

For make tut need again download full client  ... You can upload only all binary's?
## Post #5
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-17T17:27:54+00:00
- Post Title: [Request] 9 Dragons

I upload all binary there!!!! check first page.

[9Dragons Exe's yoda's cryptor 1.x](http://www.mediafire.com/download.php?1wb1vi5hj3tafan)
## Post #6
- Username: Ekey
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-02-17T17:48:30+00:00
- Post Title: [Request] 9 Dragons

```
#by chrrox
get idstring long
get files long
for i = 0 < files
get nsize short
filexor "0xEF"
getdstring NAME nsize
filexor ""
putarray 0 i NAME
next i
for i = 0 < files
get id1 long
putarray 1 i id1
next i
get SIZE asize
putarray 1 files SIZE
for i = 0 < files
set j i
math j + 1
getarray NAME 0 i
getarray OFFSET 1 i
getarray SIZE 1 j
math SIZE - OFFSET
log NAME OFFSET SIZE
next i

```
## Post #7
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-02-17T17:53:43+00:00
- Post Title: [Request] 9 Dragons

Hehe nice job
## Post #8
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-17T18:19:09+00:00
- Post Title: [Request] 9 Dragons

thanks a lot for script chrrox, grateful.
