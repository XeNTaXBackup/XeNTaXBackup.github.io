## Post #1
- Username: andy97
- Rank: beginner
- Number of posts: 36
- Joined date: Sun Apr 28, 2019 8:15 pm
- Post datetime: 2019-05-19T19:00:24+00:00
- Post Title: [Noesis] Parsing bones

Hi, after successfully completing my first noesis script, now I'm learning how to parse bone data to apply it in mine. I've consulted [this thread](https://forum.xentax.com/viewtopic.php?f=29&t=19429) from Bigchillghost and understand somehow to get bone data well but imprecisely.

This is a demo of my noesis script used to read bones:

```
	bs = NoeBitStream(data)
	bs.seek(22, NOESEEK_REL)
	boneCount = bs.readUShort()
	print(boneCount)
	boneNames = []
	bs.seek(8, NOESEEK_REL)
	for i in range(0, boneCount):
		boneNames.append("bone_" + str(i))
	bones = []
	for i in range(0, boneCount):
            
            parentIndex = bs.read(">h")
            print(parentIndex[0])
            bs.seek(2, NOESEEK_REL)
            bs.seek(48, NOESEEK_REL)
            Matrix = []
            for j in range(0, 12):
                Matrix.append(bs.readFloat())
            boneMat = NoeMat43( [(Matrix[0],Matrix[1],Matrix[2]),
                                 (Matrix[3],Matrix[4],Matrix[5]),
                                 (Matrix[6],Matrix[7],Matrix[8]),
                                 (Matrix[9],Matrix[10],Matrix[11])
                                 ] )
            if i != parentIndex[0]:
                print("TRUE")
                bones.append( NoeBone(i, boneNames[i], boneMat, None, parentIndex[0]) )#boneIDs[i]
            else: bones.append( NoeBone(i, boneNames[i], boneMat, None, -1) )
            bs.seek(28, NOESEEK_REL)

	# Converting local matrix to world space
	for i in range(0, boneCount):
		j = bones[i].parentIndex
		if j != -1:
			bones[i].setMatrix(bones[i].getMatrix().__mul__(bones[j].getMatrix()))
	
	mdl = NoeModel()
	mdl.setBones(bones)
	mdlList.append(mdl)
	rapi.setPreviewOption("setAngOfs", "0 -90 -90")
	return 1

```


This is what I've done so far:


But then I wonder why my script couldn't show the red lines which link to those points , am I missing anything to get them? And what are those lines called?

I've attached my file as well. It's just a snippet of bone data cut from the original file but the code above can work with this sample 
[bone.zip](https://xentaxbackup.github.io/file/16263_bone.zip)
## Post #2
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2019-05-19T19:23:52+00:00
- Post Title: [Noesis] Parsing bones

i don't want say something stupid, but that red lines you usually see in Noesis, aren't how bones are parented-linked ? in your picture i think every bone is standalone
## Post #3
- Username: andy97
- Rank: beginner
- Number of posts: 36
- Joined date: Sun Apr 28, 2019 8:15 pm
- Post datetime: 2019-05-20T04:28:20+00:00
- Post Title: [Noesis] Parsing bones

> Reply from fil1969 ↑Mon May 20, 2019 3:23 am at Mon May 20, 2019 3:23 am
>
> 
i don't want say something stupid, but that red lines you usually see in Noesis, aren't how bones are parented-linked ? in your picture i think every bone is standalone

I got your point, I tried to find the parentIndex and this is the result:


I assumed those bytes are parent bone indices


But it seems like the bones don't link to the correct parent bone as they should
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-05-20T10:39:14+00:00
- Post Title: [Noesis] Parsing bones

First of all: update for use of parenting indices is missing in your script in the opening post.
Parent index is still -1 for all bones:
bones.append( NoeBone(i, boneNames, boneMat, None, -1)

```
		boneNames.append("bone_" + str(i))
```
whaaat?
You can't seriously handle bone names like so!
There is a table of bone names at offset 0x591D. Why not use it?

I'd start with the "main" bones head, neck, shoulder, wrist, spine, thigh, toe  and so on and set up a hierarchy for them manually in a first try.
(arm, hand, finger are missing from the table, btw)

you may read my posts here concerning the creation of an smd file for a skeleton:

> Reply from shakotay2 ↑Sun Dec 23, 2018 11:22 pm at Sun Dec 23, 2018 11:22 pm
>
> 
(You could get the required matrices for such by logging them using your script. That's how I would do it.)

After you manged to create a proper smd file you could continue improving your Noesis script.
Or you could ask Bigchillghost, of course.

(I'd strongly recommend to start with a skeleton with less bones, btw.)
## Post #5
- Username: andy97
- Rank: beginner
- Number of posts: 36
- Joined date: Sun Apr 28, 2019 8:15 pm
- Post datetime: 2019-05-20T12:40:45+00:00
- Post Title: [Noesis] Parsing bones

> Reply from shakotay2 ↑Mon May 20, 2019 6:39 pm at Mon May 20, 2019 6:39 pm
>
> 
First of all: update for use of parenting indices is missing in your script in the opening post.
Parent index is still -1 for all bones:
bones.append( NoeBone(i, boneNames, boneMat, None, -1)

I've done it, my current issue is I can't figure out what the parent index of each bone is as it has no clue  (The failure result is shown above)

> Reply from shakotay2 ↑Mon May 20, 2019 6:39 pm at Mon May 20, 2019 6:39 pm
>
> whaaat?
You can't seriously handle bone names like so!
There is a table of bone names at offset 0x591D. Why not use it?

Don't get me wrong, as far as I'm a newbie. I've tried to see the result in Noesis first before considering anything else. Those names are just temporary, I will consider them after solving my current problem  (and gaining some basic knowledge about bones as well)

> Reply from shakotay2 ↑Mon May 20, 2019 6:39 pm at Mon May 20, 2019 6:39 pm
>
> 
you may read my posts here concerning the creation of an smd file for a skeleton:
(You could get the required matrices for such by logging them using your script. That's how I would do it.)

After you manged to create a proper smd file you could continue improving your Noesis script.
Or you could ask Bigchillghost, of course.

(I'd strongly recommend to start with a skeleton with less bones, btw.)

Thank you, I will try it
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-05-20T14:29:25+00:00
- Post Title: [Noesis] Parsing bones

> Reply from andy97 ↑Mon May 20, 2019 8:40 pm at Mon May 20, 2019 8:40 pm
>
> Those names are just temporary, I will consider them after solving my current problemYou need to print out the parenting IDs to understand whether they fit. And the bone names list may help to start with important bones only:
  1. CHEEK_00_L
  2. CHEEK_00_R
  3. CHEEK_01_L
  4. CHEEK_01_R
  5. CHEEK_02_L
  6. CHEEK_02_R
  7. CHIN
  8. CLANK_L
  9. CLANK_R
 10. CLAVICLE_L
 11. CLAVICLE_R
 12. CLOTH_00_L
 13. CLOTH_00_R
 14. CLOTH_01_L
 15. CLOTH_01_R
 16. CLOTH_02_L
 17. CLOTH_02_R
 18. CLOTH_03_L
 19. CLOTH_03_R
 20. CLOTH_04_L
 21. CLOTH_04_R
 22. CLOTH_05_L
 23. CLOTH_05_R
 24. CLOTH_06_L
 25. CLOTH_07_L
 26. CLOTH_08_L
 27. CLOTH_09_L
 28. CLOTH_10_L
 29. CLOTH_G_00
 30. CLOTH_G_01
 31. CLOTH_G_03
 32. CLOTH_G_04
 33. CLOTH_G_05
 34. CLOTH_G_06
 35. EFFECT_L
 36. EFFECT_R
 37. ELBOWROLL_L
 38. ELBOWROLL_R
 39. ELBOW_L
 40. ELBOW_R
 41. EM_TIP_00
 42. EM_TIP_00_L
 43. EM_TIP_00_R
 44. EQUIPMENT_00
 45. EQUIPMENT_00_L
 46. EQUIPMENT_00_R
 47. EYE
 48. EYEBALL_01_L
 49. EYEBALL_01_R
 50. EYEBALL_02_L
 51. EYEBALL_02_R
 52. EYEBROWS_00_L
 53. EYEBROWS_00_R
 54. EYEBROWS_01_L
 55. EYEBROWS_01_R
 56. EYEBROWS_02_L
 57. EYEBROWS_02_R
 58. EYEBROWS_03_L
 59. EYEBROWS_03_R
 60. EYEDOWN_00_L
 61. EYEDOWN_00_R
 62. EYEDOWN_01_L
 63. EYEDOWN_01_R
 64. EYEDOWN_02_L
 65. EYEDOWN_02_R
 66. EYEUP_00_L
 67. EYEUP_00_R
 68. EYEUP_01_L
 69. EYEUP_01_R
 70. EYEUP_02_L
 71. EYEUP_02_R
 72. FACE
 73. F_FORE1_L
 74. F_FORE1_R
 75. F_FORE2_L
 76. F_FORE2_R
 77. F_FORE3_L
 78. F_FORE3_R
 79. F_LITTLE1_L
 80. F_LITTLE1_R
 81. F_LITTLE2_L
 82. F_LITTLE2_R
 83. F_LITTLE3_L
 84. F_LITTLE3_R
 85. F_MEDICINAL1_L
 86. F_MEDICINAL1_R
 87. F_MEDICINAL2_L
 88. F_MEDICINAL2_R
 89. F_MEDICINAL3_L
 90. F_MEDICINAL3_R
 91. F_MIDDLE1_L
 92. F_MIDDLE1_R
 93. F_MIDDLE2_L
 94. F_MIDDLE2_R
 95. F_MIDDLE3_L
 96. F_MIDDLE3_R
 97. F_THUMB1_L
 98. F_THUMB1_R
 99. F_THUMB2_L
100. F_THUMB2_R
101. F_THUMB3_L
102. F_THUMB3_R
103. HAIR
104. HEAD
105. MOUTH
106. MOUTHDOWN_00
107. MOUTHDOWN_00_L
108. MOUTHDOWN_00_R
109. MOUTHDOWN_01_L
110. MOUTHDOWN_01_R
111. MOUTHDOWN_02_L
112. MOUTHDOWN_02_R
113. MOUTHDOWN_03_L
114. MOUTHDOWN_03_R
115. MOUTHUP_00
116. MOUTHUP_00_L
117. MOUTHUP_00_R
118. MOUTHUP_01_L
119. MOUTHUP_01_R
120. MOUTHUP_02_L
121. MOUTHUP_02_R
122. MOUTHUP_03_L
123. MOUTHUP_03_R
124. MOUTHUP_04_L
125. MOUTHUP_04_R
126. NECK
127. NOSE
128. NULL
129. OPTION_00
130. OPTION_01
131. OPTION_02
132. OPTION_03
133. OPTION_04
134. OPTION_05
135. OPTION_06
136. OPTION_10
137. OPTION_11
138. OPTION_12
139. OPTION_13
140. OPTION_14
141. RESERVE
142. SHOULDER_L
143. SHOULDER_R
144. SPINE1
145. SPINE2
146. SPINE3
147. THIGH_L
148. THIGH_R
149. THROW
150. TOE1_L
151. TOE1_R
152. TOE2_L
153. TOE2_R
154. TOOTHDOWN_00
155. TOOTHDOWN_00_L
156. TOOTHDOWN_00_R
157. TOOTHDOWN_01
158. TOOTHDOWN_01_L
159. TOOTHDOWN_01_R
160. TOOTHUP_00
161. TOOTHUP_00_L
162. TOOTHUP_00_R
163. TOOTHUP_01
164. TOOTHUP_01_L
165. TOOTHUP_01_R
166. UTILITY_00
167. UTILITY_01
168. UTILITY_02
169. UTILITY_03
170. UTILITY_04
171. UTILITY_05
172. UTILITY_06
173. UTILITY_07
174. UTILITY_08
175. UTILITY_09
176. WAIST
177. WRIST_L
178. WRIST_R
## Post #7
- Username: andy97
- Rank: beginner
- Number of posts: 36
- Joined date: Sun Apr 28, 2019 8:15 pm
- Post datetime: 2019-05-20T15:40:42+00:00
- Post Title: [Noesis] Parsing bones

> Reply from shakotay2 ↑Mon May 20, 2019 10:29 pm at Mon May 20, 2019 10:29 pm
>
> 
You need to print out the parenting IDs to understand whether they fit. And the bone names list may help to start with important bones only:

Thank you for your suggestion, I have done the name part   , it looks better than hex data by using data viewer of noesis, which helped me realize that I was wrong in parent indices  . Btw, I have no clue atm since only those remaining bytes are unused in each bone
