## Post #1
- Username: azraelaxel
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Mar 24, 2011 10:01 am
- Post datetime: 2011-04-20T03:53:28+00:00
- Post Title: OVL Legend Of Dragoon Format

Hello again Xentax Forum!... i was researching about all formats presents in the game Legend Of Dragoon of Sony Playstation... and i found a couple of archives thats i suppose that holds table information... but are in a strange format... called "*.OV_" in a folder called "OVL", when i open with a Hex editor i see head of the archive "BPE"... surely the Byte Pair Encoding compression system. I want to know if anyone have heard about some tool to decompress or sort this kind of archive... anyway i left the OVL folder with the archives upload... if someone wants to help me with this... 
Thanks a lot!...

```
http://www.mediafire.com/?d60yscryh2uq4hk
```
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-04-20T06:56:21+00:00
- Post Title: OVL Legend Of Dragoon Format

I have tried the yuke_bpe compression and nothing.
scanned with comtype_scan2 for quickbms and nothing.
## Post #3
- Username: azraelaxel
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Mar 24, 2011 10:01 am
- Post datetime: 2011-04-20T21:29:38+00:00
- Post Title: OVL Legend Of Dragoon Format

thanks aluigi!... surely i have to make some exe for open it...
## Post #4
- Username: Forte
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Aug 07, 2007 4:51 am
- Post datetime: 2013-01-02T19:41:05+00:00
- Post Title: OVL Legend Of Dragoon Format

I realize this is an old topic, but I recently went through the decompression routine via the use of a debugger and thought I'd contribute.

In general, there are several cycles of decompression, each usually dealing with up to 0x800 bytes of (decompressed) data. Each cycle also has its own pair table/dictionary. My java code is (BinaryReader being a custom class dealing with simple binary operations):

```
		int fileSize = br.readInt(); //decompressed filesize
		byte[] dFile = new byte[fileSize];
		int dIndex = 0;
		int bufferSize = 0;
		int[][] dTable = new int[256][2];
		br.readInt(); //BPE
		
		while ((bufferSize = br.readInt()) != 0) {
			int code = 0;
			for (int i = 0; i < dTable.length; i++) {
				dTable[i][0] = i;
			}
			
			/* Table creation phase */
			while (code < 256) {
				int copyAmount = br.readByte();
				if (copyAmount >= 128) { 
					code = code - 127 + copyAmount;
					copyAmount = 0; // i.e. 1 byte
				}
				
				if (code < 256) {
					for (int i = 0; i <= copyAmount; i++) {
						int b = br.readByte();
						dTable[ code][0] = b;
						
						if (b != code) {
							b = br.readByte();
							dTable[ code][1] = b;
						}
						code++;
					}
				}
			}
			
			/* File decompression phase */
			for (int i = 0; i < bufferSize;) {
				int input = br.readByte();
				Stack<Integer> unresolved = new Stack<Integer>();
				unresolved.push(input);
				
				while (!unresolved.empty()) {
					int in = unresolved.pop();
					if (in != dTable[in][0]) {
						unresolved.push(dTable[in][1]);
						unresolved.push(dTable[in][0]);
					} else {
						dFile[dIndex + (i++)] = (byte)in;
					}
				}
			}
			
			dIndex += bufferSize;
			
			if (br.getOffset() % 4 != 0) br.skip(4 - br.getOffset() % 4);
		}
		
		new FileOutputStream(path).write(dFile);
	}
```


The code closely follows what the PSX does.
I'm not familiar with BPE so I'll walk you through it a bit. Each encoding table entry contains up to two bytes, where each byte is either a reference to a different table entry or a literal character. No general distinction is made between what is a symbol and what isn't, it all depends on how the table is constructed (table creation phase). What the game does is initialize the first byte of each entry with the entry itself. During the decompression phase, it can check if the entry was changed (input != dTable[input][0]) and if so, treat the input's entry as a reference and follow it recursively.

The file decompression phase lasts until the specified buffer is filled with decompressed data. The next word after that is assumed to be the new buffer, until the value equals 0, meaning the routine is done.

There are two peculiarities I notices about the function (in case someone ever wants to create a compression routine). First is that the second byte's table is never explicitly reset and is assumed to hold zeroes until changed. Using the opposite case of 

```
							b = br.readByte();
							dTable[ code][1] = b;
						}
```

, i.e. b == code, it's possible to mark an entry as a reference and use the second byte from a previous cycle, potentially causing an endless loop in the unresolved stack later on.

Second is the line  

```
if (br.getOffset() % 4 != 0) br.skip(4 - br.getOffset() % 4);
```

What the game does is load four bytes of data to be processed at once, but since it's difficult to predict when the buffer is filled, not all of these bytes may be used as input (up to 3 wasted inputs). They are not taken over into the next cycle and are discarded (I'm just skipping them). (What's more is that the discarded bytes aren't even zero but possibly some data, yet the game seems to work fine without them)
## Post #5
- Username: azraelaxel
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Mar 24, 2011 10:01 am
- Post datetime: 2013-01-10T04:56:55+00:00
- Post Title: OVL Legend Of Dragoon Format

Thx Forte for your apport really a nice investigation of your part...
## Post #6
- Username: miruss89
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Dec 04, 2016 11:52 pm
- Post datetime: 2016-12-04T15:54:42+00:00
- Post Title: OVL Legend Of Dragoon Format

hi there, is there any news about the ov_ file? and how to decompress it?
