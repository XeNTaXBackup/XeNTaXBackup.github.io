## Post #1
- Username: blaland
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Nov 13, 2009 11:03 pm
- Post datetime: 2009-11-15T05:38:33+00:00
- Post Title: nrv2? file compression

Hi guys!
New guy on the block here 

I recently bumped into what seems to be a nrv2b (i think) file compression (i'm not at home at the moment so i can't post the code..)
and i wanted to test my theory and try to decompress it.
Problem is.. my programming skills are still at base.. so i was wondering if anyone already come across this compression method and made a script that i can use maybe?
I don't generally ask for such help but the algo itself is pretty advance for me.. and all i want to do is test a theory 

Thanks for the help in advance!
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-11-15T10:31:37+00:00
- Post Title: nrv2? file compression

why not you just use quickbms for the test?

```
get ZSIZE asize
math SIZE = ZSIZE
math SIZE *= 20
clog "dump.dat" 0 ZSIZE SIZE
```
where XXX in your case must be nrv2b or nrv2d or nrv2e (try all of them in sequence), although I doubt it's nrv and it's probably lzo1x.

obviously the input file must be the raw compressed data, otherwise you must specify its format.
## Post #3
- Username: blaland
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Nov 13, 2009 11:03 pm
- Post datetime: 2009-11-16T09:28:10+00:00
- Post Title: nrv2? file compression

Thank you for the quick answer! 

Unfortunately my computer is down at the moment so i can't make my test   but i was wondering why do you think it's lzo1x?
I can tell you this (from analyzing the assembly code)
The compressed file is built out of sections where before each section there is a byte stating if the following section is compressed or not followed by another byte stating the length of the compress data + a DWORD holding the value of 1+2*n (i hope i remembered correctly..) which i have no idea what's for.

Anyway, i know it's hard to understand just from words so i will post the code as soon as my computer is up again hopefully tomorrow 

And i would use quickbms, just need to learn "How" first from the tutorials
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-11-16T11:27:14+00:00
- Post Title: nrv2? file compression

I named lzo1x because the nrv algorithm (also known as ucl) is created by the same author and while I have never found a game/software implementing nrv there are tons of others that instead implement lzo1x.
so only a calculation of probabilities :)
## Post #5
- Username: blaland
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Nov 13, 2009 11:03 pm
- Post datetime: 2009-11-17T07:44:29+00:00
- Post Title: nrv2? file compression

O.k, got my computer back 
Unfortunately the nrv2 test didn't work   and so i will try something else..
from what i followed i think the compression code is this:

