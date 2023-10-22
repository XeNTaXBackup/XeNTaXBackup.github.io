## Post #1
- Username: wolfen
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Dec 27, 2011 7:13 am
- Post datetime: 2014-05-22T23:53:55+00:00
- Post Title: Help animation File

I need help with Animation files
how to open edit and save the file



here sample

https://mega.co.nz/#!cM0gUCZA!kTrtvrmLWsUwF1USsd3WteK9g3RLyNo8nPZgQ58AlLU
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-05-23T07:31:31+00:00
- Post Title: Help animation File

hmm, "open, edit and save"? Afaik there's no general tool for if you mean that.
(You could use a hexeditor but that's doesn't turn out to be very comfortable.)

First of all you need to analyse. On a quick view I found this:

  1. Bone09
01 2D 95 7C  
08 06 14 00  98 01 3F 01  00 00 00 00  00 00 00 00  
F4 83 12 00  C1 67 82 7C  C9 67 82 7C  CC 85 12 00  
28 D6 20 00  00 00 00 00  98 01 3F 01  28 EB 1A 00  
00 00 00 00  01 00 00 00  00 00 00 00   -- might be boneID (1) and parent ID (0)
  2. Bone10
D0 67 82 7C  
FF FF FF FF  C9 67 82 7C  FD B5 D2 77  9C 01 3F 01  
1C 84 12 00  83 B6 D2 77  9C 01 3F 01  00 00 F4 77  
28 EB 1A 00  00 00 00 00  00 00 00 00  34 84 12 00  
E1 A9 D2 77  02 00 00 00  01 00 00 00  
  3. Bone12
74 84 12 00  
DE B3 D2 77  28 D6 20 00  04 01 00 00  CC 85 12 00  
01 00 00 00  20 85 12 00  40 53 10 01  76 0B C2 00  
16 05 93 7C  88 86 12 00  97 0F 93 7C  70 48 92 7C  
76 0B C2 00  03 00 00 00  02 00 00 00  
  4. Bone11
40 53 10 01  
0D 00 00 00  04 01 00 00  CC 85 12 00  20 85 12 00  
40 53 10 01  00 00 00 00  67 BD D2 77  B3 BD D2 77  
40 53 10 01  0D 00 00 00  04 01 00 00  CC 85 12 00  
00 00 00 00  04 00 00 00  02 00 00 00  
  5. Bone13
0D 00 00 00  
04 01 00 00  CC 85 12 00  67 BD D2 77  CD AB BA DC  
00 00 00 00  20 85 12 00  67 BD D2 77  4C 85 12 00  
7E 90 D1 77  00 D0 FD 7F  4C 85 12 00  FA 86 D1 77  
0C 85 12 00  05 00 00 00  02 00 00 00  
  6. Bone01
14 00 00 00  
01 00 00 00  00 00 00 00  00 00 00 00  10 00 00 00  
00 00 00 00  FF FF FF FF  01 00 00 00  00 00 00 00  
00 00 00 00  00 85 12 00  D0 4E 17 00  90 85 12 00  
35 25 D4 77  06 00 00 00  00 00 00 00  
  7. Bone02
00 00 00 00  
67 BD D2 77  76 0B C2 00  0D 00 00 00  04 01 00 00  
CC 85 12 00  54 53 10 01  6A 9D D1 77  D0 8E 12 00  
E0 8 D 12 00  76 0B C2 00  08 60 1C 00  00 00 00 00  
74 85 12 00  07 00 00 00  06 00 00 00  
  8. Bone03
FF FF FF FF  
6A 9D D1 77  9E 02 D2 77  40 53 10 01  0D 00 00 00  
04 01 00 00  B4 02 D2 77  00 00 00 00  40 53 10 01  
00 00 00 00  0A 02 00 00  CC 85 12 00  00 00 00 00  
7C 86 12 00  08 00 00 00  07 00 00 00  
  9. Bone04
6E 79 74 61  
69 6C 31 4E  75 62 00 00  94 89 12 00  3C 00 00 00  
00 00 00 00  39 00 37 00  1C 8 D 12 00  2C 8 D 12 00  
0E 87 12 00  33 00 2D 00  1E 00 00 00  02 00 00 00  
3C 00 3E 00  09 00 00 00  00 00 00 00  
 10. Bone05
6E 79 74 61  
69 6C 32 00  75 62 00 7C  A4 89 12 00  24 00 02 00  
90 87 12 00  02 00 00 00  68 86 12 00  00 E0 FD 7F  
A6 59 92 7C  38 86 12 00  00 00 00 00  90 F2 94 7C  
B4 94 12 00  0A 00 00 00  09 00 00 00  
 11. Bone06
EC 86 12 00  
93 13 93 7C  84 86 12 00  38 00 00 00  38 00 00 00  
0C 02 00 00  01 00 00 00  1C B9 F6 E1  34 00 00 00  
00 00 00 00  40 53 10 01  0D 00 00 00  04 01 00 00  
67 BD D2 77  0B 00 00 00  0A 00 00 00  
 12. Bone07
8 D 9F D1 77  
EA 35 D4 77  76 0B C2 00  0D 00 00 00  08 02 00 00  
68 89 12 00  67 BD D2 77  B3 02 00 00  01 00 00 00  
74 87 12 00  40 53 10 01  00 00 00 00  B1 DE D2 77  
FD DE D2 77  0C 00 00 00  00 00 00 00  
 13. Bone08
