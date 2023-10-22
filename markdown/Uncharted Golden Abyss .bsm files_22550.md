## Post #1
- Username: Ice93
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jun 29, 2020 3:45 am
- Post datetime: 2020-08-14T16:02:37+00:00
- Post Title: Uncharted Golden Abyss .bsm files

Since there dosen't seem to be a model extractor for Uncharted golden Abyss can someone take a look at these models ?

Samples:
a2_ground_mesh.bsm
[https://mega.nz/file/t6hhUT4R#euCDjCaRP ... g3c916lytA](https://mega.nz/file/t6hhUT4R#euCDjCaRPVd7Xd64pJxvyhyzCk4kiS8q-g3c916lytA)
layout_artref.bsm
[https://mega.nz/file/x2whnBbS#Ff1flJtqN ... v_vYiQ4g7M](https://mega.nz/file/x2whnBbS#Ff1flJtqNVWTriS-y4Ntl3a1enZD6PcEYv_vYiQ4g7M)
loading_screen.bsm:
[https://mega.nz/file/dzxnERRa#5oK0UF21i ... a91tX3dvdk](https://mega.nz/file/dzxnERRa#5oK0UF21iFvIrtoW9XyGvbHmstykOynVba91tX3dvdk)
## Post #2
- Username: Ice93
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jun 29, 2020 3:45 am
- Post datetime: 2020-10-27T04:51:58+00:00
- Post Title: Uncharted Golden Abyss .bsm files

Bump. Anyone?
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-10-28T09:35:51+00:00
- Post Title: Uncharted Golden Abyss .bsm files

What I find is point clouds (here's normals, which look ok), but the face indices don't seem to fit.
.



a2_ground_mesh.png (25.24 KiB) Viewed 58 times



For the meshes, here for exampe is  a strange offset in columns (look at the sevens), whatever, no time to fiddle around:

```
19061 16850 45582 16587 10677 16640 31754 16296 40958 15895 65535     1 12048     0 36630     7    47     0     0     0     0 17024     1     0 
54778 16511 39472 16750 40030 16790  8288 16598 28615  5117 65535     2 12096     0 36638     7    47     0     0     0     0 17152     0     0 
address 0x690:
45789 16590 56654 16660 26440 16854 33636 16609 30280 44930 65535     2 12192     0 36658     7    47     0     0     0     0 17152     0     0 
10926 48782 15944 16589 39806 49493 33290 16470 19998 54303 65535     1 12288     0 36678     7    47     0     0     0     0 16832     1     0 
>>>
10620 16844 32520 16700  9396 16935  2146 16760     0     0  1312 65280 36708     7   453   153 13072     0 13984     0     0     0 12336     0 
64869 16884 11814 16729 15406 16920 11212 16770     0     0  1312 65280 36708     7   510   155 19008     0 20032     0     0     0 12352     0 
12184 16830 22123 16773  1108 16942 53035 16607     0     0  1056 65280 36744     7    21    11 25104     0 25152     0     0     0 12368     0 
...
address 0xf90:
43942 16437 32575 49142 43549 49668 19996 16417     0     0  1312 65280 36708     7    63    23 57840     1 57968     1     0     0 12528     0 
13141 16513 21375 49070  1489 49604 51476 16478     0     0  1312 65280 36708     7    75    24 58832     1 58992     1     0     0 12544     0 
26586 16627 21206 49121 36057 49631 54163 16247     0     0  1056 65280 36744     7     3     3 59872     1 59888     1     0     0 12560     0 
46644 16633 34938 49152 23332 49657 49779 16559     0     0  1056 65280 36744     7   327    75 60096     1 60752     1     0     0 12576     0 
...

```
