## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-18T18:38:23+00:00
- Post Title: NDS 0x40 compression type

Does quickbms support the NDS files that start with 0x40 byte?

Decompression script is here I think: [http://code.google.com/p/dsdecmp/source ... enSunDD.cs](http://code.google.com/p/dsdecmp/source/browse/trunk/CSharp/GoldenSunDD/GoldenSunDD.cs)

Well, the latest build of the tool doesn't work (it works with an older version)

Samples can be found: [http://www.spriters-resource.com/commun ... ?tid=20010](http://www.spriters-resource.com/community/showthread.php?tid=20010)
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-04-23T18:12:50+00:00
- Post Title: NDS 0x40 compression type

yes, the job can be made by the "ntcompress" COM_TYPE.
ntcompress handles automatically the type (so header included) but in the next version I will add a way to call ntcompress_40 manually.
