## Post #1
- Username: wulfn
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Oct 24, 2015 7:34 am
- Post datetime: 2015-10-24T00:08:04+00:00
- Post Title: [Request] Miscreated (.pak)

Gents,

I've had a look around and understand that Miscreated have some of their pak files encrypted (GameData.pak, Scripts.pak, etc)

If one of you guys could take a look and provide the key and any updated XXTea offsets so i can recompile PakDecrypt I would be grateful!

There didn't appear to be any hasH or crypto detected in the game executable s (I think parts of them are obfuscated with EAC ?)

Found in CrySystem.dll

1- [ CRC32 ] : Offset [ $007B0EC8 ] - VA [ $427B0F09 ]
2- [ Adler32 ] : Offset [ $001082B2 ] - VA [ $421082F3 ]
3- [ Zlib Compression ] : Offset [ $007EA400 ] - VA [ $427EA441 ]
4- [ TEAN ] : Offset [ $0023C79B ] - VA [ $4223C7DC ]
5- [ TEA / xTEA ] : Offset [ $0023C723 ] - VA [ $4223C764 ]
6- [ Hash SHA-256 ] : Offset [ $00427B4C ] - VA [ $42427B8D ]
7- [ Hash SHA-384 ] : Offset [ $00427FDB ] - VA [ $4242801C ]
8- [ Twofish ] : Offset [ $007FF8E0 ] - VA [ $427FF921 ]
9- [ Hash MD5 ] : Offset [ $004186D7 ] - VA [ $42418718 ]
10- [ Hash SHA-1 ] : Offset [ $0042A254 ] - VA [ $4242A295 ]
11- [ Zip Encryption ] : Offset [ $005B468C ] - VA [ $425B46CD ]

I have included;-

Scripts.pak
Miscreated.exe (the one found in bin64 not the EAC launcher)
CrySystem.dll

```
http://www.mediafire.com/download/xo77kjbkx9mdh2r/Game_Files.zip
```
## Post #2
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2016-09-23T11:32:32+00:00
- Post Title: [Request] Miscreated (.pak)

I realise this is nearly a year old now, but with the game getting a proper release soon, and the models inside looking better and better, I'd love to take a look at some of them up close...