```
|.  8BEC                        MOV EBP,ESP
|.  81EC D4000000               SUB ESP,0D4
|.  53                          PUSH EBX
|.  8B5D 0C                     MOV EBX,[ARG.2]
|.  56                          PUSH ESI
|.  57                          PUSH EDI
|.  33FF                        XOR EDI,EDI
|.  8BF0                        MOV ESI,EAX                                      ;  COMCTL32.7745DA80
|.  393B                        CMP DWORD PTR DS:[EBX],EDI
|.  75 08                       JNZ SHORT compress.00418C50
|.  6A 04                       PUSH 4
|.  58                          POP EAX                                          ;  COMCTL32.7745DA80
|.  E9 98020000                 JMP compress.00418EE8
|>  6A 4C                       PUSH 4C
|.  8D45 98                     LEA EAX,[LOCAL.26]
|.  50                          PUSH EAX                                         ;  COMCTL32.7745DA80
|.  E8 45F3FFFF                 CALL compress.00417FA0
|.  8B0B                        MOV ECX,DWORD PTR DS:[EBX]
|.  8D0432                      LEA EAX,DWORD PTR DS:[EDX+ESI]
|.  8945 BC                     MOV [LOCAL.17],EAX                               ;  COMCTL32.7745DA80
|.  8B45 08                     MOV EAX,[ARG.1]
|.  03C8                        ADD ECX,EAX                                      ;  COMCTL32.7745DA80
|.  8945 CC                     MOV [LOCAL.13],EAX                               ;  COMCTL32.7745DA80
|.  B8 00008000                 MOV EAX,800000
|.  C745 9C 000D0000            MOV [LOCAL.25],0D00
|.  C745 98 01100000            MOV [LOCAL.26],1001
|.  8955 B8                     MOV [LOCAL.18],EDX
|.  8955 B4                     MOV [LOCAL.19],EDX
|.  894D D0                     MOV [LOCAL.12],ECX
|.  897D D4                     MOV [LOCAL.11],EDI
|.  8955 EC                     MOV [LOCAL.5],EDX
|.  897D FC                     MOV [LOCAL.1],EDI
|.  8985 30FFFFFF               MOV [LOCAL.52],EAX                               ;  COMCTL32.7745DA80
|.  3BF0                        CMP ESI,EAX                                      ;  COMCTL32.7745DA80
|.  73 15                       JNB SHORT compress.00418CAF
|.  B8 00010000                 MOV EAX,100
|.  89B5 30FFFFFF               MOV [LOCAL.52],ESI
|.  3BF0                        CMP ESI,EAX                                      ;  COMCTL32.7745DA80
|.  77 06                       JA SHORT compress.00418CAF
|.  8985 30FFFFFF               MOV [LOCAL.52],EAX                               ;  COMCTL32.7745DA80
|>  8D45 98                     LEA EAX,[LOCAL.26]
|.  8DB5 30FFFFFF               LEA ESI,[LOCAL.52]
|.  8985 4CFFFFFF               MOV [LOCAL.45],EAX                               ;  COMCTL32.7745DA80
|.  897D AC                     MOV [LOCAL.21],EDI
|.  897D E0                     MOV [LOCAL.8],EDI
|.  897D DC                     MOV [LOCAL.9],EDI
|.  897D D8                     MOV [LOCAL.10],EDI
|.  E8 E7F7FFFF                 CALL compress.004184B6
|.  8BD8                        MOV EBX,EAX                                      ;  COMCTL32.7745DA80
|.  3BDF                        CMP EBX,EDI
|.  74 0A                       JE SHORT compress.00418CDF
|.  E8 62F9FFFF                 CALL compress.0041863C
|.  895D F8                     MOV [LOCAL.2],EBX
|.  EB 03                       JMP SHORT compress.00418CE2
|>  897D F8                     MOV [LOCAL.2],EDI
|>  8B45 F8                     MOV EAX,[LOCAL.2]
|.  3BC7                        CMP EAX,EDI
|.  0F85 FB010000               JNZ compress.00418EE8
|.  8B45 D4                     MOV EAX,[LOCAL.11]
|.  C785 34FFFFFF 00100000      MOV [LOCAL.51],1000
|.  C785 38FFFFFF 00080000      MOV [LOCAL.50],800
|.  3BC7                        CMP EAX,EDI
|.  74 09                       JE SHORT compress.00418D11
|.  FF70 04                     PUSH DWORD PTR DS:[EAX+4]
|.  6A FF                       PUSH -1
|.  57                          PUSH EDI
|.  57                          PUSH EDI
|.  FF10                        CALL DWORD PTR DS:[EAX]
|>  C745 AC 01000000            MOV [LOCAL.21],1
|.  33C0                        XOR EAX,EAX                                      ;  COMCTL32.7745DA80
|.  E9 3D010000                 JMP compress.00418E5C
|>  8B45 CC                     /MOV EAX,[LOCAL.13]
|.  2B45 08                     |SUB EAX,[ARG.1]
|.  8B5D A4                     |MOV EBX,[LOCAL.23]
|.  8B4D A8                     |MOV ECX,[LOCAL.22]
|.  8945 DC                     |MOV [LOCAL.9],EAX                               ;  COMCTL32.7745DA80
|.  895D F0                     |MOV [LOCAL.4],EBX
|.  894D 94                     |MOV [LOCAL.27],ECX
|.  397D FC                     |CMP [LOCAL.1],EDI
|.  75 06                       |JNZ SHORT compress.00418D3F
|.  8B45 B0                     |MOV EAX,[LOCAL.20]
|.  8945 EC                     |MOV [LOCAL.5],EAX                               ;  COMCTL32.7745DA80
|>  6A 02                       |PUSH 2
|.  5E                          |POP ESI
|.  3BDE                        |CMP EBX,ESI
|.  0F82 02010000               |JB compress.00418E4C
|.  75 09                       |JNZ SHORT compress.00418D55
|.  3B4D 9C                     |CMP ECX,[LOCAL.25]                              ;  ntdll.7C91930F
|.  0F87 F7000000               |JA compress.00418E4C
|>  81FB 00080000               |CMP EBX,800
|.  73 23                       |JNB SHORT compress.00418D80
|.  3B4D AC                     |CMP ECX,[LOCAL.21]
|.  74 1E                       |JE SHORT compress.00418D80
|.  8BD3                        |MOV EDX,EBX
|.  8D45 98                     |LEA EAX,[LOCAL.26]
|.  E8 ABFCFFFF                 |CALL compress.00418A17
|.  8945 E8                     |MOV [LOCAL.6],EAX                               ;  COMCTL32.7745DA80
|.  8D43 FF                     |LEA EAX,DWORD PTR DS:[EBX-1]
|.  3BC6                        |CMP EAX,ESI
|.  76 05                       |JBE SHORT compress.00418D7B
|.  8975 F4                     |MOV [LOCAL.3],ESI
|.  EB 13                       |JMP SHORT compress.00418D8E
|>  8945 F4                     |MOV [LOCAL.3],EAX                               ;  COMCTL32.7745DA80
|.  EB 08                       |JMP SHORT compress.00418D88
|>  8365 E8 00                  |AND [LOCAL.6],0
|.  8365 F4 00                  |AND [LOCAL.3],0
|>  837D F4 00                  |CMP [LOCAL.3],0
|.  76 68                       |JBE SHORT compress.00418DF6
|>  33F6                        |XOR ESI,ESI
|>  8B45 F0                     |/MOV EAX,[LOCAL.4]
|.  3945 A0                     ||CMP [LOCAL.24],EAX                             ;  COMCTL32.7745DA80
|.  76 5E                       ||JBE SHORT compress.00418DF6
|.  3D 00080000                 ||CMP EAX,800
|.  1BC0                        ||SBB EAX,EAX                                    ;  COMCTL32.7745DA80
|.  25 000C0000                 ||AND EAX,0C00
|.  05 00040000                 ||ADD EAX,400
|.  8985 34FFFFFF               ||MOV [LOCAL.51],EAX                             ;  COMCTL32.7745DA80
|.  33C0                        ||XOR EAX,EAX                                    ;  COMCTL32.7745DA80
|.  6A 00                       ||PUSH 0
|.  40                          ||INC EAX                                        ;  COMCTL32.7745DA80
|.  8D8D 30FFFFFF               ||LEA ECX,[LOCAL.52]
|.  8D5D 98                     ||LEA EBX,[LOCAL.26]
|.  E8 C5FBFFFF                 ||CALL compress.00418987
|.  47                          ||INC EDI
|.  83C6 09                     ||ADD ESI,9
|.  837D A4 02                  ||CMP [LOCAL.23],2
|.  72 25                       ||JB SHORT compress.00418DF1
|.  8B4D A8                     ||MOV ECX,[LOCAL.22]
|.  8B55 A4                     ||MOV EDX,[LOCAL.23]
|.  8BC3                        ||MOV EAX,EBX
|.  E8 3EFCFFFF                 ||CALL compress.00418A17
|.  85C0                        ||TEST EAX,EAX                                   ;  COMCTL32.7745DA80
|.  7C 14                       ||JL SHORT compress.00418DF1
|.  8B4D A4                     ||MOV ECX,[LOCAL.23]
|.  2B4D F0                     ||SUB ECX,[LOCAL.4]
|.  03C6                        ||ADD EAX,ESI
|.  03CF                        ||ADD ECX,EDI
|.  6BC9 05                     ||IMUL ECX,ECX,5
|.  034D E8                     ||ADD ECX,[LOCAL.6]
|.  3BC8                        ||CMP ECX,EAX                                    ;  COMCTL32.7745DA80
|.  7F 56                       ||JG SHORT compress.00418E47
|>  3B7D F4                     ||CMP EDI,[LOCAL.3]
|.^ 72 9A                       |\JB SHORT compress.00418D90
|>  FF75 FC                     |PUSH [LOCAL.1]
|.  8D45 98                     |LEA EAX,[LOCAL.26]
|.  50                          |PUSH EAX                                        ;  COMCTL32.7745DA80
|.  8B45 EC                     |MOV EAX,[LOCAL.5]
|.  E8 D7FCFFFF                 |CALL compress.00418ADC
|.  84C0                        |TEST AL,AL
|.  0F84 9C000000               |JE compress.00418EA9
|.  FF75 F0                     |PUSH [LOCAL.4]                                  ; /Arg1 = 00000000
|.  8B5D 94                     |MOV EBX,[LOCAL.27]                              ; |
|.  8365 FC 00                  |AND [LOCAL.1],0                                 ; |
|.  8D75 98                     |LEA ESI,[LOCAL.26]                              ; |
|.  E8 41FDFFFF                 |CALL compress.00418B60                          ; \compress.00418B60
|.  84C0                        |TEST AL,AL
|.  0F84 82000000               |JE compress.00418EA9
|.  8B45 F0                     |MOV EAX,[LOCAL.4]
|.  47                          |INC EDI
|.  57                          |PUSH EDI
|.  8D8D 30FFFFFF               |LEA ECX,[LOCAL.52]
|.  8BDE                        |MOV EBX,ESI
|.  C785 34FFFFFF 00100000      |MOV [LOCAL.51],1000
|.  E8 44FBFFFF                 |CALL compress.00418987
|>  33FF                        |XOR EDI,EDI
|.  EB 24                       |JMP SHORT compress.00418E6B
|>  017D FC                     |ADD [LOCAL.1],EDI
|.^ EB F7                       |JMP SHORT compress.00418E43
|>  FF45 FC                     |INC [LOCAL.1]
|.  33C0                        |XOR EAX,EAX                                     ;  COMCTL32.7745DA80
|.  C785 34FFFFFF 00100000      |MOV [LOCAL.51],1000
|.  40                          |INC EAX                                         ;  COMCTL32.7745DA80
|>  57                           PUSH EDI
|.  8D8D 30FFFFFF               |LEA ECX,[LOCAL.52]
|.  8D5D 98                     |LEA EBX,[LOCAL.26]
|.  E8 1CFBFFFF                 |CALL compress.00418987
|>  397D A0                     |CMP [LOCAL.24],EDI
|.^ 0F87 ABFEFFFF               \JA compress.00418D1F
|.  FF75 FC                     PUSH [LOCAL.1]
|.  8D45 98                     LEA EAX,[LOCAL.26]
|.  50                          PUSH EAX                                         ;  COMCTL32.7745DA80
|.  8B45 EC                     MOV EAX,[LOCAL.5]
|.  E8 59FCFFFF                 CALL compress.00418ADC
|.  84C0                        TEST AL,AL
|.  74 22                       JE SHORT compress.00418EA9
|.  33FF                        XOR EDI,EDI
|.  8D45 98                     LEA EAX,[LOCAL.26]
|.  E8 D4FBFFFF                 CALL compress.00418A65
|.  B9 00000001                 MOV ECX,1000000
|.  E8 7BFCFFFF                 CALL compress.00418B16
|.  68 FF000000                 PUSH 0FF
|.  E8 1DFCFFFF                 CALL compress.00418AC2
|.  84C0                        TEST AL,AL
|.  75 09                       JNZ SHORT compress.00418EB2
|>  C745 F8 04000000            MOV [LOCAL.2],4
|.  EB 28                       JMP SHORT compress.00418EDA
|>  8D75 98                     LEA ESI,[LOCAL.26]
|.  E8 33FDFFFF                 CALL compress.00418BED
|.  8B45 CC                     MOV EAX,[LOCAL.13]
|.  2B45 08                     SUB EAX,[ARG.1]
|.  8B4D 0C                     MOV ECX,[ARG.2]
|.  8901                        MOV DWORD PTR DS:[ECX],EAX                       ;  COMCTL32.7745DA80
|.  8B4D D4                     MOV ECX,[LOCAL.11]
|.  8945 DC                     MOV [LOCAL.9],EAX                                ;  COMCTL32.7745DA80
|.  85C9                        TEST ECX,ECX
|.  74 0B                       JE SHORT compress.00418EDA
|.  FF71 04                     PUSH DWORD PTR DS:[ECX+4]
|.  6A 04                       PUSH 4
|.  50                          PUSH EAX                                         ;  COMCTL32.7745DA80
|.  FF75 D8                     PUSH [LOCAL.10]
|.  FF11                        CALL DWORD PTR DS:[ECX]
|>  8DB5 30FFFFFF               LEA ESI,[LOCAL.52]
|.  E8 57F7FFFF                 CALL compress.0041863C
|.  8B45 F8                     MOV EAX,[LOCAL.2]
|>  5F                          POP EDI
|.  5E                          POP ESI
|.  5B                          POP EBX
|.  C9                          LEAVE
\.  C2 0800                     RETN 8
 >  A1 5CC64100                 MOV EAX,DWORD PTR DS:[41C65C]
 .  3D 70020000                 CMP EAX,270
 .  0F8C AF000000               JL compress.00418FAE
 .  56                          PUSH ESI
 .  57                          PUSH EDI
 .  33D2                        XOR EDX,EDX
 .  BE FFFFFF7F                 MOV ESI,7FFFFFFF
 >  8BCA                        MOV ECX,EDX
 .  C1E1 02                     SHL ECX,2
 .  8B81 64C64100               MOV EAX,DWORD PTR DS:[ECX+41C664]
 .  3381 60C64100               XOR EAX,DWORD PTR DS:[ECX+41C660]
 .  23C6                        AND EAX,ESI
 .  3381 60C64100               XOR EAX,DWORD PTR DS:[ECX+41C660]
 .  8BF8                        MOV EDI,EAX                                      ;  COMCTL32.7745DA80
 .  D1E8                        SHR EAX,1
 .  83E7 01                     AND EDI,1
 .  3304BD 24C04100             XOR EAX,DWORD PTR DS:[EDI*4+41C024]
 .  3381 94CC4100               XOR EAX,DWORD PTR DS:[ECX+41CC94]
 .  42                          INC EDX
 .  81FA E3000000               CMP EDX,0E3
 .  8981 60C64100               MOV DWORD PTR DS:[ECX+41C660],EAX                ;  COMCTL32.7745DA80
 .^ 7C C4                       JL SHORT compress.00418F08
 .  81FA 6F020000               CMP EDX,26F
 .  7D 34                       JGE SHORT compress.00418F80
 .  8D0C95 60C64100             LEA ECX,DWORD PTR DS:[EDX*4+41C660]
 >  8B01                        MOV EAX,DWORD PTR DS:[ECX]
 .  8D51 04                     LEA EDX,DWORD PTR DS:[ECX+4]
 .  3302                        XOR EAX,DWORD PTR DS:[EDX]
 .  23C6                        AND EAX,ESI
 .  3301                        XOR EAX,DWORD PTR DS:[ECX]
 .  8BF8                        MOV EDI,EAX                                      ;  COMCTL32.7745DA80
 .  83E7 01                     AND EDI,1
 .  8B3CBD 24C04100             MOV EDI,DWORD PTR DS:[EDI*4+41C024]
 .  33BA 70FCFFFF               XOR EDI,DWORD PTR DS:[EDX-390]
 .  D1E8                        SHR EAX,1
 .  33F8                        XOR EDI,EAX                                      ;  COMCTL32.7745DA80
 .  8939                        MOV DWORD PTR DS:[ECX],EDI
 .  8BCA                        MOV ECX,EDX
 .  81F9 1CD04100               CMP ECX,compress.0041D01C
 .^ 7C D3                       JL SHORT compress.00418F53
 >  8B0D 1CD04100               MOV ECX,DWORD PTR DS:[41D01C]
 .  A1 60C64100                 MOV EAX,DWORD PTR DS:[41C660]
 .  33C1                        XOR EAX,ECX
 .  23C6                        AND EAX,ESI
 .  33C1                        XOR EAX,ECX
 .  8BC8                        MOV ECX,EAX                                      ;  COMCTL32.7745DA80
 .  D1E8                        SHR EAX,1
 .  83E1 01                     AND ECX,1
 .  33048D 24C04100             XOR EAX,DWORD PTR DS:[ECX*4+41C024]
 .  5F                          POP EDI
 .  3305 90CC4100               XOR EAX,DWORD PTR DS:[41CC90]
 .  5E                          POP ESI
 .  A3 1CD04100                 MOV DWORD PTR DS:[41D01C],EAX                    ;  COMCTL32.7745DA80
 .  33C0                        XOR EAX,EAX                                      ;  COMCTL32.7745DA80
 >  8B0C85 60C64100             MOV ECX,DWORD PTR DS:[EAX*4+41C660]
 .  40                          INC EAX                                          ;  COMCTL32.7745DA80
 .  A3 5CC64100                 MOV DWORD PTR DS:[41C65C],EAX                    ;  COMCTL32.7745DA80
 .  8BC1                        MOV EAX,ECX
 .  C1E8 0B                     SHR EAX,0B
 .  33C8                        XOR ECX,EAX                                      ;  COMCTL32.7745DA80
 .  8BC1                        MOV EAX,ECX
 .  25 AD583AFF                 AND EAX,FF3A58AD
 .  C1E0 07                     SHL EAX,7
 .  33C8                        XOR ECX,EAX                                      ;  COMCTL32.7745DA80
 .  8BC1                        MOV EAX,ECX
 .  25 8CDFFFFF                 AND EAX,FFFFDF8C
 .  C1E0 0F                     SHL EAX,0F
 .  33C8                        XOR ECX,EAX                                      ;  COMCTL32.7745DA80
 .  8BC1                        MOV EAX,ECX
 .  C1E8 12                     SHR EAX,12
 .  33C1                        XOR EAX,ECX
 .  C3                          RETN

```


