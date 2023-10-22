## Post #1
- Username: victordentes
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jul 14, 2012 10:17 pm
- Post datetime: 2012-07-14T16:46:34+00:00
- Post Title: About .set files

i Would like to know if  is there any decrypter for .set files             
its for a game .. if any one knows how to ..it would be greattt
tyyy
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-07-15T01:25:06+00:00
- Post Title: About .set files

And what the game?
## Post #3
- Username: victordentes
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jul 14, 2012 10:17 pm
- Post datetime: 2012-07-16T13:32:04+00:00
- Post Title: About .set files

Fantasy Tennis   is the name of the game ... i'm still leaarning about but ... could u guys help me ? ^^
## Post #4
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-07-16T14:18:58+00:00
- Post Title: About .set files

Encrypted with AES.
## Post #5
- Username: victordentes
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jul 14, 2012 10:17 pm
- Post datetime: 2012-07-16T14:48:11+00:00
- Post Title: About .set files

If i post here the file .. u can descrypt it ? i ll search about AES 
how do u know if its AES ? ^^

thats the file
[Fielditem_EU.rar](https://xentaxbackup.github.io/file/5578_Fielditem_EU.rar)
## Post #6
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-07-16T15:40:11+00:00
- Post Title: About .set files

```
005D4DE3    A1 A85E7A00     MOV EAX,DWORD PTR DS:[7A5EA8]
005D4DE8    33C4            XOR EAX,ESP
005D4DEA    894424 14       MOV DWORD PTR SS:[ESP+14],EAX
005D4DEE    56              PUSH ESI
005D4DEF    8BF1            MOV ESI,ECX
005D4DF1    8B4C24 20       MOV ECX,DWORD PTR SS:[ESP+20]
005D4DF5    85C9            TEST ECX,ECX
005D4DF7    75 06           JNZ SHORT FT_Clien.005D4DFF
005D4DF9    8B0D 10CD7700   MOV ECX,DWORD PTR DS:[77CD10]            ; TIMOTEI_ZION
005D4DFF    33C0            XOR EAX,EAX
005D4E01    6A 10           PUSH 10
005D4E03    894424 08       MOV DWORD PTR SS:[ESP+8],EAX
005D4E07    894424 0C       MOV DWORD PTR SS:[ESP+C],EAX
005D4E0B    894424 10       MOV DWORD PTR SS:[ESP+10],EAX
005D4E0F    894424 14       MOV DWORD PTR SS:[ESP+14],EAX
005D4E13    884424 18       MOV BYTE PTR SS:[ESP+18],AL
005D4E17    51              PUSH ECX
005D4E18    8D4424 0C       LEA EAX,DWORD PTR SS:[ESP+C]
005D4E1C    50              PUSH EAX
005D4E1D    E8 3E100E00     CALL FT_Clien.006B5E60                   ; <<<---- AES Routine
005D4E22    8B0D A0D07700   MOV ECX,DWORD PTR DS:[77D0A0]            ; FT_Clien.00723040
005D4E28    83C4 0C         ADD ESP,0C
005D4E2B    6A 10           PUSH 10
005D4E2D    6A 10           PUSH 10
005D4E2F    51              PUSH ECX
005D4E30    8B0E            MOV ECX,DWORD PTR DS:[ESI]
005D4E32    8D5424 10       LEA EDX,DWORD PTR SS:[ESP+10]
005D4E36    52              PUSH EDX
005D4E37    E8 44C30200     CALL FT_Clien.00601180
005D4E3C    84C0            TEST AL,AL
005D4E3E    74 04           JE SHORT FT_Clien.005D4E44
005D4E40    C646 04 01      MOV BYTE PTR DS:[ESI+4],1
005D4E44    0FB646 04       MOVZX EAX,BYTE PTR DS:[ESI+4]
005D4E48    8B4C24 18       MOV ECX,DWORD PTR SS:[ESP+18]
005D4E4C    5E              POP ESI
005D4E4D    33CC            XOR ECX,ESP
005D4E4F    E8 A3ED0D00     CALL FT_Clien.006B3BF7
005D4E54    83C4 18         ADD ESP,18
005D4E57    C2 0800         RETN 8

```


```

db  3Fh ; ?
db  41h ; A
db  56h ; V
db  43h ; C
db  52h ; R
db  69h ; i
db  6Ah ; j
db  6Eh ; n
db  64h ; d
db  61h ; a
db  65h ; e
db  6Ch ; l
```


```
aTimotei_zion   db 'TIMOTEI_ZION',0

```


```
{
  char *v3; // ecx@1
  void *v4; // esi@1
  char v6[4]; // [sp+4h] [bp-18h]@1
  int v7; // [sp+8h] [bp-14h]@3
  int v8; // [sp+Ch] [bp-10h]@3
  int v9; // [sp+10h] [bp-Ch]@3
  char v10; // [sp+14h] [bp-8h]@3
  unsigned int v11; // [sp+18h] [bp-4h]@1

  v4 = this;
  v3 = (char *)a2;
  if ( !a2 )
    v3 = off_77CD10;
  *(_DWORD *)v6 = 0;
  v7 = 0;
  v8 = 0;
  v9 = 0;
  v10 = 0;
  strncpy(v6, v3, 0x10u);
  if ( AES(*(_DWORD *)v4, (int)v6, (int)off_77D0A0, 16, 16) )
    *((_BYTE *)v4 + 4) = 1;
  return *((_BYTE *)v4 + 4);
}
```


Very similar to the [this](http://pastebin.com/MawTfdK0) code. Currently i no have compiler on my notebook and can't check.

PS: Maybe aluigi can compile? Main executable protected with Armadillo (can send already unpacked)
## Post #7
- Username: victordentes
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jul 14, 2012 10:17 pm
- Post datetime: 2012-07-16T15:45:42+00:00
- Post Title: About .set files

really ? really thanks man ... can u post the txt file of fielditem file to me ?
## Post #8
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-07-16T15:59:06+00:00
- Post Title: About .set files

> Reply from victordentes
>
> can u post the txt file of fielditem file to me ?
Nope. It's not my and old code posted on Feb 26th, 2011
## Post #9
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-07-16T16:45:11+00:00
- Post Title: About .set files

but what's the key?
I have tested "TIMOTEI_ZION\0\0\0\0" but it's not ok
## Post #10
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-07-16T17:12:43+00:00
- Post Title: About .set files

TIMOTEI_ZION is key

Example and source attached. Decrypt work fine but at in the end of the file is appended which is trash (need alignment   ) ?
[FTSETDecrypt.rar](https://xentaxbackup.github.io/file/5581_FTSETDecrypt.rar)
## Post #11
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-07-16T19:24:01+00:00
- Post Title: About .set files

uhmmm no there are invalid things:
1) the source code recompiled doesn't decrypt correctly
2) it's the exact key I have used in my script for testing aes, I have tried both the 0 padding and TIMOTEI_ZIONTIMO without success
I'm using aes_128_cbc and I have tried also the others
3) your executable decrypts it but it adds that garbage at the end which is impossible since there is nothing similar in your source code

