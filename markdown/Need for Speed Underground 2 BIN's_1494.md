## Post #1
- Username: Jille
- Rank: VIP member
- Number of posts: 38
- Joined date: Mon Aug 29, 2005 10:07 pm
- Post datetime: 2005-09-09T17:15:39+00:00
- Post Title: Need for Speed Underground 2 BIN's

Hi all,

For some time I've been looking for a unpacker for Need for Speed Underground 2 BIN-files. These files are packages that contain most of the ingame content, like car-textures, vinyls and stuff like that.

There are tools available that can open Underground 1 BIN's, but not for Underground 2...  

I attached an example of a geometry bin file.
You can also download a textures.bin file here:
[http://members.chello.nl/g.berends1/TEXTURES.zip](http://members.chello.nl/g.berends1/TEXTURES.zip)

A vinyls.bin is under the cutter 

Thanks in advance!
[GEOMETRY.zip](https://xentaxbackup.github.io/file/429_GEOMETRY.zip)
## Post #2
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-09-09T20:46:07+00:00
- Post Title: Need for Speed Underground 2 BIN's

In archive files of following formats, MAT, DAT lay.. Structures have the format not that that in Need For Speed Underground 1 I than I can not help... Sorry
## Post #3
- Username: Jille
- Rank: VIP member
- Number of posts: 38
- Joined date: Mon Aug 29, 2005 10:07 pm
- Post datetime: 2005-09-09T21:20:10+00:00
- Post Title: Need for Speed Underground 2 BIN's

It's okay, it was worth trying  I will keep this in mind next time I do a request. Thanks anyway
## Post #4
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-09-09T21:22:34+00:00
- Post Title: Need for Speed Underground 2 BIN's

You can try program BinTex 0.4 for NFSU1
## Post #5
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-09-09T21:41:53+00:00
- Post Title: Need for Speed Underground 2 BIN's

I do think there are textures (raw) in there. I haven't figured out the format yet.
## Post #6
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-09-09T22:05:55+00:00
- Post Title: Need for Speed Underground 2 BIN's

> Reply from Mr.Mouse
>
> I do think there are textures (raw) in there. I haven't figured out the format yet.
DDS
## Post #7
- Username: SparedLife
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Mar 07, 2004 1:37 pm
- Post datetime: 2005-09-09T22:37:03+00:00
- Post Title: Need for Speed Underground 2 BIN's

Apparantly it's a lot of mix and match. The 343 byte bin files for the tracks are standard DDS with mips. The STREAML4RA.BUN file appears to be mixed DDS and other files. I looked at the bin files in the car folders present in the demo and they appear to be TPK compressed archives. 

Example: 
Vehicles\Cars\UG2\350Z\350Z_vinyls.tpk

 I couldn't find any useable non compressed textures in the files anywhere.
## Post #8
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-09-09T22:58:22+00:00
- Post Title: Need for Speed Underground 2 BIN's

I am found DDS headers .... DXT1,2,3,5
## Post #9
- Username: Jille
- Rank: VIP member
- Number of posts: 38
- Joined date: Mon Aug 29, 2005 10:07 pm
- Post datetime: 2005-09-09T22:59:12+00:00
- Post Title: Need for Speed Underground 2 BIN's

yes, I'm sure the textures are in DDS-format

bin2tex doesn't work for NFSUG2, no matter how hard you try 
the programmer of that tool (Arushan, a dutch guy) doesn't do any work in it anymore.
## Post #10
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-09-09T23:01:20+00:00
- Post Title: Need for Speed Underground 2 BIN's

The author of this program promised to make support NFSU2 so we wait for the new version bin2tex
## Post #11
- Username: Jille
- Rank: VIP member
- Number of posts: 38
- Joined date: Mon Aug 29, 2005 10:07 pm
- Post datetime: 2005-09-09T23:04:18+00:00
- Post Title: Need for Speed Underground 2 BIN's

> Reply from KorNet
>
> The author of this program promised to make support NFSU2 so we wait for the new version bin2tex

let's hope he will... as far as I know it's abandoned


I'm not sure if this helps anyone, but this was created by arushan for an xbox version of NFSU1:

```
'// NFSU BinTex (XBOX) -- Arushan (aru)

Option Explicit

Public Declare Sub CopyMemory Lib "kernel32" Alias "RtlMoveMemory" ( _
   lpvDest As Any, lpvSource As Any, ByVal cbCopy As Long)

Private Function SwizBlock(ByRef OutData() As Byte, ByRef InData() As Byte, ByRef OffsOut As Long, ByVal Offs As Long, ByVal BlWidth As Long, ByVal BlHeight As Long, ByVal Stride As Long)

   If (Offs > UBound(InData)) Then Exit Function

   If BlWidth < 2 Or BlHeight < 2 Then
       ' just copy data here
       CopyMemory OutData(Offs), InData(OffsOut), BlWidth * BlHeight
       OffsOut = OffsOut + BlWidth * BlHeight
   ElseIf BlWidth = 2 And BlHeight = 2 Then
       ' swizzle block
       OutData(OffsOut) = InData(Offs)
       OutData(OffsOut + 1) = InData(Offs + 1)
       OutData(OffsOut + 2) = InData(Offs + Stride)
       OutData(OffsOut + 3) = InData(Offs + Stride + 1)
       OffsOut = OffsOut + 4
   Else
       ' break into 4 blocks and reprocess
       SwizBlock OutData, InData, OffsOut, Offs, BlWidth / 2, BlHeight / 2, Stride
       SwizBlock OutData, InData, OffsOut, Offs + (BlWidth / 2), BlWidth / 2, BlHeight / 2, Stride
       SwizBlock OutData, InData, OffsOut, Offs + (Stride * (BlHeight / 2)), BlWidth / 2, BlHeight / 2, Stride
       SwizBlock OutData, InData, OffsOut, Offs + (Stride * (BlHeight / 2)) + (BlWidth / 2), BlWidth / 2, BlHeight / 2, Stride
   End If

End Function

Public Function Swizzle(InTex As CTpkTexture, data() As Byte) As Byte()

   Dim bytData() As Byte, bytDataOut() As Byte
   Dim lOffs As Long, i As Long, Width As Long, Height As Long
   Dim MinMax As Long, MipLevels As Long, DataLen As Long

   MinMax = IIf(InTex.TexHeight > InTex.TexWidth, InTex.TexHeight, InTex.TexWidth)
   MipLevels = Log(MinMax) / Log(2) + 1
   
   lOffs = 0
   bytData = data
   ReDim bytDataOut(UBound(bytData))
   
   Width = InTex.TexWidth
   Height = InTex.TexHeight
   
   For i = 1 To MipLevels
       SwizBlock bytDataOut, bytData, lOffs, lOffs, Width, Height, Width
       Width = Width / 2
       Height = Height / 2
       If lOffs > UBound(bytData) Then Exit For
   Next
   
   Swizzle = bytDataOut
   
End Function

Private Function UnswizBlock(ByRef InData() As Byte, ByRef OutData() As Byte, ByRef Offs As Long, ByVal OffsOut As Long, ByVal BlWidth As Long, ByVal BlHeight As Long, ByVal Stride As Long)

   If (Offs > UBound(InData)) Then Exit Function

   If BlWidth < 2 Or BlHeight < 2 Then
       ' just copy data here
       CopyMemory OutData(OffsOut), InData(Offs), BlWidth * BlHeight
       OffsOut = OffsOut + BlWidth * BlHeight
   ElseIf BlWidth = 2 And BlHeight = 2 Then
       ' unswizzle block
       OutData(OffsOut) = InData(Offs)
       OutData(OffsOut + 1) = InData(Offs + 1)
       OutData(OffsOut + Stride) = InData(Offs + 2)
       OutData(OffsOut + Stride + 1) = InData(Offs + 3)
       Offs = Offs + 4
   Else
       ' break into 4 blocks and reprocess
       UnswizBlock InData, OutData, Offs, OffsOut, BlWidth / 2, BlHeight / 2, Stride
       UnswizBlock InData, OutData, Offs, OffsOut + (BlWidth / 2), BlWidth / 2, BlHeight / 2, Stride
       UnswizBlock InData, OutData, Offs, OffsOut + (Stride * (BlHeight / 2)), BlWidth / 2, BlHeight / 2, Stride
       UnswizBlock InData, OutData, Offs, OffsOut + (Stride * (BlHeight / 2)) + (BlWidth / 2), BlWidth / 2, BlHeight / 2, Stride
   End If

End Function

Public Function Unswizzle(InTex As CTpkTexture) As Byte()

   Dim bytData() As Byte, bytDataOut() As Byte
   Dim lOffs As Long, i As Long, Width As Long, Height As Long
   Dim MinMax As Long, MipLevels As Long

   MinMax = IIf(InTex.TexHeight > InTex.TexWidth, InTex.TexHeight, InTex.TexWidth)
   MipLevels = Log(MinMax) / Log(2) + 1
   
   lOffs = 0
   bytData = InTex.GetData(True)
   ReDim bytDataOut(UBound(bytData))
   
   Width = InTex.TexWidth
   Height = InTex.TexHeight
   
   For i = 1 To MipLevels
       UnswizBlock bytData, bytDataOut, lOffs, lOffs, Width, Height, Width
       Width = Width / 2
       Height = Height / 2
       If lOffs > UBound(bytData) Then Exit For
   Next
   
   Unswizzle = bytDataOut

End Function

```
## Post #12
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-09-09T23:12:46+00:00
- Post Title: Need for Speed Underground 2 BIN's

If for the first part have made means and for the second will be
## Post #13
- Username: Jille
- Rank: VIP member
- Number of posts: 38
- Joined date: Mon Aug 29, 2005 10:07 pm
- Post datetime: 2005-09-09T23:26:13+00:00
- Post Title: Need for Speed Underground 2 BIN's

okay
## Post #14
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-09-09T23:29:47+00:00
- Post Title: Need for Speed Underground 2 BIN's

And where you have got this information?
## Post #15
- Username: Jille
- Rank: VIP member
- Number of posts: 38
- Joined date: Mon Aug 29, 2005 10:07 pm
- Post datetime: 2005-09-09T23:33:40+00:00
- Post Title: Need for Speed Underground 2 BIN's

Ð¾Ñ‚ Ð¼ÐµÑ
## Post #16
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-09-09T23:35:44+00:00
- Post Title: 

[quote="Jille"]Ð¾Ñ‚ Ð¼ÐµÑ
## Post #17
- Username: Jille
- Rank: VIP member
- Number of posts: 38
- Joined date: Mon Aug 29, 2005 10:07 pm
- Post datetime: 2005-09-09T23:38:19+00:00
- Post Title: 

Ð
## Post #18
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-09-09T23:38:25+00:00
- Post Title: 

You can use plugin for Total Commander -> GAUP - Game Archive UnPacker 3.0.7.0beta

Support games : ->  [http://wincmd.ru/files/gaup0370_formats.htm](http://wincmd.ru/files/gaup0370_formats.htm)

Download plugins there - [http://wincmd.ru/download.php?id=gaup](http://wincmd.ru/download.php?id=gaup)
## Post #19
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-09-09T23:40:31+00:00
- Post Title: 

Need For Speed Underground 2 - .BUN; .VIV supported
## Post #20
- Username: Jille
- Rank: VIP member
- Number of posts: 38
- Joined date: Mon Aug 29, 2005 10:07 pm
- Post datetime: 2005-09-09T23:47:03+00:00
- Post Title: 

I just tried, thanks for the suggestion.

Viv goes easy
BUNs give errors most of the time...   
BIN no succes at all
## Post #21
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-09-09T23:48:51+00:00
- Post Title: 

> Reply from Jille
>
> I just tried, thanks for the suggestion.

Viv goes easy
BUN gives an error...   
BIN no succes at all
Now I shall put NFSU2 and I shall check up
## Post #22
- Username: Jille
- Rank: VIP member
- Number of posts: 38
- Joined date: Mon Aug 29, 2005 10:07 pm
- Post datetime: 2005-09-09T23:53:36+00:00
- Post Title: 

Most BUN's don't contain any interesting stuff as far as I know, and there's only one VIV (sdata.viv), but go ahead 

gotta catch some sleep now
see ya tomorrow
## Post #23
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-09-09T23:57:50+00:00
- Post Title: 

In sdata.viv all music and sounds of game contains
Night
## Post #24
- Username: Jille
- Rank: VIP member
- Number of posts: 38
- Joined date: Mon Aug 29, 2005 10:07 pm
- Post datetime: 2005-09-10T00:00:01+00:00
- Post Title: 

Thanks

I know, but that's not what I'm interested in  I want textures 

Plus they are in a BIG format, which is not supported as far as I know.
## Post #25
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-09-10T00:21:18+00:00
- Post Title: 

I understand that you structures interest.. We Wait while the author of program Bin2Tex will make support NFSU2... Soon there will be Need For Speed Most Wanted interestingly there same formats of archives will?
## Post #26
- Username: Jille
- Rank: VIP member
- Number of posts: 38
- Joined date: Mon Aug 29, 2005 10:07 pm
- Post datetime: 2005-09-10T09:59:55+00:00
- Post Title: 

I don't think Most Wanted has an identical file structure... 
During the years I've been in the NFS modding community, each game had a different file format, except for NFS3 and 4, which were almost identical. 

Maybe the VIV's are in a common format but the BIN's won't be, I'm afraid... But let's just wait for Bintex
