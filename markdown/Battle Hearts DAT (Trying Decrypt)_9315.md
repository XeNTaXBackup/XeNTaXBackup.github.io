## Post #1
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-07-20T21:18:02+00:00
- Post Title: Battle Hearts DAT (Trying Decrypt)

Well all resource stored in one big archive pack.dat (1,24GB)

Header Size (Not XOR'ed) - 0x10 (16) bytes from END of file. 

```
4 Bytes - Table Offset
4 Bytes - Table Size
4 Bytes - Unknown (01 00 01 00)
```


All another data XOR'ed by key

```
ion0vasdnvVnGr9856Yiudhfgf-845.S
```


```
0x35 0x36 0x59 0x69 0x75 0x64 0x68 0x66 0x67 0x66 0x2D 0x38 0x34 0x35 0x2E 0x53
```


Table Structure

```
String - FileName
4 Bytes - Offset
4 Bytes - Size
```


PseudoCode

```
		push	edi
; 7:   v8 = a2;
		mov	edi, ecx
; 8:   result =	(*(int (__cdecl	**)(unsigned int, int))(**(_DWORD **)(a2 + 8) +	4))(a3,	a1);
		mov	ecx, [edi+8]
		mov	eax, [ecx]
		mov	eax, [eax+4]
		push	edx
		push	esi
		call	eax
; 9:   v7 = &KEY[*(_DWORD *)(v8	+ 12)];
		mov	ecx, [edi+0Ch]
; 10:	for ( i	= a3; i	< result + a3; ++i )
		lea	ebp, [eax+esi]
		add	ecx, offset KEY
		cmp	esi, ebp
		mov	edx, esi
		jnb	short loc_5D574C
		push	ebx
		lea	esp, [esp+0]
; 12:	  *(_BYTE *)i ^= *v7++;

loc_5D5730:
		mov	bl, [ecx]
		xor	[edx], bl
; 13:	  if ( (_UNKNOWN *)v7 == &unk_93BB5C )
		add	ecx, 1
		cmp	ecx, (offset aOn0vasdnvvngr9+1Fh)
		jnz	short loc_5D5744
; 14:	    v7 = KEY;
		mov	ecx, offset KEY

loc_5D5744:
		add	edx, 1
		cmp	edx, ebp
		jb	short loc_5D5730
		pop	ebx
; 16:	*(_DWORD *)(v8 + 12) = (result + *(_DWORD *)(v8	+ 12)) & 0x1F;

loc_5D574C:
		mov	ecx, [edi+0Ch]
		add	ecx, eax
		and	ecx, 1Fh
		mov	[edi+0Ch], ecx
		pop	edi
		pop	esi
		pop	ebp
		retn	8
sub_5D570A	endp


```


```
{
  int result; // eax@1
  unsigned int i; // edx@1
  char *v7; // ecx@1
  int v8; // edi@1

  v8 = a2;
  result = (*(int (__cdecl **)(unsigned int, int))(**(_DWORD **)(a2 + 8) + 4))(a3, a1);
  v7 = &KEY[*(_DWORD *)(v8 + 12)];
  for ( i = a3; i < result + a3; ++i )
  {
    *(_BYTE *)i ^= *v7++;
    if ( (_UNKNOWN *)v7 == &unk_93BB5C )
      v7 = KEY;
  }
  *(_DWORD *)(v8 + 12) = (result + *(_DWORD *)(v8 + 12)) & 0x1F;
  return result;
}
```


Trying decrypt full pack.dat

```

get SIZE asize
log "pack.dat_decrypted" 0 SIZE
```


Decrypting fine.

if try this

```
    get NSIZE byte
    getdstring NAME NSIZE
    get OFFSET long
    get SIZE long
    log NAME OFFSET SIZE
```


i get invalid decrypted data

```
             <get -0x10 (0) 0xfffffff0
             <get -0x10 (0) 0xfffffff0

4ffad3d0 06  11  get NULLS long
             >set NULLS (1) to 0x00000000

4ffad3d4 06  12  get TABLEOFFSET long
             >set TABLEOFFSET (2) to 0x4fe45e90

4ffad3d8 06  13  get TABLESIZE long
             >set TABLESIZE (3) to 0x00167538

4ffad3dc 06  14  get VERSION long
             >set VERSION (4) to 0x00010001

4ffad3e0 10  15  set FILES 23449
             <get 23449 (6) 0x00005b99
             >set FILES (5) to "23449"

4ffad3e0 08  17  goto TABLEOFFSET
             <get TABLEOFFSET (2) 0x4fe45e90
             <get TABLEOFFSET (2) 0x4fe45e90

4fe45e90 0c  19  for i = 0 < FILES
- variable "i" seems uninitialized, I use its name
             <get i (7) "i"
             <get 0 (8) 0x00000000
             >set i (7) to 0x00000000
             .start_bms start: 10 0 0
             <get i (7) 0x00000000
             <get FILES (5) "23449"
             <get i (7) 0x00000000
             <get FILES (5) "23449"
             condition < is met

4fe45e90 1c  20  filexor "0x69 0x6F 0x6E 0x30 0x76 0x61 0x73 0x64 0x6E 0x76 0x56
 0x6E 0x47 0x72 0x39 0x38 0x35 0x36 0x59 0x69 0x75 0x64 0x68 0x66 0x67 0x66 0x2D
 0x38 0x34 0x35 0x2E 0x53"
             <get -1 (9) 0xffffffff

4fe45e90 06  21  get NSIZE byte
             >set NSIZE (10) to 0x00000074

4fe45e91 07  22  getdstring NAME NSIZE
             <get NSIZE (10) 0x00000074
             <get NSIZE (10) 0x00000074
             <get NSIZE (10) 0x00000074
             >set NAME (11) to ";_=bqz^j|↕3↔3p♫2♣V;jih^h|↨      ↕(r☻14B7-dyke►{V"

4fe45f05 06  23  get OFFSET long
             >set OFFSET (12) to 0x685e6869

4fe45f09 06  24  get SIZE long
             >set SIZE (13) to 0x1f09177c

4fe45f0d 0b  25  log NAME OFFSET SIZE
             <get NAME (11) ";_=bqz^j|↕3↔3p♫2♣V;jih^h|↨      ↕(r☻14B7-dyke►{V"
             <get OFFSET (12) 0x685e6869
             <get SIZE (13) 0x1f09177c
  685e6869 520689532  ;_=bqz^j|↕3↔3p♫2♣V;jih^h|↨      ↕(r☻14B7-dyke►{V

```


Encrypted

```
1D54310D1410093A040A445D5A41493607330F521F0D00380F1A3A31261D5C51585B2C075B050A0F0B662D3834DA2E5369
```


Correct decrypted

```
286268646174615C636C69656E7467656E5C6162696C735C616C6C5F616F65696D6D756E2E6162696C00000000EF000000
```


=>>>>> 
```
(bhdata\clientgen\abils\all_aoeimmun.abil........
```


1D - FileName Length - 28 Correct decrypted = My 74

Why so? What have I missed? 

PS: Sorry for long listing code
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-07-20T22:53:06+00:00
- Post Title: Battle Hearts DAT (Trying Decrypt)

it's a matter of where the key gets applied.

filexor applies that key from offset 0x00 so if you want to start to apply it from a different offset you must specify it, example: filexor "0x11 0x22 ... 0xff" OFFSET

in this case I see that 0x1d must be xored with the byte of the key at offset 0x10 (0x35) so considering that the first 0x10 bytes are in plain-text I bet the applying of the key starts just from this offset so:

```
filexor "0x69 0x6F 0x6E 0x30 0x76 0x61 0x73 0x64 0x6E 0x76 0x56 0x6E 0x47 0x72 0x39 0x38 0x35 0x36 0x59 0x69 0x75 0x64 0x68 0x66 0x67 0x66 0x2D 0x38 0x34 0x35 0x2E 0x53" 0x10
```

try it and it should work :)
## Post #3
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-07-20T23:47:19+00:00
- Post Title: Battle Hearts DAT (Trying Decrypt)

