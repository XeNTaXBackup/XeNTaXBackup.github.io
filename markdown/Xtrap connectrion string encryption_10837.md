## Post #1
- Username: djmauro
- Rank: beginner
- Number of posts: 36
- Joined date: Tue Sep 16, 2008 9:49 pm
- Post datetime: 2013-10-05T16:38:23+00:00
- Post Title: Xtrap connectrion string encryption

Its not game specific.
It contains the updater url in it and some other data possibly.
For example: 

```
660970B4480BCE4483356D98BA30E86208FF47F4A1E342BBD1F26228A250EA906CFB7D7B33AC2D400D18DF1E3DF439106777114F07569531260CB4567A6CEF9E0F7D04245246E41FB1670C4E9553760FEC657CD8118A4C8F8D9C67940DACF085D81961A06178735153CF10
```


Its a HEX string  stored as ASCII (but for decrypting i assume its considered as HEX).
Now the important part is starting from :  
```
0F7D04245246E4 
```
.
Anything before it does not seem to have any effect on the xtrap - if i set it all to a random value, it will work (all xept 00 bytes).

0F7D04245246E4 - stands for HTTP://
And the rest: x  t  r  a  p  .  c  a  b  a  l  o  n  l  i  n  e  .  c  o  m  .  b  r  /  X  T  r  a  p  U  p  d  a  t  e
1 char is 1 word in hex. It matches up.
However, in every diff string (diff games, versions) its always similar - 0F7D04245246E4  never changes.
Also 660970B448 in the beginning is always same.
So it cant be random hash - those parts wouldnt stay the same.

Those strings from other games can work with other games -  so there is always only 1 key/method to read it.

And another example of the  string (after http):

```
p  a  t  h  .  p  o  i  n  t  b  l  a  n  k  o  n  l  i  n  e  .  c  o  m  .  b  r  /  x  t  r  a  p  /
```


```
x  t  r  a  p  .  c  a  b  a  l  o  n  l  i  n  e  .  c  o  m  .  b  r  /  X  T  r  a  p  U  p  d  a  t  e

```


Possibly a XOr encryption (with repeating key)?

EDIT:
The possible subroutine that deals with the encryption.

