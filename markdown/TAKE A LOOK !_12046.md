## Post #1
- Username: bilat1234
- Rank: beginner
- Number of posts: 23
- Joined date: Sun Sep 21, 2014 7:18 pm
- Post datetime: 2014-10-04T08:24:13+00:00
- Post Title: TAKE A LOOK !

Hello Everyone !
 how to fix this ? 


Thank you guys ~ )
## Post #2
- Username: HugoPeters
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-10-04T13:34:40+00:00
- Post Title: TAKE A LOOK !

Open CMD -> Type "format C: /U" and then make sure you type "Y" to all questions.
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-10-04T16:29:05+00:00
- Post Title: TAKE A LOOK !

> Reply from bilat1234
>
> fuck you !Welcome to the forum.  

Yes, Hugo is as nasty as his avatar and you've reason to be upset.
I don't have any clue what he intended but seems he got what he was looking for...

Anyway - for your request: which game?
What did you do exactly that caused the error message to appear?

Also keep in mind that this forum is primary for model research so might be the wrong one.
## Post #4
- Username: HugoPeters
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-10-04T16:30:04+00:00
- Post Title: TAKE A LOOK !

> Reply from bilat1234
>
> fuck you !
That didn't work? Sorry.

This program should fix the issues you're having: [http://www.angelfire.com/apes/bonzi_buddy/](http://www.angelfire.com/apes/bonzi_buddy/)
## Post #5
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2014-10-04T19:44:59+00:00
- Post Title: TAKE A LOOK !

My guess is the game has a limit of 9000 vertices for the player character and your imported mesh exceeds that limit.
## Post #6
- Username: Naroax
- Rank: beginner
- Number of posts: 30
- Joined date: Sun Aug 31, 2014 1:44 am
- Post datetime: 2014-10-04T20:41:50+00:00
- Post Title: TAKE A LOOK !

LOL hugo come on   nasty trick!
## Post #7
- Username: kazhuki01
- Rank: beginner
- Number of posts: 31
- Joined date: Tue Jun 19, 2012 1:46 am
- Post datetime: 2014-10-05T02:24:44+00:00
- Post Title: TAKE A LOOK !

> Reply from barti
>
> My guess is the game has a limit of 9000 vertices for the player character and your imported mesh exceeds that limit.

Correct bro, the game has a limit of 3500 vertices, so when you try to import new meshes to the game you encountered that error. That guy won't listen to me  clue to fix that, try to figure it in your client
## Post #8
- Username: bilat1234
- Rank: beginner
- Number of posts: 23
- Joined date: Sun Sep 21, 2014 7:18 pm
- Post datetime: 2014-10-05T15:49:34+00:00
- Post Title: TAKE A LOOK !

> Reply from barti
>
> My guess is the game has a limit of 9000 vertices for the player character and your imported mesh exceeds that limit.

 yes the limit vertices of tantra online is 3500 .. But if you don't mind sir .
how to exceed the limit of this vertices .?
what modification should i changed ? to read some highest vertices in game .

Thanks
## Post #9
- Username: HugoPeters
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-10-05T20:43:12+00:00
- Post Title: TAKE A LOOK !

> Reply from bilat1234
>
> barti wrote:My guess is the game has a limit of 9000 vertices for the player character and your imported mesh exceeds that limit.

 yes the limit vertices of tantra online is 3500 .. But if you don't mind sir .
how to exceed the limit of this vertices .?
what modification should i changed ? to read some highest vertices in game .

Thanks
The only way you could really change that is through a config file of some sort. If it's hardcoded it's going to be damn near impossible.
You could try using a memory editor such as CheatEngine, but it would take ages to find the address.
What you can do is find a LOD mesh generator. It will make the mesh you have look less detailed but it will more than halve the amount of verts you have.
You could then generate a bump / normal map and see if you could apply that on the LOD mesh to make it look like a high poly one.

