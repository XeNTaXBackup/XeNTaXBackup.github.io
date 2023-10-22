## Post #1
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-09-07T17:40:32+00:00
- Post Title: RF Online .MSH Format + Source

Hello guys well my question is anyone can fix this program, here I upload the tool + source for convert MSH to OBJ but still bugged, give errors and files broken, so please anyone can give me a hand really grateful, thanks a lot for support.





Structure of MSH

> struct MESHFILE
>
> {
>
> u16 LimbCount;
>
> child MESHLIMBDATA;
>
> }
>
> 
>
> struct MESHLIMBDATA
>
> {
>
> str[len=100] MeshName;
>
> str[len=100] LimbName;
>
> [hidden] u16 uk1;
>
> u32 ScaleX;
>
> skip 16;
>
> u32 ScaleY;
>
> skip 16;
>
> u32 ScaleZ;
>
> [hidden] u16 uk2;
>
> u32 PositionX;
>
> u32 PositionY;
>
> u32 PositionZ;
>
> [hidden] u16 uk3;
>
> u32 uk4;
>
> u32 uk5;
>
> skip 122;
>
> u16 PositionsCount;
>
> u16 FacesonLimb;
>
> u16 Sector3Count;
>
> }
>
> 
>
> proceeding is a 28 byte struct which consist of the following
>
> dword X - vector position
>
> dword Y
>
> dword Z
>
> 4 byte constant
>
> dword X - normal position
>
> dword Y
>
> dword Z
[MshtoObj Version Final.zip](https://xentaxbackup.github.io/file/4692_MshtoObj Version Final.zip)
## Post #2
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-09-07T19:25:15+00:00
- Post Title: RF Online .MSH Format + Source

Mmmm i see this tool converter before and its a true head pain, i extract sets but a the least i import and have around 20 meshes by set (normal its 5 helm, gloves, pants etc) all he parts are moved to x=0 y=0 z=0 coordenates a the least its a big trash mountain meshes, i hope anyone can fix this too.
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-09-07T19:28:59+00:00
- Post Title: RF Online .MSH Format + Source

Do modelers typically draw the mesh centered at the (0,0,0) and then simply apply transforms to move it to the desired location?
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-09-07T19:52:21+00:00
- Post Title: RF Online .MSH Format + Source

for mmo games they do sometimes because all the models are tiny pieces.
## Post #5
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-09-08T00:19:25+00:00
- Post Title: RF Online .MSH Format + Source

yes but the body parts have cuts also in the half parts, then need snap vertexs separated to make only the pants, the trouble its not the models are in the 0,0,0 coordenates the problem its the boyd parts have lots of cuts or separated in lots of meshes, the question its maybe anyone can make a importer working fine to import almos one full part of body and finaly import 5 or 6 body parts not 15 or 20 centered.
## Post #6
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2011-09-08T15:11:03+00:00
- Post Title: RF Online .MSH Format + Source

Models are attached to bones often...right? So that is the key
## Post #7
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-09-08T20:13:52+00:00
- Post Title: RF Online .MSH Format + Source

> Reply from pixellegolas
>
> Models are attached to bones often...right? So that is the key
The bones folder its out of the mesh files, and the conversor msh/obj keep only the uvmaps.
Weights are lost in the convert proces, if you can take a view of the original files posted or the source codes maybe can keep out one good conversor.. this can be nice
## Post #8
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2011-09-09T15:31:21+00:00
- Post Title: RF Online .MSH Format + Source

If you only want object then try a private server without gameguard and run 3d ripper. thats what I did and got all robots without problem. There are always nice ones in town
## Post #9
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-09-09T23:34:58+00:00
- Post Title: RF Online .MSH Format + Source

> Reply from pixellegolas
>
> If you only want object then try a private server without gameguard and run 3d ripper. thats what I did and got all robots without problem. There are always nice ones in town

Jejeje, yes bro but 3D ripper never get T Position of Riged model.
