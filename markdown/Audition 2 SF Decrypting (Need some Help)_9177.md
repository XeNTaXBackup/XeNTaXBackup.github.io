## Post #1
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-06-30T09:43:57+00:00
- Post Title: Audition 2 SF Decrypting (Need some Help)

I'm trying write unpacker for this game but need any help. All resource's contained in *.SF archives. They encrypted with custom algorithm. After hour debugging (****ing xTrap -> xCrap) i found algo :

```
A2Decrypt	proc near

arg_0		= dword	ptr  4

		push	ebx
		push	ebp
		push	esi
		push	edi
		mov	edi, eax
		mov	ecx, edi
		and	ecx, 0FF00h
		mov	edx, edi
		shl	edx, 10h
		or	ecx, edx
		shl	ecx, 8
		movzx	edx, di
		or	ecx, edx
		xor	ecx, 0B11924E1h
		movsx	esi, cl
		mov	edx, ecx
		shr	edx, 8
		movsx	edx, dl
		mov	ebx, esi
		mov	ebp, [esp+10h+arg_0]
		shl	ebx, 5
		add	ebx, esi
		add	edx, ebx
		mov	esi, edx
		shl	esi, 5
		add	esi, edx
		mov	edx, ecx
		shr	edx, 10h
		movsx	edx, dl
		add	esi, edx
		shr	ecx, 18h
		mov	edx, esi
		shl	edx, 5
		add	edx, esi
		movsx	ecx, cl
		mov	ebx, edi
		and	ebx, 3
		mov	eax, 96438AF7h
		lea	ecx, [edx+ecx+7C5D0F85h]
		mov	[esp+10h+arg_0], ebx
		jz	short loc_401645
		mov	esi, ebp
		jmp	short loc_401600
; ---------------------------------------------------------------------------
		db 8Dh,	0A4h, 24h, 4 dup(0)
; ---------------------------------------------------------------------------
		jmp	short loc_401600
; ---------------------------------------------------------------------------
		align 10h

loc_401600:
		mov	edx, ecx
		and	edx, 0FFh
		add      eax, A2Key[edx*4]
		mov	ebp, ecx
		not	ebp
		shl	ebp, 15h
		mov	dl, al
		add	dl, cl
		xor	dl, [esi]
		add	ebp, 2611501h
		shr	ecx, 0Bh
		or	ecx, ebp
		mov	ebp, eax
		shl	ebp, 5
		add	ebp, eax
		movzx	eax, dl
		mov	[esi], dl
		add	esi, 1
		sub	ebx, 1
		lea	eax, [eax+ebp+3]
		jnz	short loc_401600
		sub	edi, [esp+10h+arg_0]
		mov	ebp, esi

loc_401645:
		test	edi, edi
		mov	esi, ebp
		jz	short loc_40168B
		jmp	short loc_401650
; ---------------------------------------------------------------------------
		align 10h

loc_401650:
		mov	edx, ecx
		and	edx, 0FFh
		add	eax, A2Key[edx*4]
		mov	ebx, ecx
		not	ebx
		shl	ebx, 15h
		lea	edx, [ecx+eax]
		xor	edx, [esi]
		add	ebx, 3938731h
		shr	ecx, 0Bh
		or	ecx, ebx
		mov	ebx, eax
		shl	ebx, 5
		add	ebx, edx
		mov	[esi], edx
		add	esi, 4
		sub	edi, 4
		lea	eax, [eax+ebx+3]
		jnz	short loc_401650

loc_40168B:
		pop	edi
		pop	esi
		pop	ebp
		pop	ebx
		retn
A2Decrypt	endp
```


a1 - size (or length) , a2 - buffer ...

