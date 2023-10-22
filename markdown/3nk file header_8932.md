## Post #1
- Username: keleshome
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jul 09, 2011 2:32 pm
- Post datetime: 2012-05-12T13:38:27+00:00
- Post Title: 3nk file header

HI,everyone! 
i have a file, its header is 3nk, i need help ,how to decoding it?

```
00000010h: 95 BC 5B 72 09 20 FF D6 AD 84 13 3A 41 68 B7 9E ; •¼[r. ÿÖ­„.:Ah·ž
00000020h: E5 CC CB E2 99 B0 6F 46 3D 14 83 AA D1 F8 27 0E ; åÌËâ™°oF=.ƒªÑø'.
00000030h: 75 5C 7B 52 29 00 DF F6 8D A4 33 1A 61 48 97 BE ; u\{R).ßö¤3.aH—¾
00000040h: C5 EC EB EB B9 93 41 68 13 37 C5 F8 87 B2 74 40 ; Åìëë¹“Ah.7Åø‡²t@
00000050h: 33 11 6C 31 42 21 FD C6 AB C7 14 3C 44 62 BA 94 ; 3.l1B!ýÆ«Ç.<Dbº”
00000060h: F2 C6 C7 EF 89 FA 2C 08 73 5A EA EA 91 B8 67 4E ; òÆÇï‰ú,.sZêê‘¸gN
00000070h: 35 1C 3B 12 69 40 9F B6 CD E4 73 5A 21 08 D7 FE ; 5.;.i@Ÿ¶ÍäsZ!.×þ
00000080h: 85 AC AB 82 F9 D0 0F 26 5D 74 E3 CA B1 98 47 6E ; …¬«‚ùÐ.&]tãÊ±˜Gn
00000090h: 15 3C DB F2 89 A0 7F 56 2D 04 93 BA C1 E8 37 1E ; .<Ûò‰ V-.“ºÁè7.
000000a0h: 65 4C 4B 62 19 30 EF C6 94 BD 44 6C 14 7B ED D9 ; eLKb.0ïÆ”½Dl.{íÙ
000000b0h: B3 92 F8 8A 80 AA 0F 3D 41 75 E4 83 E0 B4 6B 6E ; ³’øŠ€ª.=Auäƒà´kn
000000c0h: 0E 20 3A 15 45 6C CE CC B7 9E 23 09 36 12 D7 FD ; . :.ElÎÌ·ž#.6.×ý
```

like this:============================
Here is a simple decoder proggy. (I used it for decoding some files in the German Truck Simulator)
Command line version. Usage:
Decode_3nk.exe File1 [File2 ...]
===================================
## Post #2
- Username: TBK
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Nov 13, 2013 6:01 am
- Post datetime: 2013-11-12T22:29:34+00:00
- Post Title: 3nk file header

Here you go:

```
# --- EQUIPMENT (base definitions) ---
#############################################################

def item {
	short:"__short__"			# disp
```


I used the SCSSIITool by Ekey - [viewtopic.php?f=10&t=9786](http://forum.xentax.com/viewtopic.php?f=10&t=9786)
