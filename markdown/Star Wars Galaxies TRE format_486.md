## Post #1
- Username: Tulebox
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Dec 09, 2003 8:04 am
- Post datetime: 2003-12-09T00:11:13+00:00
- Post Title: Star Wars Galaxies TRE format

Would like to see some support for extracting files from Star Wars Galaxies .TRE file format.

They look like uncompressed resource files, with lots of goodies like WAVs, 3D models, etc...
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-12-09T13:31:47+00:00
- Post Title: Star Wars Galaxies TRE format

As there is no demo of this game, I rely heavily on people who actually own the game. If you can upload a TRE file somewhere I can have a look at it.
## Post #3
- Username: Tulebox
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Dec 09, 2003 8:04 am
- Post datetime: 2003-12-09T15:15:37+00:00
- Post Title: Star Wars Galaxies TRE format

I would like to help, but these files are usually 100 MB or bigger, which rules me out.  I don't have a high speed connection.
## Post #4
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-12-09T15:36:41+00:00
- Post Title: Star Wars Galaxies TRE format

Well, perhaps you can send a snippet of the head part and/or tail part that looks as if there's filenames in there. I probably won't need the whole file then. I'll fix up a small program (if I find the time) that you can use to test it.
## Post #5
- Username: Tulebox
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Dec 09, 2003 8:04 am
- Post datetime: 2003-12-11T00:09:21+00:00
- Post Title: Star Wars Galaxies TRE format

I'm looking through some of the TRE files, and I can't find any filenames.
But my guess is that these files are uncompressed, since I can identify 
WAV files by their recognizable header 'RIFF','WAVE', etc...

Since SWG is an online game, I'm thinking maybe only the raw data is 
stored on the person's computer, and all the filenames are stored on the 
SWG servers, perhaps?