I dunno how this game works, there's probably a tool for it out somehwere.
## Post #10
- Username: bilat1234
- Rank: beginner
- Number of posts: 23
- Joined date: Sun Sep 21, 2014 7:18 pm
- Post datetime: 2014-10-06T01:05:53+00:00
- Post Title: TAKE A LOOK !

> Reply from HugoPeters
>
> bilat1234 wrote:barti wrote:My guess is the game has a limit of 9000 vertices for the player character and your imported mesh exceeds that limit.

 yes the limit vertices of tantra online is 3500 .. But if you don't mind sir .
how to exceed the limit of this vertices .?
what modification should i changed ? to read some highest vertices in game .

Thanks
The only way you could really change that is through a config file of some sort. If it's hardcoded it's going to be damn near impossible.
You could try using a memory editor such CheatEngine, but it would take ages to find the address.
What you can do is find a LOD mesh generator. It will make the mesh you have look less detailed but it will more than halve the amount of verts you have.
You could then generate a bump / normal map and see if you could apply that on the LOD mesh to make it look like a high poly one.

I dunno how this game works, there's probably a tool for it out somehwere.

Thank you HugoPeters i will try it anyways
## Post #11
- Username: bilat1234
- Rank: beginner
- Number of posts: 23
- Joined date: Sun Sep 21, 2014 7:18 pm
- Post datetime: 2014-10-07T09:32:56+00:00
- Post Title: TAKE A LOOK !

hello again .
i'll already find the dll to changed the Limit Vertices of the  game .

the Problem now is i don't know how e modify the Value .

they said that we can edit it through ollydb or any Hex Editor ..
Please help me )

i need your help to change the value 

the Current vertex is 3500.

by the way this is the dll file 

Thanks ^_^
[HT3DHeaven.rar](https://xentaxbackup.github.io/file/7897_HT3DHeaven.rar)
## Post #12
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2014-10-07T13:40:49+00:00
- Post Title: TAKE A LOOK !

The numbers to change is at instruction VA 0x2003880a, 0x20038827, 0x20038f24, 0x20038f3d, 0x20039429 and 0x20039446. Note that if you change the number, the game could crash if they statically allocate a maximum buffer size for 9000 indices instead of dynamically allocating it.
## Post #13
- Username: bilat1234
- Rank: beginner
- Number of posts: 23
- Joined date: Sun Sep 21, 2014 7:18 pm
- Post datetime: 2014-10-07T14:28:56+00:00
- Post Title: TAKE A LOOK !

> Reply from GMMan
>
> The numbers to change is at instruction VA 0x2003880a, 0x20038827, 0x20038f24, 0x20038f3d, 0x20039429 and 0x20039446. Note that if you change the number, the game could crash if they statically allocate a maximum buffer size for 9000 indices instead of dynamically allocating it.

can you post some screenshot on how to do it sir ?
sorry but  i don't know how to use OLLYDBG ..
## Post #14
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2014-10-07T17:19:10+00:00
- Post Title: TAKE A LOOK !

You should look at some tutorials. Load the DLL in Olly, press Yes to load using LOADDLL, then for each address, press Ctrl-G, enter the address, and OK. Hit Space to bring up the assembly box, and replace the hex number with what you want it to be (you can type in decimal if you add a '.' to the end of the number). When you've edited all the numbers, right click the CPU window, and select Edit->Copy all modifications to executable. Click OK if a dialog box comes up. Right click on the new window, click Save file..., and save the modified file somewhere. Then replace your original DLL with the modified DLL.
## Post #15
- Username: bilat1234
- Rank: beginner
- Number of posts: 23
- Joined date: Sun Sep 21, 2014 7:18 pm
- Post datetime: 2014-10-07T23:31:12+00:00
- Post Title: TAKE A LOOK !

> Reply from GMMan
>
> You should look at some tutorials. Load the DLL in Olly, press Yes to load using LOADDLL, then for each address, press Ctrl-G, enter the address, and OK. Hit Space to bring up the assembly box, and replace the hex number with what you want it to be (you can type in decimal if you add a '.' to the end of the number). When you've edited all the numbers, right click the CPU window, and select Edit->Copy all modifications to executable. Click OK if a dialog box comes up. Right click on the new window, click Save file..., and save the modified file somewhere. Then replace your original DLL with the modified DLL.

okay i will try Sir 
Thank for your reply sir )
## Post #16
- Username: bilat1234
- Rank: beginner
- Number of posts: 23
- Joined date: Sun Sep 21, 2014 7:18 pm
- Post datetime: 2014-10-07T23:38:14+00:00
- Post Title: Re: TAKE A LOOK !

