## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2013-02-21T00:28:25+00:00
- Post Title: DX Archive Unpacker

Here is a general tool that I wrote for unpacking DX archives (don't know what they are called, but they start with DX so I just took that).

These archives are used in various programs/games, such as
Wolf RPG Editor (basically all games using this program) - [viewtopic.php?f=21&t=7981](http://forum.xentax.com/viewtopic.php?f=21&t=7981)
Gensokyo Shiki - [viewtopic.php?f=21&t=9468](http://forum.xentax.com/viewtopic.php?f=21&t=9468)



[http://www.himeworks.com/tools/dxextract/](http://www.himeworks.com/tools/dxextract/)

All DX archives I have come across use a 12-byte key.
This tool uses a key.ini keystore that stores all keys that the program should try before giving up. The keystore must be placed in the same location as the exe.

The exe supports GUI and command-line. If no arguments are supplied it will automatically load the GUI.
.NET 2.0 or above required.
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2013-03-04T04:32:05+00:00
- Post Title: DX Archive Unpacker

Labyrinth of Touhou added to the keystore.
Key: 9DF6E8099CC39999914DF0A3
[touhoulabyrinth.jpg](https://xentaxbackup.github.io/file/6236_touhoulabyrinth.jpg)
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2013-07-08T03:22:03+00:00
- Post Title: DX Archive Unpacker

Added key for Rosenkreuzstilette Freudenstachel
[http://www.dlsite.com/eng/work/=/produc ... 02971.html](http://www.dlsite.com/eng/work/=/product_id/RE102971.html)

Unfortunately, I have not gotten around to implementing the decompression routine so it can't read any of the bmp's...
## Post #4
- Username: CheloXL
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Apr 10, 2011 1:41 am
- Post datetime: 2013-07-08T12:53:21+00:00
- Post Title: DX Archive Unpacker

I really didn't took the time to try to understand the compression scheme, but it looks like some kind of pattern compression. In any case, since you are using c#, it would be pretty straightforward to convert that code to c#... you can almost copy/paste the code.

I did a really quick conversion, can't warranty this will work 

```
		byte[] dest = new byte[destlen];
		byte m = src[8];

		int ps = 9, pd = 0;

		while (ps < srclen && pd < destlen) {
			if (src[ps] == m) {
				ps++;

				if (src[ps] == m) {
					dest[pd++] = src[ps++];

				} else {
					if (src[ps] >= m) {
						src[ps]--;
					}

					int pos, len = (src[ps] >> 3) + 4;

					byte type1 = (byte)(src[ps++] & 7);
					byte type2 = (byte)(type1 >> 2);

					type1 &= 3;

					if (type2 != 0) {
						len += src[ps++] << 5;
					}
						
					switch (type1) {
						case 0:
							pos = src[ps++] + 1;
							break;

						case 1:
							pos = src[ps] + (src[ps + 1] << 8) + 1;
							ps += 2;
							break;

						case 2:
							pos = src[ps] + (src[ps + 1] << 8) + (src[ps + 2] << 16) + 1;
							ps += 3;
							break;

						default:
							pos = 0;

							Debug.Fail("This should never happen!");
							break;
					} 

					for (int k = 0; k < len; ++k) {
						dest[pd + k] = dest[pd - pos + k];
					}

					pd += len;
				}
			} else {
				dest[pd++] = src[ps++];
			}
		}

		return dest;
	}

```
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2013-07-09T23:45:31+00:00
- Post Title: DX Archive Unpacker

Thanks a lot. Now it decompresses things 
File has been updated. I have also uploaded the source.
[rosen.jpg](https://xentaxbackup.github.io/file/6512_rosen.jpg)
## Post #6
- Username: CheloXL
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Apr 10, 2011 1:41 am
- Post datetime: 2013-07-10T15:15:18+00:00
- Post Title: DX Archive Unpacker

Excellent!, glad to help!
## Post #7
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2013-08-18T17:20:11+00:00
- Post Title: DX Archive Unpacker

Labyrinth of Touhou 2 added to keystore.

[http://www.dlsite.com/home/work/=/produ ... 18525.html](http://www.dlsite.com/home/work/=/product_id/RJ118525.html)

I should really try to find a way to automatically derive the key rather than manually figuring out the key by hand. However that requires me to first assume the input is a valid DX archive...
[cover.jpg](https://xentaxbackup.github.io/file/6559_cover.jpg)
## Post #8
- Username: newby
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Mar 14, 2010 7:51 pm
- Post datetime: 2014-01-27T13:57:55+00:00
- Post Title: DX Archive Unpacker

Hello, can you help me with something?
I have tried your program to unpack the SmokingWOLF RPG One Way Heroics, but it did not work.

One Way Heroics can be purchased on PlayISM for 1.99$ (or more if you want):

```

```

I just want to extract the resources (for translation to my language)
Here are the sample file and exe:

```
http://www.sendspace.com/file/kelhp9
```


Thank you for your time and for your help.
## Post #9
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2014-02-01T15:35:28+00:00
- Post Title: DX Archive Unpacker

I don't understand the problem. It looks like a regular wolf RPG game, and I can export the sound files without any issues.
## Post #10
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-08-04T18:16:36+00:00
- Post Title: DX Archive Unpacker

Hi all, I just wanted to point out that this tool and whole keystore for it is heavily outdated.
Tool was not updated since 2014 and it doesn't really support newer archives (like version 6, 7 and 8 ).

For now, it's better to use DXADecode.exe from DXLibrary which is dealing great with unpacking data.
Also, more recent information about file format can be found on our wiki [http://wiki.xentax.com/index.php/DX_Archive](http://wiki.xentax.com/index.php/DX_Archive)