```

00000000 4545 5254 3530 3030 B701 0000 F2DA 0402 EERT5000........
00000010 0200 0000 4918 0000 0200 0000 5D06 0000 ....I.......]...
00000020 022B 0000 5249 4646 2434 0E00 5741 5645 .+..RIFF$4..WAVE
00000030 666D 7420 1000 0000 0100 0200 2256 0000 fmt ........"V..


I wrote up a small program to try to flesh out the file, look for all
RIFF headers, and came up with this:


typedef struct _TRE_FILE_HEADER {

 CHAR  id[4];		// EERT
 CHAR  version[4];	// 4000, 5000

} TRE_FILE_HEADER;

 DWORD item_count;
 DWORD file_offset;
 DWORD dw1;
 DWORD dw2;
 DWORD dw3;
 DWORD dw4;
 DWORD dw5;

===================================

File size: 33887496 bytes

TRE_FILE_HEADER:
 header: EERT
version: 5000
[8]

 item_count:      439
file_offset: 33872626?
   dw1:        2?
   dw2:     6217?
   dw3:        2?
   dw4:     1629?
   dw5:    11010?
[36]

[      36]: RIFF found,  last_riff_size:        0,  count: 0
[  930896]: RIFF found,  last_riff_size:   930860,  count: 1
[ 2901296]: RIFF found,  last_riff_size:  1970400,  count: 2
[ 3518076]: RIFF found,  last_riff_size:   616780,  count: 3
[ 4053268]: RIFF found,  last_riff_size:   535192,  count: 4
[ 5572928]: RIFF found,  last_riff_size:  1519660,  count: 5
[ 7139292]: RIFF found,  last_riff_size:  1566364,  count: 6
[ 7967736]: RIFF found,  last_riff_size:   828444,  count: 7
[ 8406242]: RIFF found,  last_riff_size:   438506,  count: 8
[ 8802062]: RIFF found,  last_riff_size:   395820,  count: 9
[ 9171884]: RIFF found,  last_riff_size:   369822,  count: 10
[10563596]: RIFF found,  last_riff_size:  1391712,  count: 11
[10603754]: RIFF found,  last_riff_size:    40158,  count: 12
[10634326]: RIFF found,  last_riff_size:    30572,  count: 13
[10650632]: RIFF found,  last_riff_size:    16306,  count: 14
[10678938]: RIFF found,  last_riff_size:    28306,  count: 15
[10702370]: RIFF found,  last_riff_size:    23432,  count: 16
[10723430]: RIFF found,  last_riff_size:    21060,  count: 17
[10740320]: RIFF found,  last_riff_size:    16890,  count: 18
[10753938]: RIFF found,  last_riff_size:    13618,  count: 19
[10769564]: RIFF found,  last_riff_size:    15626,  count: 20
[10790406]: RIFF found,  last_riff_size:    20842,  count: 21
[10871414]: RIFF found,  last_riff_size:    81008,  count: 22
[10939738]: RIFF found,  last_riff_size:    68324,  count: 23
[11000568]: RIFF found,  last_riff_size:    60830,  count: 24
[11075188]: RIFF found,  last_riff_size:    74620,  count: 25
[11126480]: RIFF found,  last_riff_size:    51292,  count: 26
[11199990]: RIFF found,  last_riff_size:    73510,  count: 27
[11257840]: RIFF found,  last_riff_size:    57850,  count: 28
[11311936]: RIFF found,  last_riff_size:    54096,  count: 29
[11379018]: RIFF found,  last_riff_size:    67082,  count: 30
[11437734]: RIFF found,  last_riff_size:    58716,  count: 31
[11530600]: RIFF found,  last_riff_size:    92866,  count: 32
[11614480]: RIFF found,  last_riff_size:    83880,  count: 33
[11674818]: RIFF found,  last_riff_size:    60338,  count: 34
[11756402]: RIFF found,  last_riff_size:    81584,  count: 35
[11866250]: RIFF found,  last_riff_size:   109848,  count: 36
[11955120]: RIFF found,  last_riff_size:    88870,  count: 37
[12032244]: RIFF found,  last_riff_size:    77124,  count: 38
[12123590]: RIFF found,  last_riff_size:    91346,  count: 39
[12210848]: RIFF found,  last_riff_size:    87258,  count: 40
[12306100]: RIFF found,  last_riff_size:    95252,  count: 41
[12393736]: RIFF found,  last_riff_size:    87636,  count: 42
[12487276]: RIFF found,  last_riff_size:    93540,  count: 43
[12597396]: RIFF found,  last_riff_size:   110120,  count: 44
[12700226]: RIFF found,  last_riff_size:   102830,  count: 45
[12796596]: RIFF found,  last_riff_size:    96370,  count: 46
[12912632]: RIFF found,  last_riff_size:   116036,  count: 47
[13036112]: RIFF found,  last_riff_size:   123480,  count: 48
[13159038]: RIFF found,  last_riff_size:   122926,  count: 49
[13256382]: RIFF found,  last_riff_size:    97344,  count: 50
[13331050]: RIFF found,  last_riff_size:    74668,  count: 51
[13412660]: RIFF found,  last_riff_size:    81610,  count: 52
[13504004]: RIFF found,  last_riff_size:    91344,  count: 53
[13585678]: RIFF found,  last_riff_size:    81674,  count: 54
[13654944]: RIFF found,  last_riff_size:    69266,  count: 55
[13733656]: RIFF found,  last_riff_size:    78712,  count: 56
[13806998]: RIFF found,  last_riff_size:    73342,  count: 57
[13893604]: RIFF found,  last_riff_size:    86606,  count: 58
[13977400]: RIFF found,  last_riff_size:    83796,  count: 59
[14059274]: RIFF found,  last_riff_size:    81874,  count: 60
[14148486]: RIFF found,  last_riff_size:    89212,  count: 61
[14225322]: RIFF found,  last_riff_size:    76836,  count: 62
[14313278]: RIFF found,  last_riff_size:    87956,  count: 63
[14410366]: RIFF found,  last_riff_size:    97088,  count: 64
[14490016]: RIFF found,  last_riff_size:    79650,  count: 65
[14561084]: RIFF found,  last_riff_size:    71068,  count: 66
[14571916]: RIFF found,  last_riff_size:    10832,  count: 67
[14595550]: RIFF found,  last_riff_size:    23634,  count: 68
[14615442]: RIFF found,  last_riff_size:    19892,  count: 69
[14636608]: RIFF found,  last_riff_size:    21166,  count: 70
[14668300]: RIFF found,  last_riff_size:    31692,  count: 71
[14697382]: RIFF found,  last_riff_size:    29082,  count: 72
[14710702]: RIFF found,  last_riff_size:    13320,  count: 73
[14745934]: RIFF found,  last_riff_size:    35232,  count: 74
[14763338]: RIFF found,  last_riff_size:    17404,  count: 75
[14775154]: RIFF found,  last_riff_size:    11816,  count: 76
[14794716]: RIFF found,  last_riff_size:    19562,  count: 77
[14810626]: RIFF found,  last_riff_size:    15910,  count: 78
[14834646]: RIFF found,  last_riff_size:    24020,  count: 79
[14868510]: RIFF found,  last_riff_size:    33864,  count: 80
[14940062]: RIFF found,  last_riff_size:    71552,  count: 81
[14946964]: RIFF found,  last_riff_size:     6902,  count: 82
[14961784]: RIFF found,  last_riff_size:    14820,  count: 83
[14979598]: RIFF found,  last_riff_size:    17814,  count: 84
[14991308]: RIFF found,  last_riff_size:    11710,  count: 85
[15012282]: RIFF found,  last_riff_size:    20974,  count: 86
[15044226]: RIFF found,  last_riff_size:    31944,  count: 87
[15052960]: RIFF found,  last_riff_size:     8734,  count: 88
[15065340]: RIFF found,  last_riff_size:    12380,  count: 89
[15107324]: RIFF found,  last_riff_size:    41984,  count: 90
[15114572]: RIFF found,  last_riff_size:     7248,  count: 91
[15125634]: RIFF found,  last_riff_size:    11062,  count: 92
[15143198]: RIFF found,  last_riff_size:    17564,  count: 93
[15157362]: RIFF found,  last_riff_size:    14164,  count: 94
[15180016]: RIFF found,  last_riff_size:    22654,  count: 95
[15205632]: RIFF found,  last_riff_size:    25616,  count: 96
[15214358]: RIFF found,  last_riff_size:     8726,  count: 97
[15223168]: RIFF found,  last_riff_size:     8810,  count: 98
[15235890]: RIFF found,  last_riff_size:    12722,  count: 99
[15256490]: RIFF found,  last_riff_size:    20600,  count: 100
[15300914]: RIFF found,  last_riff_size:    44424,  count: 101
[15352318]: RIFF found,  last_riff_size:    51404,  count: 102
[15364796]: RIFF found,  last_riff_size:    12478,  count: 103
[15391366]: RIFF found,  last_riff_size:    26570,  count: 104
[15430856]: RIFF found,  last_riff_size:    39490,  count: 105
[15441022]: RIFF found,  last_riff_size:    10166,  count: 106
[15453572]: RIFF found,  last_riff_size:    12550,  count: 107
[15464956]: RIFF found,  last_riff_size:    11384,  count: 108
[15485508]: RIFF found,  last_riff_size:    20552,  count: 109
[15512562]: RIFF found,  last_riff_size:    27054,  count: 110
[15536386]: RIFF found,  last_riff_size:    23824,  count: 111
[15566914]: RIFF found,  last_riff_size:    30528,  count: 112
[15604114]: RIFF found,  last_riff_size:    37200,  count: 113
[15650500]: RIFF found,  last_riff_size:    46386,  count: 114
[15666770]: RIFF found,  last_riff_size:    16270,  count: 115
[15673270]: RIFF found,  last_riff_size:     6500,  count: 116
[15696062]: RIFF found,  last_riff_size:    22792,  count: 117
[15721446]: RIFF found,  last_riff_size:    25384,  count: 118
[15771380]: RIFF found,  last_riff_size:    49934,  count: 119
[15806474]: RIFF found,  last_riff_size:    35094,  count: 120
[15831962]: RIFF found,  last_riff_size:    25488,  count: 121
[15895572]: RIFF found,  last_riff_size:    63610,  count: 122
[15919250]: RIFF found,  last_riff_size:    23678,  count: 123
[15958210]: RIFF found,  last_riff_size:    38960,  count: 124
[16059448]: RIFF found,  last_riff_size:   101238,  count: 125
[16255206]: RIFF found,  last_riff_size:   195758,  count: 126
[16265402]: RIFF found,  last_riff_size:    10196,  count: 127
[16280756]: RIFF found,  last_riff_size:    15354,  count: 128
[16329986]: RIFF found,  last_riff_size:    49230,  count: 129
[16373512]: RIFF found,  last_riff_size:    43526,  count: 130
[16415738]: RIFF found,  last_riff_size:    42226,  count: 131
[16462826]: RIFF found,  last_riff_size:    47088,  count: 132
[16510798]: RIFF found,  last_riff_size:    47972,  count: 133
[16560454]: RIFF found,  last_riff_size:    49656,  count: 134
[16620588]: RIFF found,  last_riff_size:    60134,  count: 135
[16700724]: RIFF found,  last_riff_size:    80136,  count: 136
[16772994]: RIFF found,  last_riff_size:    72270,  count: 137
[16895376]: RIFF found,  last_riff_size:   122382,  count: 138
[16916918]: RIFF found,  last_riff_size:    21542,  count: 139
[16961442]: RIFF found,  last_riff_size:    44524,  count: 140
[17002516]: RIFF found,  last_riff_size:    41074,  count: 141
[17037168]: RIFF found,  last_riff_size:    34652,  count: 142
[17049882]: RIFF found,  last_riff_size:    12714,  count: 143
[17118896]: RIFF found,  last_riff_size:    69014,  count: 144
[17127000]: RIFF found,  last_riff_size:     8104,  count: 145
[17141970]: RIFF found,  last_riff_size:    14970,  count: 146
[17161496]: RIFF found,  last_riff_size:    19526,  count: 147
[17173000]: RIFF found,  last_riff_size:    11504,  count: 148
[17206578]: RIFF found,  last_riff_size:    33578,  count: 149
[17224864]: RIFF found,  last_riff_size:    18286,  count: 150
[17247158]: RIFF found,  last_riff_size:    22294,  count: 151
[17270680]: RIFF found,  last_riff_size:    23522,  count: 152
[17300584]: RIFF found,  last_riff_size:    29904,  count: 153
[17314114]: RIFF found,  last_riff_size:    13530,  count: 154
[17346492]: RIFF found,  last_riff_size:    32378,  count: 155
[17393378]: RIFF found,  last_riff_size:    46886,  count: 156
[17405176]: RIFF found,  last_riff_size:    11798,  count: 157
[17434340]: RIFF found,  last_riff_size:    29164,  count: 158
[17457472]: RIFF found,  last_riff_size:    23132,  count: 159
[17472582]: RIFF found,  last_riff_size:    15110,  count: 160
[17508848]: RIFF found,  last_riff_size:    36266,  count: 161
[17551774]: RIFF found,  last_riff_size:    42926,  count: 162
[17567124]: RIFF found,  last_riff_size:    15350,  count: 163
[17587542]: RIFF found,  last_riff_size:    20418,  count: 164
[17626162]: RIFF found,  last_riff_size:    38620,  count: 165
[17634226]: RIFF found,  last_riff_size:     8064,  count: 166
[17650624]: RIFF found,  last_riff_size:    16398,  count: 167
[17671558]: RIFF found,  last_riff_size:    20934,  count: 168
[17684386]: RIFF found,  last_riff_size:    12828,  count: 169
[17722912]: RIFF found,  last_riff_size:    38526,  count: 170
[17795876]: RIFF found,  last_riff_size:    72964,  count: 171
[17810876]: RIFF found,  last_riff_size:    15000,  count: 172
[17839304]: RIFF found,  last_riff_size:    28428,  count: 173
[17911460]: RIFF found,  last_riff_size:    72156,  count: 174
[17928812]: RIFF found,  last_riff_size:    17352,  count: 175
[17954174]: RIFF found,  last_riff_size:    25362,  count: 176
[17976080]: RIFF found,  last_riff_size:    21906,  count: 177
[18015716]: RIFF found,  last_riff_size:    39636,  count: 178
[18039258]: RIFF found,  last_riff_size:    23542,  count: 179
[18069024]: RIFF found,  last_riff_size:    29766,  count: 180
[18099138]: RIFF found,  last_riff_size:    30114,  count: 181
[18139940]: RIFF found,  last_riff_size:    40802,  count: 182
[18158908]: RIFF found,  last_riff_size:    18968,  count: 183
[18187008]: RIFF found,  last_riff_size:    28100,  count: 184
[18224286]: RIFF found,  last_riff_size:    37278,  count: 185
[18305656]: RIFF found,  last_riff_size:    81370,  count: 186
[18382006]: RIFF found,  last_riff_size:    76350,  count: 187
[18500674]: RIFF found,  last_riff_size:   118668,  count: 188
[18603644]: RIFF found,  last_riff_size:   102970,  count: 189
[18631468]: RIFF found,  last_riff_size:    27824,  count: 190
[18662744]: RIFF found,  last_riff_size:    31276,  count: 191
[18706438]: RIFF found,  last_riff_size:    43694,  count: 192
[18742720]: RIFF found,  last_riff_size:    36282,  count: 193
[18799070]: RIFF found,  last_riff_size:    56350,  count: 194
[18861558]: RIFF found,  last_riff_size:    62488,  count: 195
[18979636]: RIFF found,  last_riff_size:   118078,  count: 196
[19069766]: RIFF found,  last_riff_size:    90130,  count: 197
[19119758]: RIFF found,  last_riff_size:    49992,  count: 198
[19160074]: RIFF found,  last_riff_size:    40316,  count: 199
[19183466]: RIFF found,  last_riff_size:    23392,  count: 200
[19253080]: RIFF found,  last_riff_size:    69614,  count: 201
[19323914]: RIFF found,  last_riff_size:    70834,  count: 202
[19395750]: RIFF found,  last_riff_size:    71836,  count: 203
[19513020]: RIFF found,  last_riff_size:   117270,  count: 204
[19600302]: RIFF found,  last_riff_size:    87282,  count: 205
[19669034]: RIFF found,  last_riff_size:    68732,  count: 206
[19738752]: RIFF found,  last_riff_size:    69718,  count: 207
[19802370]: RIFF found,  last_riff_size:    63618,  count: 208
[19844728]: RIFF found,  last_riff_size:    42358,  count: 209
[19862694]: RIFF found,  last_riff_size:    17966,  count: 210
[19905150]: RIFF found,  last_riff_size:    42456,  count: 211
[19967712]: RIFF found,  last_riff_size:    62562,  count: 212
[20071908]: RIFF found,  last_riff_size:   104196,  count: 213
[20157158]: RIFF found,  last_riff_size:    85250,  count: 214
[20188810]: RIFF found,  last_riff_size:    31652,  count: 215
[20240920]: RIFF found,  last_riff_size:    52110,  count: 216
[20305792]: RIFF found,  last_riff_size:    64872,  count: 217
[20424594]: RIFF found,  last_riff_size:   118802,  count: 218
[20532858]: RIFF found,  last_riff_size:   108264,  count: 219
[20572726]: RIFF found,  last_riff_size:    39868,  count: 220
[20618746]: RIFF found,  last_riff_size:    46020,  count: 221
[20646230]: RIFF found,  last_riff_size:    27484,  count: 222
[20711434]: RIFF found,  last_riff_size:    65204,  count: 223
[20809674]: RIFF found,  last_riff_size:    98240,  count: 224
[20865652]: RIFF found,  last_riff_size:    55978,  count: 225
[21017744]: RIFF found,  last_riff_size:   152092,  count: 226
[21116676]: RIFF found,  last_riff_size:    98932,  count: 227
[21247032]: RIFF found,  last_riff_size:   130356,  count: 228
[21314966]: RIFF found,  last_riff_size:    67934,  count: 229
[21385528]: RIFF found,  last_riff_size:    70562,  count: 230
[21437734]: RIFF found,  last_riff_size:    52206,  count: 231
[21455212]: RIFF found,  last_riff_size:    17478,  count: 232
[21498550]: RIFF found,  last_riff_size:    43338,  count: 233
[21561044]: RIFF found,  last_riff_size:    62494,  count: 234
[21657724]: RIFF found,  last_riff_size:    96680,  count: 235
[21759502]: RIFF found,  last_riff_size:   101778,  count: 236
[21784410]: RIFF found,  last_riff_size:    24908,  count: 237
[21806880]: RIFF found,  last_riff_size:    22470,  count: 238
[21837896]: RIFF found,  last_riff_size:    31016,  count: 239
[21886458]: RIFF found,  last_riff_size:    48562,  count: 240
[21916792]: RIFF found,  last_riff_size:    30334,  count: 241
[21968018]: RIFF found,  last_riff_size:    51226,  count: 242
[22096062]: RIFF found,  last_riff_size:   128044,  count: 243
[22221860]: RIFF found,  last_riff_size:   125798,  count: 244
[22263376]: RIFF found,  last_riff_size:    41516,  count: 245
[22488926]: RIFF found,  last_riff_size:   225550,  count: 246
[22553440]: RIFF found,  last_riff_size:    64514,  count: 247
[22602048]: RIFF found,  last_riff_size:    48608,  count: 248
[22650330]: RIFF found,  last_riff_size:    48282,  count: 249
[22687342]: RIFF found,  last_riff_size:    37012,  count: 250
[22747180]: RIFF found,  last_riff_size:    59838,  count: 251
[22770088]: RIFF found,  last_riff_size:    22908,  count: 252
[22786702]: RIFF found,  last_riff_size:    16614,  count: 253
[22808334]: RIFF found,  last_riff_size:    21632,  count: 254
[22851250]: RIFF found,  last_riff_size:    42916,  count: 255
[22898400]: RIFF found,  last_riff_size:    47150,  count: 256
[22959634]: RIFF found,  last_riff_size:    61234,  count: 257
[22975114]: RIFF found,  last_riff_size:    15480,  count: 258
[23024544]: RIFF found,  last_riff_size:    49430,  count: 259
[23124502]: RIFF found,  last_riff_size:    99958,  count: 260
[23208342]: RIFF found,  last_riff_size:    83840,  count: 261
[23212440]: RIFF found,  last_riff_size:     4098,  count: 262
[23253706]: RIFF found,  last_riff_size:    41266,  count: 263
[23266400]: RIFF found,  last_riff_size:    12694,  count: 264
[23273136]: RIFF found,  last_riff_size:     6736,  count: 265
[23320784]: RIFF found,  last_riff_size:    47648,  count: 266
[23452324]: RIFF found,  last_riff_size:   131540,  count: 267
[23522198]: RIFF found,  last_riff_size:    69874,  count: 268
[23535706]: RIFF found,  last_riff_size:    13508,  count: 269
[23564420]: RIFF found,  last_riff_size:    28714,  count: 270
[23600994]: RIFF found,  last_riff_size:    36574,  count: 271
[23642356]: RIFF found,  last_riff_size:    41362,  count: 272
[23676828]: RIFF found,  last_riff_size:    34472,  count: 273
[23731020]: RIFF found,  last_riff_size:    54192,  count: 274
[23765812]: RIFF found,  last_riff_size:    34792,  count: 275
[23802132]: RIFF found,  last_riff_size:    36320,  count: 276
[23843790]: RIFF found,  last_riff_size:    41658,  count: 277
[23878642]: RIFF found,  last_riff_size:    34852,  count: 278
[23915474]: RIFF found,  last_riff_size:    36832,  count: 279
[23988398]: RIFF found,  last_riff_size:    72924,  count: 280
[24031784]: RIFF found,  last_riff_size:    43386,  count: 281
[24068610]: RIFF found,  last_riff_size:    36826,  count: 282
[24145900]: RIFF found,  last_riff_size:    77290,  count: 283
[24277516]: RIFF found,  last_riff_size:   131616,  count: 284
[24449114]: RIFF found,  last_riff_size:   171598,  count: 285
[24472104]: RIFF found,  last_riff_size:    22990,  count: 286
[24548864]: RIFF found,  last_riff_size:    76760,  count: 287
[24625380]: RIFF found,  last_riff_size:    76516,  count: 288
[24658630]: RIFF found,  last_riff_size:    33250,  count: 289
[24766476]: RIFF found,  last_riff_size:   107846,  count: 290
[24785280]: RIFF found,  last_riff_size:    18804,  count: 291
[24898988]: RIFF found,  last_riff_size:   113708,  count: 292
[24949290]: RIFF found,  last_riff_size:    50302,  count: 293
[25095186]: RIFF found,  last_riff_size:   145896,  count: 294
[25192168]: RIFF found,  last_riff_size:    96982,  count: 295
[25196140]: RIFF found,  last_riff_size:     3972,  count: 296
[25370950]: RIFF found,  last_riff_size:   174810,  count: 297
[25385064]: RIFF found,  last_riff_size:    14114,  count: 298
[25394286]: RIFF found,  last_riff_size:     9222,  count: 299
[25466800]: RIFF found,  last_riff_size:    72514,  count: 300
[25501948]: RIFF found,  last_riff_size:    35148,  count: 301
[25633472]: RIFF found,  last_riff_size:   131524,  count: 302
[25678950]: RIFF found,  last_riff_size:    45478,  count: 303
[25727182]: RIFF found,  last_riff_size:    48232,  count: 304
[25763252]: RIFF found,  last_riff_size:    36070,  count: 305
[25817328]: RIFF found,  last_riff_size:    54076,  count: 306
[25916744]: RIFF found,  last_riff_size:    99416,  count: 307
[26074496]: RIFF found,  last_riff_size:   157752,  count: 308
[26208384]: RIFF found,  last_riff_size:   133888,  count: 309
[26303920]: RIFF found,  last_riff_size:    95536,  count: 310
[26329488]: RIFF found,  last_riff_size:    25568,  count: 311
[26373414]: RIFF found,  last_riff_size:    43926,  count: 312
[26401756]: RIFF found,  last_riff_size:    28342,  count: 313
[26499340]: RIFF found,  last_riff_size:    97584,  count: 314
[26545064]: RIFF found,  last_riff_size:    45724,  count: 315
[26568832]: RIFF found,  last_riff_size:    23768,  count: 316
[26631626]: RIFF found,  last_riff_size:    62794,  count: 317
[26657718]: RIFF found,  last_riff_size:    26092,  count: 318
[26682788]: RIFF found,  last_riff_size:    25070,  count: 319
[26706718]: RIFF found,  last_riff_size:    23930,  count: 320
[26722202]: RIFF found,  last_riff_size:    15484,  count: 321
[26741308]: RIFF found,  last_riff_size:    19106,  count: 322
[26767426]: RIFF found,  last_riff_size:    26118,  count: 323
[26852586]: RIFF found,  last_riff_size:    85160,  count: 324
[26909734]: RIFF found,  last_riff_size:    57148,  count: 325
[26925984]: RIFF found,  last_riff_size:    16250,  count: 326
[27001094]: RIFF found,  last_riff_size:    75110,  count: 327
[27044560]: RIFF found,  last_riff_size:    43466,  count: 328
[27078326]: RIFF found,  last_riff_size:    33766,  count: 329
[27121740]: RIFF found,  last_riff_size:    43414,  count: 330
[27166008]: RIFF found,  last_riff_size:    44268,  count: 331
[27190708]: RIFF found,  last_riff_size:    24700,  count: 332
[27281932]: RIFF found,  last_riff_size:    91224,  count: 333
[27312992]: RIFF found,  last_riff_size:    31060,  count: 334
[27368482]: RIFF found,  last_riff_size:    55490,  count: 335
[27381460]: RIFF found,  last_riff_size:    12978,  count: 336
[27398624]: RIFF found,  last_riff_size:    17164,  count: 337
[27416514]: RIFF found,  last_riff_size:    17890,  count: 338
[27453600]: RIFF found,  last_riff_size:    37086,  count: 339
[27494988]: RIFF found,  last_riff_size:    41388,  count: 340
[27513192]: RIFF found,  last_riff_size:    18204,  count: 341
[27553416]: RIFF found,  last_riff_size:    40224,  count: 342
[27582946]: RIFF found,  last_riff_size:    29530,  count: 343
[27599458]: RIFF found,  last_riff_size:    16512,  count: 344
[27616708]: RIFF found,  last_riff_size:    17250,  count: 345
[27644126]: RIFF found,  last_riff_size:    27418,  count: 346
[27664338]: RIFF found,  last_riff_size:    20212,  count: 347
[27739032]: RIFF found,  last_riff_size:    74694,  count: 348
[27799320]: RIFF found,  last_riff_size:    60288,  count: 349
[27860762]: RIFF found,  last_riff_size:    61442,  count: 350
[27922314]: RIFF found,  last_riff_size:    61552,  count: 351
[27983608]: RIFF found,  last_riff_size:    61294,  count: 352
[28033206]: RIFF found,  last_riff_size:    49598,  count: 353
[28075244]: RIFF found,  last_riff_size:    42038,  count: 354
[28151490]: RIFF found,  last_riff_size:    76246,  count: 355
[28255216]: RIFF found,  last_riff_size:   103726,  count: 356
[28315114]: RIFF found,  last_riff_size:    59898,  count: 357
[28578652]: RIFF found,  last_riff_size:   263538,  count: 358
[28639940]: RIFF found,  last_riff_size:    61288,  count: 359
[28722406]: RIFF found,  last_riff_size:    82466,  count: 360
[28808582]: RIFF found,  last_riff_size:    86176,  count: 361
[28869096]: RIFF found,  last_riff_size:    60514,  count: 362
[29029796]: RIFF found,  last_riff_size:   160700,  count: 363
[29062114]: RIFF found,  last_riff_size:    32318,  count: 364
[29208370]: RIFF found,  last_riff_size:   146256,  count: 365
[29306806]: RIFF found,  last_riff_size:    98436,  count: 366
[29353936]: RIFF found,  last_riff_size:    47130,  count: 367
[29427712]: RIFF found,  last_riff_size:    73776,  count: 368
[29489904]: RIFF found,  last_riff_size:    62192,  count: 369
[29529310]: RIFF found,  last_riff_size:    39406,  count: 370
[29566570]: RIFF found,  last_riff_size:    37260,  count: 371
[29605578]: RIFF found,  last_riff_size:    39008,  count: 372
[29654392]: RIFF found,  last_riff_size:    48814,  count: 373
[29696248]: RIFF found,  last_riff_size:    41856,  count: 374
[29749422]: RIFF found,  last_riff_size:    53174,  count: 375
[29830122]: RIFF found,  last_riff_size:    80700,  count: 376
[29864304]: RIFF found,  last_riff_size:    34182,  count: 377
[30138486]: RIFF found,  last_riff_size:   274182,  count: 378
[30177370]: RIFF found,  last_riff_size:    38884,  count: 379
[30256650]: RIFF found,  last_riff_size:    79280,  count: 380
[30342224]: RIFF found,  last_riff_size:    85574,  count: 381
[30379548]: RIFF found,  last_riff_size:    37324,  count: 382
[30518226]: RIFF found,  last_riff_size:   138678,  count: 383
[30547606]: RIFF found,  last_riff_size:    29380,  count: 384
[30679446]: RIFF found,  last_riff_size:   131840,  count: 385
[30755338]: RIFF found,  last_riff_size:    75892,  count: 386
[30801940]: RIFF found,  last_riff_size:    46602,  count: 387
[30874016]: RIFF found,  last_riff_size:    72076,  count: 388
[30941772]: RIFF found,  last_riff_size:    67756,  count: 389
[30956558]: RIFF found,  last_riff_size:    14786,  count: 390
[30971920]: RIFF found,  last_riff_size:    15362,  count: 391
[30996080]: RIFF found,  last_riff_size:    24160,  count: 392
[31016102]: RIFF found,  last_riff_size:    20022,  count: 393
[31067698]: RIFF found,  last_riff_size:    51596,  count: 394
[31129562]: RIFF found,  last_riff_size:    61864,  count: 395
[31149564]: RIFF found,  last_riff_size:    20002,  count: 396
[31193116]: RIFF found,  last_riff_size:    43552,  count: 397
[31214388]: RIFF found,  last_riff_size:    21272,  count: 398
[31239038]: RIFF found,  last_riff_size:    24650,  count: 399
[31258208]: RIFF found,  last_riff_size:    19170,  count: 400
[31285718]: RIFF found,  last_riff_size:    27510,  count: 401
[31317216]: RIFF found,  last_riff_size:    31498,  count: 402
[31337766]: RIFF found,  last_riff_size:    20550,  count: 403
[31361918]: RIFF found,  last_riff_size:    24152,  count: 404
[31549304]: RIFF found,  last_riff_size:   187386,  count: 405
[31660410]: RIFF found,  last_riff_size:   111106,  count: 406
[31767132]: RIFF found,  last_riff_size:   106722,  count: 407
[31924328]: RIFF found,  last_riff_size:   157196,  count: 408
[32114836]: RIFF found,  last_riff_size:   190508,  count: 409
[32280112]: RIFF found,  last_riff_size:   165276,  count: 410
[32475454]: RIFF found,  last_riff_size:   195342,  count: 411
[32589516]: RIFF found,  last_riff_size:   114062,  count: 412
[32696008]: RIFF found,  last_riff_size:   106492,  count: 413
[32867844]: RIFF found,  last_riff_size:   171836,  count: 414
[33015406]: RIFF found,  last_riff_size:   147562,  count: 415
[33229632]: RIFF found,  last_riff_size:   214226,  count: 416
[33354984]: RIFF found,  last_riff_size:   125352,  count: 417
[33386016]: RIFF found,  last_riff_size:    31032,  count: 418
[33413852]: RIFF found,  last_riff_size:    27836,  count: 419
[33433832]: RIFF found,  last_riff_size:    19980,  count: 420
[33463290]: RIFF found,  last_riff_size:    29458,  count: 421
[33481264]: RIFF found,  last_riff_size:    17974,  count: 422
[33506532]: RIFF found,  last_riff_size:    25268,  count: 423
[33528234]: RIFF found,  last_riff_size:    21702,  count: 424
[33546158]: RIFF found,  last_riff_size:    17924,  count: 425
[33573978]: RIFF found,  last_riff_size:    27820,  count: 426
[33596106]: RIFF found,  last_riff_size:    22128,  count: 427
[33607998]: RIFF found,  last_riff_size:    11892,  count: 428
[33620942]: RIFF found,  last_riff_size:    12944,  count: 429
[33643340]: RIFF found,  last_riff_size:    22398,  count: 430
[33667754]: RIFF found,  last_riff_size:    24414,  count: 431
[33697418]: RIFF found,  last_riff_size:    29664,  count: 432
[33725174]: RIFF found,  last_riff_size:    27756,  count: 433
[33752156]: RIFF found,  last_riff_size:    26982,  count: 434
[33775550]: RIFF found,  last_riff_size:    23394,  count: 435
[33797782]: RIFF found,  last_riff_size:    22232,  count: 436
[33821968]: RIFF found,  last_riff_size:    24186,  count: 437
[33847866]: RIFF found,  last_riff_size:    25898,  count: 438
[33887496] final_size: 39630

33887496 bytes = FILE SIZE

FINAL_ITEM_COUNT: 439

```
## Post #6
- Username: Captain
- Rank: Site Admin
- Number of posts: 248
- Joined date: Thu Jan 16, 2003 1:25 am
- Post datetime: 2003-12-11T06:41:54+00:00
- Post Title: Star Wars Galaxies TRE format