```
0x9CCF2FD2, 0x91542960, 0x22A7E2DC, 0x2F5F2939, 0x86DF1BE4, 0xF1D290BA,
0x5DC28797, 0x784AD804, 0x1343FEE2, 0xBEA992BD, 0x9EB0F889, 0xB2344BC0,
0x3EA9FFCA, 0x808EC853, 0xC028690B, 0xADAFEA14, 0x0168CAA7, 0x9E7A3993,
0x3A7CC8B9, 0x4C6062A9, 0xEC5988EC, 0x20D3C9DB, 0xA9372000, 0x66521A52,
0x9917ED9C, 0x410B8A73, 0xC53086EF, 0x7533BC63, 0x9BAD6806, 0xFAA7733D,
0xAFE603DB, 0xE6FE2B38, 0x876288DE, 0xCC2ACF4A, 0x58A04273, 0x2D923506,
0x1F58FE7E, 0xB4A6AF7D, 0xC1010813, 0xD8229666, 0xA324900D, 0x11056F56,
0x83847047, 0xD087414D, 0x76449268, 0xFEFA27C8, 0xAD83AFBD, 0xCC88EDE2,
0xA8F61AE6, 0xA06AE1AD, 0x1D87BF9D, 0xC38B8265, 0x10403E23, 0x4155E5C1,
0xDF23C8FD, 0x1014E311, 0x7D91DAD6, 0xE9E5AB6F, 0x80032F12, 0xA335B8F4,
0x4335DC66, 0x6076AA62, 0xB3394421, 0xB51C33E8, 0x778D21A9, 0x04675FBA,
0x85334A67, 0x6EA15962, 0xA8B0FAC5, 0x481F97DD, 0x45D03061, 0x6730CBC4,
0xE844B8BA, 0xE2104CB2, 0x2DB06737, 0x888E6E9A, 0x617A78D6, 0x93DCEAE2,
0x0E59E13A, 0xA7432D38, 0xC29703E2, 0x0BCFA85E, 0x363C78D1, 0xAC0FD055,
0x9ED23C8F, 0x4D38A0A4, 0xD17EA7B8, 0xA5761A03, 0x50574857, 0xAB4C76F4,
0xED199834, 0x6EE568D8, 0xF26FF2FF, 0x75313216, 0xFE5F9671, 0xB402476C,
0xD32BDA42, 0x27AE0FAC, 0x95FC3703, 0x369B9EE2, 0xCCE7DCD3, 0xA12C7199,
0x27477BDE, 0xA32DCC6A, 0x6A1342C3, 0x0F1F5478, 0xF987FBD9, 0x2A7695F6,
0x0EFA9883, 0x5A2F1B2D, 0x5F27E767, 0xAA80F0B7, 0xF6720901, 0x7ED36604,
0xED95F87E, 0x5971C4B5, 0x328B59B0, 0x4AE06B0B, 0x6FAFF688, 0x85A4648D,
0x818B0A9D, 0x049683B2, 0x96C14250, 0x2A7344F9, 0x4C0D2120, 0x0CE5418F,
0xE6AAD2B5, 0x8E2FAE6B, 0xBB44D1CD, 0xF1F59598, 0xE5B44387, 0x9D95ABAD,
0x86AB063D, 0x060F0FE1, 0xE313C46F, 0xA4A1C5A9, 0xFCA2F3E8, 0xF33F7D49,
0x7A2AD746, 0x0F50799A, 0xAD37ACD9, 0x200389A4, 0xA9123216, 0xFB2B0187,
0x8862457D, 0xCF7D8E5D, 0xDCC92ADE, 0x7DB3E603, 0xE3F22E1C, 0x2B0BE412,
0x5795D064, 0x5B7C049D, 0x7CCB97D4, 0x8DDB4D4B, 0x2A9C63BA, 0x7D5FC4A0,
0x53F6849D, 0x7045DDDD, 0x8E1E83CB, 0x020BC071, 0x1F5E117D, 0x10A15E7A,
0x71860F8F, 0x822CA80F, 0xE6DDFFE5, 0x1680B127, 0x94060BF1, 0x113BA6E2,
0xF6F746E9, 0xEB79EE6E, 0x553A4815, 0xAF269CB8, 0xF6E34229, 0x7E944159,
0x4838BE88, 0xB3B92E29, 0xAC79E668, 0xAB9FB6C4, 0xA7CB3406, 0x4F2FDBCC,
0xBA420B67, 0x78CE1C3B, 0xED6D0A8E, 0xBCD96C8F, 0xB2F1C0A5, 0x2F7334DD,
0x668D5D64, 0x30DA458D, 0x0B6E57CB, 0x0000F91F, 0xC402A009, 0xC48DE853,
0x89AB04FA, 0x7FE039B5, 0xED83CF02, 0xD500BAFF, 0x66DDCBB1, 0x77AE3D7B,
0x3E281C11, 0xADFDFF5C, 0xBA5A507F, 0xD528C9AA, 0x55324C0A, 0x77661A77,
0x5E0DAAA1, 0x2485E991, 0x8D2602F4, 0x969B9C2B, 0x824B71C0, 0x4F25F6B5,
0xEC847A54, 0x68B9C1BB, 0xC756F065, 0x6DEE813A, 0x6D7C3EE0, 0xC3E5D782,
0x9680441A, 0xF7EE3E08, 0x41E3DED3, 0x9F1060A5, 0x866B1139, 0x51A95E08,
0x7429796C, 0xC2A7368A, 0x31A3CBC4, 0x1E908A16, 0x3FE9E1A9, 0xB1A7E875,
0x14598F76, 0x27AAB57D, 0x4C4A259F, 0xBF33DC2B, 0x7019343A, 0x07B3744E,
0xE68BE849, 0x93485D9E, 0x8C8E6222, 0x15E24C94, 0x61CC7A0D, 0xB931751F,
0x9C1AB6F8, 0x737EBE0A, 0xC4AD2B2F, 0xE78499F1, 0x02690861, 0xB1602837,
0x9E30AE09, 0x23BBB3BC, 0xEB94F741, 0xB12F144F, 0x49DAB1D2, 0x22AD0715,
0x9588DD1A, 0x810BC01D, 0x4A7A384A, 0xB78FA974};
```