> Reply from GMMan
>
> The numbers to change is at instruction VA 0x2003880a, 0x20038827, 0x20038f24, 0x20038f3d, 0x20039429 and 0x20039446. Note that if you change the number, the game could crash if they statically allocate a maximum buffer size for 9000 indices instead of dynamically allocating it.

 Sir just to clarify 
this are the address you said ?? 
VA 0x2003880a, 0x20038827, 0x20038f24, 0x20038f3d, 0x20039429 and 0x20039446 ??
## Post #17
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-10-08T00:36:25+00:00
- Post Title: Re: TAKE A LOOK !

that's the addressess where the instruction starts, the data (0x2328=9000 dec.) to be changed is at address+1:
(data in code is 28 23 because of little endian, low byte, high byte)

```
2003880F  |.  7E 5B         |JLE SHORT 2003886C
---------
>> 20038827  |.  68 28230000   |PUSH 2328                               ; /<%d> = 9000.
2003882C  |.  8D0440        |LEA EAX,[EAX*2+EAX]                     ; |
2003882F  |.  50            |PUSH EAX                                ; |<%d>
20038830  |.  8D85 F0FEFFFF |LEA EAX,[EBP-110]                       ; |
20038836  |.  68 70080620   |PUSH OFFSET 20060870                    ; |Format = "Num IB : %d Max IB : %d"
2003883B  |.  50            |PUSH EAX                                ; |Arg1 => ARG.EBP-110
2003883C  |.  E8 6FC60000   |CALL 20044EB0                           ; \HT3DHeaven.20044EB0
20038841  |.  83C4 10       |ADD ESP,10
20038844  |.  6A 00         |PUSH 0
20038846  |.  68 58080620   |PUSH OFFSET 20060858                    ; ASCII "SkinnedMesh IB Overflow"

---------

200388C2  |.  E8 69C70000   CALL 20045030                            ; [HT3DHeaven.20045030
200388C7  |.  57            PUSH EDI                                 ; /<%d> => 3000.
200388C8  |.  FF76 10       PUSH DWORD PTR DS:[ESI+10]               ; |<%d>
200388CB  |.  8D85 F0FDFFFF LEA EAX,[EBP-210]                        ; |
200388D1  |.  68 40080620   PUSH OFFSET 20060840                     ; |Format = "Num VB : %d Max VB : %d"
200388D6  |.  50            PUSH EAX                                 ; |Arg1 => ARG.EBP-210
200388D7  |.  C745 FC 01000 MOV DWORD PTR SS:[EBP-4],1               ; |
200388DE  |.  E8 CDC50000   CALL 20044EB0                            ; \HT3DHeaven.20044EB0
200388E3  |.  83C4 10       ADD ESP,10
200388E6  |.  6A 00         PUSH 0
200388E8  |.  68 28080620   PUSH OFFSET 20060828                     ; ASCII "SkinnedMesh VB Overflow"


>> 20038F24  |.  3D 28230000   |CMP EAX,2328
20038F29  |.  7E 5C         |JLE SHORT 20038F87
---------
>> 20038F3D  |.  68 28230000   |PUSH 2328                               ; /<%d> = 9000.
20038F42  |.  8D0440        |LEA EAX,[EAX*2+EAX]                     ; |
20038F45  |.  50            |PUSH EAX                                ; |<%d>
20038F46  |.  8D85 F0FEFFFF |LEA EAX,[EBP-110]                       ; |
20038F4C  |.  68 70080620   |PUSH OFFSET 20060870                    ; |Format = "Num IB : %d Max IB : %d"
20038F51  |.  50            |PUSH EAX                                ; |Arg1 => ARG.EBP-110
20038F52  |.  895D FC       |MOV DWORD PTR SS:[EBP-4],EBX            ; |
20038F55  |.  E8 56BF0000   |CALL 20044EB0                           ; \HT3DHeaven.20044EB0
20038F5A  |.  83C4 10       |ADD ESP,10
20038F5D  |.  53            |PUSH EBX                                ; /Type
20038F5E  |.  68 58080620   |PUSH OFFSET 20060858                    ; |Caption = "SkinnedMesh IB Overflow"

---------

>> 20039429  |.  3D 28230000   |CMP EAX,2328
2003942E  |.  7E 5B         |JLE SHORT 2003948B
---------
>> 20039446  |.  68 28230000   |PUSH 2328                               ; /<%d> = 9000.
2003944B  |.  8D0440        |LEA EAX,[EAX*2+EAX]                     ; |
2003944E  |.  50            |PUSH EAX                                ; |<%d>
2003944F  |.  8D85 F0FEFFFF |LEA EAX,[EBP-110]                       ; |
20039455  |.  68 70080620   |PUSH OFFSET 20060870                    ; |Format = "Num IB : %d Max IB : %d"
2003945A  |.  50            |PUSH EAX                                ; |Arg1 => ARG.EBP-110
2003945B  |.  E8 50BA0000   |CALL 20044EB0                           ; \HT3DHeaven.20044EB0
20039460  |.  83C4 10       |ADD ESP,10
20039463  |.  6A 00         |PUSH 0
20039465  |.  68 58080620   |PUSH OFFSET 20060858                    ; ASCII "SkinnedMesh IB Overflow"

---------

200394E1  |.  E8 4ABB0000   CALL 20045030                            ; [HT3DHeaven.20045030
200394E6  |.  57            PUSH EDI                                 ; /<%d> => 3000.
200394E7  |.  FF76 10       PUSH DWORD PTR DS:[ESI+10]               ; |<%d>
200394EA  |.  8D85 F0FDFFFF LEA EAX,[EBP-210]                        ; |
200394F0  |.  68 40080620   PUSH OFFSET 20060840                     ; |Format = "Num VB : %d Max VB : %d"
200394F5  |.  50            PUSH EAX                                 ; |Arg1 => ARG.EBP-210
200394F6  |.  C745 FC 01000 MOV DWORD PTR SS:[EBP-4],1               ; |
200394FD  |.  E8 AEB90000   CALL 20044EB0                            ; \HT3DHeaven.20044EB0
20039502  |.  83C4 10       ADD ESP,10
20039505  |.  6A 00         PUSH 0
20039507  |.  68 28080620   PUSH OFFSET 20060828                     ; ASCII "SkinnedMesh VB Overflow"
```


