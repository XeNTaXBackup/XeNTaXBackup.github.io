## Post #1
- Username: zzz
- Rank: beginner
- Number of posts: 21
- Joined date: Wed May 21, 2014 9:36 pm
- Post datetime: 2014-05-21T22:10:25+00:00
- Post Title: DUST 514 (UE3 console FPS, official download link)

DUST 514 is an F2P FPS available on PSN and is a counterpart to EVE Online.

```
https://www.youtube.com/watch?v=jzVjggarRns
```


EVE has a thriving render & machinma community

```
https://www.youtube.com/watch?v=d8Ke1P3m4nU&list=PLpSf_IYABOmuq2EaO8sCxtyJITOOFcUYi&index=3
```


and I'd like to be able to add character models and small arms to it. Mr Mouse has permitted me to post the official (PSN) download links:

```
Ver    = 05.08
Size   = 2.42 GB
System = PS3 FW v4.40
SHA1   = 71cd1fc002b934324e12a1bdb1c66c1aff8ba5fa
Link   = http://b0.ww.np.dl.playstation.net/tppkg/np/NPEB00777/NPEB00777_T49/347777640d0c24df/EP5018-NPEB00777_00-DUST514EVEONLINE-A0508-V0100-PE.pkg

Title  = DUST 514® patch
Ver    = 05.09
Size   = 513.02 MB
System = PS3 FW v4.40
SHA1   = 62d7ab64c79eea04c22cae8bf06d7c09fbe4cc43
Link   = http://b0.ww.np.dl.playstation.net/tppkg/np/NPEB00777/NPEB00777_T49/347777640d0c24df/EP5018-NPEB00777_00-DUST514EVEONLINE-A0509-V0100-PE.pkg

```


The patch is only for people who want all the content.

These are two tools you will need, a PKG unpacker and a PSARC unpacker.

```
https://www.mediafire.com/?q1ad6buoh8scvft
```


I unpacked the PKG and it seemed the standard UE3 layout with a CookedPS3 folder instead of a CookedPC. The CookedPSARC folder contained standard PS3 packages that can be unpacked with the tool above. It produced a lot of XXX, TFC, other UE3 files so I copied them to CookedPS3.

Then I used Gildor's uModel tool to try and unpack them all with the -ps3 -uncook -sounds tags. This is where I run into problems. It unpacks animations and textures, but no meshes or sounds, and 99% of the textures were stripped to 64x64. CharacterIcons_SF.xxx extracts perfectly.

The uncook option groups everything in identifiable folders. GA, CA, AM and MI are faction prefixes, WP for weapons, CH for characters, etc. I contacted Gildor but he says he can't reverse engineer PS3 games for his tool. Any help?
## Post #2
- Username: zzz
- Rank: beginner
- Number of posts: 21
- Joined date: Wed May 21, 2014 9:36 pm
- Post datetime: 2014-05-22T16:39:03+00:00
- Post Title: DUST 514 (UE3 console FPS, official download link)

Well it seems Ravioli Explorer can handle the sounds fine.