IDA PseudoCode

```
typedef unsigned char _BYTE;
typedef unsigned int _DWORD;

int __usercall A2Decrypt(int a1, int a2)
{
  int v2; // edi@1
  int v3; // ebp@1
  int v4; // edx@1
  int v5; // ecx@1
  bool v6; // zf@1
  int v7; // ebx@1
  int result; // eax@1
  int v9; // ecx@1
  int v10; // esi@2
  int v11; // eax@3
  unsigned __int8 v12; // dl@3
  int i; // esi@5
  int v14; // eax@6
  int v15; // edx@6
  int v16; // [sp+14h] [bp+4h]@1

  v2 = a1;
  v3 = a2;
  v4 = 33
     * ((char)((((unsigned __int16)a1 | (((a1 << 16) | (unsigned __int16)(a1 & 0xFF00)) << 8)) ^ 0xB11924E1u) >> 16)
      + 33
      * (33 * (char)((unsigned __int8)a1 ^ 0xE1) + (char)((unsigned __int16)((a1 | ((a1 & 0xFF00) << 8)) ^ 0x24E1) >> 8)));
  v5 = (char)((((unsigned __int16)a1 | (((a1 << 16) | (unsigned __int16)(a1 & 0xFF00)) << 8)) ^ 0xB11924E1u) >> 24);
  v7 = a1 & 3;
  v6 = (a1 & 3) == 0;
  result = -1773958409;
  v9 = v4 + v5 + 2086473605;
  v16 = v7;
  if ( !v6 )
  {
    v10 = v3;
    do
    {
      v11 = A2Key[(unsigned __int8)v9] + result;
      v12 = *(_BYTE *)v10 ^ (v9 + (_BYTE)v11);
      v9 = ((~v9 << 21) + 39916801) | ((unsigned int)v9 >> 11);
      *(_BYTE *)v10++ = v12;
      --v7;
      result = v12 + 33 * v11 + 3;
    }
    while ( v7 );
    v2 -= v16;
    v3 = v10;
  }
  for ( i = v3; v2; result = v14 + v15 + 32 * v14 + 3 )
  {
    v14 = A2Key[(unsigned __int8)v9] + result;
    v15 = *(_DWORD *)i ^ (v9 + v14);
    v9 = ((~v9 << 21) + 60000049) | ((unsigned int)v9 >> 11);
    *(_DWORD *)i = v15;
    i += 4;
    v2 -= 4;
  }
  return result;
}

```


Trying to use but something wrong. For example first 12 bytes A525D86D6EBFB8C061812835 after decrypt should be 4C494643535953454D4554 (LIFCSYSEMET) -> CFILESYSTEM. My unreadable crap -> 2BCF7277CAE9088660E11E33

```

	fseek(fi, 0, SEEK_END);
	size_t size = ftell(fi);
	fseek(fi, 0, SEEK_SET);

	char * buffer = (char *)malloc(size);

	size_t read = fread(buffer, 1, size, fi);

	A2Decrypt((int)buffer,size);

	fclose(fi);
```


here example PseudoCode (how it use game)

