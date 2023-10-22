## Post #1
- Username: omonim2007
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Sep 01, 2018 11:22 pm
- Post datetime: 2018-09-02T02:56:47+00:00
- Post Title: PC Engine Wii VC ROMs - unable to correctly extract

I have a problem extracting PC Engine / TGX-16 ROMs - extracted *.PCE files seems to be kind of encrypted or compressed and doesn't feet to normal No-Intro or GoodPCE ROMs. I'm experienced well in extraction Sega Master System and Sega Mega Drives ROMs - there were any problem for me. The main program for me to extract WADs is ShowMiiWads 1.4 x64.

There are two kind of 00000005.app files in PCE/TG-16 WADs: the ones contains good uncompressed PCE ROMs (matching No-Intro dumps) and the others that contains LZ77xxxxxxx.BIN compressed archives. We'are talking about just the compressed ones. For example I take Adventure Island (Japan) (PCE) (Virtual Console) that contains LZ77N43205GD.BIN ROM file inside of 00000005.app file.

Experienced way, I got the opportunity to unpack this file (I'm using Plombo's lz77.py script from his vcromclaim project) and get the output file with the normal size (262 144 bytes) and normal extension .PCE, but its composition is not similar to any of the known ROMs and it is doesn't run in emulators. It seems to me that I'm using the wrong way for LZ77 decompression or specifically for this platform wee need to use a special unpacker. Maybe you know how to properly decompress these compressed .BIN files?