but I guess you'll also have to handle the VB overflow. You'll need some basic debugging skills to find out where
the 3000 is defined (if so).
## Post #18
- Username: bilat1234
- Rank: beginner
- Number of posts: 23
- Joined date: Sun Sep 21, 2014 7:18 pm
- Post datetime: 2014-10-08T00:41:44+00:00
- Post Title: Re: TAKE A LOOK !

> Reply from shakotay2
>
> that's the addressess where the instruction starts, the data to be changed is at address+1:
Code: Select all>> 2003880A  |.  3D 28230000   |CMP EAX,2328
2003880F  |.  7E 5B         |JLE SHORT 2003886C
---------
>> 20038827  |.  68 28230000   |PUSH 2328                               ; /<%d> = 9000.
2003882C  |.  8D0440        |LEA EAX,[EAX*2+EAX]                     ; |
2003882F  |.  50            |PUSH EAX                                ; |<%d>
20038830  |.  8D85 F0FEFFFF |LEA EAX,[EBP-110]                       ; |
20038836  |.  68 70080620   |PUSH OFFSET 20060870                    ; |Format = "Num IB : %d Max IB : %d"
2003883B  |.  50            |PUSH EAX                                ; |Arg1 => ARG.EBP-110
2003883C  |.  E8 6FC60000   |CALL 20044EB0                           ; \HT3DHeaven.20044EB0
20038841  |.  83C4 10       |ADD ESP,10
20038844  |.  6A 00         |PUSH 0
20038846  |.  68 58080620   |PUSH OFFSET 20060858                    ; ASCII "SkinnedMesh IB Overflow"