Ah. RIFF. Looks very familiar. What do you think Mr.Mouse? Do we have a script that already supports it?
## Post #7
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-12-11T09:40:30+00:00
- Post Title: Star Wars Galaxies TRE format

Well, we do have a RIFF-ripping script in there. Try to open the files as No One Lives Forever .REZ files. (Rename a TRE file to REZ temporarily). 
This is not the cleanest way however, but it will give you the sounds. I will have a looksee at that data you posted.   Oh and could you just save 1 mb of a tre file (from start to 1 mb) and 1 mb from the tail of a tre file (from end of file to 1mb before the end of file), zip these two files and email them to me? As you are capable of writing programs, opening a tre file and saving 1mb parts of this file separately should not be a problem eh?
## Post #8
- Username: Tulebox
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Dec 09, 2003 8:04 am
- Post datetime: 2003-12-12T01:52:02+00:00
- Post Title: Star Wars Galaxies TRE format

I'll see what I can do. 

BTW, these files can contain any kind of data, it just happens that this particular file 
contains all WAVs, so fleshing out the file format should be easier.

I don't have any experience with archive/resource formats, so I'm having 
trouble locating chunk sizes and/or file offsets for each item chunk.
## Post #9
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-12-12T23:21:16+00:00
- Post Title: Star Wars Galaxies TRE format

