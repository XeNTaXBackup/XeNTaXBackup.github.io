## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-06-07T02:30:36+00:00
- Post Title: rgssad bms script

Here's an extraction algorithm written in C++

[http://pastebin.com/g9utQpC9](http://pastebin.com/g9utQpC9)

Is there a nice way to write a bms script for this?
The problem I'm having is working with the xor key and the performance implications of using a loop to perform the xor, math, and putting the data somewhere.

It is like incremental XOR where you XOR each byte with a new byte, except instead of just increasing by 1, it's increasing like

```

```


For example, reading a filename is done like

```
		{
			tmpInfo.filename[i] ^= magickey & 0xFF;
			magickey = magickey * 7 + 3;
		}

```


And reading the file data is done like

```
		{
			rgssad_file.Read(buf, 1024);
			for(j = 0; j < 1024; j+=4)
			{
				*(unsigned long *)(&buf[j]) ^= magickey;
				magickey = magickey * 7 + 3;
			}
			sp_file.Write(buf, 1024);
			leftsize -= 1024;
		}
for(j = 0; j < leftsize; j+=4)
		{
			*(unsigned long *)(&buf[j]) ^= magickey;
			magickey = magickey * 7 + 3;
		}

```


If I went ahead and started using a for loop, it would get really slow.

It looks like the key used to grab the file table is different from the key for each individual file (hence the reason why the key is saved for each file data entry)

Here is a simple archive that I put together myself for testing purposes:

[http://db.tt/BBfrxkXI](http://db.tt/BBfrxkXI)

Here is my shot at it. I've gotten the filenames out (really ugly code to try to reproduce what is being done), but the data looks even messier...

```

idstring "RGSSAD\x00"
get VERSION byte
print "Version %VERSION%"

#set the key
set key = 0xDEADCAFE

#set eof
get EOF asize

# start looping
savepos OFFSET
do
  string name = ''
  get len long
  math len ^= key

  math key *= 7
  math key += 3
  
  for j = 0 < len
    get char byte
    math charkey = key
    math charkey &= 0xFF
    math char ^= charkey
    math key *= 7
    math key += 3
    string new = char
    string name += new
  next j
  print "%name%"
  get SIZE long
  math SIZE ^= key
  math key *= 7
  math key += 3
  
  #read data
  getdstring DATA SIZE
  
  savepos OFFSET
while OFFSET < EOF

```


Also, how do I initialize a string to be the empty string? You can see that I set the name as "_" but that's only cause I don't know how to make it an empty string lol

Upon extracting my archive, you should get the following files...without the leading underscore

```
_Data\Animations.rxdata
_Data\Armors.rxdata
_Data\Classes.rxdata
_Data\CommonEvents.rxdata
_Data\Enemies.rxdata
_Data\Items.rxdata
_Data\Map001.rxdata
_Data\MapInfos.rxdata
_Data\Scripts.rxdata
_Data\Skills.rxdata
_Data\States.rxdata
_Data\System.rxdata
_Data\Tilesets.rxdata
_Data\Troops.rxdata
_Data\Weapons.rxdata
_Graphics\Pictures\levels1.jpg

```
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-06-08T04:20:47+00:00
- Post Title: rgssad bms script

Hmm I went and wrote a C# console app for it lol it's probably faster than using strange hacks to get the quickbms to decrypt it.
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-06-08T08:07:12+00:00
- Post Title: rgssad bms script

*edit*
updated:
[http://aluigi.org/papers/bms/others/rgssad.bms](http://aluigi.org/papers/bms/others/rgssad.bms)
## Post #4
- Username: Falo
- Rank: advanced
- Number of posts: 78
- Joined date: Fri Oct 23, 2009 8:29 pm
- Post datetime: 2012-08-12T20:58:15+00:00
- Post Title: rgssad bms script

Here, a decrypt Tool + source, works with both RGSSAD V1 (RPG Maker XP,VX) & V3 (RPG Maker VX Ace), it uses UTF8, so you should be able to decrypt JPN/CHS games with it.

[](http://www.imagebanana.com/view/ns9mu0e6/RPGMakerDecrypter.jpg)
dl: [http://www.mediafire.com/download.php?xweoqp2ieep5mxv](http://www.mediafire.com/download.php?xweoqp2ieep5mxv)

V3 uses the same xor encryption, but there are some changes,
1. It uses now a Filetable
2. Base Key is fixed in file header
3. Base Key is not modified in each step
4. decrypt key is fixed for each file in file table

```
7 Byte = "RGSSAD" & 0x00 
1 Byte = Version // 3
4 Byte = base key // calculate it base key = (base key * 9) +3

File Table Structure:
4 Byte = Offset // xor with base key
4 Byte = Size // xor with base key
4 Byte = Key // xor with base key
4 Byte = Length (Filename) // xor with base key
X Byte = Filename // xor with base key in 4 byte steps

// read file table structure until Offset = 0,
// last entry (Offset = 0) does not have a filename
// file data uses the same encryption as V1, use key from filetable
```
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-08-12T23:43:33+00:00
- Post Title: rgssad bms script

thanx for the info, I have updated my script in case someone is interested
## Post #6
- Username: PCto
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Dec 31, 2008 6:37 pm
- Post datetime: 2015-05-06T14:06:15+00:00
- Post Title: rgssad bms script

@aluigi is there any chance you can check what is wrong with the RGSSAD V3 algorithm. For some reason it meses up on the last 2 symbols on some of the extracted files resulting in unopenable files.

P.S. Falo's program seems to work fine.
## Post #7
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2015-05-09T17:06:06+00:00
- Post Title: rgssad bms script

Thanks, fixed.
