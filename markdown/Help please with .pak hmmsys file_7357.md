## Post #1
- Username: CymineVatera
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Sep 14, 2011 7:53 pm
- Post datetime: 2011-09-14T12:11:39+00:00
- Post Title: Help please with .pak hmmsys file

hello everyone can anyone please give me a bms script for extracting .Pak HMMSYS files
for my GameExtractor

these files originally belongs to a pc game called rising kingdoms i really could use of your help thank you all ^_^  

PAK
---------------------------------------
Format Type : Archive 
Endian Order : Little Endian 

Format Specifications
char {16}    - Header ("HMMSYS PackFile" + (byte)10) 
uint32 {4}   - Unknown (26) 
byte {12}    - null 
uint32 {4}   - Number Of Files? 
uint32 {4}   - Directory Length [+40 archive header] 

// for each file 
byte {1}     - Filename Length 
byte {1}     - Previous Filename Reuse Length 
char {X}     - Filename Part (length = filenameLength - previousFilenameReuseLength) 
uint32 {4}   - File Offset 
uint32 {4}   - File Length 

byte {X}     - Padding (repeating 153,121,150,50) until first file offset 
byte {X}     - File Data 


originally was taken from here, links are below)

[http://wiki.xentax.com/index.php/Rising_Kingdoms](http://wiki.xentax.com/index.php?title=)
## Post #2
- Username: invisghost
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Jul 14, 2010 2:16 am
- Post datetime: 2011-09-15T21:47:37+00:00
- Post Title: Help please with .pak hmmsys file

Wrong place to post this in.
## Post #3
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-09-24T00:42:19+00:00
- Post Title: Help please with .pak hmmsys file

upload a small sample file. the format description is confusing.
