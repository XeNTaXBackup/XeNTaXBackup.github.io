## Post #1
- Username: andrevictor18
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Sep 11, 2016 2:38 pm
- Post datetime: 2017-03-13T06:56:43+00:00
- Post Title: Help to decompress game file

the game is: 舞力全开：活力派 (download: adl.netease.com/d/g/justdance/c/gw_pcclient). In the pastes of installed game there is a paste called Setting, in older versions of the game this paste contained files .json that can be easily readed.

But in the current version, the paste Setting contains .z files that cannot be extracted or readed. I want to read the text in the setting files but it is kind compressed. So I decided to use dotPeek to decompile the Assembly-CSharp.dll (an dll from the game) and I discover that it uses sevenzip lzma comprfession, So I got some interesting codes that can be useful to decode these files.

Here is the Setting old and current files [https://www.dropbox.com/sh/d64b1pjx3sp8 ... uHNxa?dl=0](https://www.dropbox.com/sh/d64b1pjx3sp8r4z/AABmDj78ZpcT1RuGq35HuHNxa?dl=0)

and here it is the codes I decompiled [https://www.dropbox.com/sh/frejsrezln9y ... -Hiaa?dl=0](https://www.dropbox.com/sh/frejsrezln9ycib/AADfMb3iylo8sS4KM8kM-Hiaa?dl=0)

If someone can help me I will be thankful
## Post #2
- Username: MaKiPL
- Rank: advanced
- Number of posts: 60
- Joined date: Sat Sep 13, 2014 9:05 pm
- Post datetime: 2017-03-13T19:40:59+00:00
- Post Title: Help to decompress game file

It's indeed 7Zip algorithm you IL-generated code posted:
[http://www.7-zip.org/sdk.html](http://www.7-zip.org/sdk.html)
Download LZMA SDK for C# and you will get 1:1 code as is inside assembly-CSharp.dll
Neither of the official SDK tools for decompression works as this is not an archive. I'll try to test algorithms on raw data now.

EDIT: grr, I can't decode it, maybe there's something additional?
EDIT2: Yeah, the SettingsManager uses JDCStreamReader.messageParse()... (not LZMA)

```
{
	totalLen = 0;
	readSuccess = false;
	int num = messageLength - startIndex;
	if (num < 5)
	{
		return string.Empty;
	}
	int num2 = BasicFunc.stringConvertToNumber(Encoding.UTF8.GetString(message, startIndex, 5), 36);
	int num3 = (num2 & 29360128) >> 22;
	int num4 = num2 & 4194303;
	totalLen = num4 + 5;
	if (num4 <= num - 5)
	{
		byte[] buffer = BufferPool<byte>.GetBuffer((long)num4);
		Array.Copy(message, startIndex + 5, buffer, 0, num4);
		string result = Singleton<JDCZlibWrapper>.GetInstance().doDeCompress(buffer, num4);
		BufferPool<byte>.Release(buffer, true);
		readSuccess = true;
		return result;
	}
	return string.Empty;
}
```


JDCZlib:

```
private static extern IntPtr JDCZlibDeCompress([MarshalAs(UnmanagedType.LPArray)] byte[] source, int length);
```

Ah, not the first time I see this... They are coding the file via streamer and/or password/key that is stored in unmanaged binary (Mobius: Final Fantasy uses external assembly to get AES key for example)
Let's see if there's something special about this Zlib stream

UPDATE:
Basically, the first 5 characters in .z file are used to get final size of decompressed file. File content is after these five characters.

Done!
I'm coding a tool for you
## Post #3
- Username: MaKiPL
- Rank: advanced
- Number of posts: 60
- Joined date: Sat Sep 13, 2014 9:05 pm
- Post datetime: 2017-03-13T21:24:55+00:00
- Post Title: Help to decompress game file

Decompressor:
[https://github.com/MaKiPL/JAP_JustDance ... r/Form1.cs](https://github.com/MaKiPL/JAP_JustDance_JDCZlib_Decompressor/blob/1.0.0/JAP_JustDance_JDCZlib_Decompressor/Form1.cs)

Binary:
[https://github.com/MaKiPL/JAP_JustDance ... r/releases](https://github.com/MaKiPL/JAP_JustDance_JDCZlib_Decompressor/releases)

.NET Framework 4.0 or 4.5 you will need it
## Post #4
- Username: andrevictor18
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Sep 11, 2016 2:38 pm
- Post datetime: 2017-03-14T22:32:20+00:00
- Post Title: Help to decompress game file

Thank you very much for your effort! But can you send a example of a decompressed file? No, better can you show me some tutorial How to use the decompressor?
## Post #5
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2017-03-15T05:29:46+00:00
- Post Title: Help to decompress game file

Just download the binary and run it. MaKi made really simple but useful graphical interface there.
## Post #6
- Username: MaKiPL
- Rank: advanced
- Number of posts: 60
- Joined date: Sat Sep 13, 2014 9:05 pm
- Post datetime: 2017-03-15T23:08:09+00:00
- Post Title: Help to decompress game file

> Reply from andrevictor18
>
> Thank you very much for your effort! But can you send a example of a decompressed file? No, better can you show me some tutorial How to use the decompressor?

> Reply from andrevictor18
>
> do I need visual studio?

No, you don't need it. 
Just get on this link: [https://github.com/MaKiPL/JAP_JustDance ... tag/1.0.0b](https://github.com/MaKiPL/JAP_JustDance_JDCZlib_Decompressor/releases/tag/1.0.0b)
download 'debug.7z' from there, unpack the archive and run "JAP_JustDance_JDCZlib_Decompressor.exe". You should see a window like on this image:



If you are getting error about ".NET Framework" then please download Microsoft .NET Framework 4.5 (you can get it from official Microsoft site: [https://www.microsoft.com/pl-pl/downloa ... x?id=30653](https://www.microsoft.com/pl-pl/download/details.aspx?id=30653))

Right in software you have labels for "input file" and "output file". In input file please click on "Browse..." button on it's right and file browser will appear allowing you to choose a .z file (e.g. currency.z) that is compressed. Next step is choosing the output file, do the same, use "Browse..." button (the second one) and type the filename of the decompressed file (e.g. currency.Unpacked). If you did the both, then the last step is clicking on "DECOMPRESS" button. If everything worked well a "DONE!" message box should appear.
## Post #7
- Username: andrevictor18
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Sep 11, 2016 2:38 pm
- Post datetime: 2017-03-15T23:17:30+00:00
- Post Title: Help to decompress game file

THank you very much! You are amazing
## Post #8
- Username: MaKiPL
- Rank: advanced
- Number of posts: 60
- Joined date: Sat Sep 13, 2014 9:05 pm
- Post datetime: 2017-04-16T12:14:58+00:00
- Post Title: Help to decompress game file

I'm so sorry I couldn't done it faster. Here:
[https://github.com/MaKiPL/JAP_JustDance ... es/tag/1.1](https://github.com/MaKiPL/JAP_JustDance_JDCZlib_Decompressor/releases/tag/1.1)

The compression support
## Post #9
- Username: jmticon
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Apr 28, 2019 3:12 am
- Post datetime: 2019-04-27T19:19:10+00:00
- Post Title: Help to decompress game file

Hi. Does anyone know how to decompress common and secondscreen files in game Just Dance Vitality School? These files you can find in \舞力全开：活力派\PCMonitor64_Data\StreamingAssets\preinstall\songdata\dance and select any dancesong folder.
## Post #10
- Username: MaKiPL
- Rank: advanced
- Number of posts: 60
- Joined date: Sat Sep 13, 2014 9:05 pm
- Post datetime: 2019-09-10T17:42:25+00:00
- Post Title: Help to decompress game file

The files you mentioned are casual "unityFS" with lz4 compression- I was able to open them without problem with UnityPack. Here's content of xmas/common:

```
0x7ac4042a8b5c8ff3 TextAsset b'\x0
0x7ac4042a8b5c8ff3 TextAsset '{\r\
0x7ac4042a8b5c8ff3 TextAsset b'\x0
0x7ac4042a8b5c8ff3 TextAsset b'\x0
0x7ac4042a8b5c8ff3 Sprite
0x7ac4042a8b5c8ff3 TextAsset b"\x0
0x7ac4042a8b5c8ff3 TextAsset b'\x0
0x7ac4042a8b5c8ff3 TextAsset b'\x0
0x7ac4042a8b5c8ff3 TextAsset b'\x0
0x7ac4042a8b5c8ff3 TextAsset b"\x0
0x7ac4042a8b5c8ff3 TextAsset b"\x0
0x7ac4042a8b5c8ff3 Sprite
0x7ac4042a8b5c8ff3 TextAsset b'\x0
0x7ac4042a8b5c8ff3 TextAsset b'\x0
0x7ac4042a8b5c8ff3 TextAsset b'\x0
0x7ac4042a8b5c8ff3 TextAsset b"\x0
0x7ac4042a8b5c8ff3 TextAsset b'\x0
0x7ac4042a8b5c8ff3 TextAsset b'\x0
0x7ac4042a8b5c8ff3 TextAsset b'\x0
0x7ac4042a8b5c8ff3 TextAsset b'\x0
0x7ac4042a8b5c8ff3 Texture2D
0x7ac4042a8b5c8ff3 TextAsset b'\x0
0x7ac4042a8b5c8ff3 AssetBundle
0x7ac4042a8b5c8ff3 TextAsset b'\x0
0x7ac4042a8b5c8ff3 Sprite
0x7ac4042a8b5c8ff3 TextAsset b'\x0
0x7ac4042a8b5c8ff3 TextAsset b'\x0
0x7ac4042a8b5c8ff3 TextAsset b"\x0
0x7ac4042a8b5c8ff3 TextAsset b'\x0
0x7ac4042a8b5c8ff3 TextAsset b'\x0
0x7ac4042a8b5c8ff3 TextAsset '[\r\
0x7ac4042a8b5c8ff3 TextAsset b'\x0
0x7ac4042a8b5c8ff3 TextAsset b'\x0
0x7ac4042a8b5c8ff3 TextAsset b'\x0
0x7ac4042a8b5c8ff3 TextAsset b'\x0
0x7ac4042a8b5c8ff3 TextAsset b'\x0
0x7ac4042a8b5c8ff3 Texture2D
0x7ac4042a8b5c8ff3 TextAsset '{\r\
0x7ac4042a8b5c8ff3 TextAsset b'\x0
0x7ac4042a8b5c8ff3 Texture2D
0x7ac4042a8b5c8ff3 TextAsset b'\x0
0x7ac4042a8b5c8ff3 TextAsset b"\x0
0x7ac4042a8b5c8ff3 TextAsset b'\x0
0x7ac4042a8b5c8ff3 TextAsset '{\r\
0x7ac4042a8b5c8ff3 TextAsset b'\x0
0x7ac4042a8b5c8ff3 TextAsset b'\x0
0x7ac4042a8b5c8ff3 TextAsset b'\x0
0x7ac4042a8b5c8ff3 Sprite
0x7ac4042a8b5c8ff3 TextAsset b'\x0
0x7ac4042a8b5c8ff3 TextAsset b"\x0
0x7ac4042a8b5c8ff3 Texture2D

```


just find any Unity package viewer/ unity extractor