```
{
  void *v2; // ebx@1
  FILE *v3; // eax@1
  int *v4; // edi@2
  char *v5; // esi@2
  signed int v6; // ecx@2
  bool v7; // zf@2
  char DstBuf; // [sp+8h] [bp-14h]@1
  unsigned int v10; // [sp+18h] [bp-4h]@1

  v10 = (unsigned int)&DstBuf ^ dword_41E3D4; // 4C494643535953454D4554 (LIFCSYSEMET) -> CFILESYSTEM
  v2 = this;
  (*(void (**)(void))(*(_DWORD *)this + 4))();
  v3 = fopen(Filename, "r+bc");
  *((_DWORD *)v2 + 136) = v3;
  if ( !v3 )
    return 0;
  fread(&DstBuf, 0xCu, 1u, v3);
  A2Decrypt(12, (int)&DstBuf);
  v4 = &dword_419E54;
  v5 = &DstBuf;
  v6 = 12;
  v7 = 1;
  do
  {
    if ( !v6 )
      break;
    v7 = *v5++ == *(_BYTE *)v4;
    v4 = (int *)((char *)v4 + 1);
    --v6;
  }
  while ( v7 );
  if ( !v7 )
  {
    fclose(*((FILE **)v2 + 136));
    *((_DWORD *)v2 + 136) = 0;
    return 0;
  }
  (*(void (__thiscall **)(void *, _DWORD))(*(_DWORD *)v2 + 76))(v2, "/");
  return 1;
}

```


Any ideas whats wrong and how correct use it? C++ only began to study
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-06-30T13:38:55+00:00
- Post Title: Audition 2 SF Decrypting (Need some Help)

are you sure to have not switched the two arguments of the function?
in the game pseudo code it's "size, buffer" and not the opposite like you used in your code.

anyway working on this thing require some time, I don't know if I can help you.
## Post #3
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-06-30T14:50:12+00:00
- Post Title: Audition 2 SF Decrypting (Need some Help)

Ok. Here other try.

Read first 12 bytes in buffer



```
    l = ftell(fi);
    fseek(fi,0,SEEK_SET);

    fread(&buffer, 0xCu, sizeof(char),fi);

    A2Decrypt(12, int(&buffer));
```


and decrypt work ^_^
## Post #4
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-07-04T14:59:45+00:00
- Post Title: Audition 2 SF Decrypting (Need some Help)

Source for testing (found algo generating key)

```

errno_t __cdecl A2GenKey()
{
  errno_t result;
  unsigned int v1;
  unsigned int v2;
  unsigned int v3;
  unsigned int v4;
  unsigned int v5;
  unsigned int v6;
  unsigned int v7;
  unsigned int v8;
  unsigned int v9;
  unsigned int v10;
  unsigned int v11;
  unsigned int v12;
  unsigned int v13;
  unsigned int v14;
  unsigned int v15;
  unsigned int v16;
  int v17[256];
  int v18[256];
  int v19[256];
  int v20[256];
  int Src[256];
  int A2OutKey;

  result = 5120;
  if ( !A2OutKey )
  {
    v1 = 16785407;
    v2 = 0;
    do
    {
      v3 = (131 * v1 + 5) % 0xFF7FF;
      v4 = v3 << 16;
      v5 = (149 * v3 + 3) % 0x2001B9;
      v17[v2] = v4 | (unsigned __int16)v5;
      v6 = (131 * v5 + 5) % 0xFF7FF;
      v7 = v6 << 16;
      v8 = (149 * v6 + 3) % 0x2001B9;
      v18[v2] = v7 | (unsigned __int16)v8;
      v9 = (131 * v8 + 5) % 0xFF7FF;
      v10 = v9 << 16;
      v11 = (149 * v9 + 3) % 0x2001B9;
      v19[v2] = v10 | (unsigned __int16)v11;
      v12 = (131 * v11 + 5) % 0xFF7FF;
      v13 = v12 << 16;
      v14 = (149 * v12 + 3) % 0x2001B9;
      v20[v2] = v13 | (unsigned __int16)v14;
      v15 = (131 * v14 + 5) % 0xFF7FF;
      v16 = v15 << 16;
      v1 = (149 * v15 + 3) % 0x2001B9;
      Src[v2++] = v16 | (unsigned __int16)v1;
    }
    while ( v2 < 0x100 );
    result = memcpy_s(A2Key, 0x400u, Src, 0x400u);
    A2OutKey = 1;
  }
  return result;
}

```

[A2_SF_Test_Decrypt.rar](https://xentaxbackup.github.io/file/5540_A2_SF_Test_Decrypt.rar)