01 00 00 00  
B1 DE D2 77  38 87 12 00  B0 85 D1 77  76 0B C2 00  
0D 00 00 00  08 02 00 00  68 89 12 00  B1 DE D2 77  
CD AB BA DC  00 00 00 00  74 87 12 00  B1 DE D2 77  
A0 87 12 00  0D 00 00 00  00 00 00 00  

56 x2 matrices to follow: (on a first thought, but seems to be just 112 matrices)
 1.000000 0.000000 0.000000 0.000000 I
 0.000000 -0.559670 0.828716 0.000000 > rotation
 0.000000 -0.828716 -0.559670 0.000000 I
 -0.021937 1.319742 0.835669 1.000000 -- might be position

 -0.020615 0.999788 0.000003 0.000000 I
 0.559551 0.011535 0.828716 0.000000  > rotation
 0.828540 0.017086 -0.559670 0.000000 I
 -1.402790 -0.051211 0.842764 1.000000 -- position 

 -0.007177 0.999970 -0.002984 0.000000 
 0.198617 0.004350 0.980068 0.000000 
 0.980051 0.006442 -0.198642 0.000000 
 -1.687503 -0.032240 0.211094 1.000000 -- pos
 -0.488473 0.867592 -0.093155 0.000000 
 -0.142046 0.026271 0.989511 0.000000 
 0.860939 0.496582 0.110406 0.000000 
 -1.712269 -0.928904 -0.408941 1.000000 -- pos

 0.389079 0.918079 0.075815 0.000000 
 -0.134161 -0.024951 0.990645 0.000000 
 0.911383 -0.395610 0.113463 0.000000 
 -1.822307 0.677477 -0.416984 1.000000 
 -0.485270 0.836974 0.252959 0.000000 
 0.737695 0.236603 0.632317 0.000000 
 0.469382 0.493451 -0.732247 0.000000 
 -1.111176 -1.024193 1.294448 1.000000 -- pos

 0.874083 0.386109 0.294787 0.000000 
 0.107981 -0.746086 0.657035 0.000000 
 0.473624 -0.542472 -0.693834 0.000000 
 -0.926466 0.862390 1.096799 1.000000 
 0.684916 0.478589 0.549402 0.000000 
 0.248787 -0.862323 0.441026 0.000000 
 0.684832 -0.165382 -0.709686 0.000000 
 -1.506131 0.156178 1.037959 1.000000 

 0.308531 -0.258362 0.915455 0.000000 
 -0.864440 -0.477754 0.156506 0.000000 
 0.396927 -0.839643 -0.370741 0.000000 
 -0.850816 1.839043 0.204555 1.000000 
 -0.860775 0.375579 -0.343523 0.000000 
 0.061292 0.746490 0.662567 0.000000 
 0.505282 0.549266 -0.665580 0.000000 
 -0.954142 -0.887262 1.051639 1.000000 

 -0.764340 0.397973 -0.507348 0.000000 
 0.214549 0.898946 0.381922 0.000000 
 0.608073 0.183068 -0.772485 0.000000 
 -1.372932 -0.225789 1.197833 1.000000 
 -0.278385 -0.504094 -0.817552 0.000000 
 -0.858648 0.512034 -0.023336 0.000000 
 0.430378 0.695493 -0.575382 0.000000 
 -0.906622 -1.665082 0.686825 1.000000 

 -0.147014 -0.984127 0.099402 0.000000 
 0.007903 0.099322 0.995024 0.000000 
 -0.989103 0.147068 -0.006824 0.000000 
 1.439650 -0.282832 0.022925 1.000000 
 0.227582 -0.961524 -0.153877 0.000000 
 0.018383 -0.153753 0.987938 0.000000 
 -0.973585 -0.227665 -0.017316 0.000000 
 1.404709 0.427397 0.046550 1.000000 

now 1255 blocks with 3 lines follow, could not make sense of them:
 0.000000 0.000000 1.000000 0.000000 
 0.000000 0.000000 0.000000 -0.000000 
 -1.000000 0.000000 0.000000 1.000000 

 -0.000000 0.000000 0.023228 0.083829 
 0.500785 1.000000 0.000000 0.000000 
 1.000000 0.000000 0.000000 0.000000 

 0.000000 -0.000000 -1.000000 0.000000 
 0.000000 1.000000 -0.000000 0.000000 
 0.023228 0.084260 1.648006 1.000000 

 0.000000 0.000000 1.000000 0.000000 
 0.000000 0.000000 0.000000 -0.000000 
 -1.000000 0.000000 0.000000 1.000000 

 -0.000000 0.000000 0.023228 0.051391 
 1.610771 1.000000 0.000000 0.000000 
 1.000000 0.000000 0.000000 0.000000 

 0.000000 -0.000000 -1.000000 0.000000 
 0.000000 1.000000 -0.000000 0.000000 
 0.023228 0.051391 1.599544 1.000000 

 0.000000 0.000000 1.000000 0.000000 
 0.000000 0.000000 0.000000 -0.000000 
 -1.000000 0.000000 0.000000 1.000000 

 -0.000000 0.000000 0.023228 0.026718 
 1.492078 1.000000 0.000000 0.000000 
 1.000000 -0.000000 -0.000000 0.000000 
... cutting the rest