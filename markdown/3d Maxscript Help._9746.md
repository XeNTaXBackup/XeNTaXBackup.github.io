## Post #1
- Username: ptowery
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Aug 19, 2011 6:56 am
- Post datetime: 2012-10-16T04:27:28+00:00
- Post Title: 3d Maxscript Help.

Hello, it's my first time trying to crack a model format on my own and since I use 3ds max a lot, I thought I'd use maxscript to read the format. I have the header and block definitions/offsets/sizes for the file but I don't know where to go from there because I keep looking for vertex floats and they are all too long for vertex coordinates. Can someone give me some advice on what I should be looking for or doing at this step; or better yet walk me through this format. From what I can tell it's pretty simple? Thanks for reading.



```
-- _____________________________________________________________________
--																															|
--											File Header Loading														|
--																															|
fileMagic=readBElong f					--File Magic 		(seen in every Halo Wars Format) |
fileHeaderLength=readBElong f		--Header Length 	(always 32?)							|	Header is 32 Bytes long
readBElong f --unknown					--UNKNOWN														|
fileSize=readBElong f					--File Size in Bytes												|	113024
fileBlocks=readBEshort f 				--Number of Blocks												|	5
readBEshort f --unknown	nil				--UNKNOWN Null											|
readBElong f --unknown					--UNKNOWN														|
readBElong f --unknown nil				--UNKNOWN Null												|
clearlistener()	--																									|
print ("File Header Length is " + fileHeaderLength as string)	--							|
print ("File Size is " + fileSize as string + " Bytes")--											|
print ("File has " + fileBlocks as string + " Blocks")--											|
-- _____________________________________________________________________|

fseek in_file fileHeaderLength #seek_set
readBElong f --what the -----

-- Load UGX File Block Definition 1
-- _______________________________________________________________________________
--																																			|
--											File Block Def Loading (1/fileBlocks)												|  Block Definitions are 24 Bytes long
--																																			|  Alligned to 20?
readBElong f--unknown						--UNKNOWN Null 															|
fileBckdType=readBElong f				--Block Type 																	|	
fileBckdOffset=readBElong f			--Block Offset																	|
fileBckdSize=readBElong f				--Block Size																	|
readBElong f --unknown						--UNKNOWN																	|
readBElong f --unknown						--UNKNOWN																	|
print ("Block Type is " + fileBckdType as string)	--																|
print ("Block Offset points to " + fileBckdOffset as string + ". This shouldn't be zero.")--	|
print ("Block Size is " + fileBckdSize as string + " Bytes")--												|
-- ______________________________________________________________________________|
```


That's the loading part of my max script and it appears to load this Big endian file correctly.
