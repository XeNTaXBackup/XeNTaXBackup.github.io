## Post #1
- Username: GlitchingNo
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Aug 23, 2021 7:35 am
- Post datetime: 2021-10-29T03:09:06+00:00
- Post Title: Need Help with Hex to Obj

Hey Guys! I have a problem... again 
I want have a model file from the 3ds Games Metroid Samus Returns and i really want one model from the game the problem is there is no way to convert the model to something a 3d program can read so there was only one method that could help me hex to obj and i made a bit progress since the last time i used it. I first tried to work with Hex2Obj but I wasnt able to do much so i tried another hex to obj program i found and in this program I was able to find the Vertices (but I am pretty sure some of them are still missing) and get the shape of the model I want. Then I tried for houres to find the faces but no success  
thats why i ask here now for someone who can help me with this

Attached is the file with the model I need, a picture of the Creature I want (so you know what the Armor and Body looks like) and a obj file with the Vertices I was able to get (Offset: 0x3438  Count 7528) maybe this will help

Ok while writing this I found that the shape I got is just his armor but i was able to find the vertices for his normal body too. Offset is somewhere around 0x54200 but i have no idea how many they are
## Post #2
- Username: dimis9138
- Rank: veteran
- Number of posts: 85
- Joined date: Tue Jul 28, 2020 1:37 am
- Post datetime: 2021-10-29T06:02:46+00:00
- Post Title: Need Help with Hex to Obj

You didn't attach anything.
## Post #3
- Username: GlitchingNo
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Aug 23, 2021 7:35 am
- Post datetime: 2021-10-29T14:46:26+00:00
- Post Title: Need Help with Hex to Obj