> Reply from Tulebox
>
> I'll see what I can do.

Thanks, hope to get them soon!
## Post #10
- Username: Tulebox
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Dec 09, 2003 8:04 am
- Post datetime: 2003-12-13T01:20:30+00:00
- Post Title: Star Wars Galaxies TRE format

Your email address is not working!  I hope this is correct?

```

Action: failed
Status: 5.0.0
    Requested action not taken: mailbox unavailable (in reply to RCPT
TO
    command)

```
## Post #11
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-12-13T07:39:10+00:00
- Post Title: Star Wars Galaxies TRE format

Ah, try 

[mr.mouse@xentax.com](mailto:mr.mouse@xentax.com)

That should work.
## Post #12
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-12-14T16:08:15+00:00
- Post Title: Star Wars Galaxies TRE format

Good. Here's the big picture I could find out about the TRE format, 

[http://www.xentax.com/opengraf/](http://www.xentax.com/opengraf/)

(at OpenGRAF). 

This should be enough info to implement it in future OpenMEX releases.
## Post #13
- Username: Tulebox
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Dec 09, 2003 8:04 am
- Post datetime: 2003-12-14T16:51:59+00:00
- Post Title: Star Wars Galaxies TRE format

Ah, cool!  So the filenames are really in there, just compressed at the end of file,
using the standard zlib library?  That would make sense.
## Post #14
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-12-14T21:34:33+00:00
- Post Title: Star Wars Galaxies TRE format

Right!   Well, matters are more clear now, and new questions arise, after I looked at the pach.tre you sent. It turns out that there will always be two tails, an file-info and filename tail. Yet, the value just before the Compressed_Size of each tail (in the previous TRE, the values that were both 2) identifies the compression method. This I gather, as the File-Info Tail in the patch file is NOT compressed and the value I mean reads 0. However, the value reads 1 for the Filename Tail, and not 2, and likewise ZLib can't handle it just like that. The FIlename Tail is compressed 39 bytes in size, which fits exactly with the number of bytes that come after the first File_Info Tail, answering the previous "junk"question and answering it with "yes, that's junk" (see OpenGRAF).   
BUT, it leaves me with the problem of compresion method numero uno. What IS compression method "1", as needed? I will have to look into that.
## Post #15
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-12-16T15:54:09+00:00
- Post Title: Star Wars Galaxies TRE format

Ok, I have updated the OpenGRAF entry for Star Wars Galaxies and it is now more accurate. I still need to explain compression method 1. And some unknown variable. Compression method 2 is now confirmed GZip (Zlib) NORMAL compression. 

[http://www.xentax.com/opengraf](http://www.xentax.com/opengraf)
## Post #16
- Username: Tulebox
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Dec 09, 2003 8:04 am
- Post datetime: 2003-12-16T18:53:45+00:00
- Post Title: 

That's awesome!

You certainly got farther than I did. 

Thanks for the help.  Many thanks.
## Post #17
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-12-16T23:34:57+00:00
- Post Title: 

They key to compression/encription/method 1 lies probably in LIBPNG . In the official credits to the game they mention LIBPNG as stuff they worked with, which includes Zlib compression, and more. Also, they use something called PCRE which may be helping.
## Post #18
- Username: Tulebox
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Dec 09, 2003 8:04 am
- Post datetime: 2003-12-17T04:42:48+00:00
- Post Title: 

I can't find it anywhere else except in that EERT4000 file, so it must be obsolete
in EERT5000.  I won't worry about it too much.
## Post #19
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-12-17T23:12:21+00:00
- Post Title: 

I just couldn't resist...  



Version 0.5 (alpha).In Visual basic, because that would be the quickest way IMHO. At the time of writing it retrieves info from a test.tre. This is based on the parts you sent. I just glued the start and end part together and changed the tailpointer to overcome the missing parts (i don't need the actual contents, as long as i have the tails). In the shot you see the contents of that file you sent the parts of. 439 files. 

Also, the tool can create TRE files for you (using compression for all files and tails), although this is tricky of course, since there's that missing unknown value, which probably serves a great purpose in the game. 
(I had to be able to create my own TRE files, to test the routines, and future routines, since I don't have any official TRE files)

Most importantly, a TRE file is a Class in the program, which I can likely transform to an activeX dll, for everyone to use in their own programs. 

Not yet supported: 
- extract contents (but will be soon, it's easy)
- add contents
- remove contents
- replace contents

add and remove will be possible in the future, but they will alter that crucial unknown value and expectations that the game has of the TRE files. Replace however, is a good way to change the contents, without altering that unknown stuff, this has priority. 

I estimate a release in a day or so.
## Post #20
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-12-18T15:16:56+00:00
- Post Title: 

Get the first alpha release here (no warranty , use at your own risk, only use the functions mentioned in the readme.)

[http://www.xentax.com/downloads/tools/X ... chiver.zip](http://www.xentax.com/downloads/tools/XeNTaX_TRE_Archiver.zip)

And let me know here if it worked.
## Post #21
- Username: Tulebox
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Dec 09, 2003 8:04 am
- Post datetime: 2003-12-18T18:41:59+00:00
- Post Title: 

Sorry, I couldn't get it to work with any TRE files.  And I couldn't create a TRE file.
After I added some files in 'Files to include', and click OK, nothing happens.  The 
dialog box just sits there.


Error messages I get:

"Not a valid TRE file"

or 

"Error opening TRE file"

"Run-time error '91'
Object variable or With block variable not set"
## Post #22
- Username: Tulebox
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Dec 09, 2003 8:04 am
- Post datetime: 2003-12-18T18:45:37+00:00
- Post Title: 

It would help if your program generated a debug log, 
so you could know where the problem is happening.
## Post #23
- Username: Tulebox
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Dec 09, 2003 8:04 am
- Post datetime: 2003-12-18T18:54:02+00:00
- Post Title: 

> I just glued the start and end part together and changed the tailpointer to overcome the 
>
> missing parts (i don't need the actual contents, as long as i have the tails).

How about creating a file the same size as the original (33MB,100MB or however big) and fill
in missing data with zeroes?  That way, you don't have to change any data or pointers.
## Post #24
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-12-18T19:16:49+00:00
- Post Title: 

> Reply from Tulebox
>
> Sorry, I couldn't get it to work with any TRE files.  And I couldn't create a TRE file.
After I added some files in 'Files to include', and click OK, nothing happens.  The 
dialog box just sits there.


Error messages I get:

"Not a valid TRE file"

or 

"Error opening TRE file"

"Run-time error '91'
Object variable or With block variable not set"

Interesting. But you should also set the new name of the file, before you include any files. If you click ok without, the checker will see that there's an attempt to create a file with no name and abort. It's not all that sophisticated yet. 

Yeah, yeah, I know there should be a debuglog or other stuff. Cut me some slack here, I am doing this for fun (and free) and this is an alpha version after all.   

The error messages at least give away something. "This is not a valid TRE file" for instance, tells me version a 0004 file was attempted to open. 

"Error opening TRE file" is a general file i/o error and can be anything, and the last one you mention is clearly a bug somewhere, I think somewhere where you should not have been yet. 

Can you please specify in detail how you go about it? Exactly when these errors occur? And wich file you tried to open (i've got the header and tail parts eh!). 

Thanks!
## Post #25
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-12-18T22:21:12+00:00
- Post Title: 

It works fine on my homebrew bottom.tre file. It opens it anyway. 

What OS are you running, and did you previously install MultiEx Commander?

Try to download the new versino (same link), I altered it a tiny bit.
## Post #26
- Username: Tulebox
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Dec 09, 2003 8:04 am
- Post datetime: 2003-12-19T01:02:30+00:00
- Post Title: 

Downloaded the link again, and still getting the same error.

BTW, this is one error.  I get these two messages together:
"Error opening TRE file" 
"Run-time error '91' 
Object variable or With block variable not set"

All EERT5000 files give me this error, with exception of the EERT4000 file.

I'm running winXP.  All I do is extract TREArchiver.exe and run it in its own directory.
## Post #27
- Username: Tulebox
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Dec 09, 2003 8:04 am
- Post datetime: 2003-12-19T08:05:04+00:00
- Post Title: 

I certainly couldn't have gotten this far without your help, so
thanks again.

You said you pasted the header and tail parts together.  You could 
send me one of your pasted files so I could try it out.
## Post #28
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-12-19T09:39:04+00:00
- Post Title: 

Ok, well, as you should have read in the readme.txt   you MUST install MultiEx Commander. This program is not yet standalone.

Again a new version, this time it will create a log.txt when you open something. I think I know what the problem is. You don't have a registered zlib.dll v1.1.2.0. This will be installed if you install MultiEx Commander. Zlib is needed for compression.decompression. 

Alternatively, [download it here](http://www.xentax.com/downloads/tools/zlib.dll) and type Start->Run->"regsvr32 (location where you saved zlib.dll)", and if that doesn't work copy it into the win/system32 folder.
## Post #29
- Username: Tulebox
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Dec 09, 2003 8:04 am
- Post datetime: 2003-12-19T18:54:49+00:00
- Post Title: 

Yea! That was it.  it worked! 

Tested all the files, all of them extracted with no problems.


btw, when I ran regsvr32, I got:
"zlib.dll was loaded, but the DllRegisterServer entry point was not found.
This file can not be registered."

But, I guess that didn't matter, since it worked fine. 


Also, I tried creating a tre archive and I got:

TREArchiver
Run-time error '6':
Overflow

I first browse enter the name of a new file, like new.tre (this file does not exist).
Then I browse to enter a single filename, then click OK.


But other than that, extracting is great!
## Post #30
- Username: Tulebox
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Dec 09, 2003 8:04 am
- Post datetime: 2003-12-19T19:02:15+00:00
- Post Title: 

Some more info on creating tre files.  Even though I got that overflow error, three files were created:

new.tre
t1.tmp
t2.tmp

But when I try to load new.tre back into TREArchiver, I get an overflow
error, trying to read it.

here's the log, trying to load new.tre after the error:

[x] Ok - *** New Debug Log *** > 12/19/2003
[x] Ok - OpenTRE->Opening C:\new.tre, 1
[x] Ok - OpenTRE->Loading Header of C:\new.tre, 1
[x] Ok - OpenTRE->Header ID =EERT5000
[x] Ok - OpenTRE->Header variables : 1,365,2,27,2,48,41
[x] Ok - OpenTRE->Reading tail data at : 365
[x] Ok - OpenTRE->Tails read (in bytes) : 26, 47
[x] Ok - OpenTRE->Decompression if necessary
[x] Ok - DecompressData>Decompression Result: 0
[x] Ok - OpenTRE->Decompression Result: 0
[x] Ok - DecompressData>Decompression Result: 0
[x] Ok - OpenTRE->Creating temporary tailfiles : 
C:\t1.tmp
C:\t2.tmp
[x] Ok - OpenTRE->Temporary tailfiles created
[x] Ok - OpenTRE->Opening Temporary Tails
[x] Ok - OpenTRE->Reading tails
## Post #31
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-12-19T22:37:43+00:00
- Post Title: 

Well, well. Indeed. I'm glad it workes now, can you send me some of the files you extracted, like some one or two cool sounds? So I can be proud!   

Anyway, you are right about that error, but that only occurs when you try to create a TRE file that contains only 1 file, select multiple files in the select dialog (holding ctrl or shift) and it will work. I will have a look at which damn routine can't handle a single file inclusion....Damn non-zero-based programming probably....
## Post #32
- Username: wright_left
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Jan 10, 2004 4:32 pm
- Post datetime: 2004-01-10T08:36:08+00:00
- Post Title: 

This is pretty sweet so far, I had no idea about all this stuff until today. I'm very interested in using the sounds from SWG in something I'm doing, so I downloaded all this goodness here and extracted a bunch of files. I got wavs and mp3 and all kinds of other stuff. However, and this is probally a n00b question, how do you play the sounds, or convert them into something else? I none of my players will play these seemingly standard formats. I know I'm missing something here, but any help would be cool.

[Edit]
I just noticed that all the files which are extracted are 1k in size or less. So I know I'm doing something wrong. Help!
## Post #33
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-01-10T17:35:13+00:00
- Post Title: 

This issue was first addressed here :
[viewtopic.php?p=2759#2759](http://forum.xentax.com/viewtopic.php?p=2759#2759)

And as I say there, I am working on it.
## Post #34
- Username: wright_left
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Jan 10, 2004 4:32 pm
- Post datetime: 2004-01-10T22:01:29+00:00
- Post Title: 

Oh, my bad. I read that thread, but for some reason I didn't see that he was having the same problem. I told you it was a n00b question. It's just that the program seemed to be working great, and in your post above you said to send you some cool sounds. I guess I'll just give you some time to work on it. Thanks for your effort.
## Post #35
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-01-11T11:58:28+00:00
- Post Title: 

Okay, see [viewtopic.php?p=2767#2767](http://forum.xentax.com/viewtopic.php?p=2767#2767)
## Post #36
- Username: xc
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Apr 15, 2004 11:53 am
- Post datetime: 2004-04-15T03:54:44+00:00
- Post Title: 

hi i was searching on google on how to open up these files. i read through this thread and understood a few things, but i still dont know how to open up the files and play them in a music player like winamp etc. in other words get them into a wav or mp3 format. if any of you guys could help me i woudl really appreciate it.
## Post #37
- Username: xc
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Apr 15, 2004 11:53 am
- Post datetime: 2004-04-15T04:01:46+00:00
- Post Title: 

err i feel like an idiot, when i was searching it brought me to the post so i didnt see the extra pages, my bad guys, very sorry. i downloaded the program and thanks
## Post #38
- Username: cepolly
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Sep 02, 2005 9:32 pm
- Post datetime: 2005-09-02T13:35:02+00:00
- Post Title: 

hi am a complete noob on this stuff.

i downloaded the multi ex commander and the tre archiver.

i tried to open the .tre files and i cannot.

can someone give me a step by step on how to read the SWG .tre files.

thanks in advance.
## Post #39
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-09-02T13:53:52+00:00
- Post Title: 

Please read other threads on this forum about this subject. Check the Game Request forums to start with. Also, the TRE archiver is old and not updated.