I apologize if i added some useless code as well.. it was really hard to follow the whole code in memory.. plus as you can see there are several calls inside here that i didn't include so this post will stay "readable" 

Thanks again for the help!
## Post #6
- Username: blaland
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Nov 13, 2009 11:03 pm
- Post datetime: 2009-11-17T09:38:58+00:00
- Post Title: nrv2? file compression

O.k, when trying to run the decompression it says:
Error: UCL input is wrong or incomplete (-203)
Error: there is an error with the decompression the returened output size is negative (-1)

same goes for the lzo1x 

in anyway, i'm uploading a test file that is compressed with this "unknown" algo.
Would appreciate the help 

Notice that the first byte states the size of the file (minus 1 i think?) then the 9th byte states the number of sections in the compressed file (again, i'm deducting here based on the code i followed..) then there are some other unknown parameters..

In any case, notice that before each section there is a byte ("1" or "0") that states if this section is compressed or not (byte number 127 marks that the next section is compressed).
3 bytes before each section there is a byte stating the size of the next line etc..

That is all i got for now..
Would appreciate some help from here 

Thanks in advance!
[testfile.zip](https://xentaxbackup.github.io/file/2535_testfile.zip)
## Post #7
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-11-17T11:38:02+00:00
- Post Title: nrv2? file compression

the only recognizable thing I see in the code you posted is a part of an encryption algorithm commonly called MT_decrypt or MT.
while in the testfile is not clear where starts exactly the raw compressed data.

in any case I guess you will find the following post enough interesting:
[viewtopic.php?p=33056#p33056](http://forum.xentax.com/viewtopic.php?p=33056#p33056)
## Post #8
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-11-17T11:42:45+00:00
- Post Title: nrv2? file compression

is this the compression?
[http://www.koders.com/c/fid99C56BFCDFDD ... 4F3E5.aspx](http://www.koders.com/c/fid99C56BFCDFDD75D6A3F5D0A7339B672A5E04F3E5.aspx)
you should post another file that is a little bigger to get a better idea of what is meant to be in the compressed data.
## Post #9
- Username: blaland
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Nov 13, 2009 11:03 pm
- Post datetime: 2009-11-17T12:24:33+00:00
- Post Title: nrv2? file compression

Thank you aluigi, i will look into your post 

chrrox,
I believe this is the compression method though i am unable to decompress it using the tools provided at that site. (for some reason the code doesn't compile) and since that is extremely advance C for me.. i'm trying different methods at the moment.

In any case, i hope this file is better 
if not, i will provide you with a file that is around the 30KB big.. just wanted to "save" time 
Thanks again!
[testfile.zip](https://xentaxbackup.github.io/file/2536_testfile.zip)
## Post #10
- Username: blaland
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Nov 13, 2009 11:03 pm
- Post datetime: 2009-11-18T08:03:33+00:00
- Post Title: nrv2? file compression

aluigi,
I have worked according to the post you gave here and i have some questions..
you state in the post that the file that you scan has to be the "raw" data, the problem is that i don't know if this file is considered the raw data..

I'll explain a little by an example of the latest file i uploaded.
If you look into the file (in HEX mode) you'll see it is divided into sections. (i believe that each section is marked with "(some char)N" like at the 21th character from the beginning of the file "!N").

Before each section there are some parameters that gives you a little information about that section like length, compressed, etc..
If it is unclear if the section is compressed, please note that the 127th byte from the beginning states that the next section is compressed (marked "01") and thus, the "raw" compressed data starts somewhere around the 129th+ area.
You can clearly see that up until that 127th byte all the data is in plain txt and readable where the data that starts after the 129th byte is starting to get "jumbled".

I can also tell you that this file supposed to look like a long list of URLs (search engines, news sites etc..)

That's about all i know..
Thanks again for the help!

p.s: good eye recognizing the encrypting algo  though that section is not part of the compression, it's always good to know it has a name
## Post #11
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-11-18T11:06:57+00:00
- Post Title: nrv2? file compression

for example in the last file you uploaded we have something like the compressed size (32bit) at offset 0x82, the uncompressed size at 0x86 and the raw data at 0x8a.

I have already scanned that raw data with quickbms without luck, and I have also cut the first 4 bytes of the raw data as additional check.
so I don't have other ideas

P.S.: to be exact the previous code was about a pseudo number generation algorithm, but it's used also as a decryption in some software (autoit)
## Post #12
- Username: blaland
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Nov 13, 2009 11:03 pm
- Post datetime: 2009-11-19T07:08:54+00:00
- Post Title: nrv2? file compression

Thanks aluigi for all the help 
I will try and reverse the compression method though from the look of it, it's going to be a pain..

In anyway, i wanted to ask 2 things about the quickbms if i'm here already 

1. When running manually the test on "LZO1B" for example, i got a 0 length output file.. any reason for that? (I'm sorry, i'm not a compression expert so i have no idea how the algo works..)

2. When running the complete scan, for some reason it skips doesn't create an output for the first 11th tests.. only starts from 12th, i mean, it does make the test, it shows me to check several algo's but doesn't provide the output file like the 12th+ tests.. is it a known "bug"?

Thanks again for all the help!
## Post #13
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-11-19T15:14:14+00:00
- Post Title: nrv2? file compression

1) an output file of 0 bytes means that the algorithm is not the good one

2) quickbms doesn't create the output files for the algorithms that have failed (they return an error if the compressed data is invalid), so they are not created just because doesn't exist a decompressed data obtained from them :)
