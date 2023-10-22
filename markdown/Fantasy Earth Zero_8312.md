## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-17T07:12:00+00:00
- Post Title: Fantasy Earth Zero

Models are mdl files.
Textures stored in tex files. A single tex file may contain multiple textures. Materials index into the texture file.
The tex filename is the same as the model filename.

It is a typical chunk based format.
You have the tag, followed by chunk size, followed by two integers, followed by the rest of the data.

So for example if you have the VTX0 vertex chunk, it'll be followed by the chunk size, the numVerts, and a 0, followed by the vertex buffer.

Unfortunately, some of the chunks have extra padding at the end which is not included in the chunk size.
I have not figured out how this works, so I can't write a general parser and have to parse each chunk manually, then run some silly function to skip the potential padding. Would be nice if there was a way to determine whether there's padding ahead of time so I can ignore all this manual parsing and just parse it like a proper chunk-based format.



Script permalink: [http://db.tt/4nOiIdl4](http://db.tt/4nOiIdl4)
Client DL: available on [wiki](http://wiki.xentax.com/index.php/Game_Clients)

bms unpacker:

```
get UNK long 
for i = 0 < FILES 
get NSIZE short 
getdstring NAME NSIZE 
get OFFSET long 
get SIZE long 

log NAME OFFSET SIZE 
next i  
```

[Fantasy Earth Zero.7z](https://xentaxbackup.github.io/file/5076_Fantasy Earth Zero.7z)
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-02-17T12:00:08+00:00
- Post Title: Fantasy Earth Zero

its just padded to 16 bytes.
[http://en.wikipedia.org/wiki/Data_structure_alignment](http://en.wikipedia.org/wiki/Data_structure_alignment)
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-17T17:42:04+00:00
- Post Title: Fantasy Earth Zero

Oh, I see it.
Lol no more silly hacking-around code.

Alright updated script to incorporate struct alignment.
It should properly skip things now, unless someone sees something wrong with this algorithm:

```
	'''Return the amount of padding left to read'''

	padSize = size
	if size % 16 != 0:
			padSize = size + (16 - (size % 16))
			
	#calculate current position relative to start of chunk
	relativeOfs = self.inFile.tell() - start

	#calculate the amount of bytes remaining in the chunk
	remain = padSize - relativeOfs
	self.inFile.seek(remain, 1)

```


Or whether there is a faster way to deal with it.
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-23T21:08:27+00:00
- Post Title: Fantasy Earth Zero

Script updated to load the rest of the models (rooms and monsters).

It was just a different vertex type (52 bytes vs 56 bytes)
## Post #5
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-02-23T21:52:18+00:00
- Post Title: Fantasy Earth Zero

your code looks fine you could simplify it by just getting your current pos to 16 and skip if not 0 just makes it one line but i doubt you will see any noticeable speed difference.
## Post #6
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-02-23T22:20:11+00:00
- Post Title: Fantasy Earth Zero

Faster way to pad to 16.

(pos + 0xF)  & ~0xF
## Post #7
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-23T22:55:25+00:00
- Post Title: Fantasy Earth Zero

What's that ~ ? Not?
## Post #8
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-02-23T23:37:27+00:00
- Post Title: Fantasy Earth Zero

Actually negate. Do the bit math to see why it works. It zeroes the lowest 4 bits. Also called bitwise negate, bitwise not, or bitwise complement.
## Post #9
- Username: craver
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Nov 07, 2013 1:46 pm
- Post datetime: 2013-11-13T06:36:09+00:00
- Post Title: Fantasy Earth Zero

I hope I can rip this game model... nice thread, very thanks
## Post #10
- Username: Bringbackfez
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Sep 04, 2014 12:22 am
- Post datetime: 2014-09-04T18:26:55+00:00
- Post Title: Fantasy Earth Zero

Seeking all & any info pertaining to Fantasy earth Zero. We are a movement bringing back Fantasy Earth zero & lookin g to start a private server. We are aware that Gamepot gave up rights to the NA version Gamania etc & looking for server files.
## Post #11
- Username: sunny710
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Jul 05, 2015 10:51 pm
- Post datetime: 2022-10-30T15:10:55+00:00
- Post Title: Fantasy Earth Zero

Could you reupload the script?
Great thanks!
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-10-30T16:03:23+00:00
- Post Title: Fantasy Earth Zero

Simply use the Noesis Plugins link in finale00*s sig to get FantasyEarthZero_mdl plugin.
