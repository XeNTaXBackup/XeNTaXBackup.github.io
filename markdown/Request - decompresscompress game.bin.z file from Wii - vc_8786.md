## Post #1
- Username: srcorsario
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Aug 16, 2010 11:08 pm
- Post datetime: 2012-04-18T16:38:19+00:00
- Post Title: Request - decompress/compress game.bin.z file from Wii - vc

Hello!!!
This project its about to decompress and then compress again a file from a Virtual Console game (wii)
The file come from the last Virtual Console NEOGEO game realised last tuestday (Metal Slug 3)
The purpouse is repack the file with another unrealised game (is called "injection") as i did timeee ago.


I did a very similar request with the same file name. On this thread -->([viewtopic.php?t=4906](http://forum.xentax.com/viewtopic.php?t=4906))

(last time it was used "Simplyzip" with option "External progs"-->Zlib (pack/unpack) or Xpert 2.0 tool decompres/compress it) An "extrange" type of zlib compression


Now It has just appear a new compression type (for me) and im not able to decompress it.

Information:

-File name game.bin.z
-Size 35.732.788bytes
-Start with "header" 43 52 .. .. .. 
[](http://imageshack.us/photo/my-images/441/gamebinz.jpg/)


-End with:
[](http://imageshack.us/photo/my-images/171/gamebinzend.jpg/)


-Suppose:

               *-Supposed extracted size 93.192.256 bytes (the sum of header+game file+bios)

               *-The result of file extraction allways was a single file, for instance i suppose it will be the sema.
                    If not, it could have:
                                  Header: 64bytes (used to be) 
                                  M file:524.288 bytes (original neogeo game file) 
                                  S file:262.144 bytes (original neogeo game file)
                                  V file(s):16.777.216 byte (original neogeo game file)
                                  C file(s):67.108.864 bytes (modified original neogeo game file )
                                  P file(s):8.388.608 bytes (modified original neogeo game file)
                                  Bios: 131.072 bytes (a special bios for this purpose) "similar" to a regular neogeo bios

                *-The old extructure of the extracted file used to be: (the file we want to obtain)
                              *Header (64bytes) with a list of file sizes or offset where they start (depends on versions)
                              *Game files (all joined one after another, thats the reason of the header)
                              *Bios (131.072 bytes), on lastest version not necesary at the end of the file

-Original file: (34Mb aprox)
[http://uppit.com/4mg45xu0gc37/game.bin.z](http://uppit.com/4mg45xu0gc37/game.bin.z)


-Split first 2MB
[http://uppit.com/izo0oe2gy5sp/(Ini_file)game.bin.z](http://uppit.com/izo0oe2gy5sp/%28Ini_file%29game.bin.z)

-Split last 2Mb
[http://uppit.com/d8akec1as03u/(end_file)game.bin.z](http://uppit.com/d8akec1as03u/%28end_file%29game.bin.z)


Thanks in advance
## Post #2
- Username: srcorsario
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Aug 16, 2010 11:08 pm
- Post datetime: 2012-04-19T15:02:15+00:00
- Post Title: Request - decompress/compress game.bin.z file from Wii - vc

Anyyy idea????

Thanks in advance!
## Post #3
- Username: srcorsario
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Aug 16, 2010 11:08 pm
- Post datetime: 2012-04-22T14:23:53+00:00
- Post Title: Request - decompress/compress game.bin.z file from Wii - vc

Acording with file header, "43 52 30 30" it could be variant of CRUSH compression. "cr00" 

CRUSH compression as description : "Powerful LZ featuring extremely fast decompression" (LZ77)

Moreover, nintendo used many times diferents LZ compresion types.

Font:

> http://encode.narod.ru/
>
> http://encode.narod.ru/crush001.zip

Anyone could help on this project???

Thanks in advance


Edit:

I have good news... The original "rom" from mslug 3 is encrypted, for this reason compressor programs cant get a good ratio... AFTER decrypt them (S file and C files) the compression rate (with a LZ compressor or winrar) is very similar to our game.bin.z Thats a good new
## Post #4
- Username: srcorsario
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Aug 16, 2010 11:08 pm
- Post datetime: 2012-04-23T19:22:33+00:00
- Post Title: Request - decompress/compress game.bin.z file from Wii - vc

I tried with quickbms "comtype_scan2.bat"/"comtype_scan2.bms" but didnt get a good reasold :'(

I dont know how to use "encryption_scan" it need a key or something similar... any help¿?¿?¿?


Any suggestion¿?¿?¿?


Pleeeeeeaseeee!!!

EDit:

I got the answer how to use encryption_scan ... I need the key...
## Post #5
- Username: srcorsario
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Aug 16, 2010 11:08 pm
- Post datetime: 2012-04-24T17:05:34+00:00
- Post Title: Request - decompress/compress game.bin.z file from Wii - vc

DISASTER !!!

Having a look into 1.app I found this, where we can read "REX-PPC 2.4.2 55.0 (RevoEX-2.4)" and NETLockCrypto etc etc 

[](http://imageshack.us/photo/my-images/196/1apppart1.jpg/)

And this... where i think its making reference to game.bin.z file because "CR00" is the file header  and then ... "NETAESDecryp"  

[](http://imageshack.us/photo/my-images/593/1apppart2.jpg/)



DISASTER if game.bin.z is compressed with password/key


Obviouslly i looked for this values in a "old" 1.app and didnt appear!!  

Heelpppp!!!
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-06-15T02:55:06+00:00
- Post Title: Request - decompress/compress game.bin.z file from Wii - vc

the files have the CR00 magic at the beginning and the rest is encrypted with AES using a key and an ivec.
looks like both are generated for each file... don't know.
anyway even after decrypting the file (the key is correct but it's not that easy to debug) the content means nothing.

if someone is interested the following was my work-in-progress test script for Shock Troopers:

```
#getdstring IVEC 0x10   # ivec or hash or what?
savepos OFFSET
get SIZE asize
math SIZE -= OFFSET
encryption aes "\x88\x2A\x16\xFB\x4E\x08\xD9\x9C\x19\x2D\x98\x68\xEB\xA3\xB7\x99" "\xF4\xC1\x23\xF2\xF3\xAD\x49\xA1\xC3\xC7\xD4\xB1\xE2\x91\x65\x2D"
# "\xD1\xF4\x55\xF2\x0F\x10\x5D\x8A\x0C\x8C\xD3\xFA\x56\x32\x30\xE5" ivec xored with first 16 bytes?
log "test.dat" OFFSET SIZE
```
or
```
getdstring IVEC 0x10
savepos OFFSET
get SIZE asize
math SIZE -= OFFSET
set IVECX binary "\xD1\xF4\x55\xF2\x0F\x10\x5D\x8A\x0C\x8C\xD3\xFA\x56\x32\x30\xE5"
string IVEC ^= IVECX
encryption aes_128_cbc "\x88\x2A\x16\xFB\x4E\x08\xD9\x9C\x19\x2D\x98\x68\xEB\xA3\xB7\x99" IVEC
log "test.dat" OFFSET SIZE
```
so nothing is finished and I'm not interested in this thing
## Post #7
- Username: srcorsario
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Aug 16, 2010 11:08 pm
- Post datetime: 2012-06-15T10:58:05+00:00
- Post Title: Request - decompress/compress game.bin.z file from Wii - vc

Thanks for your help and for answering.
