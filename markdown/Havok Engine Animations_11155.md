## Post #1
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2014-01-24T01:55:24+00:00
- Post Title: Havok Engine Animations

The Havok engine is fairly popular, and there are [official tools](http://havok.com/try-havok) for it. However, they only work for native Havok .hkx files.
The issue here is how to extract those out of games. 

[Here are some sample files](http://puu.sh/880cs.zip), [and an accompanying skeleton](http://puu.sh/880kF.smd). They use Havok Engine "hkaSplineCompressedAnimation".

To my knowledge nobody has managed to extract .hkx files out of these. Would anyone be willing to take a look?
## Post #2
- Username: mono24
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2014-01-24T02:47:43+00:00
- Post Title: Havok Engine Animations

I've looked at The Witcher 2 files and I've also looked at the havok files that the Assassin's Creed games use.  I have yet to make anything out of either one.

From what I understand, the havok engine is very configurable which means that each developer that uses it could create a completely different file.

Makes it somewhat tougher to decipher the file.

-- MDA
## Post #3
- Username: Bastien
- Rank: advanced
- Number of posts: 70
- Joined date: Sun Apr 15, 2012 8:08 am
- Post datetime: 2014-01-24T02:56:14+00:00
- Post Title: Havok Engine Animations

To visualize it in the havok tools, you also have to have an skeleton, and the correct version (could be above the version of the havok file, according to one test I did).

I took a quick look and the files doesn't seem to be compressed. The "real" havok file starts when you see this ID magic: 0x57E0E057.
The thing is it's in binary mode, and it's quite an old version (6.5). I mentioned in other post there's a tool for converting from binary to xml and/or KF files, to then be imported to 3ds max.
You could try creating a new file cutting the havok file and changing the version to the same as skyrim's (hkxcmd tool only reads those) "hk_2010.2.0-r1" and run hkxcmd. I don't think it will work though. I read the source in the past and is pretty big, didn't get much info on the format unfortunately.
[https://github.com/figment/hkxcmd](https://github.com/figment/hkxcmd) 
[http://www.youtube.com/watch?v=OoyP_SWaxnE](http://www.youtube.com/watch?v=OoyP_SWaxnE)

I've never made an importer with animations but I really want to do my first for havok, the only problem I didn't figure it out how to interpret the xml code yet   (only a small part to match bone indices)
As soon as I find out, I could help you with this version.

Here's one sample xml havok animation, and also attached the binary equivalent in case someone could throw a hint.

```
<hkpackfile classversion="8" contentsversion="hk_2010.2.0-r1" toplevelobject="#0040">

	<hksection name="__data__">

		<hkobject name="#0043" class="hkaDefaultAnimatedReferenceFrame" signature="0x6d85e445">
			<!-- memSizeAndFlags SERIALIZE_IGNORED -->
			<!-- referenceCount SERIALIZE_IGNORED -->
			<hkparam name="up">(0.000000 1.000000 0.000000 0.000000)</hkparam>
			<hkparam name="forward">(0.000000 0.000000 1.000000 0.000000)</hkparam>
			<hkparam name="duration">1.066667</hkparam>
			<hkparam name="referenceFrameSamples" numelements="33">
				(0.000000 0.000000 0.000000 0.000977)
				(0.000001 0.000000 0.028074 0.000977)
				(0.000002 0.000000 0.136542 0.000977)
				(0.000003 0.000000 0.688910 0.000977)
				(0.000004 0.000000 1.291227 0.000977)
				(0.000006 0.000000 1.904401 0.000977)
				(0.000007 0.000000 2.182335 0.000977)
				(0.000008 0.000000 2.460175 0.000977)
				(0.000009 0.000000 2.737976 0.000977)
				(0.000010 0.000000 3.015785 0.000977)
				(0.000011 0.000000 3.293650 0.000977)
				(0.000012 0.000000 3.571601 0.000977)
				(0.000013 0.000000 3.849666 0.000977)
				(0.000014 0.000000 4.127872 0.000977)
				(0.000016 0.000000 4.406248 0.000977)
				(0.000017 0.000000 4.684819 0.000977)
				(0.000018 0.000000 4.963606 0.000977)
				(0.000018 0.000000 5.286085 0.000977)
				(0.000018 0.000000 5.602636 0.000977)
				(0.000018 0.000000 5.873286 0.000977)
				(0.000018 0.000000 6.080829 0.000977)
				(0.000018 0.000000 6.186240 0.000977)
				(0.000018 0.000000 6.214421 0.000977)
				(0.000018 0.000000 6.214398 0.000977)
				(0.000018 0.000000 6.213490 0.000977)
				(0.000018 -0.041430 6.211854 0.000977)
				(0.000020 -0.200448 6.209347 0.000977)
				(0.000023 -0.502627 6.206564 0.000977)
				(0.000027 -0.908922 6.203559 0.000977)
				(0.000031 -1.380289 6.200387 0.000977)
				(0.000034 -1.877685 6.197104 0.000977)
				(0.000037 -2.362068 6.193763 0.000977)
				(0.000037 -2.794391 6.190422 0.000977)
			</hkparam>
		</hkobject>

		<hkobject name="#0042" class="hkaSplineCompressedAnimation" signature="0x792ee0bb">
			<!-- memSizeAndFlags SERIALIZE_IGNORED -->
			<!-- referenceCount SERIALIZE_IGNORED -->
			<hkparam name="type">HK_SPLINE_COMPRESSED_ANIMATION</hkparam>
			<hkparam name="duration">1.066667</hkparam>
			<hkparam name="numberOfTransformTracks">30</hkparam>
			<hkparam name="numberOfFloatTracks">0</hkparam>
			<hkparam name="extractedMotion">#0043</hkparam>
			<hkparam name="annotationTracks" numelements="0"></hkparam>
			<hkparam name="numFrames">33</hkparam>
			<hkparam name="numBlocks">1</hkparam>
			<hkparam name="maxFramesPerBlock">256</hkparam>
			<hkparam name="maskAndQuantizationSize">120</hkparam>
			<hkparam name="blockDuration">8.500002</hkparam>
			<hkparam name="blockInverseDuration">0.117647</hkparam>
			<hkparam name="frameDuration">0.033333</hkparam>
			<hkparam name="blockOffsets" numelements="1">
				0
			</hkparam>
			<hkparam name="floatBlockOffsets" numelements="1">
				4744
			</hkparam>
			<hkparam name="transformOffsets" numelements="0"></hkparam>
			<hkparam name="floatOffsets" numelements="0"></hkparam>
			<hkparam name="data" numelements="4752">
				69 0 0 0 69 112 240 0 69 5 240 0 69 1 240 0
				69 1 240 0 69 1 240 0 69 1 10 0 69 5 240 0
				69 1 240 0 69 1 240 0 69 1 240 0 69 1 10 0
				69 1 240 0 69 1 240 0 69 1 240 0 69 7 240 0
				69 7 15 0 69 1 240 0 69 1 240 0 69 1 240 0
				69 7 15 0 69 1 240 0 69 1 240 0 69 1 15 0
				69 7 240 0 69 7 15 0 69 1 240 0 69 1 240 0
				69 1 240 0 69 112 240 0 24 0 1 0 0 1 2 3
				4 5 11 15 16 17 18 19 20 21 22 23 24 25 26 27
				28 29 30 31 32 32 0 0 230 166 17 189 4 186 35 61
				24 182 35 63 186 249 148 63 0 248 31 188 0 32 180 58
				8 121 181 133 113 231 165 48 41 58 26 231 0 0 0 0
				178 230 180 89 27 38 218 229 220 156 2 90 127 229 214 220
				143 144 100 229 222 223 15 150 162 228 255 227 27 155 26 228
				105 151 143 169 105 224 183 173 12 182 105 224 58 196 253 197
				105 224 73 219 133 216 90 188 244 236 201 230 30 140 0 250
				195 233 186 93 255 255 114 224 59 52 201 254 1 204 12 18
				197 247 169 168 0 0 32 236 247 121 102 19 26 221 39 96
				127 80 236 203 93 108 28 155 183 185 94 144 244 221 127 167
				40 190 255 255 32 150 244 231 64 254 71 134 255 255 30 239
				116 120 91 248 86 223 0 0 27 0 1 0 0 1 2 3
				4 5 6 7 9 13 15 16 17 18 19 20 21 22 23 24
				25 26 27 28 29 30 31 32 32 100 252 192 99 46 186 108
				196 245 45 44 29 197 121 45 31 94 189 187 44 140 190 179
				146 44 183 238 173 175 44 205 94 171 139 44 224 62 169 106
				44 1 191 165 49 44 56 223 159 200 43 85 95 156 142 43
				92 203 238 127 12 8 77 223 82 13 175 205 208 172 29 88
				237 196 217 29 247 188 186 16 30 151 204 178 67 30 66 156
				173 112 30 6 76 171 145 30 234 11 172 164 30 248 171 176
				160 30 42 92 184 134 30 106 76 193 96 30 162 204 201 58
				30 190 108 208 34 30 189 12 213 28 30 171 124 216 32 30
				142 236 224 175 61 0 0 0 18 104 75 189 233 220 226 61
				30 0 1 0 0 1 2 3 4 5 6 7 8 9 10 12
				14 15 16 17 18 19 20 21 22 23 24 25 26 27 28 29
				30 31 32 32 244 99 106 157 89 6 178 115 221 89 6 65
				122 6 90 73 100 118 8 89 202 55 108 171 88 63 168 84
				128 88 252 23 86 131 88 202 103 87 134 88 165 183 88 136
				88 138 247 89 137 88 119 23 91 138 88 96 247 92 139 88
				79 71 94 140 88 69 167 94 141 88 35 21 101 51 88 103
				226 108 231 87 44 80 113 253 71 17 193 114 9 72 28 177
				115 5 72 44 209 117 252 71 47 81 120 237 71 14 33 122
				214 71 180 224 121 184 71 46 208 119 154 71 118 208 116 130
				87 37 1 113 119 87 222 145 108 124 87 154 178 103 143 87
				82 179 98 170 87 3 244 93 199 87 168 164 89 225 87 0
				127 42 227 62 30 0 1 0 0 1 2 3 4 5 6 7
				8 9 10 11 13 15 16 17 18 19 20 21 22 23 24 25
				26 27 28 29 30 31 32 32 35 200 126 180 51 21 120 126
				199 48 6 200 126 237 110 26 152 125 188 111 40 200 126 61
				52 48 24 127 202 53 48 248 126 129 53 49 232 126 73 53
				49 216 126 31 53 49 216 126 254 52 49 200 126 230 52 49
				200 126 213 52 47 200 126 196 52 44 216 126 196 52 17 200
				125 79 48 4 56 125 22 109 4 88 125 238 107 4 136 125
				43 108 4 120 125 28 108 4 104 125 250 107 4 72 125 208
				107 4 40 125 174 107 4 8 125 166 107 5 8 125 192 107
				6 24 125 245 107 7 56 125 70 108 7 120 125 175 108 8
				184 125 42 109 8 8 126 176 109 8 88 126 59 110 7 152
				126 196 110 0 101 7 227 62 27 0 1 0 0 1 2 3
				4 5 7 9 11 13 15 16 17 18 19 20 21 22 23 24
				25 26 27 28 29 30 31 32 32 188 200 123 36 62 230 40
				120 151 63 36 9 116 50 47 1 201 130 187 46 249 104 123
				215 60 231 56 109 201 58 239 216 108 7 59 253 232 108 71
				59 16 9 109 136 59 41 233 108 195 59 72 57 108 241 59
				172 73 125 107 62 205 169 142 228 62 74 250 142 84 61 125
				154 137 83 60 124 202 137 87 60 118 90 138 102 60 102 186
				139 135 60 67 90 142 193 60 8 154 146 21 61 189 153 151
				118 61 115 89 156 207 61 55 73 160 20 62 17 9 163 66
				62 3 185 164 88 62 7 57 165 87 62 21 217 164 69 62
				39 201 163 35 62 0 0 0 121 169 44 62 17 0 1 0
				0 1 2 3 4 5 6 7 8 9 10 14 15 16 17 18
				19 32 32 126 86 134 216 58 116 22 134 172 58 126 86 134
				216 58 0 55 140 17 61 83 55 147 26 61 208 55 140 168
				58 215 231 139 122 58 218 183 139 93 58 220 151 139 79 58
				220 151 139 78 58 220 167 139 85 58 210 23 140 151 58 209
				39 140 163 58 189 87 139 189 58 148 151 137 210 58 186 54
				134 219 58 126 86 134 216 58 126 86 134 216 58 0 0 0
				245 171 177 61 254 167 246 0 56 0 0 0 12 48 78 189
				247 59 226 189 32 0 1 0 0 1 2 3 4 5 6 7
				8 9 10 11 12 13 14 15 16 17 18 19 20 21 22 23
				24 25 26 27 28 29 30 31 32 32 7 90 96 197 26 253
				90 124 32 27 19 186 136 60 27 91 217 140 102 26 238 91
				134 105 25 167 171 131 153 24 61 124 131 136 24 203 44 131
				116 24 84 205 130 91 24 217 61 130 63 24 92 126 129 30
				24 219 142 128 251 23 85 111 127 212 23 199 31 126 170 23
				197 159 124 128 7 91 31 123 87 7 185 143 122 204 24 17
				158 126 8 26 204 204 128 101 26 113 172 127 93 26 131 76
				127 100 26 172 156 125 110 26 216 188 121 109 26 241 236 115
				77 26 229 220 110 18 26 188 188 107 206 25 121 124 106 134
				25 33 188 106 62 25 178 43 108 251 24 45 107 110 191 24
				142 42 113 139 24 201 57 116 96 24 183 72 119 62 24 0
				126 42 227 62 32 0 1 0 0 1 2 3 4 5 6 7
				8 9 10 11 12 13 14 15 16 17 18 19 20 21 22 23
				24 25 26 27 28 29 30 31 32 32 1 200 127 87 124 234
				167 128 68 127 207 71 130 198 127 226 215 128 58 126 247 7
				128 56 127 254 135 127 155 32 255 87 127 18 33 0 24 127
				127 33 2 216 126 226 33 4 136 126 56 34 5 72 126 129
				34 6 24 126 185 34 6 248 125 224 34 6 248 125 245 34
				5 24 126 246 34 5 56 126 229 34 255 183 126 75 35 250
				87 127 196 35 244 23 128 251 35 242 119 128 0 36 242 119
				128 36 36 242 103 128 105 36 244 7 128 145 36 247 135 127
				90 36 250 55 127 205 35 252 39 127 36 35 254 39 127 99
				34 255 71 127 145 33 255 87 127 179 32 1 120 127 201 127
				2 136 127 183 126 4 152 127 81 125 6 168 127 67 123 0
				100 7 227 62 32 0 1 0 0 1 2 3 4 5 6 7
				8 9 10 11 12 13 14 15 16 17 18 19 20 21 22 23
				24 25 26 27 28 29 30 31 32 32 140 24 131 74 113 146
				231 125 43 96 252 38 116 111 97 232 168 131 91 116 25 233
				138 118 116 234 200 137 125 113 232 120 137 86 113 229 120 137
				66 113 224 200 137 65 113 218 72 138 85 113 210 248 138 125
				113 201 184 139 185 113 191 152 140 9 114 181 120 141 105 114
				171 72 142 216 114 162 8 143 81 115 184 120 139 123 115 239
				184 131 254 114 254 8 123 144 114 243 248 118 103 114 243 184
				119 70 114 242 120 122 6 114 234 248 127 213 113 224 152 135
				221 113 222 72 142 21 114 231 232 146 79 114 247 200 149 142
				114 11 41 151 212 114 35 137 151 37 115 63 9 151 133 115
				93 233 149 252 115 125 9 148 151 116 163 41 145 126 117 0
				119 169 44 62 14 0 1 0 0 1 2 3 4 5 6 8
				10 15 16 17 18 19 32 32 246 42 128 78 59 252 74 128
				174 59 236 58 128 198 59 155 74 127 1 59 44 58 126 15
				58 181 105 124 163 57 173 73 124 156 57 165 25 124 149 57
				166 41 124 150 57 180 105 124 162 57 212 249 124 192 57 253
				153 125 229 57 228 25 124 128 58 128 153 121 216 58 128 153
				121 216 58 0 0 172 177 61 0 232 127 148 80 0 0 0
				76 142 233 61 28 0 1 0 0 1 2 3 4 5 6 7
				8 9 10 13 14 15 16 17 18 19 22 23 24 25 26 27
				28 29 30 31 32 32 179 247 125 125 56 140 215 123 187 56
				110 167 121 48 57 111 55 121 143 57 123 39 121 222 57 135
				231 120 252 57 134 167 121 242 57 136 103 122 213 57 138 55
				123 168 57 141 39 124 113 57 143 23 125 53 57 145 7 128
				115 56 146 7 129 56 56 147 247 129 5 56 180 215 129 251
				55 204 7 129 23 56 205 247 126 90 56 193 119 125 174 56
				173 151 127 61 57 169 247 127 101 57 169 247 127 122 57 175
				103 127 99 57 183 167 126 38 57 193 23 126 216 56 199 215
				125 145 56 202 231 125 107 56 203 7 126 105 56 203 7 126
				123 56 204 231 125 150 56 0 52 87 229 61 24 0 1 0
				0 1 2 3 4 5 6 9 12 15 16 17 18 19 22 23
				24 25 26 27 28 29 30 31 32 32 108 71 122 10 57 29
				119 123 219 56 218 6 125 167 56 213 214 124 161 56 232 38
				124 197 56 5 231 123 205 56 5 55 124 181 56 18 183 125
				98 56 22 199 127 35 56 23 135 130 224 55 92 103 129 26
				56 140 167 127 93 56 150 247 123 214 56 140 71 121 69 57
				132 215 122 174 57 130 39 123 205 57 131 39 123 221 57 133
				215 122 205 57 137 119 122 160 57 141 71 122 103 57 144 87
				122 51 57 146 119 122 25 57 148 151 122 26 57 150 151 122
				40 57 153 103 122 62 57 0 71 117 230 61 26 0 1 0
				0 1 2 3 4 5 6 8 9 12 14 15 16 17 18 19
				22 23 24 25 26 27 28 29 30 31 32 32 111 7 122 9
				57 30 199 122 84 56 226 182 123 148 55 222 230 123 141 55
				241 198 123 194 55 11 39 124 224 55 7 215 124 225 55 10
				55 126 228 55 13 231 126 234 55 17 199 128 10 56 21 71
				130 19 56 23 55 131 13 56 94 247 129 89 56 143 23 128
				150 56 153 39 124 237 56 146 39 121 70 57 148 39 122 176
				57 149 71 122 206 57 149 55 122 222 57 149 7 122 206 57
				148 231 121 160 57 147 247 121 103 57 147 71 122 52 57 149
				151 122 25 57 151 183 122 27 57 153 167 122 41 57 156 103
				122 62 57 0 49 217 52 62 159 120 25 60 187 63 251 60
				25 0 1 0 0 1 2 3 4 5 6 7 8 9 10 11
				14 15 16 17 18 19 20 21 22 23 25 27 29 32 32 205
				138 90 19 94 217 138 93 131 94 201 186 97 33 95 101 90
				13 146 54 204 217 32 242 54 109 89 44 14 55 91 57 46
				9 55 84 217 46 0 55 84 89 46 244 54 90 233 44 230
				54 101 217 42 213 54 115 89 40 193 54 155 25 32 127 54
				164 201 29 105 54 19 122 21 97 54 96 26 15 91 54 238
				9 12 175 53 121 41 11 247 52 166 57 8 218 52 199 105
				76 136 95 222 153 75 117 95 238 249 74 110 95 3 74 74
				111 95 14 10 74 115 95 18 26 74 118 95 18 74 74 122
				95 0 0 0 206 204 76 61 247 81 184 61 169 214 35 60
				102 136 160 186 79 0 0 0 156 18 56 62 31 0 1 0
				0 1 2 3 4 5 6 7 8 9 10 11 12 13 15 16
				17 18 19 20 21 22 23 24 25 26 27 28 29 30 31 32
				32 209 23 71 97 59 221 70 85 107 58 241 117 97 16 58
				120 100 108 113 59 180 179 117 130 60 178 3 120 34 61 177
				211 119 37 61 183 179 118 40 61 195 243 116 37 61 210 195
				114 26 61 230 163 112 1 61 254 131 110 223 60 29 68 108
				184 60 66 4 106 142 60 151 196 101 59 60 200 100 87 48
				59 60 245 85 56 58 166 166 113 18 56 198 87 121 9 54
				15 168 113 247 52 18 200 107 198 52 229 119 107 240 52 4
				120 113 90 53 175 167 118 249 53 42 199 121 193 54 156 38
				125 139 55 123 22 121 15 56 148 102 113 117 56 214 102 104
				194 56 39 231 95 251 56 108 167 89 32 57 136 55 87 45
				57 0 0 0 17 214 139 62 30 0 1 0 0 1 2 3
				4 5 6 7 8 9 10 11 14 15 16 17 18 19 20 21
				22 23 24 25 26 27 28 29 30 31 32 32 177 247 126 36
				59 156 119 125 212 60 183 199 125 138 61 78 232 131 181 62
				194 216 139 205 63 211 232 142 121 47 203 24 143 63 47 191
				216 142 18 47 179 88 142 241 46 167 152 141 218 46 155 200
				140 204 46 143 232 139 194 46 102 168 136 175 46 89 152 135
				164 46 84 248 131 61 47 46 72 127 207 63 54 119 116 197
				62 86 6 113 215 61 108 213 109 235 60 14 229 108 112 60
				103 53 111 109 60 227 85 114 199 60 51 150 114 76 61 71
				134 113 169 61 19 6 110 229 61 57 70 110 32 62 134 150
				112 82 62 229 6 116 121 62 65 199 119 147 62 135 199 122
				162 62 162 247 123 166 62 0 76 57 139 62 29 0 1 0
				0 1 2 3 4 5 6 7 8 9 11 13 15 16 17 18
				19 20 21 22 23 24 25 26 27 28 29 30 31 32 32 129
				87 129 235 56 33 40 154 152 58 237 72 173 67 59 135 201
				182 98 58 255 121 179 41 57 62 250 173 134 56 81 90 173
				98 56 93 26 173 74 56 98 74 173 61 56 98 202 173 55
				56 88 10 175 61 56 73 10 176 79 56 61 74 176 94 56
				24 186 166 20 56 243 217 159 189 55 229 168 169 53 56 31
				152 160 123 58 69 40 143 37 60 91 40 144 22 60 106 136
				155 2 59 121 104 162 21 58 137 232 161 98 57 147 200 156
				132 56 151 168 149 171 55 146 8 149 124 55 132 72 151 146
				55 116 24 155 212 55 105 72 159 36 56 98 120 162 106 56
				97 200 163 135 56 0 0 0 4 99 150 61 136 150 5 187
				214 186 27 61 84 16 164 202 57 0 0 0 156 142 116 62
				29 0 1 0 0 1 2 3 4 5 6 7 8 9 11 12
				15 16 17 18 19 20 21 22 23 24 25 26 27 28 29 30
				31 32 32 2 121 100 209 57 208 136 100 192 57 173 168 102
				165 57 156 56 111 100 57 142 216 121 11 57 138 216 128 200
				56 147 72 131 174 56 151 216 132 167 56 154 168 133 171 56
				157 24 134 178 56 165 152 134 179 56 167 152 134 179 56 162
				56 134 184 56 53 136 127 158 57 211 119 122 145 58 186 7
				126 148 58 187 183 131 64 58 167 23 131 117 58 158 71 130
				144 58 159 135 129 148 58 165 231 128 134 58 180 135 128 120
				58 204 55 128 134 58 234 231 127 170 58 9 88 127 217 58
				42 152 126 3 59 74 184 125 23 59 103 216 124 19 59 126
				8 124 253 58 140 56 123 218 58 0 0 0 96 15 88 61
				30 0 1 0 0 1 2 3 4 5 6 7 8 9 10 11
				12 15 16 17 18 19 20 21 22 23 24 25 26 27 28 29
				30 31 32 32 111 202 139 150 52 124 58 138 166 52 121 250
				136 152 52 75 154 135 48 52 21 106 134 172 51 250 121 133
				98 51 249 169 132 90 51 6 218 131 107 51 24 250 130 142
				51 42 10 130 186 51 54 234 128 231 51 59 202 127 20 52
				62 138 126 71 52 62 170 122 244 52 87 105 123 97 53 164
				88 127 216 53 87 56 133 70 54 71 248 135 144 54 49 24
				136 198 54 36 152 135 227 54 31 184 134 232 54 33 216 133
				218 54 43 40 133 204 54 63 152 132 217 54 91 24 132 254
				54 122 104 131 45 55 155 136 130 88 55 185 104 129 110 55
				211 40 128 107 55 231 232 126 86 55 241 168 125 52 55 0
				16 123 154 61 88 130 37 166 77 0 0 0 51 217 52 62
				138 120 25 60 128 63 251 188 30 0 1 0 0 1 2 3
				4 5 6 7 8 9 10 11 14 15 16 17 18 19 20 21
				22 23 24 25 26 27 28 29 30 31 32 32 152 22 98 77
				31 165 134 95 27 31 119 86 91 0 31 147 37 83 23 31
				109 100 76 37 31 193 131 238 157 52 155 99 237 146 52 134
				227 236 139 52 127 3 237 134 52 130 163 237 130 52 143 147
				238 127 52 162 227 71 230 30 229 163 71 204 30 246 131 71
				195 30 10 52 75 120 30 85 52 82 64 30 214 132 90 35
				30 117 197 98 55 30 16 134 106 133 30 131 38 113 244 30
				182 118 117 112 31 175 166 118 233 31 137 134 247 91 55 81
				150 240 43 55 16 150 235 226 54 204 213 232 137 54 135 165
				231 46 54 70 133 231 217 53 14 213 231 148 53 231 84 232
				103 53 216 132 232 86 53 0 199 204 76 61 231 81 184 61
				16 215 35 188 8 74 4 152 103 0 0 0 158 18 56 62
				29 0 1 0 0 1 2 3 4 5 6 7 8 9 11 13
				15 16 17 18 19 20 21 22 23 24 25 26 27 28 29 30
				31 32 32 229 100 199 250 58 226 212 188 16 59 248 164 183
				25 59 76 5 196 216 58 38 117 204 229 58 223 84 205 224
				58 220 100 204 221 58 214 164 202 201 58 208 84 200 174 58
				204 180 197 144 58 202 36 192 99 58 199 4 186 60 58 195
				132 179 22 58 76 133 177 202 57 225 117 176 133 57 127 198
				171 61 57 32 247 161 252 56 186 151 150 207 56 61 232 141
				184 56 164 200 135 178 56 193 232 131 196 56 221 40 130 213
				56 247 56 130 227 56 15 201 131 239 56 33 73 135 245 56
				46 121 140 245 56 52 89 146 241 56 52 217 151 234 56 48
				217 155 227 56 43 89 157 222 56 0 0 0 18 214 139 62
				29 0 1 0 0 1 2 3 4 5 6 7 8 9 10 11
				14 15 16 17 18 19 20 21 22 23 24 25 26 27 29 30
				31 32 32 76 218 134 36 58 117 170 134 242 57 136 154 135
				34 58 124 106 140 92 59 126 122 147 221 60 110 250 151 193
				61 96 170 152 247 61 83 218 152 25 62 69 170 152 43 62
				57 58 152 47 62 46 154 151 42 62 37 218 150 29 62 5
				106 148 234 61 249 185 147 224 61 180 41 145 235 61 118 41
				143 3 62 53 41 141 34 62 247 40 139 69 62 190 72 137
				103 62 143 168 135 133 62 109 120 134 156 62 107 136 134 167
				62 107 136 134 165 62 110 104 134 144 62 114 56 134 105 62
				120 248 133 55 62 134 88 133 198 61 139 24 133 149 61 143
				216 132 114 61 145 200 132 101 61 0 0 0 82 57 139 62
				22 0 1 0 0 1 2 3 4 5 7 9 12 14 15 16
				17 18 19 20 21 22 26 28 30 31 32 32 245 118 118 109
				53 202 182 120 60 53 246 102 120 120 53 255 7 109 63 55
				205 120 89 237 57 182 24 80 94 59 161 72 79 92 59 141
				184 77 96 59 115 216 74 112 59 103 24 73 113 59 100 104
				72 108 59 16 88 74 189 58 168 119 78 15 58 43 55 84
				100 57 162 38 91 202 56 23 150 98 74 56 151 181 105 234
				55 47 117 111 171 55 210 228 113 194 55 170 228 114 204 55
				147 132 115 210 55 144 148 115 210 55 146 116 115 210 55 0
				17 0 3 0 0 0 0 1 1 1 4 4 4 5 5 17
				17 17 19 19 19 32 32 32 32 0 0 0 238 130 172 61
				160 191 216 61 1 80 241 186 0 46 155 60 64 1 5 189
				0 3 249 188 255 255 254 255 26 0 30 247 30 247 249 8
				62 238 62 238 216 17 94 229 94 229 183 26 201 161 201 161
				65 94 52 94 53 94 204 161 159 26 160 26 86 229 191 17
				192 17 51 238 223 8 223 8 15 247 0 0 0 0 242 255
				0 0 0 0 248 255 0 0 1 0 255 255 53 94 54 94
				201 161 138 179 138 179 125 76 255 255 255 255 26 0 254 255
				255 255 17 0 254 255 255 255 8 0 253 255 255 255 0 0
				23 0 3 0 0 0 0 1 1 1 2 3 4 4 4 5
				5 5 17 17 17 18 18 18 19 19 19 32 32 32 32 215
				142 56 62 119 220 238 56 53 119 225 78 57 44 119 231 158
				57 35 119 243 110 58 14 119 11 47 60 227 118 53 63 63
				151 118 75 255 64 109 118 85 239 65 88 118 90 79 66 79
				118 94 175 66 70 118 99 15 67 61 118 99 15 67 61 118
				99 15 67 61 118 99 15 67 61 118 75 15 65 108 118 50
				15 63 155 118 25 47 61 202 118 3 159 59 241 118 237 14
				58 23 119 215 142 56 62 119 215 142 56 62 119 215 142 56
				62 119 215 142 56 62 119 0 0 0 0 0 0 0 0 0
			</hkparam>
			<hkparam name="endian">0</hkparam>
		</hkobject>

		<hkobject name="#0041" class="hkaAnimationBinding" signature="0x66eac971">
			<!-- memSizeAndFlags SERIALIZE_IGNORED -->
			<!-- referenceCount SERIALIZE_IGNORED -->
			<hkparam name="originalSkeletonName">skel_root</hkparam>
			<hkparam name="animation">#0042</hkparam>
			<hkparam name="transformTrackToBoneIndices" numelements="30">
				0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15
				16 17 18 19 40 41 42 43 44 45 46 47 48 69
			</hkparam>
			<hkparam name="floatTrackToFloatSlotIndices" numelements="0"></hkparam>
			<hkparam name="blendHint">NORMAL</hkparam>
		</hkobject>

		<hkobject name="#0044" class="hkaAnimationContainer" signature="0x8dc20333">
			<!-- memSizeAndFlags SERIALIZE_IGNORED -->
			<!-- referenceCount SERIALIZE_IGNORED -->
			<hkparam name="skeletons" numelements="0"></hkparam>
			<hkparam name="animations" numelements="1">
				#0042
			</hkparam>
			<hkparam name="bindings" numelements="1">
				#0041
			</hkparam>
			<hkparam name="attachments" numelements="0"></hkparam>
			<hkparam name="skins" numelements="0"></hkparam>
		</hkobject>

		<hkobject name="#0040" class="hkRootLevelContainer" signature="0x2772c11e">
			<hkparam name="namedVariants" numelements="1">
				<hkobject>
					<hkparam name="name">Animation Container</hkparam>
					<hkparam name="className">hkaAnimationContainer</hkparam>
					<hkparam name="variant">#0044</hkparam>
				</hkobject>
			</hkparam>
		</hkobject>

	</hksection>

</hkpackfile>

```

[havok_anim_binary.zip](https://xentaxbackup.github.io/file/6949_havok_anim_binary.zip)
## Post #4
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2014-01-24T09:06:26+00:00
- Post Title: Havok Engine Animations

You could try asking shakotay, he figured out how to convert them into a useable format.

He provided the W2 animations, and even included an example skeleton. 

I have a Sleeping Dogs skeleton [here](http://puu.sh/6wc9k.smd) but you'll have to ask him for the .hkx file, he's the only one that can extract them.
## Post #5
- Username: freakshow
- Rank: beginner
- Number of posts: 36
- Joined date: Mon Jan 20, 2014 2:08 am
- Post datetime: 2014-03-07T16:50:58+00:00
- Post Title: Havok Engine Animations

so witcher 2 animations are really made into something usable?
## Post #6
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2014-03-07T22:35:04+00:00
- Post Title: Havok Engine Animations

I highly doubt it, but you'll have to wait for one of those fellows to answer.
## Post #7
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2014-04-14T05:08:56+00:00
- Post Title: Havok Engine Animations

Say Bastien, did you ever figure this out? I tried those Skyrim tools but I never was able to find a working download link. I doubt it would work anyway, these are hk_2011.2.0-r1 instead of 2010.

Also, I fixed the dead links in the first post. Now the download has two types of files: a few with a single hkx in them, and a couple with multiple hkx anims in them. 
I don't know if there's a difference but I included them just in case.

I also added a skeleton. It's in Source SMD though, not sure how to convert it to hkx.
## Post #8
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2014-04-16T23:58:51+00:00
- Post Title: Havok Engine Animations

EDIT: Disregard my method. While it does in fact produce a .hkx file, it's broken to the point of uselessness.
## Post #9
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2014-05-15T02:21:00+00:00
- Post Title: Havok Engine Animations

Congrats on Getting that to work. I should have checked here first before making my [thread](http://forum.xentax.com/viewtopic.php?f=10&t=11507)
There is one difference in mine is that there are multiple animation files in one tmp
## Post #10
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2014-05-16T02:49:28+00:00
- Post Title: Havok Engine Animations

> Reply from JohnHudeski
>
> Congrats on Getting that to work. I should have checked here first before making my thread
There is one difference in mine is that there are multiple animation files in one tmp
But that's the thing, it doesn't work at all.

There multiple anims in mine too. [Example](http://puu.sh/8O3Jf.bin), the first one starts at 28, the next at 17F8. And hkxcmd thinks it's all one large animation. It's clear that hkxcmd will not help in this case, we need a whole new program. 
Just out of curiosity, are your files marked hk_2011.2.0-r1 as well? Maybe the formats are similar.

I saw you said you were a programmer. Would you be able to help with this? The only other person who showed the slightest bit of interest is Bastien and unfortunately it seems he's gone for good.
## Post #11
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2014-05-17T05:44:24+00:00
- Post Title: Havok Engine Animations

My files 4.6.0 R1 (Tenchu  on the Wii)
But I have had a 2011 version before. Never worked with hkcmd so I had to use the havok sdk.

I converted it to my own custom format. 

Where do you plan to use these animations? PM me I can show you what I did
## Post #12
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2014-05-30T20:03:37+00:00
- Post Title: Havok Engine Animations

EDIT: Nvm, I overreacted. Sorry about that.

In any case, this topic is still wide open. It shouldn't be that difficult, the format is practically the same as the 2010 version, only there's a small header and multiple animations per file.
## Post #13
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2014-10-10T07:31:25+00:00
- Post Title: Havok Engine Animations

Last time I talked to Bastien several months ago, he was incredibly busy but promised to take a look when he could. Haven't heard anything since.


However, with the release of Definitive Edition, the files have changed. They are now Havok 2013. 

What this means I do know know, but from the looks of it they're the same format as the original 2011 files.
## Post #14
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2014-10-11T04:54:26+00:00
- Post Title: Havok Engine Animations

Found the SplineComprssedAnimations section!

```
struct __cppobj __declspec(align(8)) hkaSplineCompressedAnimation : hkaAnimation
{
  int m_numFrames;
  int m_numBlocks;
  int m_maxFramesPerBlock;
  int m_maskAndQuantizationSize;
  float m_blockDuration;
  float m_blockInverseDuration;
  float m_frameDuration;
  hkArray<unsigned int,hkContainerHeapAllocator> m_blockOffsets;
  hkArray<unsigned int,hkContainerHeapAllocator> m_floatBlockOffsets;
  hkArray<unsigned int,hkContainerHeapAllocator> m_transformOffsets;
  hkArray<unsigned int,hkContainerHeapAllocator> m_floatOffsets;
  hkArray<unsigned char,hkContainerHeapAllocator> m_data;
  int m_endian;
};
```


There's apparently a ton of other animation types as well:

```
enum hkaAnimation::AnimationType
{
  HK_UNKNOWN_ANIMATION = 0x0,
  HK_INTERLEAVED_ANIMATION = 0x1,
  HK_MIRRORED_ANIMATION = 0x2,
  HK_SPLINE_COMPRESSED_ANIMATION = 0x3,
  HK_QUANTIZED_COMPRESSED_ANIMATION = 0x4,
  HK_PREDICTIVE_COMPRESSED_ANIMATION = 0x5,
  HK_REFERENCE_POSE_ANIMATION = 0x6,
};
```
## Post #15
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2014-11-10T09:02:54+00:00
- Post Title: Havok Engine Animations

Alright, I figured it out. BIN animation files are just a bunch of compressed HKX files in a row. 

Each individual .hkx file starts with hex value 6499 




and ends with this line.




Plus they're awfully similar to the 2011/2010 format.




Maybe we can try what Bastien said, simply cutting out that starting data, changing 2013 to 2010, and feeding it through hkxcmd.

I tried this already for 2011 version, but the reason it probably didn't work was because I was giving it the entire .bin file with all the hkx files combined. Maybe if I give it an isolated hkx file it'll work.
## Post #16
- Username: Snaz
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Oct 19, 2015 3:46 am
- Post datetime: 2016-02-29T19:24:04+00:00
- Post Title: Re: Havok Engine Animations

Should anyone end up at this topic like I did:

[https://github.com/Danilodum/dark_souls_hkx/releases](https://github.com/Danilodum/dark_souls_hkx/releases)

>Extract hkx animations to xml format (.damnhavok)
>open in noesis; make sure there's a Skeleton-out.hkx (converted with hkxcmd) in the same folder as the .damnhavok file you're opening
## Post #17
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2016-03-04T06:35:51+00:00
- Post Title: Re: Havok Engine Animations

Sweet jimminy christ, this may finally be the breakthrough we've all needed. [See here for further.](http://forum.xentax.com/viewtopic.php?f=16&p=116538#p116538)
## Post #18
- Username: TrumpetPro
- Rank: advanced
- Number of posts: 73
- Joined date: Wed Jul 06, 2016 8:51 am
- Post datetime: 2020-11-18T21:20:31+00:00
- Post Title: Re: Havok Engine Animations

Any of you guys ever manage to get Havok 2011|2013 anims into a more accessible format?
