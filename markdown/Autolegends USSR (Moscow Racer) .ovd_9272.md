## Post #1
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2012-07-15T04:40:24+00:00
- Post Title: Autolegends USSR (Moscow Racer) .ovd

[Here](https://drive.google.com/uc?export=download&id=13dVQDd7KKtsitjiU3ZQSp4OpcO1yAZpt) are the samples for Autolegends USSR (Moscow Racer) model files. Two pretty detailed vintage russian cars.

edit: link updated 12 Jan, 2023
## Post #2
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2012-07-21T23:53:41+00:00
- Post Title: Autolegends USSR (Moscow Racer) .ovd

I think there might be more files that describe the entries that are in the .ovd, as I can not find a subfile listing. Though I did see some sections that give their size so maybe the file is supposed to be streamed.
Here is one type of mesh section found numerous times in both of the car's OVD files:
....
Type One Mesh sections:

4ByteIntegerSizeofSection(need to also add +4Bytes to get the true size)
2ByteInteger#NumberOfFaces
2ByteInteger#NumberOfFaces (yes it is repeated)
2ByteInteger#UnknownStructure
2ByteInteger#Vertexes

Vertex Section 12Bytes per Vertex:
{4ByteFloatingPointVertexes(X,Y,Z)

FaceIndexSection (16Bytes per Triangle)
{2ByteIntegerFaceIndexes(#1,#2,#3), FF FF, 8ByteUnknown}

UnknownSection(FaceNormalMaps??) (12Bytes per Entry)
{2ByteID, 2ByteNormalMaps(X,Y,Z), 4ByteID}

End of Section.

Seen in for example
at offsets 
0x0000D04B in GAZ14.ovd
0x000256D4 in GAZ14.ovd
0x00035674 in GAZ14.ovd
0x0005B0DF in GAZ14.ovd

Type 2 mesh sections:
2ByteInteger#ofVertexsInFaceIndex
01 00 00 00 00 00 00 00 00 00 00 00
2ByteInteger#ofVertexesInMesh
2ByteInteger#ofVertexesInMesh
Triangle List
{First Vertex In Triangle, Second Vertex in Triangle, Third Vertexes In Triangle}
4ByteUnknown
2ByteUnknown
{4ByteFloatingPointVertexes(X,Y,Z)}
End of Mesh???

For Example Seen in Offsets:
0x00051070 in GAZ14.ovd
0x0005DD44 in GAZ14.ovd
## Post #3
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2012-07-22T04:05:49+00:00
- Post Title: Autolegends USSR (Moscow Racer) .ovd

thank you for your researches, i will try to find more related to the model files
## Post #4
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2023-01-10T15:38:14+00:00
- Post Title: Autolegends USSR (Moscow Racer) .ovd

I've made research with ModelResearcher and something is wrong with the faces. Everything should work but they just messed for some reason.
Can anyone help me with faces?
[GAZ14_mesh1_LOD0.jpg](https://xentaxbackup.github.io/file/23278_GAZ14_mesh1_LOD0.jpg)
## Post #5
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2023-01-12T09:30:03+00:00
- Post Title: Autolegends USSR (Moscow Racer) .ovd

> Reply from Tosyk ↑Tue Jan 10, 2023 11:38 pm at Tue Jan 10, 2023 11:38 pm
>
> 
Can anyone help me with faces?
Using AXE:



GAZ14.ovd.png (115.91 KiB) Viewed 63 times
## Post #6
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2023-01-12T09:40:37+00:00
- Post Title: Autolegends USSR (Moscow Racer) .ovd

@Bigchillghost this is nice! Can you tell me where I made a mistake?
## Post #7
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2023-01-12T10:08:25+00:00
- Post Title: Autolegends USSR (Moscow Racer) .ovd

> Reply from Tosyk ↑Thu Jan 12, 2023 5:40 pm at Thu Jan 12, 2023 5:40 pm
>
> Can you tell me where I made a mistake?
The vertex cache should not be referenced directly by the face indices, coz it's been "optimized".
What the reorganizer does is:

```

```

The info in that screenshot should be straightforward enough.
