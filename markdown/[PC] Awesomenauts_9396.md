## Post #1
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2012-08-03T15:58:59+00:00
- Post Title: [PC] Awesomenauts

Hi,
Can somebody look at this game? It looks like it uses some kind of encryption on all files (except sounds and videos).

Log from Luigi's Signsrch:

```
- 5158400 bytes allocated
- load signatures
- open file D:\Awesomenauts\signsrch.sig
- 1774060 bytes allocated for the signatures
- 2278 signatures in the database
- start signatures scanning:

  offset   num  description [bits.endian.size]
  --------------------------------------------
  007c45f0 145  SHA256 Hash constant words K (0x428a2f98) [32.le.256]
  0042fe2b 147  SHA256 Initial hash value H (0x6a09e667UL) [32.le.32&]
  007c46f0 149  Hash constant words K for SHA-384 and SHA-512 [64.le.640]
  004315b0 165  AES Rijndael S / ARIA S1 [..256]
  00431640 166  AES Rijndael Si / ARIA X1 [..256]
  007c4580 185  Rijndael rcon [32.le.40]
  007d6634 186  Rijndael rcon [32.be.40]
  00413b24 307  SHA1 / SHA0 / RIPEMD-160 initialization [32.le.20&]
  0081a06a 550  Windows CryptAcquireContext [..21]
  00408bf4 815  libavcodec ff_zigzag_direct [..64]
  00442602 855  Generic bitmask table [32.le.128]
  0071844a 1176 Vorbis FLOOR1_fromdB_LOOKUP [float.le.1024]
  007145ee 1523 zinflate_lengthStarts [32.le.116]
  007145e9 1525 zinflate_lengthExtraBits [32.le.116]
  007c2a9d 1526 zinflate_lengthExtraBits [32.be.116]
  0071463a 1527 zinflate_distanceStarts [32.le.120]
  00714635 1529 zinflate_distanceExtraBits [32.le.120]
  007d574c 1588 Crypton kp [32.le.16]
  0081c422 1767 anti-debug: IsDebuggerPresent [..17]
  007c42b4 1810 bitmask [32.le.128]
  00714927 2259 unlzx table_three [32.le.64]
  054b57af 2271 compression algorithm seen in the game DreamKiller [32.le.12&]

- 22 signatures found in the file
```


Link to binaries and few example files on request.

Thanks
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-03T19:10:17+00:00
- Post Title: [PC] Awesomenauts

Files Encrypted with AES 128 (Key + IV) - CFB mode + compressed with ZLIB. For each file is generated key and IV seems from file size.

Examples Keys and IV's

Manifest.dat - Not needed uncompress after decrypt
Key - 826757DB26C6BC74D0B7AFEF2C65E944
IV - AFE1B1BB3C908D7F6224D9260426CA37

data\texturessd\splashscreen_loading_en.dds - Need uncompress after decrypt
Key - 565824AB59423379E741AC2886501659
IV - 20584671121FD9C6CC2B06391D2DA4F9

data\settings\all.settings - Need uncompress after decrypt
Key - F19AB36BB3E4D8A7245A96EC74D9B8EC
IV - EADF84D02D9A4DDBDD726029D30D9060

Function generating key and iv

```
		mov	eax, [ecx]
		movzx	edx, ax
		imul	edx, 9069h
		shr	eax, 10h
		add	edx, eax
		mov	eax, [ecx+4]
		push	esi                            ; Here file size
		movzx	esi, ax
		imul	esi, 4650h
		shr	eax, 10h
		add	eax, esi
		mov	[ecx], edx
		mov	[ecx+4], eax
		pop	esi
		test	edx, edx
		jnz	short loc_495EA2
		mov	dword ptr [ecx], 1
loc_495EA2:
		test	eax, eax
		jnz	short loc_495EAD
		mov	dword ptr [ecx+4], 0FFFFFFFFh
loc_495EAD:
		mov	eax, [ecx]
		shl	eax, 10h
		add	eax, [ecx+4]
		retn
Generate_Key_IV	endp
```


How it use game

