## Post #1
- Username: PowerBlade
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Jul 19, 2007 3:37 am
- Post datetime: 2007-07-18T20:08:31+00:00
- Post Title: Compression used in NWN2 protocol

I have a very strange problem with Never Winter Nights 2.
I'm looking at the game protocol, and discovered a lot of packets but 1 sequence is annoying me.
I found out the game uses ZLIB compression and in the zlib.bin, there is an example of a packet using zlib. (The 0x78 0xda)

0000   4d d7 4a 00 01 00 01 0f 00 01 00 c1 7d 02 00 00  M.J.........}...
0010   78 da a4 92 41 0a c2 30 10 45 27 a9 36 6d 76 3d  x...A..0.E'.6mv=
.....


When a client tries to connect to a server, the contents of the servervault is sent to the client in ZLIB compressed format (zlib.bin) I successfully uncompressed this.

What happens next is the client requests detailed info for a single character by sending the name of the character.
The server then responds with 5 packets (packet1 - 5.bin since the packets are > 960 bytes)
The compression format starts with "EC 9c". It reminds me a bit of ZLIB (9c = default compression), but 0xec is not a zlib header..
Any ideas? In front of the EC9C there is a 16 bit file size field.
The packet format is the following for the 5 files

1st.) 4D CCCC PPPP SSSS 0E NPNP 0000 SSSS Data*
2nd.) 4D CCCC PPPP SSSS 08 0000 0000 Data*
3nd.) 4D CCCC PPPP SSSS 08 0000 0000 Data*
4nd.) 4D CCCC PPPP SSSS 08 0000 0000 Data*
5nd.) 4D CCCC PPPP SSSS 08 0000 0000 Data*


CC = CRC
PP = Packet Num
SN = Stream num
NP = Number of packets together
SS = Size of unzipped file


Right in front of the "EC 9C" there is a DWORD containing "D348 0000" which is the size of the decompressed file (18643 bytes)

I know the uncompressed data for sure will contain the following string:
"Not much is known about your history, and you are a closed book to even those who live in your home village. Whatever history you wish to record you may enter here, or let it remain in the past and in your memory alone."
[nwn2.zip](https://xentaxbackup.github.io/file/1274_nwn2.zip)
