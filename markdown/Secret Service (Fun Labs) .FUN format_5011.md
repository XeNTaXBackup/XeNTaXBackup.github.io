## Post #1
- Username: npchemicon
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Sep 12, 2010 6:09 am
- Post datetime: 2010-09-11T22:16:15+00:00
- Post Title: Secret Service (Fun Labs) .FUN format

(Not sure if this should go in the "Compressed files and methods" board or here)

Hey all! There's this old game called Secret Service: In Harm's Way and it's got a file format that I haven't been able to extract . The extension is .fun, presumably a custom format by the game's developers, Fun Labs.

I'm pretty sure the contents of the files are compressed/encrypted, as I tried multiple tools (audiorip, bitmaprip, Jaeder Naub, trid) and I couldn't get any usable data out of the files.

One of the .fun files has an accompanying .zip file which is similar size, and I suspect the contents of the .zip are also in the .fun. I RARed the fun and zip and attached it to this post.

A demo of the game is available [here.](http://www.fileplanet.com/82887/80000/fileinfo/Secret-Service:-In-Harm%27s-Way-Demo)

Hope someone can give some insight on this file format. Thanks in advance!
[ScriptFUNandZIP.rar](https://xentaxbackup.github.io/file/3432_ScriptFUNandZIP.rar)
## Post #2
- Username: npchemicon
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Sep 12, 2010 6:09 am
- Post datetime: 2011-03-16T09:05:11+00:00
- Post Title: Secret Service (Fun Labs) .FUN format

Hello again,

I was able to extract some data from the .fun files using offzip. Unfortunately, I'm still unable to figure out the rest of the archive which would seemingly contain the filenames, etc.

I was looking at Delta Force: Razor Unit (a game that uses the same packfile format, or very similar) in a disassembler but I don't know enough asm to really understand what's going on with the packfile stuff.

Can anybody more experienced than me take a look at these packfiles?

Possibly a mod could move this to the compressed/encrypted section.
## Post #3
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-03-16T15:37:07+00:00
- Post Title: Secret Service (Fun Labs) .FUN format

forum redirected my last post to a login screen so it wasn't even in my history - wish they'd fix that

anyway, there are consistent zip headers which can be read by xoring with 89 8a 8b 8c which appear when the compressed data does (thanks to offzip) however i haven't found anything else. i've tried guessing the filenames (credits/quotes) to find similar patterns (+1 +2 +3) with any xor keys, but no luck)
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-03-16T16:51:43+00:00
- Post Title: Secret Service (Fun Labs) .FUN format

I gave a quick look at it before and the job can be done, maybe I will do it later or tomorrow.
it doesn't seem hard, it's just an incremental xor requiring 2 arguments: the beginning xor byte and the amount of the incrementing (for example 0x88 and 1 as WRS noticed).
## Post #5
- Username: npchemicon
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Sep 12, 2010 6:09 am
- Post datetime: 2011-03-16T17:48:16+00:00
- Post Title: Secret Service (Fun Labs) .FUN format

Thanks to both of you for taking a look!

aluigi, if you could post a QuickBMS script or something to break the encryption, I could try to work out the format myself (I've successfully done it for a few other archives). If I had trouble with that, I could come back here again   

Thanks again.
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-03-17T09:01:49+00:00
- Post Title: Secret Service (Fun Labs) .FUN format

as I promised:
[http://aluigi.org/papers/bms/funlabs.bms](http://aluigi.org/papers/bms/funlabs.bms)
## Post #7
- Username: npchemicon
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Sep 12, 2010 6:09 am
- Post datetime: 2011-03-18T01:39:40+00:00
- Post Title: Secret Service (Fun Labs) .FUN format

It's working great. Thanks!
## Post #8
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-03-18T19:19:24+00:00
- Post Title: Secret Service (Fun Labs) .FUN format

all my replies just redirecting me to login again! last try..


aluigi, i admire your skills (i signed up to xentax because of you)

also, i was not finding the xor keys and incrementor in the header like that  


edit: finally. xentax is totally broken for me right now
## Post #9
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-03-18T19:38:36+00:00
- Post Title: Secret Service (Fun Labs) .FUN format

> Reply from WRS
>
> aluigi, i admire your skills (i signed up to xentax because of you)
wow that's cool :)

in case it could be useful the following is the assembly dump of the code that does the job in Secret Service demo with some comments, hope it helps who is interested:

```
006297BA   . 817D EC 504B0304   CMP DWORD PTR SS:[EBP-14],4034B50   ; is "PK\x03\x04"?
006297C1   . 0F85 96010000      JNZ ss.0062995D
006297C7   . 8B8E 1C020000      MOV ECX,DWORD PTR DS:[ESI+21C]
006297CD   . 8D45 C4            LEA EAX,DWORD PTR SS:[EBP-3C]
006297D0   . 6A 1A              PUSH 1A
006297D2   . 50                 PUSH EAX
006297D3   . 8B11               MOV EDX,DWORD PTR DS:[ECX]
006297D5   . FF52 20            CALL DWORD PTR DS:[EDX+20]          ; read 0x1a bytes
006297D8   . 83F8 1A            CMP EAX,1A
006297DB   . 0F85 7C010000      JNZ ss.0062995D
006297E1   . 33C9               XOR ECX,ECX
006297E3   . 8B16               MOV EDX,DWORD PTR DS:[ESI]
006297E5   . 8A4D C5            MOV CL,BYTE PTR SS:[EBP-3B]         ; arg2 = data[1]
006297E8   . 66:8165 C4 FF00    AND WORD PTR SS:[EBP-3C],0FF        ; arg1 = data[0]
006297EE   . 884D 0C            MOV BYTE PTR SS:[EBP+C],CL
006297F1   . 8B4D C4            MOV ECX,DWORD PTR SS:[EBP-3C]
006297F4   . 8B45 0C            MOV EAX,DWORD PTR SS:[EBP+C]
006297F7   . 50                 PUSH EAX                            ; arg2
006297F8   . 51                 PUSH ECX                            ; arg1
006297F9   . 8D45 C6            LEA EAX,DWORD PTR SS:[EBP-3A]
006297FC   . 6A 18              PUSH 18                             ; size
006297FE   . 50                 PUSH EAX                            ; data + 2
006297FF   . 8BCE               MOV ECX,ESI
00629801   . FF52 2C            CALL DWORD PTR DS:[EDX+2C]          ; decrypt the file informations
00629804   . 8B45 DA            MOV EAX,DWORD PTR SS:[EBP-26]
00629807   . BF 04010000        MOV EDI,104
0062980C   . 25 FFFF0000        AND EAX,0FFFF
00629811   . 3BC7               CMP EAX,EDI
00629813   . 73 02              JNB SHORT ss.00629817               ; name_len must be <= 0x104 bytes
00629815   . 8BF8               MOV EDI,EAX
00629817   > 8B5D 08            MOV EBX,DWORD PTR SS:[EBP+8]
0062981A   . 57                 PUSH EDI
0062981B   . 53                 PUSH EBX
0062981C   . C6041F 00          MOV BYTE PTR DS:[EDI+EBX],0
00629820   . 8B8E 1C020000      MOV ECX,DWORD PTR DS:[ESI+21C]
00629826   . 8B11               MOV EDX,DWORD PTR DS:[ECX]
00629828   . FF52 20            CALL DWORD PTR DS:[EDX+20]          ; read name_len bytes
0062982B   . 3BC7               CMP EAX,EDI
0062982D   . 0F85 2A010000      JNZ ss.0062995D
00629833   . 8B4D 0C            MOV ECX,DWORD PTR SS:[EBP+C]
00629836   . 8B55 C4            MOV EDX,DWORD PTR SS:[EBP-3C]
00629839   . 8B06               MOV EAX,DWORD PTR DS:[ESI]
0062983B   . 51                 PUSH ECX                            ; arg2 (still the previous one)
0062983C   . 52                 PUSH EDX                            ; arg1 (still the previous one)
0062983D   . 57                 PUSH EDI                            ; size
0062983E   . 53                 PUSH EBX                            ; data
0062983F   . 8BCE               MOV ECX,ESI
00629841   . FF50 2C            CALL DWORD PTR DS:[EAX+2C]          ; decrypt
```