Doesn't work. The same result :\

```
 0x6E 0x47 0x72 0x39 0x38 0x35 0x36 0x59 0x69 0x75 0x64 0x68 0x66 0x67 0x66 0x2D
 0x38 0x34 0x35 0x2E 0x53" 0x10
             <get 0x10 (9) 0x00000010

4fe45e90 06  21  get NSIZE byte
             >set NSIZE (10) to 0x00000074
```


@Edited: Strange. Tested separately

```
1D54310D1410093A040A445D5A41493607330F521F0D00380F1A3A31261D5C51585B2C075B050A0F0B662D3834DA2E5369
```


and work fine. a feeling that the 0x10 ignored. any ideas ?
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-07-21T13:31:33+00:00
- Post Title: Battle Hearts DAT (Trying Decrypt)

no the offset doesn't get ignored, you must just set the correct one since from what I have understood the whole table starting from 0x10 is xored and it's possible that the key is not used like you see there.
I mean the offset is 0x10 ok but maybe the key is used not from its beginning (the'i') but maybe it gets started to use from the middle.
## Post #5
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-07-21T14:08:59+00:00
- Post Title: Battle Hearts DAT (Trying Decrypt)

Lol idk but finally it work if use this

```
filexor "0x69 0x6F 0x6E 0x30 0x76 0x61 0x73 0x64 0x6E 0x76 0x56 0x6E 0x47 0x72 0x39 0x38 0x35 0x36 0x59 0x69 0x75 0x64 0x68 0x66 0x67 0x66 0x2D 0x38 0x34 0x35 0x2E 0x53" NULLS
```