```
{
  unsigned int v5; // edi@1
  unsigned int v6; // edi@3
  char v8; // [sp-1A0h] [bp-1ACh]@2
  int v9; // [sp-198h] [bp-1A4h]@1
  void *v10; // [sp-194h] [bp-1A0h]@1
  char v11; // [sp-190h] [bp-19Ch]@5
  char v12; // [sp-140h] [bp-14Ch]@5
  int v13; // [sp-40h] [bp-4Ch]@6
  void *v14; // [sp-3Ch] [bp-48h]@5
  char v15; // [sp-34h] [bp-40h]@2
  char v16; // [sp-24h] [bp-30h]@4
  unsigned int v17; // [sp-14h] [bp-20h]@1
  char *v18; // [sp-10h] [bp-1Ch]@1
  int v19; // [sp-Ch] [bp-18h]@1
  int (__cdecl *v20)(int, int); // [sp-8h] [bp-14h]@1
  signed int v21; // [sp-4h] [bp-10h]@1
  int v22; // [sp+0h] [bp-Ch]@1
  void *v23; // [sp+4h] [bp-8h]@1
  char v24; // [sp+8h] [bp-4h]@1
  int v25; // [sp+Ch] [bp+0h]@1

  v22 = a2;
  v23 = (void *)v25;
  v21 = -1;
  v20 = sub_72CCC6;
  v19 = a1;
  v18 = &v24;
  v17 = (unsigned int)&v22 ^ __security_cookie;
  v10 = a3;
  v9 = sub_5657C0(a4);
  sub_495EC0(a4 * a5, (unsigned __int64)a4 * a5 >> 32);
  v5 = 0;
  do
    *(&v15 + v5++) = Generate_Key_IV((int)&v8);                          ;Generating KEY
  while ( v5 < 0x10 );
  v6 = 0;
  do
    *(&v16 + v6++) = Generate_Key_IV((int)&v8);                          ;Generating IV
  while ( v6 < 0x10 );
  sub_47AC20(&v15, 16, &v16);                          ; AES Routine
  v21 = 0;
  sub_433E00(v9, v10, a4);
  v21 = 1;
  sub_4799F0(&v11);
  if ( v14 == &v12 + (-(signed int)&v12 & 0xF) )
    memset(v14, 0, 4 * v13);
  return __security_check_cookie((unsigned int)&v22 ^ v17);
}
```

[splashscreen_loading_en.dds.png](https://xentaxbackup.github.io/file/5633_splashscreen_loading_en.dds.png)
## Post #3
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-08-03T21:54:35+00:00
- Post Title: [PC] Awesomenauts

I've always wondered... why do these PC game developers even bother with encryption if it's just going to be defeated in 10 minutes?
## Post #4
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2012-08-04T13:05:24+00:00
- Post Title: [PC] Awesomenauts

Thanks for your time and effort, Ekey  
Is there a way to write a quickBMS script or crypter/decrypter?
## Post #5
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2012-08-05T12:56:41+00:00
- Post Title: [PC] Awesomenauts

Ekey, Need more keys and IV )
Ex:

```
# encryption aes_128_cfb128 "\x56\x58\x24\xAB\x59\x42\x33\x79\xE7\x41\xAC\x28\x86\x50\x16\x59" "\x20\x58\x46\x71\x12\x1F\xD9\xC6\xCC\x2B\x06\x39\x1D\x2D\xA4\xF9"
encryption aes_128_cfb128 "\xF1\x9A\xB3\x6B\xB3\xE4\xD8\xA7\x24\x5A\x96\xEC\x74\xD9\xB8\xEC" "\xEA\xDF\x84\xD0\x2D\x9A\x4D\xDB\xDD\x72\x60\x29\xD3\x0D\x90\x60"
comtype unzip_dynamic
get SIZE asize
clog "decrypted_file.dat" 0 SIZE SIZE
```
## Post #6
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-05T19:27:28+00:00
- Post Title: [PC] Awesomenauts

OMG many files. Need concrete? Or for all  ?
## Post #7
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2012-08-05T19:31:49+00:00
- Post Title: [PC] Awesomenauts

Ekey

```
LocalizationNEW.settings
LocalizationPC.settings
```
## Post #8
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-05T19:37:06+00:00
- Post Title: [PC] Awesomenauts

Ok. I try write tool for generate key and iv. For this files post key and iv later
## Post #9
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-05T22:21:43+00:00
- Post Title: [PC] Awesomenauts