Oh sorry apparently the file was to big I removed the .obj file from the zip now it should work
[Ridley.zip](https://xentaxbackup.github.io/file/21093_Ridley.zip)
## Post #4
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-10-29T16:35:44+00:00
- Post Title: Need Help with Hex to Obj

1st submesh:



1st_mesh.png (131.55 KiB) Viewed 155 times
## Post #5
- Username: GlitchingNo
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Aug 23, 2021 7:35 am
- Post datetime: 2021-10-29T18:19:24+00:00
- Post Title: Need Help with Hex to Obj

Thank you so much for your help @Bigchillghost

I think his normal body starts at Offset: 54200 and has a Vertex count of 850 at least this gives me a pretty good point cloud. 
But I still have no idea how i can find the Faces. Maybe someone can help me to find this model too.
also I am pretty sure his body and armor just get fused to make a complete model

Here is a pic of the Point Cloud I was able to get:



ViewScene 29.10.2021 20_15_00.png (35.34 KiB) Viewed 142 times
## Post #6
- Username: GlitchingNo
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Aug 23, 2021 7:35 am
- Post datetime: 2021-10-29T21:11:52+00:00
- Post Title: Need Help with Hex to Obj

Update:
Still no progress on the Faces for his body which i really need to use the model 
But i found the Verticles from his Wings: (Offset: 0xb5920  Count: 135) but they arent that important
## Post #7
- Username: GlitchingNo
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Aug 23, 2021 7:35 am
- Post datetime: 2021-10-30T01:47:34+00:00
- Post Title: Need Help with Hex to Obj

I spend way to much time to try to get the faces for his body but no success can someone pls do it for me or tell me how i can find them I really have no idea how it works.
## Post #8
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-10-30T06:06:44+00:00
- Post Title: Need Help with Hex to Obj

Seriously, why do you think I post the params of the 1st mesh for?  

If you search for the vertex count of the 1st mesh (3764, or 0xEB4 in hex) in the file, you'll find the only match at address 0x4A0, where the layout of the vertex record table is as:


Then here comes the index record table at address 0xA74, where each entry takes 20 bytes:

This table records the index count for each sub-mesh of a different material group, meaning that a single mesh object could be consisted of more than 1 index entries.

Hence there's a mesh record table at address 0xC18, right after the index record table, where each entry takes 100 bytes. Skip 0x4C bytes (0x40 bytes for a 4x4 matrix, and 12 bytes for the world-space pivot perhaps) from the beginning you'll get the info you need:


Here's an example on using exactly the vertex addresses recorded in the file for the 1st mesh:


The mesh has been scaled down to 10% for better observation, so as the translation vectors.

And here's the overall view of all meshes (well, almost) of the hightest lod:
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-10-30T11:44:52+00:00
- Post Title: Need Help with Hex to Obj

> Reply from GlitchingNo ↑Sat Oct 30, 2021 2:19 am at Sat Oct 30, 2021 2:19 am
>
> I think his normal body starts at Offset: 54200 and has a Vertex count of 850 at least this gives me a pretty good point cloud. 
But I still have no idea how i can find the Faces.well, you picked up a somewhat complicated format as a beginner. I'm surprised you were pretty close, despite this!  
.



Mmdl_head.png (83.3 KiB) Viewed 101 times



Maybe this log (based on the research by Bigchillghost) may help a little bit:

```
 0. 494,  3764 3438 <- see #3 below
 1. 51c,  846 54218 <- see #5 below
 2. 5a4,  705 664e8
 3. 62c, 2128 74c3c
 4. 6b4,  544 a27bc
 5. 73c,  387 ada3c
 6. 7c4,  136 b5938
 7. 84c,  92 b87f8
 8. 8c4,  72 ba348
 9. 90c,  70 bac48
 10. 954,  73 bb508
 11. 99c,  74 bbe28
 12. 9e4,  72 bc768
 13. a2c,  63 bd068

        (vCount, dec.)              (FI count dec.)
#0.             (1251), FIs 0xbd848 (2190)
#1.             (2102), FIs 0xbe964 (2070)
#2.             (3199), FIs 0xbf990 (2832)
#3. v at 0x3438 (3764), FIs 0xc0fb0 (1272)

#4.             (253), FIs 0xc19a0 (903)
#5. v at 0x54218 (846), FIs 0xc20b0 (2388)

#6.             (705), FIs 0xc3358 (1764)
#7.             (621), FIs 0xc4120 (1707)
#8.             (1260), FIs 0xc4e78 (2076)
#9.             (2128), FIs 0xc5eb0 (2160)
#10.             (367), FIs 0xc6f90 (1347)
#11.             (544), FIs 0xc7a18 (618)
#12.             (387), FIs 0xc7eec (912)
#13.             (136), FIs 0xc860c (492)
#14.             (92), FIs 0xc89e4 (372)
#15.             (72), FIs 0xc8ccc (192)
#16.             (70), FIs 0xc8e4c (204)
#17.             (73), FIs 0xc8fe4 (210)
#18.             (74), FIs 0xc9188 (204)
#19.             (72), FIs 0xc9320 (204)
#20.             (63), FIs 0xc94b8 (174)

```
## Post #10
- Username: GlitchingNo
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Aug 23, 2021 7:35 am
- Post datetime: 2021-10-30T21:02:01+00:00
- Post Title: Need Help with Hex to Obj

Ok first of all Thank you Guys so much for the Help
Through the "tutorial" I understand it way better and was able to get nearly the complete model



ViewScene 30.10.2021 22_40_01.png (59.83 KiB) Viewed 91 times


Only the Teeth/Claws are missing. But I am trying to get them rn
also could you tell me how I can make his body appear inside his Armor like on your pic.
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-10-31T00:45:23+00:00
- Post Title: Need Help with Hex to Obj

> Reply from GlitchingNo ↑Sun Oct 31, 2021 5:02 am at Sun Oct 31, 2021 5:02 am
>
> also could you tell me how I can make his body appear inside his ArmorNot sure what you mean exactly - you could move parts manually:
.



Movehead.png (85.94 KiB) Viewed 85 times


or use position offsets (translation vectors?).
## Post #12
- Username: GlitchingNo
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Aug 23, 2021 7:35 am
- Post datetime: 2021-10-31T00:58:33+00:00
- Post Title: Need Help with Hex to Obj

@shakotay2 I meant Bigchillghost because on his pic they are at the perfect position but yeah i think he used position offsets/translation vectors

Also I was able to get the the rest of models from the file. But without the help of you two I wouldnt have been able to do this thank you guys so much again

I made a list from your log in case someone wants to get this model too:

```
#0.  v at 0x3438     (1251),       FIs 0xbd848     (2190)

#1.  v at 0x3438     (2102),       FIs 0xbe964     (2070)

#2.  v at 0x3438     (3199),       FIs 0xbf990     (2832)

#3.  v at 0x3438     (3764),       FIs 0xc0fb0     (1272)

#4.  v at 0x54218    (253),        FIs 0xc19a0     (903)

#5.  v at 0x54218    (846),        FIs 0xc20b0     (2388)

#6.  v at 0x664E8    (705),        FIs 0xc3358     (1764)

#7.  v at 0x74C3C    (621),        FIs 0xc4120     (1707)

#8.  v at 0x74C3C    (1260),       FIs 0xc4e78     (2076)

#9.  v at 0x74C3C    (2128),       FIs 0xc5eb0     (2160)

#10. v at 0xA27BC    (367),        FIs 0xc6f90     (1347)

#11. v at 0xA27BC    (544),        FIs 0xc7a18     (618)

#12. v at 0xADA3C    (387),        FIs 0xc7eec     (912)

#13. v at 0xB5938    (136),        FIs 0xc860c     (492)

#14. v at 0xB87F8    (92),         FIs 0xc89e4     (372)

#15. v at 0xBA348    (72),         FIs 0xc8ccc     (192)

#16. v at 0xBAC48    (70),         FIs 0xc8e4c     (204)

#17. v at 0xBB508    (73),         FIs 0xc8fe4     (210)

#18. v at 0xBBE28    (74),         FIs 0xc9188     (204)

#19. v at 0xBC768    (72),         FIs 0xc9320     (204)

#20. v at 0xBD068    (63),         FIs 0xc94b8     (174)
```
## Post #13
- Username: dimis9138
- Rank: veteran
- Number of posts: 85
- Joined date: Tue Jul 28, 2020 1:37 am
- Post datetime: 2021-10-31T03:14:46+00:00
- Post Title: Need Help with Hex to Obj

> Reply from Bigchillghost ↑Sat Oct 30, 2021 2:06 pm at Sat Oct 30, 2021 2:06 pm
>
> 

My question is how do you do multiple submeshes in the same file with AXE. Just press add next to mesh?
## Post #14
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-10-31T05:01:24+00:00
- Post Title: Need Help with Hex to Obj

> Reply from GlitchingNo ↑Sun Oct 31, 2021 8:58 am at Sun Oct 31, 2021 8:58 am
>
> 
... yeah i think he used position offsets/translation vectors
If you had read carefully my message and the notes in the images you should notice that I have emphasized that already:

> Reply from Bigchillghost ↑Sat Oct 30, 2021 2:06 pm at Sat Oct 30, 2021 2:06 pm
>
> 
The mesh has been scaled down to 10% for better observation, so as the translation vectors.
And if you interpret the first vector (FA FF 7F 29 B0 FD 8E 42 F6 98 FE C3) in the mesh record table as floats you'll have [5.68434e-014, 71.49548, -509.195]. But since I scaled down the mesh to 10% (by using a scaling vector [0.1, 0.1, 0.1]), I'd also need to perform the same operation on the translation vector. And since "5.68434e-014" is way smaller than 0 you can just ignore the error between them. Hence you got [0, 7.149548, -50.9195], which is what was used in that example image in the above quote. But if you're using the default/normal scaling you can simply just paste the vector as is.
## Post #15
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-10-31T06:26:23+00:00
- Post Title: Need Help with Hex to Obj

> Reply from dimis9138 ↑Sun Oct 31, 2021 11:14 am at Sun Oct 31, 2021 11:14 am
>
> 
My question is how do you do multiple submeshes in the same file with AXE. Just press add next to mesh?
I'm not sure if our understanding about the concept of "sub-mesh" are on the same page. But AXE cares only how the data are stored. For AXE, a "mesh" should be considered as a sinlge geometry object sharing the specified set of point cloud, whether it's a collapse of all parts ("sub-meshes") of a character ("mesh") or just a small item. 
So for the 1st "mesh" in this example, which is splitted into 4 index entries, one simple solution would be specifying the whole "Polygon Vertex Indices" set (of all 4 entries, coz their addresses are continuous), and use material groups to separate them "logically" (instead of physically). You can also specify explicitly all the 4 "Polygon Paramter Sets" but why bother to do things the hard way (if not for fun )?

But the 2nd mesh is splitted into 2 index entries so you can't use the "Polygon Paramter Sets" workaround even with the "Zero Accumulation" option checked, because they both require to be based upon the previous set of point cloud, not the max counts of the referenced vertices resulted by adding the "Polygon Paramter Sets" one after another. So you have to save the existing params of the 1st mesh into the "Paramter List" (by clicking the "Add" button, yes), and start over for the rest "mesh" objects.

Here's the PLC file of the previewed meshes in that image:


 75dc3003_1.zip
(1.04 KiB) Downloaded 13 times



Unfortunately there's a new bug introduced since the previous update of AXE. You can't save a valid PLC file if you're not using the "All Same" mode for Stride and Data Type.  
The fix would be released in the next version but if you're using v1.1.1 then you're good to go.
## Post #16
- Username: dimis9138
- Rank: veteran
- Number of posts: 85
- Joined date: Tue Jul 28, 2020 1:37 am
- Post datetime: 2021-10-31T07:35:23+00:00
- Post Title: Re: Need Help with Hex to Obj

> Reply from Bigchillghost ↑Sun Oct 31, 2021 2:26 pm at Sun Oct 31, 2021 2:26 pm
>
> 
dimis9138 wrote: ↑Sun Oct 31, 2021 11:14 am
My question is how do you do multiple submeshes in the same file with AXE. Just press add next to mesh?

I'm not sure if our understanding about the concept of "sub-mesh" are on the same page. But AXE cares only how the data are stored. For AXE, a "mesh" should be considered as a sinlge geometry object sharing the specified set of point cloud, whether it's a collapse of all parts ("sub-meshes") of a character ("mesh") or just a small item. 
So for the 1st "mesh" in this example, which is splitted into 4 index entries, one simple solution would be specifying the whole "Polygon Vertex Indices" set (of all 4 entries, coz their addresses are continuous), and use material groups to separate them "logically" (instead of physically). You can also specify explicitly all the 4 "Polygon Paramter Sets" but why bother to do things the hard way (if not for fun )?

But the 2nd mesh is splitted into 2 index entries so you can't use the "Polygon Paramter Sets" workaround even with the "Zero Accumulation" option checked, because they both require to be based upon the previous set of point cloud, not the max counts of the referenced vertices resulted by adding the "Polygon Paramter Sets" one after another. So you have to save the existing params of the 1st mesh into the "Paramter List" (by clicking the "Add" button, yes), and start over for the rest "mesh" objects.

Here's the PLC file of the previewed meshes in that image:
75dc3003_1.zip


Unfortunately there's a new bug introduced since the previous update of AXE. You can't save a valid PLC file if you're not using the "All Same" mode for Stride and Data Type.  
The fix would be released in the next version but if you're using v1.1.1 then you're good to go.

What confused me is how you managed to preview all of the different meshes in one. I think I understand a little better now, I'll take a look at the PLC file also  - however I still use the parameters often with the sniper elite models you helped me with a while back. Keep up the good work with AXE, it truly is a masterpiece - who knows, maybe a few years from now we'll be able to somehow convert AXE saves into actual .exe tools for diff formats, maybe (although probably not )
## Post #17
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-10-31T08:43:38+00:00
- Post Title: Re: Need Help with Hex to Obj

> Reply from dimis9138 ↑Sun Oct 31, 2021 3:35 pm at Sun Oct 31, 2021 3:35 pm
>
> 
What confused me is how you managed to preview all of the different meshes in one.
If you had the parameter list all set you can navigate to Options > Preview All in List to preview all objects.

> Reply from dimis9138 ↑Sun Oct 31, 2021 3:35 pm at Sun Oct 31, 2021 3:35 pm
>
> 
Keep up the good work with AXE, it truly is a masterpiece
Thanks for the compliment, I appreciate it, really. 

> Reply from dimis9138 ↑Sun Oct 31, 2021 3:35 pm at Sun Oct 31, 2021 3:35 pm
>
> 
who knows, maybe a few years from now we'll be able to somehow convert AXE saves into actual .exe tools for diff formats, maybe (although probably not )
Yeah, probably not.
## Post #18
- Username: dimis9138
- Rank: veteran
- Number of posts: 85
- Joined date: Tue Jul 28, 2020 1:37 am
- Post datetime: 2021-10-31T11:01:03+00:00
- Post Title: Re: Need Help with Hex to Obj

> Reply from Bigchillghost ↑Sun Oct 31, 2021 4:43 pm at Sun Oct 31, 2021 4:43 pm
>
> 
dimis9138 wrote: ↑Sun Oct 31, 2021 3:35 pm
What confused me is how you managed to preview all of the different meshes in one.

If you had the parameter list all set you can navigate to Options > Preview All in List to preview all objects.
dimis9138 wrote: ↑Sun Oct 31, 2021 3:35 pm
Keep up the good work with AXE, it truly is a masterpiece

I'll redirect the two new questions I have on the AXE thread, sorry to clutter up this thread.