where is the mistake?

EDIT:
I'm doing other tests, it's necessary to use "TIMOTEI_ZION\0\0\0\0" as key in your code so still remain the doubt about quickbms

EDIT2:
the problem is CRijndael (here used as normal ecb) which is non-standard and indeed none of the standard aes implementations used in openssl and tomcrypt work.
that's boring, I guess I must implement this new thing in quickbms.
[http://www.codeproject.com/Articles/138 ... ption-Decr](http://www.codeproject.com/Articles/1380/A-C-Implementation-of-the-Rijndael-Encryption-Decr)
## Post #12
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-07-16T20:30:46+00:00
- Post Title: About .set files

So anyway tool already posted [here](http://forum.xentax.com/viewtopic.php?f=21&t=7440) long time ago
## Post #13
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-07-18T16:18:30+00:00
- Post Title: About .set files

what a shame... I forgot "fseek(filein,1,SEEK_SET);"... ah ah ah

```
get ALIGN byte
savepos OFFSET
get SIZE asize
math SIZE -= OFFSET
math SIZE -= ALIGN
get NAME basename
string NAME += ".str"
log NAME OFFSET SIZE
```
ok, after this stupid mistake that wasted many of my time I'm open to insults (for a limited amount of time) :)
## Post #14
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-07-18T16:22:17+00:00
- Post Title: About .set files

> Reply from aluigi
>
> what a shame... I forgot "fseek(filein,1,SEEK_SET);"... ah ah ah
It happens :}
## Post #15
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-08-31T13:27:56+00:00
- Post Title: About .set files

if you refer to how do re-encryption in practive the reimport function of quickbms should do the job.
read section 3 of quickbms.txt to know all the details.

if you refer to what to do as programmer, the format is really basic so add the align byte (aligned size of the encrypted data - size of original data) and then encrypt the data with the same key