Here promised keys and iv's for localization 

```
Key: EFE76754EB0C72513EDA9B088F43A0C3
IV: 3581A13109A6741EDC90C2C83EDDD249
Compressed: No

Data\Fonts\ZEKTON__.TTF
Key: C754B2CD0DEE570E1C111CA87DE2AEA7
IV: EBC65E6EF4A840134D1D7B3BF0E88C6C
Compressed: No

Data\Fonts\CYRILLIC.TTF
Key: A4B261B994FFF0F9CAE4B53B44663964
IV: 89308D9250A8A476B3ADF9CB28A61DB1
Compressed: No

Data\Fonts\UKIJQOLYAZMA.TTF
Key: 72E5894C29E58C115DC2C3A303F2A200
IV: 8C8BC7365DC5240C7AB2288F2B56F5FE
Compressed: No

Data\Fonts\textchatFont.config
Key: 22F8BA684A202F29BA700AAE1EC42309
IV: 46CEA26BFEC0664B2E291683CB2B484B
Compressed: No

Data\Settings\FontButtonMapping.settings
Key: 0C0D66B13A8320B1EBE60BDCBC2A3161
IV: BB364997DAC4A728C67D6C0407767DA4
Compressed: Yes

Data\Settings\Debug.settings
Key: 1DC01AA4DD3F10DD66D8C426775082FE
IV: 5EAB91DB43299E13E5B7909213849ACF
Compressed: Yes

Data\Settings\Localization.settings
Key: C7BBD7874228803AA3DFA3FD90960952
IV: CE91D6317B0E706304089A2A6E761F01
Compressed: Yes

Data\Settings\LocalizationPC.settings
Key: 64BEF8F9A65E0D505CA70CBF3EB7C47F
IV: AEAB7282F20F5B72C99778143EB3ED1C
Compressed: Yes

Data\Settings\LocalizationNEW.settings
Key: 89D36C4BFEC57FE5E2EF0EFE1A9A2E30
IV: 2BA3772C8AF42A80A9EADE18036A4C19
Compressed: Yes
```
## Post #10
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2012-08-06T05:29:34+00:00
- Post Title: [PC] Awesomenauts

Ekey
Big Thx
## Post #11
- Username: maicomzoio
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Apr 27, 2012 3:13 pm
- Post datetime: 2012-08-12T06:26:18+00:00
- Post Title: [PC] Awesomenauts

I am very noob in this scheme.
Anyone here could tell me how to use a key to decrypt the files?
I'm trying to translate this game for (Brazilian Portuguese) for my son.
If someone can help me I am very grateful.
## Post #12
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-12T09:17:16+00:00
- Post Title: [PC] Awesomenauts

You need download [OpenSSL](http://slproweb.com/download/Win32OpenSSL_Light-1_0_1c.exe)

Example use :

```
openssl enc -aes-128-cfb -d -K 89D36C4BFEC57FE5E2EF0EFE1A9A2E30 -iv 2BA3772C8AF42A80A9EADE18036A4C19 -in LocalizationNEW.settings -out LocalizationNEW.settings.dec
```
## Post #13
- Username: maicomzoio
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Apr 27, 2012 3:13 pm
- Post datetime: 2012-08-14T23:07:07+00:00
- Post Title: [PC] Awesomenauts

Thank you, I'll see what I can do!
## Post #14
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2013-07-16T16:55:12+00:00
- Post Title: [PC] Awesomenauts

So is there a standard method of decrypting the game's DDS files for easy viewing?
## Post #15
- Username: boregore
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Feb 04, 2014 7:08 am
- Post datetime: 2014-02-04T08:33:34+00:00
- Post Title: [PC] Awesomenauts

Anyone still able to help with some keys? or make a tool on how to obtain this keys? Would be really helpful.

I need mostly the keys for this:
ch_blazer001_0.dds
ch_blazer001_1.dds

Thank you!
## Post #16
- Username: g302939
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Aug 15, 2016 10:57 am
- Post datetime: 2016-08-15T03:06:50+00:00
- Post Title: Re: [PC] Awesomenauts

Is it possible to create an automated tool for decrypting settings files regardless of game version? Also I'm curious can it be run on Linux or Windows is a must?
