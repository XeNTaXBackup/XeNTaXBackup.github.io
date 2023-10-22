## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-11T10:27:35+00:00
- Post Title: Chinese Paladin 5

5th game in the PC series.
[http://en.wikipedia.org/wiki/The_Legend ... _and_Fairy](http://en.wikipedia.org/wiki/The_Legend_of_Sword_and_Fairy)



Unpacker: [viewtopic.php?f=10&t=8655](http://forum.xentax.com/viewtopic.php?f=10&t=8655)
Noesis plugin: [http://db.tt/aW2Kxyis](http://db.tt/aW2Kxyis)

Loads most meshes including buildings and stuff.
I am not sure how the mesh should be parsed and so far am just hardcoding a bunch of values I think indicates the mesh type. So far it works.

It's a chunk-based format.

```
dword size
dword ?

```


It seems like the chunk 0x1 means something like "data chunk", which is followed by the actual data.

The face struct is like

```
short v2
short matNum
short v3

```


Materials come after mesh, and this repeats. 

I haven't actually parsed the materials.
Some materials explicitly define a texture name (without extension), others don't. The ones that don't just mean the texName is the same as the model name (I think). Otherwise, you will see an 0x2 chunk that gives you the texture name associated with that material.
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-11T17:41:57+00:00
- Post Title: Chinese Paladin 5

Turns out 0x8 is the start of the mesh material section.
Followed by 0x7, and 0x6, which will then contain a bunch of material entries.

Though, some of the textures are not mapped correctly.
I am not sure if this is because I assigned the wrong texture to the wrong material, or the UV are being carried from one mesh to the other (some of the meshes don't have UV's...), or...
## Post #3
- Username: z22901206
- Rank: advanced
- Number of posts: 40
- Joined date: Thu Dec 24, 2015 8:50 pm
- Post datetime: 2023-03-22T11:40:36+00:00
- Post Title: Chinese Paladin 5

Excuse me, may I ask if the scripts mentioned in this topic are used to load skins and motions? This is a game series and several of them use these formats. I haven't found any discussions about them elsewhere.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-03-22T21:20:35+00:00
- Post Title: Chinese Paladin 5

> Reply from z22901206 ↑Wed Mar 22, 2023 7:40 pm at Wed Mar 22, 2023 7:40 pm
>
> 
Excuse me, may I ask if the scripts mentioned in this topic are used to load skins and motions?Not to my knowledge. ChinesePaladin5.py (which loads .dff files) can be found here: [https://himeworks.com/noesis-plugins/](https://himeworks.com/noesis-plugins/)
As you can see, def parse_bones(self, numBones) is "empty". So vertices/faces/uvs supported only.

Here's the bones' names from PAL4-101.dff as a start (got them August 2019; didn't care for this any further):

```
1. <Bip02>
2. <Bip02 Pelvis>
3. <hook_ef_bottom>
4. <Bone56>
5. <Bone53>
6. <Bone49>
7. <Bip02 Spine>
8. <Bone11>
9. <Bone07>
10. <Bip02 Spine1>
11. <Bip02 R Thigh>
12. <Bip02 L Thigh>
13. <Bip02 L Calf>
14. <Bip02 L Foot>
15. <Bip02 L Toe0>
16. <Bip02 L Toe01>
17. <Bip02 L Toe0Nub>
18. <Bip02 R Calf>
19. <Bip02 R Foot>
20. <Bip02 R Toe0>
21. <Bip02 R Toe01>
22. <Bip02 R Toe0Nub>
23. <Bip02 Spine2>
24. <hook_ef_chest>
25. <Bone88>
26. <Bone47>
27. <Bone45>
28. <Bone43>
29. <Bone41>
30. <Bone21>
31. <Bone14>
32. <Bone03>
33. <Bip02 Neck>
34. <Bip02 R Clavicle>
35. <Bip02 L Clavicle>
36. <Bip02 Head>
37. <Bone84>
38. <Bone82>
39. <Bone80>
40. <Bone78>
41. <Bone76>
42. <Bone73>
43. <Bone69>
44. <Bone66>
45. <Bone63>
46. <Bone60>
47. <Bone05>
48. <Bip02 HeadNub>
49. <Bone06>
50. <Bone61>
51. <Bone62>
52. <Bone64>
53. <Bone65>
54. <Bone67>
55. <Bone68>
56. <Bone70>
57. <Bone71>
58. <Bone72>
59. <Bone74>
60. <Bone75>
61. <Bone77>
62. <Bone79>
63. <Bone81>
64. <Bone83>
65. <Bone85>
66. <Bip02 L UpperArm>
67. <Bone01>
68. <Bip02 L ForeArm>
69. <Bip02 L Hand>
70. <hook_ef_lhand>
71. <hook_LHWeapon>
72. <Bip02 L Finger4>
73. <Bip02 L Finger3>
74. <Bip02 L Finger2>
75. <Bip02 L Finger1>
76. <Bip02 L Finger0>
77. <Bip02 L Finger01>
78. <Bip02 L Finger0Nub>
79. <Bip02 L Finger11>
80. <Bip02 L Finger1Nub>
81. <Bip02 L Finger21>
82. <Bip02 L Finger2Nub>
83. <Bip02 L Finger31>
84. <Bip02 L Finger3Nub>
85. <Bip02 L Finger41>
86. <Bip02 L Finger4Nub>
87. <Bone02>
88. <Bip02 R UpperArm>
89. <Bone86>
90. <Bip02 R ForeArm>
91. <Bip02 R Hand>
92. <hook_ef_rhand>
93. <Bip02 R Finger4>
94. <Bip02 R Finger3>
95. <Bip02 R Finger2>
96. <Bip02 R Finger1>
97. <Bip02 R Finger0>
98. <Bip02 R Finger01>
99. <Bip02 R Finger0Nub>
100. <Bip02 R Finger11>
101. <Bip02 R Finger1Nub>
102. <Bip02 R Finger21>
103. <Bip02 R Finger2Nub>
104. <Bip02 R Finger31>
105. <Bip02 R Finger3Nub>
106. <Bip02 R Finger41>
107. <Bip02 R Finger4Nub>
108. <Bone87>
109. <Bone04>
110. <Bone20>
111. <Bone15>
112. <Bone16>
113. <Bone22>
114. <Bone42>
115. <Bone44>
116. <Bone46>
117. <Bone48>
118. <Bone89>
119. <Bone90>
120. <Bone08>
121. <Bone09>
122. <Bone10>
123. <Bone12>
124. <Bone13>
125. <Bone50>
126. <Bone51>
127. <Bone52>
128. <Bone54>
129. <Bone55>
130. <Bone57>
131. <Bone58>
132. <Bone59>
```
