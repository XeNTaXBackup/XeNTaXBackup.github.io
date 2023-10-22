## Post #1
- Username: ehnoah
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Feb 29, 2012 6:21 am
- Post datetime: 2012-02-28T22:28:12+00:00
- Post Title: ArcheAge Online

Hey,

I searching help for a new upcoming MMO to open the PAK File.

The File is renamed by launcher to "game_pak"  and it is ~ 18 GB big.

I want to open the Archive to translate the game to my native language 

So if someone can maybe help me? 

Thank's!
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-02-28T23:15:56+00:00
- Post Title: ArcheAge Online

Cute ~2mb with File Cutter (attached)
[FileCutter.rar](https://xentaxbackup.github.io/file/5117_FileCutter.rar)
## Post #3
- Username: ehnoah
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Feb 29, 2012 6:21 am
- Post datetime: 2012-02-28T23:37:46+00:00
- Post Title: ArcheAge Online

I think I should upload it so here I have:

It is cutted to 2 Mbit.

[http://ul.to/kpf9tcpo](http://ul.to/kpf9tcpo)
## Post #4
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-02-28T23:52:49+00:00
- Post Title: ArcheAge Online

Hm PE file. It's setup or all pack's (resource) stored in main exe
## Post #5
- Username: ehnoah
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Feb 29, 2012 6:21 am
- Post datetime: 2012-02-29T06:37:00+00:00
- Post Title: ArcheAge Online

Hey,

Shall I upload ArcheAge.exe + DDL's too?

Sorry I am not a real pro 
I am very happy that you help me
## Post #6
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-02-29T07:37:14+00:00
- Post Title: ArcheAge Online

I downloading client now.
## Post #7
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-02-29T18:59:31+00:00
- Post Title: ArcheAge Online

So some table, strings contained in SQLite format 3.

```
"game\db\game.sqlite3"
```


File encrypted with AES-128-CFB -> xlcommon.dll

```
void __cdecl aes_crypt_cbc_signed(struct aes_context *,int,int,char * const,char const *,char *)
void __cdecl aes_crypt_cfb128(struct aes_context *,int,int,int *,unsigned char * const,unsigned char *,unsigned char *)
void __cdecl aes_crypt_ecb(struct aes_context *,int,unsigned char * const,unsigned char * const)
void __cdecl aes_setkey_dec(struct aes_context *,unsigned char *,int)
void __cdecl aes_setkey_dec_signed(struct aes_context *,char const *,int)
void __cdecl aes_setkey_enc(struct aes_context *,unsigned char *,int)
void __cdecl aes_setkey_enc_signed(struct aes_context *,char const *,int)
```


functions obfuscated.

If someone manages to come somehow miraculously pull the keys here is the ecrypted [game.sqlite3](http://www.mediafire.com/?tdfzg5uzb0wsti0)
## Post #8
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-02-29T21:19:30+00:00
- Post Title: ArcheAge Online

why don't you put a breakpoint on aes_setkey_dec when the game starts?
the raw alternative is placing the byte 0xcc with a hex editor and then waiting the popup of the debugger
## Post #9
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-03-01T11:28:16+00:00
- Post Title: ArcheAge Online

I do not have enough time for reversing. aluigi maybe can look  ?
Binaries [here](http://www.mediafire.com/?4kvny44qpc349ky) + removed HSHield which prevents debugging.
PS: Worked without game.pak

Open "Bin32\archeage.exe"
F9 (Run)
F12 (Pause)
CTRL+G (for following address 33014D50 (aes_setkey_dec))
F2 (Breakpoint)
F9 (Run)
## Post #10
- Username: ehnoah
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Feb 29, 2012 6:21 am
- Post datetime: 2012-03-01T11:41:01+00:00
- Post Title: ArcheAge Online

Exe is Themidia locked too.
## Post #11
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-03-01T11:43:03+00:00
- Post Title: ArcheAge Online

Game binaries not packed, packed only HSHield modules (Themida)
## Post #12
- Username: ehnoah
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Feb 29, 2012 6:21 am
- Post datetime: 2012-03-01T15:38:52+00:00
- Post Title: ArcheAge Online

Edited
## Post #13
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-03-01T18:10:35+00:00
- Post Title: ArcheAge Online

@Ekey
you have a working environment (here doesn't work) and you have already done everything.
there is nothing to reverse, when the debugger breaks take a look at argument 2 and 3 of the stack:
- the first is the key
- the second is the length of the key (probably multiplied by 8)
## Post #14
- Username: ehnoah
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Feb 29, 2012 6:21 am
- Post datetime: 2012-03-01T19:16:50+00:00
- Post Title: ArcheAge Online

Hey,

i am a real noob but:

I step over from this Point out and that I get:

ARG 3 = 80

Stack (0018E9c8) = 00040002
ECX=00000080 (decimal 128.)


ARG 2 = x2game.8982F9AC

Stack (0018E9C4) = 0
EAX=x2game.3982F9AC  (I goed to x2game at 3982F9AC = Imm=04)

ARG 1 = 10E9D4

Stack (0018E9C0)=06CF0B88
ECX=0018E904


hope this help 's *g*
## Post #15
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-03-01T21:53:07+00:00
- Post Title: ArcheAge Online

I hope this is what you need

[http://img62.imageshack.us/img62/1862/aeskeys.png](http://img62.imageshack.us/img62/1862/aeskeys.png)

used the reading pack

AES_SETKEY_DEC and "\x1F\xD3\xFC\xAD\xCE\x70\xDF\x51\x72\x3A\x9E\x5F\x1E\x52\x07\x11\x1C\xD3\x12\xBC\xE3\x51\x08\x7E\xAC\x69\xDF\xFE\xF5\xBE\x18\x70"

[http://img828.imageshack.us/img828/2880 ... empak1.png](http://img828.imageshack.us/img828/2880/crysystempak1.png)
[http://img710.imageshack.us/img710/939/ ... empak2.png](http://img710.imageshack.us/img710/939/crysystempak2.png)
[http://img94.imageshack.us/img94/3084/crysystempak3.png](http://img94.imageshack.us/img94/3084/crysystempak3.png)
[ENC_DEC_KEYS.rar](https://xentaxbackup.github.io/file/5133_ENC_DEC_KEYS.rar)
## Post #16
- Username: ehnoah
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Feb 29, 2012 6:21 am
- Post datetime: 2012-03-02T06:44:17+00:00
- Post Title: Re: ArcheAge Online

> Reply from Ekey
>
> I hope this is what you need

http://img62.imageshack.us/img62/1862/aeskeys.png

used the reading pack

AES_SETKEY_DEC and "\x1F\xD3\xFC\xAD\xCE\x70\xDF\x51\x72\x3A\x9E\x5F\x1E\x52\x07\x11\x1C\xD3\x12\xBC\xE3\x51\x08\x7E\xAC\x69\xDF\xFE\xF5\xBE\x18\x70"

http://img828.imageshack.us/img828/2880 ... empak1.png
http://img710.imageshack.us/img710/939/ ... empak2.png
http://img94.imageshack.us/img94/3084/crysystempak3.png

Can someone "translate" me to use it with open SSL? 

I want to learn to make this self.
## Post #17
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-03-02T09:16:00+00:00
- Post Title: Re: ArcheAge Online

the key is "\x32\x1F\x2A\xEE\xAA\x58\x4A\xB4\x9A\x6C\x9E\x09\xD5\x9E\x9C\x6F", it's just the one said by the code at offset 36607EE0 of crysystem.dll.

about openssl, quickbms already implements everything indeed you can test it using a simple script like the following (check quickbms.txt for all the available algorithms of the Encryption command):

```
get SIZE asize
log "dump.dat" 0 SIZE
```

BUT don't be happy because the key is probably not for game.sqlite3 so it's totally useless
## Post #18
- Username: ehnoah
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Feb 29, 2012 6:21 am
- Post datetime: 2012-03-02T10:01:43+00:00
- Post Title: Re: ArcheAge Online

I used but It seem's not to be work as you told 

Reverse Engeneering seems realy hard  I just want to translate =(
## Post #19
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-03-02T11:39:40+00:00
- Post Title: Re: ArcheAge Online

> Reply from aluigi
>
> the key is "\x32\x1F\x2A\xEE\xAA\x58\x4A\xB4\x9A\x6C\x9E\x09\xD5\x9E\x9C\x6F", it's just the one said by the code at offset 36607EE0 of crysystem.dll.

about openssl, quickbms already implements everything indeed you can test it using a simple script like the following (check quickbms.txt for all the available algorithms of the Encryption command):
Code: Select allencryption aes "\x32\x1F\x2A\xEE\xAA\x58\x4A\xB4\x9A\x6C\x9E\x09\xD5\x9E\x9C\x6F"
get SIZE asize
log "dump.dat" 0 SIZE
BUT don't be happy because the key is probably not for game.sqlite3 so it's totally useless
It's key for File Table  (Yesterday i dump memory region 39MB after read pak file).

Before using script



After using script



Dumped table [here](http://www.mediafire.com/?44ecajqa4cohdb1)
## Post #20
- Username: ehnoah
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Feb 29, 2012 6:21 am
- Post datetime: 2012-03-02T12:09:44+00:00
- Post Title: Re: ArcheAge Online

So I can use this tkey on the GAME_PAK  file and extract them?
## Post #21
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-03-02T12:48:21+00:00
- Post Title: Re: ArcheAge Online

> Reply from ehnoah
>
> So I can use this tkey on the GAME_PAK  file and extract them?
Nope.

Decrypting DB sqlite3 files -> x2game.dll -> 39598960

Already decrypted [here](http://www.mediafire.com/?k3i7ismmu5tt9up)
## Post #22
- Username: ehnoah
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Feb 29, 2012 6:21 am
- Post datetime: 2012-03-02T13:33:20+00:00
- Post Title: Re: ArcheAge Online

Hey,

thank's for all.

Can you or someone else make me an Little Tutorial how to read the AES Key out?

I know now how to set Breakpoint. And then Follow in Dump I think.
But i am not realy sure what exactly do to read the key out.

And is maybe someone here able to extract the Game_PAK. I need to repack my File (the sqlite3 File) back in Game.

So if someone can help me. Or make an "Work Arround" with Inject etc dunno. Then Please help me.

PS: Every day / secound day Patch come out so exe change every Day I think.

Dunno if this is a "big" problem?

Thank's
## Post #23
- Username: ehnoah
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Feb 29, 2012 6:21 am
- Post datetime: 2012-03-02T21:30:14+00:00
- Post Title: Re: ArcheAge Online

Hey,

I decrypted the GAME_PAK. I don't know realy how but.

I deleted the File. And with "File Recover" I found now Files in a "Game" Folder....

Called Folder: world -> Main_world -> Instance_burntcastle_amory etc.

Anyone know how I decrypted?

PS: I could open the Game_PAK like a Folder. So maybe the PAK file is not a PAK File?

I created an Folder who called "game.pak" Game renamed him to "Game_PAK" and deleted the "GAME_PAK" FILE.
## Post #24
- Username: psychopigeon
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Mar 08, 2012 4:24 pm
- Post datetime: 2012-03-08T08:26:46+00:00
- Post Title: Re: ArcheAge Online

Hi

Would it be possible for you to PM me if you could extract the soundtrack?

I have been successful at opening up the text files using the decrypt files mentioned in this thread however it doesn't really enable you to do anything such as extract soundtrack.

I tried what you did, deleting the file then using a recover tool to bring it back but it never found it
## Post #25
- Username: Emir
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Mar 10, 2010 5:37 pm
- Post datetime: 2012-04-04T11:55:02+00:00
- Post Title: Re: ArcheAge Online

Hello

How to unpack ArcheAge game.pak ?

Help me please
## Post #26
- Username: Buemo
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Jul 01, 2012 5:02 am
- Post datetime: 2012-07-01T10:28:05+00:00
- Post Title: Re: ArcheAge Online

Hello.
Please help me.  
I don't know, as decrypt file game.pak
Please example code for decrypt game.pak in quickbms.
## Post #27
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-07-03T18:01:37+00:00
- Post Title: Re: ArcheAge Online

All info about decrypting you can read the above. I assume that the key might have changed in current CBT or OBT.
## Post #28
- Username: Buemo
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Jul 01, 2012 5:02 am
- Post datetime: 2012-07-11T19:52:02+00:00
- Post Title: Re: ArcheAge Online

> Reply from Ekey
>
> I hope this is what you need

http://img62.imageshack.us/img62/1862/aeskeys.png

used the reading pack

AES_SETKEY_DEC and "\x1F\xD3\xFC\xAD\xCE\x70\xDF\x51\x72\x3A\x9E\x5F\x1E\x52\x07\x11\x1C\xD3\x12\xBC\xE3\x51\x08\x7E\xAC\x69\xDF\xFE\xF5\xBE\x18\x70"

http://img828.imageshack.us/img828/2880 ... empak1.png
http://img710.imageshack.us/img710/939/ ... empak2.png
http://img94.imageshack.us/img94/3084/crysystempak3.png

Ekey, how use this files?   
Thanks.
## Post #29
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-07-11T21:51:33+00:00
- Post Title: Re: ArcheAge Online

What files? It's outdated info.
## Post #30
- Username: Buemo
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Jul 01, 2012 5:02 am
- Post datetime: 2012-07-12T02:29:52+00:00
- Post Title: Re: ArcheAge Online

> Reply from Ekey
>
> What files? It's outdated info.

Well [download/file.php?id=5133](http://forum.xentax.com/download/file.php?id=5133)
How you decrypt game.pak please example. 
Thanks
## Post #31
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-07-12T16:26:33+00:00
- Post Title: Re: ArcheAge Online

> Reply from Buemo
>
> How you decrypt game.pak please example.
No ideas. All info here for CBT3 client. Current version CBT5. PAK format and encryption could be changed.
## Post #32
- Username: ehnoah
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Feb 29, 2012 6:21 am
- Post datetime: 2012-08-06T12:49:15+00:00
- Post Title: Re: ArcheAge Online

You will help me / us again to decrypt CBT5 Client?

We would of curse give you what we can
## Post #33
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-06T13:04:16+00:00
- Post Title: Re: ArcheAge Online

It's posible but need full client. I do not know where download. Official site does not load (IP Block ?) As far as I can remember full size client ~ 27gb
## Post #34
- Username: ehnoah
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Feb 29, 2012 6:21 am
- Post datetime: 2012-08-06T13:43:21+00:00
- Post Title: Re: ArcheAge Online

We will link you the Client as soon as possible he is out.

We realy thank you for your great support.
## Post #35
- Username: iaw
- Rank: advanced
- Number of posts: 52
- Joined date: Wed Oct 21, 2009 7:52 pm
- Post datetime: 2012-08-14T09:17:12+00:00
- Post Title: Re: ArcheAge Online

client:

> http://download-xlgamesdn.x-cdn.com/cbt ... cheAge.exe
>
> http://download.xlgames.gscdn.com/cbt5/ ... cheAge.exe
>
> http://cdnet.archeage.com/cbt5/install/ ... cheAge.exe
## Post #36
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-14T13:51:20+00:00
- Post Title: Re: ArcheAge Online

This basic info:

Header - Full Size = 0x2e0

Header data begin offset -0x200 (size - 0x20) from end of file and encrypted. You need decrypt hem. After decrypt 

```
4 Bytes - Nulls
4 Bytes - Total Files
4 Bytes - Unknown
```

File Table
Size: (Total Files + Unknown * 0x150)
Offset:  (PAK SIZE - Table Size + Header Size)

Each entry size = 0x150

```
4 Bytes - Offset
4 Bytes - Nulls
4 Bytes - Size
4 Bytes - Nulls
4 Bytes - Size Again
4 Bytes - Nulls
4 Bytes - Compressed Size
16 Bytes - Maybe CheckSum (md5 or like)
4 Bytes - Nulls
16 Bytes - Again Maybe CheckSum (md5 or like)
8 Bytes - Nulls

```

[http://img267.imageshack.us/img267/9601/pakm.png](http://img267.imageshack.us/img267/9601/pakm.png)

```
get SIZE asize
log "decrypted.dat" 0 SIZE
```

[Here](http://www.mediafire.com/?zv54oq1k57but5e) filetable and sql base from CBT5. Some filenames not correct decrypted.

Note: Encrypted only FileTable.
## Post #37
- Username: iaw
- Rank: advanced
- Number of posts: 52
- Joined date: Wed Oct 21, 2009 7:52 pm
- Post datetime: 2012-08-15T11:10:48+00:00
- Post Title: Re: ArcheAge Online

> Some filenames not correct decrypted

Only decryption 0x150 can filename correctly
## Post #38
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-15T12:47:06+00:00
- Post Title: Re: ArcheAge Online

> Reply from iaw
>
> Only decryption 0x150 can filename correctly
Yeah I already figured out.
## Post #39
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-08-15T15:37:13+00:00
- Post Title: Re: ArcheAge Online

why not starting to put some bms code on the thread?
I don't have files to test so I have simply followed what I have understood, correct everything you see wrong:

*edit*
new scripts in the next posts
## Post #40
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-15T16:15:28+00:00
- Post Title: Re: ArcheAge Online

All files not compressed only sqlite3 need uncompress after decrypt (used other AES key). Check script later.
## Post #41
- Username: ehnoah
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Feb 29, 2012 6:21 am
- Post datetime: 2012-08-15T16:24:19+00:00
- Post Title: Re: ArcheAge Online

Can you get a working tool to decrypt the the Sqlite3 File?

As I PMd it is ok to use OllyDBG but maybe we can get a Decrypter for this File working
## Post #42
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-15T19:05:37+00:00
- Post Title: Re: ArcheAge Online

Yep. Just need search correct key.

@aluigi

```
             <get OFFSET (1) 0x02d17200
             <get OFFSET (1) 0x02d17200
             >set OFFSET (1) to 0xfffffffffd2e8e00

5383f8c00 2b  28  callfunction DECRYPT 1
             .start_bms start: 35 0 0

5383f8c00 26  49  encryption aes_128_cbc "\x32\x1F\x2A\xEE\xAA\x58\x4A\xB4\x9A\x
6C\x9E\x09\xD5\x9E\x9C\x6F"
- variable "aes_128_cbc" seems uninitialized, I use its name
             <get aes_128_cbc (16) "aes_128_cbc"
- encryption with algorithm aes_128_cbc and key of 16 bytes

5383f8c00 0b  50  log MEMORY_FILE OFFSET SIZE
             <get MEMORY_FILE (17) "MEMORY_FILE"
             <get OFFSET (1) 0xfffffffffd2e8e00
             <get SIZE (2) 0x02d16f20
- create a memory file from offset fffffffffd2e8e00 of 47279904 bytes

Error: the offset 0xfffffffffd2e8e00 in the file 0 can't be reached
```
## Post #43
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-08-15T19:09:02+00:00
- Post Title: Re: ArcheAge Online

script fixed, let me know the other problems
## Post #44
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-15T19:27:21+00:00
- Post Title: Re: ArcheAge Online

Incorrect offset again. Taken offset from begin file, not from the end.

```
             <get MEMORY_FILE (17) "MEMORY_FILE"
             <get OFFSET (1) 0x356e0af0
             <get SIZE (2) 0x02d16f20
- create a memory file from offset 356e0af0 of 47279904 bytes
```
## Post #45
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-08-15T19:43:05+00:00
- Post Title: Re: ArcheAge Online

seriously I don't understand.

in the specifications about the file table you wrote:

> Offset: (Total Files * 0x150 + 0x3D0)
>
> from end of file and it also encrypted.and indeed my script does:

```
math OFFSET -= SIZE # less the size of the table
math OFFSET -= 0x3d0 # less 0x3d0 (0x200 of header plus something else I guess)
```

so where is located the filetable?
and is it encrypted in with the usual key?
## Post #46
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-15T19:45:55+00:00
- Post Title: Re: ArcheAge Online

My bad (forgot edit post)

TableOffset need take PAK Size (22418525696 bytes) and minus TotalFiles * 0x150
## Post #47
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-08-15T19:48:24+00:00
- Post Title: Re: ArcheAge Online

are you sure I don't need to remove also 0x200 of the header to get the correct offset?
I mean: offset = pak_size - (files * 0x150) - 0x200

because if I do only "pak_size - (files * 0x150)" then we have an overlapping of the last 2 entries
## Post #48
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-15T20:53:34+00:00
- Post Title: Re: ArcheAge Online

Ok. Let's do it again because after patсh there some changes:

Full Header Size = (2e0)
Encrypted Data offset same = -0x200
Encrypted Data size = 0x20

In decrypted header after total files is now unknown value = 13 (0xD) (before patch this value = 0)

```
Total Files in PAK = 140701 (2259D) + Unknown (0xD)

Correct Table Offset : 5356e1c00 (22371245056) - from begin file or 02d16f20 (47279904) from end.
Correct Table Size : 02d16f20 (47279904)
```

Get Table Size:
Total Files (2259D) + Unknown (0xD) * 0x150 = 2d16f20 (<- This value can also be used as an offset from end of file for Table Offset)

Get Table Offset: from begin of file
PAK Size (5383f8e00) - Table Size (2d16f20) = 5356e1ee0 + Full Header Size (2e0) = 5356e21c0

[http://img809.imageshack.us/img809/971/23997401.png](http://img809.imageshack.us/img809/971/23997401.png)

All rechecked!
## Post #49
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-08-15T21:05:26+00:00
- Post Title: Re: ArcheAge Online

well done, I have updated the script and verified all the values using those you gave me as example.

just as hypothesis, do you think 0x2e0 may be related to that new value?
like 0x2e0 = (0xd * 0x38) + 8
probably we need to wait the next versions of the game to know the answer :)
## Post #50
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-15T21:17:40+00:00
- Post Title: Re: ArcheAge Online

> Reply from aluigi
>
> well done

```
  expected by the script:

  this one: "аУQ_"
  a0 93 51 5f                                       ..Q_

  expeceted: "WIBO"
  57 49 42 4f                                       WIBO
```


:}

> Reply from aluigi
>
> 
just as hypothesis, do you think 0x2e0 may be related to that new value?
like 0x2e0 = (0xd * 0x38) + 8
probably we need to wait the next versions of the game to know the answer

I'm just a beginner in reversing game's PAK's..... w8 0.2.2
## Post #51
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-08-15T21:29:29+00:00
- Post Title: Re: ArcheAge Online

I have removed "goto 0x20 MEMORY_FILE", now "WIBO" should be there so exactly at PAK size - 0x200
## Post #52
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-15T21:36:41+00:00
- Post Title: Re: ArcheAge Online

```
- variable "SIZE" seems uninitialized, I use its name
             <get SIZE (0) "SIZE"
             <get 0x200 (1) 0x00000200
             >set SIZE (0) to 0x00000200

00000000 06  7   get OFFSET asize
             >set OFFSET (2) to 0x383f8e00

00000000 0c  9   math OFFSET -= SIZE
             <get OFFSET (2) 0x383f8e00
             <get SIZE (0) 0x00000200
             >set OFFSET (2) to 0x383f8c00

00000000 2b  10  callfunction DECRYPT 1
             .start_bms start: 34 0 0

00000000 26  42  encryption aes_128_cbc "\x32\x1F\x2A\xEE\xAA\x58\x4A\xB4\x9A\x6
C\x9E\x09\xD5\x9E\x9C\x6F"
- variable "aes_128_cbc" seems uninitialized, I use its name
             <get aes_128_cbc (15) "aes_128_cbc"
- encryption with algorithm aes_128_cbc and key of 16 bytes

00000000 0b  43  log MEMORY_FILE OFFSET SIZE
             <get MEMORY_FILE (16) "MEMORY_FILE"
             <get OFFSET (2) 0x383f8c00
             <get SIZE (0) 0x00000200
- create a memory file from offset 383f8c00 of 512 bytes

00000000 26  44  encryption "" ""
             <get  (17) ""
             <get  (17) ""
             <get  (17) ""

00000000 2c  45  endfunction
             .start_bms end: 34 0 0 (ret 37)

00000000 09  12  idstring MEMORY_FILE "WIBO"

- signature of 4 bytes at offset 0x00000000 doesn't match the one
  expected by the script:

  this one: "♂ч9к"
  0b e7 39 aa                                       ..9.

  expeceted: "WIBO"
  57 49 42 4f                                       WIBO
```
## Post #53
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-08-15T22:49:49+00:00
- Post Title: Re: ArcheAge Online

I have verified everything here using even the image you posted and it's all correct.

the data "56 97 b3..." is located at -0x200 so it's ok.
I hope it's not a problem of quickbms_4gb_files...

anyway I guess that most of the fields there are longlong so the nulls are just the 64bit part
## Post #54
- Username: iaw
- Rank: advanced
- Number of posts: 52
- Joined date: Wed Oct 21, 2009 7:52 pm
- Post datetime: 2012-08-16T05:06:06+00:00
- Post Title: Re: ArcheAge Online

Sample pak:
```
http://download-xlgamesdn.cdn.x-cdn.com/cbt5/xlpak/106040to106057_pak
```


wrong:
```
math OFFSET += 0x2e0
```

correct:
```
math OFFSET -= 0x2e0  #Not fixed
```


Filename is wrong
## Post #55
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-16T13:05:11+00:00
- Post Title: Re: ArcheAge Online

quickbms get same incorrect full PAK size.

```
------------------------------

00000000 06  2   get SIZE asize
             >set SIZE (0) to 0x383f8e00

00000000 27  3   print %SIZE%
- SCRIPT's MESSAGE:
               <get SIZE (0) 0x383f8e00
943689216
```


Correct -> 22418525696 (5383F8E00)
## Post #56
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-08-16T14:00:05+00:00
- Post Title: Re: ArcheAge Online

@iaw
thanx a lot for the files, if you have other links about newer pak versions I would be happy to check them

@Ekey
you can't use quickbms.exe on an archive bigger than 4gb

and now the new script:
*edit* check next posts
## Post #57
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-16T14:18:54+00:00
- Post Title: Re: ArcheAge Online

> Reply from aluigi
>
> 
@Ekey
you can't use quickbms.exe on an archive bigger than 4gb
I mean quickbms_4gb_files



New Script

```
  expected by the script:

  this one: "♂ч9к"
  0b e7 39 aa                                       ..9.

  expeceted: "WIBO"
  57 49 42 4f                                       WIBO
```
## Post #58
- Username: iaw
- Rank: advanced
- Number of posts: 52
- Joined date: Wed Oct 21, 2009 7:52 pm
- Post datetime: 2012-08-16T14:30:44+00:00
- Post Title: Re: ArcheAge Online

Sample pak Working properly
## Post #59
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-16T14:43:25+00:00
- Post Title: Re: ArcheAge Online

For main archive not work because get invalid pak size

```
- variable "SIZE" seems uninitialized, I use its name
             <get SIZE (0) "SIZE"
             <get 0x200 (1) 0x00000200
             >set SIZE (0) to 0x00000200

00000000 06  7   get OFFSET asize
             >set OFFSET (2) to 0x383f8e00

00000000 0c  8   math OFFSET -= SIZE
             <get OFFSET (2) 0x383f8e00
             <get SIZE (0) 0x00000200
             >set OFFSET (2) to 0x383f8c00

00000000 2b  9   callfunction DECRYPT 1
             .start_bms start: 54 0 0
```
## Post #60
- Username: iaw
- Rank: advanced
- Number of posts: 52
- Joined date: Wed Oct 21, 2009 7:52 pm
- Post datetime: 2012-08-16T14:47:27+00:00
- Post Title: Re: ArcheAge Online

The problem of quickbms_4gb_files.exe?
## Post #61
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-08-16T14:51:37+00:00
- Post Title: Re: ArcheAge Online

I'm performing some tests with quickbms_4gb_files, I will keep you update
## Post #62
- Username: McMagic
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Jun 27, 2012 10:13 pm
- Post datetime: 2012-08-16T14:54:46+00:00
- Post Title: Re: ArcheAge Online

Hello,

There is the possibility to download the full client.

[http://torrents.thepiratebay.se/7528787 ... PB.torrent](http://torrents.thepiratebay.se/7528787/ArcheAge%5BL%5D%5BKR___KR%5D%282012-2013%29.7528787.TPB.torrent)
(I had downloaded it in 4 hours)

Despite the launcher you can download the latest patches around 1GB - I was even without a VPN, but now I start the launcher and play only with the VPN turned on 

Personally, I will be very happy if you manage to extract the main game archive "game_pak" 22GB+
## Post #63
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-08-16T20:05:09+00:00
- Post Title: Re: ArcheAge Online

regarding the 22gb files, it was a bug of quickbms_4gb_files because I used fstat instead of _fstati64... yeah boring large files support.

anyway don't worry it's possible to use the following script to bypass the bug:

```
# version 0.3.1

math SIZE = 0x200
goto 0 0 SEEK_END
savepos OFFSET
math OFFSET -= SIZE
callfunction DECRYPT 1

idstring MEMORY_FILE "WIBO"
get DUMMY long MEMORY_FILE
get FILES long MEMORY_FILE
get EXTRA_FILES long MEMORY_FILE
get DUMMY long MEMORY_FILE
get DUMMY long MEMORY_FILE
get DUMMY long MEMORY_FILE
get DUMMY long MEMORY_FILE
print "Files:              %FILES|x%"
print "Extra files:        %EXTRA_FILES|x%"

math SIZE = FILES
math SIZE += EXTRA_FILES
math SIZE *= 0x150
goto 0 0 SEEK_END
savepos INFO_OFF
math INFO_OFF -= 0x200
for INFO_OFF -= SIZE >= 0
    if INFO_OFF % 0x200
        math INFO_OFF -= 0x10
    else
        break
    endif
next
print "FileTable offset:   %INFO_OFF|x%"

for i = 0 < FILES
    math SIZE = 0x150
    math OFFSET = INFO_OFF
    callfunction DECRYPT 1
    math INFO_OFF += 0x150

    getdstring NAME 0x108 MEMORY_FILE
    get OFFSET longlong MEMORY_FILE
    get SIZE longlong MEMORY_FILE
    get XSIZE longlong MEMORY_FILE  # used for encryption alignment?
    get ZSIZE long MEMORY_FILE      # ???
    getdstring DUMMY 16 MEMORY_FILE
    get DUMMY1 long MEMORY_FILE
    get TIMESTAMP longlong MEMORY_FILE
    get TIMESTAMP longlong MEMORY_FILE
    get DUMMY2 longlong MEMORY_FILE

    set EXT extension NAME
    if EXT == "sqlite3"
        #encryption aes? ???
    endif
    log NAME OFFSET SIZE            # don't use clog for the moment
    encryption "" ""
next i

startfunction DECRYPT
    encryption aes_128_cbc "\x32\x1F\x2A\xEE\xAA\x58\x4A\xB4\x9A\x6C\x9E\x09\xD5\x9E\x9C\x6F"
    log MEMORY_FILE OFFSET SIZE
    encryption "" ""
endfunction
```
## Post #64
- Username: McMagic
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Jun 27, 2012 10:13 pm
- Post datetime: 2012-08-16T20:31:54+00:00
- Post Title: Re: ArcheAge Online

It seems that it works well 
[aa_rip.jpg](https://xentaxbackup.github.io/file/5671_aa_rip.jpg)
## Post #65
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-08-16T20:33:33+00:00
- Post Title: Re: ArcheAge Online

so now you have 22 gigabytes of extracted content... wow.
I'm curious to know why this game is so big, I mean does it contain entire worlds with high quality textures or what?
## Post #66
- Username: McMagic
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Jun 27, 2012 10:13 pm
- Post datetime: 2012-08-16T20:49:26+00:00
- Post Title: Re: ArcheAge Online

So less of a problem - I managed to extracts 4.21 gigabytes
BMS then report a problem with memory - I did it on Win7 64bit 6GB RAM

--------
Otherwise, thank you for your time and effort.
[aa_rip.jpg](https://xentaxbackup.github.io/file/5672_aa_rip.jpg)
## Post #67
- Username: wiener
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Aug 17, 2012 2:05 am
- Post datetime: 2012-08-16T20:56:26+00:00
- Post Title: Re: ArcheAge Online

> Reply from McMagic
>
> So less of a problem - I managed to extracts 4.21 gigabytes
BMS then report a problem with memory - I did it on Win7 64bit 6GB RAM

--------
Otherwise, thank you for your time and effort.

I have the same error with W7 64bit & 8GB RAM. But on another file.
Mine extracted 4.16 gb
[52d7a29d.png](https://xentaxbackup.github.io/file/5673_52d7a29d.png)
## Post #68
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-08-16T20:58:03+00:00
- Post Title: Re: ArcheAge Online

can you try launching quickbms with the -9 option?

just make a link to quickbms.exe and add -9 in the Target property.
let me know if the problem continues.
## Post #69
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-16T20:59:51+00:00
- Post Title: Re: ArcheAge Online

For sample in game World of Warcraft full game size v4.0.1 = 31gb . Content with not used files = ~16gb.
The developers decided to remove unused files from game after patch 4.0.6 and full game size only = 17gb. I am sure in this game is the same
## Post #70
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-08-16T21:06:05+00:00
- Post Title: Re: ArcheAge Online

ih ih ih I guess that's the result of incremental patches: add add add add and then you have 22gb of which only half or less necessary.
## Post #71
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-16T21:07:17+00:00
- Post Title: Re: ArcheAge Online

Exactly
## Post #72
- Username: McMagic
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Jun 27, 2012 10:13 pm
- Post datetime: 2012-08-16T21:13:06+00:00
- Post Title: Re: ArcheAge Online

> Reply from aluigi
>
> can you try launching quickbms with the -9 option?

just make a link to quickbms.exe and add -9 in the Target property.
let me know if the problem continues.

-9 options? 
Error: wrong command-line argument (-9)

```
ame_pak D:\RIP3D models\ArcheAge\bms_extract\

QuickBMS generic files extractor and reimporter 0.5.5 (64bit test)
by Luigi Auriemma
e-mail: aluigi@autistici.org
web:    aluigi.org


Error: wrong command-line argument (-9)

D:\RIP3D models\ArcheAge>

```
## Post #73
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-08-16T21:19:23+00:00
- Post Title: Re: ArcheAge Online

```
quickbms_4gb_files -9 "C:\Program Files (x86)\ArcheAge\game_pak" "D:\RIP3D models\ArcheAge\bms_extract\"
```
## Post #74
- Username: McMagic
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Jun 27, 2012 10:13 pm
- Post datetime: 2012-08-16T21:21:21+00:00
- Post Title: Re: ArcheAge Online

same problem

```
game_pak" "D:\RIP3D models\ArcheAge\bms_extract\"

QuickBMS generic files extractor and reimporter 0.5.5 (64bit test)
by Luigi Auriemma
e-mail: aluigi@autistici.org
web:    aluigi.org


Error: wrong command-line argument (-9)

D:\RIP3D models\ArcheAge>
```
## Post #75
- Username: wiener
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Aug 17, 2012 2:05 am
- Post datetime: 2012-08-16T21:26:50+00:00
- Post Title: Re: ArcheAge Online

> Reply from aluigi
>
> can you try launching quickbms with the -9 option?

just make a link to quickbms.exe and add -9 in the Target property.
let me know if the problem continues.

Worked for me, I've already extracted 10 gb.
Just make a desktop icon for quickbms_4gb_files.exe and write -9 in properties like on my screenie
[win.png](https://xentaxbackup.github.io/file/5674_win.png)
## Post #76
- Username: McMagic
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Jun 27, 2012 10:13 pm
- Post datetime: 2012-08-16T21:28:50+00:00
- Post Title: Re: ArcheAge Online

I now downloaded the latest version already quickbms and it works.

We'll see whether it passes or everything will turn error - quickbms currently works.
## Post #77
- Username: wiener
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Aug 17, 2012 2:05 am
- Post datetime: 2012-08-16T21:52:06+00:00
- Post Title: Re: ArcheAge Online

19.6 GB extracted;
Console says:
--140701 files found in 2851 seconds.

Seems OK
## Post #78
- Username: iaw
- Rank: advanced
- Number of posts: 52
- Joined date: Wed Oct 21, 2009 7:52 pm
- Post datetime: 2012-08-17T03:06:31+00:00
- Post Title: Re: ArcheAge Online

> Reply from Ekey
>
> Exactly

SQLite3 how to decrypt
## Post #79
- Username: leenuli
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Aug 20, 2012 4:36 pm
- Post datetime: 2012-08-20T14:45:22+00:00
- Post Title: Re: ArcheAge Online

> Reply from Ekey
>
> 
Here filetable and sql base from CBT5. Some filenames not correct decrypted.
So how i can decrypt compact.sqlite3? Thanks for your reply.
## Post #80
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-20T16:14:34+00:00
- Post Title: Re: ArcheAge Online

> Reply from leenuli
>
> So how i can decrypt compact.sqlite3? Thanks for your reply.

> Reply from Ekey
>
> Yep. Just need search correct key.

Or dump from memory already decrypted SQL base (if you know how use olly movie [here](http://www.mediafire.com/download.php?48v2qy2imlzr1c0)).
## Post #81
- Username: wiener
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Aug 17, 2012 2:05 am
- Post datetime: 2012-08-20T18:46:46+00:00
- Post Title: Re: ArcheAge Online

so anyone figured out how does it calculate npc hp?
it can come from the server but there are a lot of formulas in sqlite database and also item data, drop data, npc names/races stored
for example, there is a golem-like boss (id 8123) with 110750 hp but I cant find any record with "11750".
## Post #82
- Username: leenuli
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Aug 20, 2012 4:36 pm
- Post datetime: 2012-08-21T01:39:53+00:00
- Post Title: Re: ArcheAge Online

> Reply from Ekey
>
> leenuli wrote:So how i can decrypt compact.sqlite3? Thanks for your reply.
Ekey wrote:Yep. Just need search correct key.

Or dump from memory already decrypted SQL base (if you know how use olly movie here).

Thanks very much! With video, I'll try now.
So did you find correct key to decrypt sqlite3?
## Post #83
- Username: leenuli
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Aug 20, 2012 4:36 pm
- Post datetime: 2012-08-21T03:37:48+00:00
- Post Title: Re: ArcheAge Online

> Reply from Ekey
>
> leenuli wrote:So how i can decrypt compact.sqlite3? Thanks for your reply.
Ekey wrote:Yep. Just need search correct key.

Or dump from memory already decrypted SQL base (if you know how use olly movie here).

I have tried with video, but if i add a breapoint at a function of x2game.dll (this function references "game_%u.sqlite3" string), then an exception raises.
Please help me. and if possible, upload your ollydbg program and plugins.
Thanks.
## Post #84
- Username: wiener
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Aug 17, 2012 2:05 am
- Post datetime: 2012-08-25T16:59:32+00:00
- Post Title: Re: ArcheAge Online

> Reply from leenuli
>
> 
I have tried with video, but if i add a breapoint at a function of x2game.dll (this function references "game_%u.sqlite3" string), then an exception raises.
Thanks.
It works with the OllyDbg 1.10
## Post #85
- Username: amzerof6
- Rank: advanced
- Number of posts: 57
- Joined date: Sat Oct 23, 2010 10:50 pm
- Post datetime: 2012-08-28T06:26:49+00:00
- Post Title: Re: ArcheAge Online

I use that bms script,get this error. anyone seen this befor.
my ArcheAge client is CBT5
[未标题-1.jpg](https://xentaxbackup.github.io/file/5713_未标题-1.jpg)
## Post #86
- Username: Pilgrim
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Dec 03, 2010 1:41 am
- Post datetime: 2012-08-28T16:37:20+00:00
- Post Title: Re: ArcheAge Online

The same thing happened to me.  Try adding -9 to the target property as mentioned on the previous page.  That worked for me, though it still did error out at 140,695 files, which is about 6 files short of what someone listed above after they completed it.
## Post #87
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-08-29T19:41:43+00:00
- Post Title: Re: ArcheAge Online

@amzerof6
you are using a jurassik version.

please check if there are updates first and retry:
[http://quickbms.aluigi.org](http://quickbms.aluigi.org)
## Post #88
- Username: ehnoah
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Feb 29, 2012 6:21 am
- Post datetime: 2012-08-30T09:36:38+00:00
- Post Title: Re: ArcheAge Online

Please PM me if some can get working loading the Models in Model Editor.

We not able to show Models because it is edited Engine 

Hope some of you can help us show Models
## Post #89
- Username: Evial
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Sep 05, 2012 2:30 am
- Post datetime: 2012-09-04T23:05:59+00:00
- Post Title: Re: ArcheAge Online

> Reply from Ekey
>
> 
Or dump from memory already decrypted SQL base (if you know how use olly movie here).

> Reply from Ekey
>
> 
Here filetable and sql base from CBT5. Some filenames not correct decrypted.

Upload these files please.  I want decrypt compact.sqlite3 but i don't know how to do it. I am newbie.
## Post #90
- Username: psychopigeon
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Mar 08, 2012 4:24 pm
- Post datetime: 2012-12-22T20:18:39+00:00
- Post Title: Re: ArcheAge Online

Open beta client is out

[http://download-archeage.x-cdn.com/inst ... cheAge.exe](http://download-archeage.x-cdn.com/install/SetupArcheAge.exe)

i want that JUICY soundtrack
## Post #91
- Username: qwerty
- Rank: advanced
- Number of posts: 54
- Joined date: Wed Mar 31, 2010 6:00 am
- Post datetime: 2012-12-23T07:13:52+00:00
- Post Title: Re: ArcheAge Online

> Reply from psychopigeon
>
> i want that JUICY soundtrack
This one? [http://www.mediafire.com/?66fnlg640y0w7hc](http://www.mediafire.com/?66fnlg640y0w7hc) (from loginscreen)

Btw can someone remove HackShield/Themida protection from archeage.exe? That would be really nice, i want to find a key for database. (binaries: [http://www.mediafire.com/?0wnadbrh5u9j3wb](http://www.mediafire.com/?0wnadbrh5u9j3wb))
## Post #92
- Username: psychopigeon
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Mar 08, 2012 4:24 pm
- Post datetime: 2012-12-23T16:39:44+00:00
- Post Title: Re: ArcheAge Online

That is one of the songs, but there's a lot more unavailable on youtube.
## Post #93
- Username: ehnoah
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Feb 29, 2012 6:21 am
- Post datetime: 2012-12-25T10:18:58+00:00
- Post Title: Re: ArcheAge Online

No one will remove for you the Hackshield I think, it is all explained here in the thread. Not needed to redo it.

All you need is avaliable in this thread ~

PS: Nothing special in the Database, no content change for OBT same as in CBT5  only some model changes and some minor changes. Focus of the Game is on balancing now.

For Soundtrack's PM me.
## Post #94
- Username: iaw
- Rank: advanced
- Number of posts: 52
- Joined date: Wed Oct 21, 2009 7:52 pm
- Post datetime: 2012-12-26T06:30:20+00:00
- Post Title: Re: ArcheAge Online

> Reply from qwerty
>
> 
i want to find a key for database.
database key

```
\xFA\x51\xFD\x28\x6E\xCE\x37\x67\xEC\x09\xF6\x04\x48\x08\x24\x04
```

Key will change after the game update.
## Post #95
- Username: qwerty
- Rank: advanced
- Number of posts: 54
- Joined date: Wed Mar 31, 2010 6:00 am
- Post datetime: 2012-12-26T09:26:45+00:00
- Post Title: Re: ArcheAge Online

Hm guys i still cannot decrypt db with this key. It looks like some problems with filetable or what? I got different data when extracting db file with unpacker and watching source dump while archeage decrypting it
## Post #96
- Username: iaw
- Rank: advanced
- Number of posts: 52
- Joined date: Wed Oct 21, 2009 7:52 pm
- Post datetime: 2012-12-26T09:44:24+00:00
- Post Title: Re: ArcheAge Online

> Reply from qwerty
>
> Hm guys i still cannot decrypt db with this key. It looks like some problems with filetable or what? I got different data when extracting db file with unpacker and watching source dump while archeage decrypting it

You need the latest database
md5:94060694284CE82AD08E6CD362289531
## Post #97
- Username: qwerty
- Rank: advanced
- Number of posts: 54
- Joined date: Wed Mar 31, 2010 6:00 am
- Post datetime: 2012-12-26T10:45:30+00:00
- Post Title: Re: ArcheAge Online

> Reply from iaw
>
> qwerty wrote:Hm guys i still cannot decrypt db with this key. It looks like some problems with filetable or what? I got different data when extracting db file with unpacker and watching source dump while archeage decrypting it

You need the latest database
md5:94060694284CE82AD08E6CD362289531

omg my bad ty. 3 days with ollydbg made me braindead xD
## Post #98
- Username: ragingwolf
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Dec 27, 2012 5:43 am
- Post datetime: 2012-12-26T22:45:55+00:00
- Post Title: Re: ArcheAge Online

Hi, i'm working on archeagecodex.com, I've successfully extracted game.pak, but I don't understand how to extract game.sqlite3, can you explain me how to do it or post already decrypted database.

thanks
## Post #99
- Username: ehnoah
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Feb 29, 2012 6:21 am
- Post datetime: 2012-12-27T18:32:53+00:00
- Post Title: Re: ArcheAge Online

Hmpf so hard all try now to translate the Client and ruin the hard work of all guys here very mad to see this.

But that is life... better next time not share any information how the system work.
## Post #100
- Username: comivan
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Dec 31, 2012 2:45 am
- Post datetime: 2012-12-30T21:36:54+00:00
- Post Title: Re: ArcheAge Online

that bms script works perfect for extracting and decrypting the database but as far as reimporting it you would need a different script right? or will the re-encryption have to be a separate process before the reimport?
## Post #101
- Username: ragingwolf
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Dec 27, 2012 5:43 am
- Post datetime: 2012-12-31T09:59:20+00:00
- Post Title: Re: ArcheAge Online

my script extract all files but don't decrypt database, I don't know why, I think something is wrong
## Post #102
- Username: comivan
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Dec 31, 2012 2:45 am
- Post datetime: 2012-12-31T15:56:21+00:00
- Post Title: Re: ArcheAge Online

> Reply from ragingwolf
>
> my script extract all files but don't decrypt database, I don't know why, I think something is wrong

the script that is posted will; you have to uncomment the  few line that deal with SQLite and insert the correct key where the ?? are.
## Post #103
- Username: nicoli_s
- Rank: advanced
- Number of posts: 77
- Joined date: Fri Jan 07, 2005 2:47 pm
- Post datetime: 2013-01-10T18:27:26+00:00
- Post Title: Re: ArcheAge Online

Is the key still valid for the current version? i tried uncommenting out the line and replacing it with encryption aes_128_cbc "\xFA\x51\xFD\x28\x6E\xCE\x37\x67\xEC\x09\xF6\x04\x48\x08\x24\x04" and it did not work
## Post #104
- Username: Ulimo
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Feb 19, 2013 8:26 pm
- Post datetime: 2013-02-19T15:59:37+00:00
- Post Title: Re: ArcheAge Online

I have been trying now for a while to get the database decrypted with no luck!
Im not really sure how to use olly to dump the database since the links previosly posted doesnt work anymore.

Is it anyone that have the old database left that could update it? 
Or any tips on how to dump the database/find the encryption key?
## Post #105
- Username: ehnoah
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Feb 29, 2012 6:21 am
- Post datetime: 2013-04-16T20:35:39+00:00
- Post Title: Re: ArcheAge Online

They changed the way how to find the Key etc. so there is no way right now until one of the gods here will come and help again
## Post #106
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-04-21T14:48:41+00:00
- Post Title: Re: ArcheAge Online

I have client only from 10.04.2013 if you needed [here](http://www.sendspace.com/file/wzolzh) decrypted db
## Post #107
- Username: ehnoah
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Feb 29, 2012 6:21 am
- Post datetime: 2013-04-21T23:02:14+00:00
- Post Title: Re: ArcheAge Online

Thanks Ekey! Can you tell me where Key is stored? (Please dump the Location for me if you can)
(Or explain me how dump work now after the Force Launcher start *g*)

Normaly the Key is stored in the "ArcheAge.exe" at Location (000002CXX) The actually Database Decryption Key should be:
\x52\x44\x29\x22\x6C\xB2\x36\x59\x48\xBA\x24\x5D\x14\xBA\x0A\x5D

But this not working anymore. Do they use now a second Key for encryption? (see below)
aes_128_cbc "\x52\x44\x29\x22\x6C\xB2\x36\x59\x48\xBA\x24\x5D\x14\xBA\x0A\x5D" "\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0" 0

Any Information about Ekey?
## Post #108
- Username: ehnoah
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Feb 29, 2012 6:21 am
- Post datetime: 2013-05-01T18:20:54+00:00
- Post Title: Re: ArcheAge Online

/push

Can someone tell me the new Decrypt key for Actual Patch (coming out ~ 5 Hours)


Then I can create extractor for the future keys .)
## Post #109
- Username: ehnoah
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Feb 29, 2012 6:21 am
- Post datetime: 2013-05-10T18:55:42+00:00
- Post Title: Re: ArcheAge Online

Do I am allowed to push?

Would be great if anyone can tell me the actual Keys for ArcheAge DB so that I can find them In Future alone! (I not want to ask for any help all the time)

You can Download the newest archeage.exe + DB here : [http://bit.ly/14aRBe3](http://bit.ly/14aRBe3) (In ~ 1 Hour after Post created)

Thanks again for all the help here on this board!
## Post #110
- Username: ehnoah
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Feb 29, 2012 6:21 am
- Post datetime: 2013-07-15T00:47:47+00:00
- Post Title: Re: ArcheAge Online

Hey Ekey,

do you may have time to spent for ARcheAGe or do you not help anymore here? I can fully understand it because it cost your Free Time, but it would be nice if you can help us decrypt.

Specialy because US/EU Version running in Alpha State
## Post #111
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-07-15T09:28:46+00:00
- Post Title: Re: ArcheAge Online

I dont have AA EU/US client.
## Post #112
- Username: ehnoah
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Feb 29, 2012 6:21 am
- Post datetime: 2013-07-30T09:28:24+00:00
- Post Title: Re: ArcheAge Online

It is the same Cryption like Korea/Japan/China Database.

The old way you showed me us got changed. Key was allways in 0x02CXX as I told before.

I uploaded AA Bin32 Folder + Crypted DB. If you could help us find the Key / Cryption Method.

If I know where the Key is, I can simply copy & paste it all the time but yeah...

Actual Key should be:

\xEC\x35\xF6\x1A\xB8\xBE\x5C\x5F\xB8\x47\xDC\x23\xE8\x79\xF4\x3C

But isn't working so dunno.

Here is the File Link:

[http://www.multiupload.nl/GGO1VEQUXD](http://www.multiupload.nl/GGO1VEQUXD)
## Post #113
- Username: OutSide
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Sep 12, 2013 9:39 pm
- Post datetime: 2013-09-13T10:30:10+00:00
- Post Title: Re: ArcheAge Online

bump, ekey, need your help, post in private msg
## Post #114
- Username: BloodForce
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Oct 30, 2013 10:49 pm
- Post datetime: 2013-11-07T16:44:09+00:00
- Post Title: Re: ArcheAge Online

anyone find new key?
## Post #115
- Username: Lerain
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon May 26, 2014 6:18 pm
- Post datetime: 2014-05-26T10:43:55+00:00
- Post Title: Re: ArcheAge Online

Hey there, I’ve been reading through the topic and managed to unpack the game_pak of the EU/NA Alpha version. Now I’m stuck with the encrypted compact.sqlite3 file. I tried to look for the key in the ArcheAge.exe but couldn’t find anything. Like some people in this topic already pointed out - it seems they have changed the location of the key.

There are a couple of ArcheAge database-websites online already, so I guess someone must have found the right place to look at. Could anyone point me in the right direction or send me the key by any chance?

If you know how to do this, but don’t have the current key or database I’ll happily upload any files needed or send them to you directly.

If you’re the owner of one of the currently available online-aa-databases - don’t worry, I am working on a web-app for the game (not yet another database website) which would greatly benefit from an actual item-database in the background, so I will be no competition for your site  

Help is much appreciated!
## Post #116
- Username: Sungam
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun May 31, 2009 2:35 pm
- Post datetime: 2014-08-10T03:40:28+00:00
- Post Title: Re: ArcheAge Online

> Reply from Ekey
>
> I have client only from 10.04.2013 if you needed here decrypted db

I need the whole client, any mirror?
## Post #117
- Username: divStar
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Sep 22, 2010 6:46 am
- Post datetime: 2014-08-10T14:47:26+00:00
- Post Title: Re: ArcheAge Online

I'm using the most recent Alpha client (Trion, EU/NA). I got the files extracted. However: I neither can open compact.sqlite3 nor import the models (perhaps those are encrypted, too? or are they not present as files, but hidden somewhere?). Textures (.dds) and sounds/music seems to work though. Can anyone help get models and access to the database, please?
## Post #118
- Username: Sungam
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun May 31, 2009 2:35 pm
- Post datetime: 2014-08-10T20:27:30+00:00
- Post Title: Re: ArcheAge Online

> Reply from divStar
>
> I'm using the most recent Alpha client (Trion, EU/NA). I got the files extracted. However: I neither can open compact.sqlite3 nor import the models (perhaps those are encrypted, too? or are they not present as files, but hidden somewhere?). Textures (.dds) and sounds/music seems to work though. Can anyone help get models and access to the database, please?

Where can i download this alpha client? I can decrypt the database for you!
## Post #119
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2014-08-11T06:31:53+00:00
- Post Title: Re: ArcheAge Online

> Reply from Sungam
>
> divStar wrote:I'm using the most recent Alpha client (Trion, EU/NA). I got the files extracted. However: I neither can open compact.sqlite3 nor import the models (perhaps those are encrypted, too? or are they not present as files, but hidden somewhere?). Textures (.dds) and sounds/music seems to work though. Can anyone help get models and access to the database, please?

Where can i download this alpha client? I can decrypt the database for you!

It has 22GB not sure how to upload it and where. Ill think of something..... BTW i would need items, map, markers and so on
## Post #120
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2014-08-11T06:38:23+00:00
- Post Title: Re: ArcheAge Online

> Reply from divStar
>
> I'm using the most recent Alpha client (Trion, EU/NA). I got the files extracted. However: I neither can open compact.sqlite3 nor import the models (perhaps those are encrypted, too? or are they not present as files, but hidden somewhere?). Textures (.dds) and sounds/music seems to work though. Can anyone help get models and access to the database, please?

Please share method of extraction ?? Thx
## Post #121
- Username: divStar
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Sep 22, 2010 6:46 am
- Post datetime: 2014-08-11T10:32:04+00:00
- Post Title: Re: ArcheAge Online

Sure thing!

This is how I extracted the current ArcheAge BETA (Trion-client):

```
quickbms_4gb_files -9 archeage_unpack.txt <GAME_PAK-file with complete path> <folder to extract to>
```

Example:

```
quickbms_4gb_files -9 archeage_unpack.txt c:\ArcheAgeBetaNA\game_pak "C:\temp\AAUNPACK"
```


archeage_unpack.txt:

```
# script for QuickBMS http://quickbms.aluigi.org

math SIZE = 0x200
goto 0 0 SEEK_END
savepos OFFSET
math OFFSET -= SIZE
callfunction DECRYPT 1

idstring MEMORY_FILE "WIBO"
get DUMMY long MEMORY_FILE
get FILES long MEMORY_FILE
get EXTRA_FILES long MEMORY_FILE
get DUMMY long MEMORY_FILE
get DUMMY long MEMORY_FILE
get DUMMY long MEMORY_FILE
get DUMMY long MEMORY_FILE
print "Files:              %FILES|x%"
print "Extra files:        %EXTRA_FILES|x%"

math SIZE = FILES
math SIZE += EXTRA_FILES
math SIZE *= 0x150
goto 0 0 SEEK_END
savepos INFO_OFF
math INFO_OFF -= 0x200
for INFO_OFF -= SIZE >= 0
    if INFO_OFF % 0x200
        math INFO_OFF -= 0x10
    else
        break
    endif
next
print "FileTable offset:   %INFO_OFF|x%"

for i = 0 < FILES
    math SIZE = 0x150
    math OFFSET = INFO_OFF
    callfunction DECRYPT 1
    math INFO_OFF += 0x150

    getdstring NAME 0x108 MEMORY_FILE
    get OFFSET longlong MEMORY_FILE
    get SIZE longlong MEMORY_FILE
    get XSIZE longlong MEMORY_FILE  # used for encryption alignment?
    get ZSIZE long MEMORY_FILE      # ???
    getdstring DUMMY 16 MEMORY_FILE
    get DUMMY1 long MEMORY_FILE
    get TIMESTAMP longlong MEMORY_FILE
    get TIMESTAMP longlong MEMORY_FILE
    get DUMMY2 longlong MEMORY_FILE

    #set EXT extension NAME
    #if EXT == "sqlite3"
    #    encryption aes? ???
    #endif
    log NAME OFFSET SIZE            # don't use clog for the moment
    #encryption "" ""
next i

startfunction DECRYPT
    encryption aes_128_cbc "\x32\x1F\x2A\xEE\xAA\x58\x4A\xB4\x9A\x6C\x9E\x09\xD5\x9E\x9C\x6F"
    log MEMORY_FILE OFFSET SIZE
    encryption "" ""
endfunction

```


Result I got when done extracting the recent beta client:

```
  coverage file 0    99%   23448018021 23623106048
  coverage file -1  21497809%   72232640   336

```

Texture- and [strike]music[/strike] files seem to work the right way.

I can imagine though, that the key inside the DECRYPT-function is invalid and thus the files, which need separate decryption, don't work.

As for alpha client... I believe its not currently available to the public, but perhaps I could upload it somewhere .. not sure yet, though. If someone would give me some space to upload to, I'd do that .

Edit: oh - right! If you want to extract the music from *.fsb to something playable, I suggest using Aezay FSB Extractor ([http://aezay.site11.com/aezay/fsbextractor/](http://aezay.site11.com/aezay/fsbextractor/)).
Edit2: D: can't have much playable I guess ... stupid headerless ogg files . Sorry if I got your hopes up.
## Post #122
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2014-08-11T15:26:09+00:00
- Post Title: Re: ArcheAge Online

thx yeah i need to get infor DB or is there any chance to get map form there ?
## Post #123
- Username: Sungam
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun May 31, 2009 2:35 pm
- Post datetime: 2014-08-11T17:14:31+00:00
- Post Title: Re: ArcheAge Online

> Reply from michalss
>
> thx yeah i need to get infor DB or is there any chance to get map form there ?
What do you need?
## Post #124
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2014-08-12T09:45:19+00:00
- Post Title: Re: ArcheAge Online

> Reply from Sungam
>
> michalss wrote:thx yeah i need to get infor DB or is there any chance to get map form there ?
What do you need?

I need map pointes etc... Might some items descriptions and so on
## Post #125
- Username: divStar
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Sep 22, 2010 6:46 am
- Post datetime: 2014-08-12T12:00:03+00:00
- Post Title: Re: ArcheAge Online

I'd also second this . I would like to get my hands on a decrypted database with locations, item names etc.
## Post #126
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2014-08-24T22:19:25+00:00
- Post Title: Re: ArcheAge Online

anyone got luck with database please  on beta?
## Post #127
- Username: Azie
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Sep 04, 2014 12:14 am
- Post datetime: 2014-09-03T16:32:16+00:00
- Post Title: Re: ArcheAge Online

Like others I am currently running the Trion EU/NA version of ArcheAge. I have unpacked the game_pak file but having major issues with the sqlite3 database file due to encryption. You can download the database file here: [https://www.mediafire.com/?3aywv2rccsk3hdn](https://www.mediafire.com/?3aywv2rccsk3hdn)

Thanks
## Post #128
- Username: Nensec
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Oct 02, 2014 3:28 am
- Post datetime: 2014-10-01T19:36:29+00:00
- Post Title: Re: ArcheAge Online

Hey there,

While doing some research into the game files of ArcheAge on the almighty Google I ended up here, so far it has been an amazing help in learning how to get the PAK unpacked!
However, as above has pointed out, the sqlite3 file remains locked due to the wrong key.

Any help/pointers on retrieving the key?
## Post #129
- Username: onroP
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Oct 04, 2014 1:00 am
- Post datetime: 2014-10-03T17:08:12+00:00
- Post Title: Re: ArcheAge Online

How about this guys ? 
[http://rghost.net/58131008](http://rghost.net/58131008)


Its a Russian Mod, working for the US/EU Version. 

But make a Copy of ur pak file, couz the AH is not working for me so far. If anyone is able to fix it, would be great 

Here is the Russian Topic that explains what it is. 
Just use the chrome translation and you unterstand it ^^

[http://allcheats.ru/t219724/](http://allcheats.ru/t219724/)
## Post #130
- Username: Nensec
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Oct 02, 2014 3:28 am
- Post datetime: 2014-10-04T17:48:15+00:00
- Post Title: Re: ArcheAge Online

On the last page of that thread you linked people say they had their accounts stolen after using the mod, so I would stay clear of it
## Post #131
- Username: philodox
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Oct 29, 2014 2:35 am
- Post datetime: 2014-10-28T18:38:41+00:00
- Post Title: Re: ArcheAge Online

Has anyone had any luck finding new key to decrypt DB?
## Post #132
- Username: medwed
- Rank: advanced
- Number of posts: 49
- Joined date: Fri Sep 03, 2010 3:45 pm
- Post datetime: 2018-10-14T20:18:03+00:00
- Post Title: Re: ArcheAge Online

model viewer ArcheAge ? [http://shader.tistory.com/129](http://shader.tistory.com/129)