```
.text:00A090B0 ; =============== S U B R O U T I N E =======================================
.text:00A090B0
.text:00A090B0
.text:00A090B0 ; int __cdecl sub_A090B0(char *Src, int)
.text:00A090B0 sub_A090B0      proc near               ; CODE XREF: sub_A08FC0+62p
.text:00A090B0
.text:00A090B0 var_104         = byte ptr -104h
.text:00A090B0 var_103         = byte ptr -103h
.text:00A090B0 Src             = dword ptr  4
.text:00A090B0 arg_4           = dword ptr  8
.text:00A090B0
.text:00A090B0                 sub     esp, 104h
.text:00A090B6                 push    ebx
.text:00A090B7                 push    esi
.text:00A090B8                 push    edi
.text:00A090B9                 mov     ecx, 40h
.text:00A090BE                 xor     eax, eax
.text:00A090C0                 lea     edi, [esp+110h+var_103]
.text:00A090C4                 mov     [esp+110h+var_104], 0
.text:00A090C9                 mov     ebx, [esp+110h+Src]
.text:00A090D0                 rep stosd
.text:00A090D2                 stosw
.text:00A090D4                 stosb
.text:00A090D5                 mov     edi, ebx
.text:00A090D7                 or      ecx, 0FFFFFFFFh
.text:00A090DA                 xor     eax, eax
.text:00A090DC                 xor     esi, esi
.text:00A090DE                 repne scasb
.text:00A090E0                 not     ecx
.text:00A090E2                 dec     ecx
.text:00A090E3                 mov     edi, ecx
.text:00A090E5                 shr     edi, 1
.text:00A090E7                 test    edi, edi
.text:00A090E9                 jle     short loc_A0910B
.text:00A090EB
.text:00A090EB loc_A090EB:                             ; CODE XREF: sub_A090B0+59j
.text:00A090EB                 lea     eax, [esp+esi+110h+var_104]
.text:00A090EF                 push    eax
.text:00A090F0                 push    offset a02x_5   ; "%02X"
.text:00A090F5                 push    ebx             ; Src
.text:00A090F6                 call    _sscanf
.text:00A090FB                 add     esp, 0Ch
.text:00A090FE                 cmp     eax, 0FFFFFFFFh
.text:00A09101                 jz      short loc_A0910B
.text:00A09103                 inc     esi
.text:00A09104                 add     ebx, 2
.text:00A09107                 cmp     esi, edi
.text:00A09109                 jl      short loc_A090EB
.text:00A0910B
.text:00A0910B loc_A0910B:                             ; CODE XREF: sub_A090B0+39j
.text:00A0910B                                         ; sub_A090B0+51j
.text:00A0910B                 push    10h
.text:00A0910D                 push    offset a5fe02a7a34bcf7 ; "5fe02a7a34bcf778"
.text:00A09112                 lea     ecx, [esp+118h+var_104]
.text:00A09116                 push    edi
.text:00A09117                 push    ecx
.text:00A09118                 call    sub_A09400
.text:00A0911D                 mov     eax, [esp+120h+arg_4]
.text:00A09124                 add     esp, 10h
.text:00A09127                 lea     edx, [esp+110h+var_104]
.text:00A0912B                 push    edx
.text:00A0912C                 push    eax
.text:00A0912D                 call    lstrcpy
.text:00A09133                 pop     edi
.text:00A09134                 pop     esi
.text:00A09135                 pop     ebx
.text:00A09136                 add     esp, 104h
.text:00A0913C                 retn
.text:00A0913C sub_A090B0      endp
.text:00A0913C
.text:00A0913C ; ---------------------------------------------------------------------------
.text:00A0913D                 align 10h
.text:00A09140
.text:00A09140 ; =============== S U B R O U T I N E =======================================
.text:00A09140
.text:00A09140
.text:00A09140 ; int __cdecl sub_A09140(LPCSTR lpszUrlName, LPCSTR lpFileName)
.text:00A09140 sub_A09140      proc near               ; CODE XREF: sub_A08FC0+D6p
.text:00A09140
.text:00A09140 var_18          = IBindStatusCallback ptr -18h
.text:00A09140 var_C           = dword ptr -0Ch
.text:00A09140 var_4           = dword ptr -4
.text:00A09140 lpszUrlName     = dword ptr  4
.text:00A09140 lpFileName      = dword ptr  8
.text:00A09140
.text:00A09140                 push    0FFFFFFFFh
.text:00A09142                 push    offset unknown_libname_1705 ; Microsoft VisualC 2-8/net runtime
.text:00A09147                 mov     eax, large fs:0
.text:00A0914D                 push    eax
.text:00A0914E                 mov     large fs:0, esp
.text:00A09155                 sub     esp, 0Ch
.text:00A09158                 push    esi
.text:00A09159                 push    edi
.text:00A0915A                 lea     ecx, [esp+20h+var_18]
.text:00A0915E                 call    sub_A09460
.text:00A09163                 mov     esi, [esp+20h+lpszUrlName]
.text:00A09167                 mov     [esp+20h+var_4], 0
.text:00A0916F                 push    esi             ; lpszUrlName
.text:00A09170                 call    DeleteUrlCacheEntry
.text:00A09176                 mov     edi, [esp+20h+lpFileName]
.text:00A0917A                 lea     eax, [esp+20h+var_18]
.text:00A0917E                 push    eax             ; LPBINDSTATUSCALLBACK
.text:00A0917F                 push    0               ; DWORD
.text:00A09181                 push    edi             ; LPCSTR
.text:00A09182                 push    esi             ; LPCSTR
.text:00A09183                 push    0               ; LPUNKNOWN
.text:00A09185                 call    URLDownloadToFileA
.text:00A0918A                 mov     esi, eax
.text:00A0918C                 test    esi, esi
.text:00A0918E                 jz      short loc_A091C8
.text:00A09190                 push    edi             ; lpFileName
.text:00A09191                 call    sub_A08F60
.text:00A09196                 push    esi
.text:00A09197                 push    10001h
.text:00A0919C                 call    sub_A091F0
.text:00A091A1                 add     esp, 0Ch
.text:00A091A4                 lea     ecx, [esp+20h+var_18]
.text:00A091A8                 mov     [esp+20h+var_4], 0FFFFFFFFh
.text:00A091B0                 call    sub_A09490
.text:00A091B5                 pop     edi
.text:00A091B6                 xor     eax, eax
.text:00A091B8                 pop     esi
.text:00A091B9                 mov     ecx, [esp+18h+var_C]
.text:00A091BD                 mov     large fs:0, ecx
.text:00A091C4                 add     esp, 18h
.text:00A091C7                 retn
.text:00A091C8 ; ---------------------------------------------------------------------------
.text:00A091C8
.text:00A091C8 loc_A091C8:                             ; CODE XREF: sub_A09140+4Ej
.text:00A091C8                 lea     ecx, [esp+20h+var_18]
.text:00A091CC                 mov     [esp+20h+var_4], 0FFFFFFFFh
.text:00A091D4                 call    sub_A09490
.text:00A091D9                 mov     ecx, [esp+20h+var_C]
.text:00A091DD                 pop     edi
.text:00A091DE                 mov     eax, 1
.text:00A091E3                 pop     esi
.text:00A091E4                 mov     large fs:0, ecx
.text:00A091EB                 add     esp, 18h
.text:00A091EE                 retn
.text:00A091EE sub_A09140      endp
.text:00A091EE
.text:00A091EE ; ---------------------------------------------------------------------------

```
## Post #2
- Username: masterX244
- Rank: beginner
- Number of posts: 31
- Joined date: Tue Aug 17, 2010 12:48 am
- Post datetime: 2013-10-12T08:40:35+00:00
- Post Title: Xtrap connectrion string encryption

Had you tried to Xor the hex values of the known parts with the encrypted part already? Maybe you can get parts of the key that way
## Post #3
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2013-10-12T15:24:08+00:00
- Post Title: Xtrap connectrion string encryption

sub_A09400 looks like where the business is done, if the posted snippet indeed is used for decrypting the string.
