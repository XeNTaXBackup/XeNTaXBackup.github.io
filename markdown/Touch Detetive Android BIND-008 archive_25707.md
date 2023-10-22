## Post #1
- Username: luatsenpai
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Apr 21, 2020 8:08 am
- Post datetime: 2022-08-17T08:05:46+00:00
- Post Title: Touch Detetive Android BIND-008 archive

Does anyone know how to unpack *.obb in BIND-008 archive?
Link file: [https://drive.google.com/file/d/1OsP3T3 ... pP5uK/view](https://drive.google.com/file/d/1OsP3T3_-9LxAoIZ3stDYc1xj1IcpP5uK/view)
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-08-17T19:38:14+00:00
- Post Title: Touch Detetive Android BIND-008 archive

Here is the file format [http://wiki.xentax.com/index.php/Touch_Detective_OBB](http://wiki.xentax.com/index.php/Touch_Detective_OBB)

And here is quickbms script to unpack/pack [https://github.com/bartlomiejduda/Tools ... script.bms](https://github.com/bartlomiejduda/Tools/blob/master/NEW%20Tools/Touch%20Detective/Touch_Detective_OBB_script.bms)
## Post #3
- Username: luatsenpai
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Apr 21, 2020 8:08 am
- Post datetime: 2022-08-18T01:18:26+00:00
- Post Title: Touch Detetive Android BIND-008 archive

> Reply from ikskoks ↑Thu Aug 18, 2022 3:38 am at Thu Aug 18, 2022 3:38 am
>
> 
Here is the file format http://wiki.xentax.com/index.php/Touch_Detective_OBB

And here is quickbms script to unpack/pack https://github.com/bartlomiejduda/Tools ... script.bms

Thank, but i have one more problem
Could you help me with the aqc file?
[L299_en.zip](https://xentaxbackup.github.io/file/22663_L299_en.zip)
## Post #4
- Username: barncastle
- Rank: beginner
- Number of posts: 32
- Joined date: Wed Apr 14, 2021 12:13 am
- Post datetime: 2022-08-18T14:06:48+00:00
- Post Title: Touch Detetive Android BIND-008 archive

Those AQ files are compressed using standard LZSS starting from 0xC.

```
   char magic[8]; // "IZW:SDIC"
   uint32 decompressedSize;
   byte data[x];  // LZSS compressed
}

```
## Post #5
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-08-18T19:43:41+00:00
- Post Title: Touch Detetive Android BIND-008 archive

> Could you help me with the aqc file?

AQC wiki page [http://wiki.xentax.com/index.php/Touch_Detective_AQC](http://wiki.xentax.com/index.php/Touch_Detective_AQC)

And script for unpack/pack data [https://github.com/bartlomiejduda/Tools ... script.bms](https://github.com/bartlomiejduda/Tools/blob/master/NEW%20Tools/Touch%20Detective/Touch_Detective_AQC_script.bms)

Thanks to barncastle for figuring out compression method
## Post #6
- Username: luatsenpai
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Apr 21, 2020 8:08 am
- Post datetime: 2022-08-20T01:53:38+00:00
- Post Title: Touch Detetive Android BIND-008 archive

Sorry to bother you so much, but honestly, I don't have anyone more knowledgeable about this matter than you.

Could you help me with the bin file too?

Thanks a lot!
[L036_en_out.zip](https://xentaxbackup.github.io/file/22669_L036_en_out.zip)
## Post #7
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-08-20T09:22:58+00:00
- Post Title: Touch Detetive Android BIND-008 archive

All I know is that this is some kind of binary text format (index + text).
There's not much I can do about it without debugging.
## Post #8
- Username: luatsenpai
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Apr 21, 2020 8:08 am
- Post datetime: 2022-08-22T00:29:59+00:00
- Post Title: Touch Detetive Android BIND-008 archive

Here is game link for debug: [https://apkpure.com/touch-detective/com.beeworks.ozawa](https://apkpure.com/touch-detective/com.beeworks.ozawa), thank a lot
## Post #9
- Username: barncastle
- Rank: beginner
- Number of posts: 32
- Joined date: Wed Apr 14, 2021 12:13 am
- Post datetime: 2022-08-22T14:16:07+00:00
- Post Title: Touch Detetive Android BIND-008 archive

The file contains some form of bytecode which the game appears to process with a custom interpreter.

I had a quick look around and couldn't find any existing implementations so you might need to roll your own. I've dumped all of the [notable strings](https://pastebin.com/PU4QUL8U) in case anyone else has knowledge of this.

```
  int stringDataOffset; // multiply by 4
  byte byteCode[stringDataOffset - 4];
  int stringDataSize;   // multiply by 4, inclusive of this field
  char stringData[stringDataSize - 4];
}

```
