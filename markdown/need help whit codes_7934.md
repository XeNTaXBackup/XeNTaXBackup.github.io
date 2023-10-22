## Post #1
- Username: wolfen
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Dec 27, 2011 7:13 am
- Post datetime: 2011-12-26T23:30:26+00:00
- Post Title: need help whit codes

hello. wanted to know how to use these codes to see the model
or create a plugin for 3d model (any programs)




> dword idstring (05 10 00 00)
>
> dword meshType? (have seen 0, 1, 2, 3, 4)
>
> dword_2 ???
>
> float_16 matrix?
>
> dword_4 ???
>
> 
>
> 
>
> #unk section. Contains materials and what seems to be animations>
>
> dword ???
>
> dword ???
>
> dword sectionSize
>
> dword ???
>
> dword ???
>
> dword ???
>
> 
>
> <sectionSize number of bytes>
>
> 
>
> dword unk
>
> dword unk
>
> dword numVerts
>
> dword numIndices
>
> 
>
> #some variables for now
>
> dword VAR1
>
> dword VAR2
>
> dword VAR3
>
> dword VAR4
>
> 
>
> <100 bytes>
>
> 
>
> #unk section
>
> if VAR4 == 4:
>
>    28 bytes
>
> elif VAR4 == 6:
>
>    44 bytes
>
> 
>
> struct vertices {
>
>    float_8
>
> }
>
> 
>
> #unk section
>
> if VAR4 == 4:
>
>    pass
>
> elif VAR4 == 5:
>
>    numVerts * 4 bytes
>
> elif VAR4 == 1:
>
>    numVerts * 20 bytes
>
> 
>
> struct face {
>
>    dword_3 indices
>
> }
>
> dword numFaces
>
> dword ???
>
> dword numVerts
>
> dword ???
>
> 
>
> #IF END OF FILE THEN DONE, ELSE
>
> 
>
> dword_? ???
>
> 
>
> struct unk3 { #several different types...only figured out how to skip one of them
>
>    dword index?
>
>    float_16 ???
>
>    Byte_72 nulls
>
> }
>
> 96 bytes
>
> 
>
> EOF
or these other codes

> Data on:
>
> .lgo (Geometry Object)
>
> .lab (Animation Bone)
>
> .lmo (Model Object)
>
> .lxo (Model Pack/Scene) // I donno why .lxo
>
> Read Routines: http://pastebin.com/00eiYEdB
>
> Structures + Enums: http://pastebin.com/fGSDq5Vu

thanks
## Post #2
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2011-12-26T23:42:59+00:00
- Post Title: need help whit codes

there not codes, there just someones notes.. you can't do anything with these really. unless your the person who wrote them
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-12-26T23:43:46+00:00
- Post Title: need help whit codes

Oh, there's the outline I posted some months ago lol

Someone then sent those pastebin's to me but I never got around to looking at it.
It looks like the full parser though, so you just need to write some script to pass data to it and then take the output and do stuff with it.