---------

200388C2  |.  E8 69C70000   CALL 20045030                            ; [HT3DHeaven.20045030
200388C7  |.  57            PUSH EDI                                 ; /<%d> => 3000.
200388C8  |.  FF76 10       PUSH DWORD PTR DS:[ESI+10]               ; |<%d>
200388CB  |.  8D85 F0FDFFFF LEA EAX,[EBP-210]                        ; |
200388D1  |.  68 40080620   PUSH OFFSET 20060840                     ; |Format = "Num VB : %d Max VB : %d"
200388D6  |.  50            PUSH EAX                                 ; |Arg1 => ARG.EBP-210
200388D7  |.  C745 FC 01000 MOV DWORD PTR SS:[EBP-4],1               ; |
200388DE  |.  E8 CDC50000   CALL 20044EB0                            ; \HT3DHeaven.20044EB0
200388E3  |.  83C4 10       ADD ESP,10
200388E6  |.  6A 00         PUSH 0
200388E8  |.  68 28080620   PUSH OFFSET 20060828                     ; ASCII "SkinnedMesh VB Overflow"


>> 20038F24  |.  3D 28230000   |CMP EAX,2328
20038F29  |.  7E 5C         |JLE SHORT 20038F87
---------
>> 20038F3D  |.  68 28230000   |PUSH 2328                               ; /<%d> = 9000.
20038F42  |.  8D0440        |LEA EAX,[EAX*2+EAX]                     ; |
20038F45  |.  50            |PUSH EAX                                ; |<%d>
20038F46  |.  8D85 F0FEFFFF |LEA EAX,[EBP-110]                       ; |
20038F4C  |.  68 70080620   |PUSH OFFSET 20060870                    ; |Format = "Num IB : %d Max IB : %d"
20038F51  |.  50            |PUSH EAX                                ; |Arg1 => ARG.EBP-110
20038F52  |.  895D FC       |MOV DWORD PTR SS:[EBP-4],EBX            ; |
20038F55  |.  E8 56BF0000   |CALL 20044EB0                           ; \HT3DHeaven.20044EB0
20038F5A  |.  83C4 10       |ADD ESP,10
20038F5D  |.  53            |PUSH EBX                                ; /Type
20038F5E  |.  68 58080620   |PUSH OFFSET 20060858                    ; |Caption = "SkinnedMesh IB Overflow"

---------

>> 20039429  |.  3D 28230000   |CMP EAX,2328
2003942E  |.  7E 5B         |JLE SHORT 2003948B
---------
>> 20039446  |.  68 28230000   |PUSH 2328                               ; /<%d> = 9000.
2003944B  |.  8D0440        |LEA EAX,[EAX*2+EAX]                     ; |
2003944E  |.  50            |PUSH EAX                                ; |<%d>
2003944F  |.  8D85 F0FEFFFF |LEA EAX,[EBP-110]                       ; |
20039455  |.  68 70080620   |PUSH OFFSET 20060870                    ; |Format = "Num IB : %d Max IB : %d"
2003945A  |.  50            |PUSH EAX                                ; |Arg1 => ARG.EBP-110
2003945B  |.  E8 50BA0000   |CALL 20044EB0                           ; \HT3DHeaven.20044EB0
20039460  |.  83C4 10       |ADD ESP,10
20039463  |.  6A 00         |PUSH 0
20039465  |.  68 58080620   |PUSH OFFSET 20060858                    ; ASCII "SkinnedMesh IB Overflow"

---------

200394E1  |.  E8 4ABB0000   CALL 20045030                            ; [HT3DHeaven.20045030
200394E6  |.  57            PUSH EDI                                 ; /<%d> => 3000.
200394E7  |.  FF76 10       PUSH DWORD PTR DS:[ESI+10]               ; |<%d>
200394EA  |.  8D85 F0FDFFFF LEA EAX,[EBP-210]                        ; |
200394F0  |.  68 40080620   PUSH OFFSET 20060840                     ; |Format = "Num VB : %d Max VB : %d"
200394F5  |.  50            PUSH EAX                                 ; |Arg1 => ARG.EBP-210
200394F6  |.  C745 FC 01000 MOV DWORD PTR SS:[EBP-4],1               ; |
200394FD  |.  E8 AEB90000   CALL 20044EB0                            ; \HT3DHeaven.20044EB0
20039502  |.  83C4 10       ADD ESP,10
20039505  |.  6A 00         PUSH 0
20039507  |.  68 28080620   PUSH OFFSET 20060828                     ; ASCII "SkinnedMesh VB Overflow"

but I guess you'll also have to handle the VB overflow. You'll need some basic debugging skills to find out where
the 3000 is defined (if so).

yes sir ..

so how to changed the value sir ?? 
i'm sorry Sir .
i dunno how to debugg
## Post #19
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-10-08T00:46:33+00:00
- Post Title: Re: TAKE A LOOK !

GMMan explained it. Do you have OllyDbg?

The 3000 to be changed is here:
200388B3  |.  BF B80B0000   MOV EDI,0BB8
200388B8  |.  3BC7          CMP EAX,EDI
and here
200394D2  |.  BF B80B0000   MOV EDI,0BB8
200394D7  |.  3BC7          CMP EAX,EDI

20002ED7  |.  68 B80B0000   PUSH 0BB8  << not sure

edit: 20002EFB  |.  68 28230000   |PUSH 2328 << not sure

You also could use a hexeditor. Search for 28230000 (7 finds) and B80B0000 (3 finds).
## Post #20
- Username: bilat1234
- Rank: beginner
- Number of posts: 23
- Joined date: Sun Sep 21, 2014 7:18 pm
- Post datetime: 2014-10-08T00:55:15+00:00
- Post Title: Re: TAKE A LOOK !

> Reply from shakotay2
>
> GMMan explained it. Do you have OllyDbg?

The 3000 to be changed is here:
200388B3  |.  BF B80B0000   MOV EDI,0BB8
200388B8  |.  3BC7          CMP EAX,EDI
and here
200394D2  |.  BF B80B0000   MOV EDI,0BB8
200394D7  |.  3BC7          CMP EAX,EDI

You also could use a hexeditor. Search for 28230000 (7 finds) and B80B0000 (3 finds).
Guess you've to exclude one find because in the code there are only 6 resp. 3 places.

sir if you dont mind 
can you send to me the one you edit ?
i just have to try it here on my pc ..
please ?
## Post #21
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-10-08T01:00:23+00:00
- Post Title: Re: TAKE A LOOK !

yes, but it's late here and I've to fall asleep now.

If you didn't manage it for yourself I'll post the edited dll tomorrow.

Good night.
## Post #22
- Username: bilat1234
- Rank: beginner
- Number of posts: 23
- Joined date: Sun Sep 21, 2014 7:18 pm
- Post datetime: 2014-10-08T01:01:26+00:00
- Post Title: Re: TAKE A LOOK !

> Reply from shakotay2
>
> yes, but it's late here and I've to fall asleep now.

If you didn't manage it for yourself I'll post the edited dll tomorrow.

Good night.

Thank you Very Much Sir ) 

Good night too
## Post #23
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2014-10-08T04:59:44+00:00
- Post Title: Re: TAKE A LOOK !

I'll do it for you this time only. If you want to get deeper into game modding, you really need to learn how to use a debugger. Just start by stepping through the code and seeing how it changes the registers and stack.

Both IB and VB buffer sizes have been doubled.
[HT3DHeaven_double_IB_VB.zip](https://xentaxbackup.github.io/file/7898_HT3DHeaven_double_IB_VB.zip)
## Post #24
- Username: bilat1234
- Rank: beginner
- Number of posts: 23
- Joined date: Sun Sep 21, 2014 7:18 pm
- Post datetime: 2014-10-08T05:08:17+00:00
- Post Title: Re: TAKE A LOOK !

> Reply from GMMan
>
> I'll do it for you this time only. If you want to get deeper into game modding, you really need to learn how to use a debugger. Just start by stepping through the code and seeing how it changes the registers and stack.

Both IB and VB buffer sizes have been doubled.

okay sir 
i will try
## Post #25
- Username: bilat1234
- Rank: beginner
- Number of posts: 23
- Joined date: Sun Sep 21, 2014 7:18 pm
- Post datetime: 2014-10-08T05:18:21+00:00
- Post Title: Re: TAKE A LOOK !

Still got error sir
## Post #26
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-10-08T10:46:07+00:00
- Post Title: Re: TAKE A LOOK !

you could use a hexeditor to edit 20 bytes as shown in the code:
replaced B8 0B by 2F 75   (3000 -> 29999)
replaced 28 23 by D2 F0   (9000 -> 61650)

1. column: address
2. column: original byte
3. column: patched byte
Offsets: hexadec.

```
 2ED9:	0B	75
 2EFC:	28	D2
 2EFD:	23	F0
3880B:	28	D2
3880C:	23	F0
38828:	28	D2
38829:	23	F0
388B4:	B8	2F
388B5:	0B	75
38F25:	28	D2
38F26:	23	F0
38F3E:	28	D2
38F3F:	23	F0
3942A:	28	D2
3942B:	23	F0
39447:	28	D2
39448:	23	F0
394D3:	B8	2F
394D4:	0B	75
```

use the patched dll ON YOUR OWN RISK only.
Don't blame me for any loss or damage.

make backup copies of ALL your important data before
keep a copy of the original dll
keep copies of your savegames
why?

the use of patched executables or dlls is NOT safe!
There maybe unexpected results.

At least the game may crash at worst data damage might occur.

YOU HAVE BEEN WARNED!

The dll contains a limit for IB and VB. 
This game might use a file buffer with fixed size.

The patch exceeds the limits so a buffer overflow might occur (== crash)

In case everything works as expected I wouldn't rely on savegames 
which are created with the patched dll in use.

with this said:
good luck, Cmdr Kirk
## Post #27
- Username: bilat1234
- Rank: beginner
- Number of posts: 23
- Joined date: Sun Sep 21, 2014 7:18 pm
- Post datetime: 2014-10-08T10:55:45+00:00
- Post Title: Re: TAKE A LOOK !

> Reply from shakotay2
>
> you could use a hexeditor to edit 20 bytes as shown in the code:
replaced B8 0B by 2F 75   (3000 -> 29999)
replaced 28 23 by D2 F0   (9000 -> 61650)

1. column: address
2. column: original byte
3. column: patched byte
Offsets: hexadec.
Code: Select all 2ED8:	B8	2F
 2ED9:	0B	75
 2EFC:	28	D2
 2EFD:	23	F0
3880B:	28	D2
3880C:	23	F0
38828:	28	D2
38829:	23	F0
388B4:	B8	2F
388B5:	0B	75
38F25:	28	D2
38F26:	23	F0
38F3E:	28	D2
38F3F:	23	F0
3942A:	28	D2
3942B:	23	F0
39447:	28	D2
39448:	23	F0
394D3:	B8	2F
394D4:	0B	75
use this patched dll ON YOUR OWN RISK only.
Don't blame me for any loss or damage.

make backup copies of ALL your important data before
keep a copy of the original dll
keep copies of your savegames
why?

the use of patched executables or dlls is NOT safe!
There maybe unexpected results.

At least the game may crash at worst data damage might occur.

YOU HAVE BEEN WARNED!

The dll contains a limit for IB and VB. 
This game might use a file buffer with fixed size.

The patch exceeds the limits so a buffer overflow might occur (== crash)

In case everything works as expected I wouldn't rely on savegames 
which are created with the patched dll in use.

with this said:
good luck, Cmdr Kirk

okay sir i will try
## Post #28
- Username: bilat1234
- Rank: beginner
- Number of posts: 23
- Joined date: Sun Sep 21, 2014 7:18 pm
- Post datetime: 2014-10-08T11:06:32+00:00
- Post Title: Re: TAKE A LOOK !

Still got error sir
## Post #29
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-10-08T11:24:09+00:00
- Post Title: Re: TAKE A LOOK !

if the overflow error windows is showing ...Max IB : 29999
you might patch 3 bytes in your patched dll:
2ED9 F0
388B5 F0
394D4 F0

If this doesn't work it will be required to attach OllyDbg to the running game
and debug the problem using breakpoints.
## Post #30
- Username: bilat1234
- Rank: beginner
- Number of posts: 23
- Joined date: Sun Sep 21, 2014 7:18 pm
- Post datetime: 2014-10-08T11:28:32+00:00
- Post Title: Re: TAKE A LOOK !

> Reply from shakotay2
>
> if the overflow error windows is showing ...Max IB : 29999
you might patch 3 bytes in your patched dll:
2ED9 F0
388B5 F0
394D4 F0

If this doesn't work it will be required to attach OllyDbg to the running game
and debug the problem using breakpoints.

Sir can you edit the Ht3DHeaven.dll ??
Then send to me so that i can try it here
i dunno how to attach it to ollyDBg
## Post #31
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2014-10-08T11:45:59+00:00
- Post Title: Re: TAKE A LOOK !

10x buffer sizes.

Note it's likely for the buffers to be allocated with the same size, so this means each model may be taking up nearly 10x the memory it would have taken. Make sure you have plenty of RAM.
[HT3DHeaven_10x_IB_VB.zip](https://xentaxbackup.github.io/file/7899_HT3DHeaven_10x_IB_VB.zip)
## Post #32
- Username: bilat1234
- Rank: beginner
- Number of posts: 23
- Joined date: Sun Sep 21, 2014 7:18 pm
- Post datetime: 2014-10-08T11:56:53+00:00
- Post Title: Re: TAKE A LOOK !

> Reply from GMMan
>
> 10x buffer sizes.

Note it's likely for the buffers to be allocated with the same size, so this means each model may be taking up nearly 10x the memory it would have taken. Make sure you have plenty of RAM.

i'll try this sir GMMan
## Post #33
- Username: bilat1234
- Rank: beginner
- Number of posts: 23
- Joined date: Sun Sep 21, 2014 7:18 pm
- Post datetime: 2014-10-08T12:12:36+00:00
- Post Title: Re: TAKE A LOOK !

It's now Working Sir GMMan 

Thank You Very Much ! )
## Post #34
- Username: gehashel
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Dec 04, 2016 1:08 am
- Post datetime: 2016-12-03T17:13:21+00:00
- Post Title: Re: TAKE A LOOK !

Awesome fix ! Dunno but tihs remembers me [http://bonzi-buddy.com](http://bonzi-buddy.com)
