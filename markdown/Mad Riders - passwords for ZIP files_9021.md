## Post #1
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2012-06-01T10:17:23+00:00
- Post Title: Mad Riders - passwords for ZIP files

Hi,
Mad Riders\MadRiders\DataEn.pak
Mad Riders\MadRiders\Data0.pak
Mad Riders\MadRiders\Data1.pak
Mad Riders\MadRiders\Data2.pak
This is password-protected zip-files

Who can get the passwords?
## Post #2
- Username: delutto
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2012-06-01T14:00:30+00:00
- Post Title: Mad Riders - passwords for ZIP files

Pass for DataEn.pak - TN2kTjNmBvn5axaS6tGX
Thx kagym
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-06-01T18:34:32+00:00
- Post Title: Mad Riders - passwords for ZIP files

oh come on, you beat me only because I went outside with my bike before working on it :)

anyway:

offset 0x1ed80 of filesystem_x86.dll
Code: Select all1000D7D0  /$ C702 78563412  MOV DWORD PTR DS:[EDX],12345678 ; zipcrypto
1000D7D6  |. C742 04 896745>MOV DWORD PTR DS:[EDX+4],23456789
1000D7DD  |. C742 08 907856>MOV DWORD PTR DS:[EDX+8],34567890
1000D7E4  |. 8A0D 80010210  MOV CL,BYTE PTR DS:[10020180]
1000D7EA  |. 56             PUSH ESI
1000D7EB  |. BE 80010210    MOV ESI,filesyst.10020180 ; password
xor that sequence of 20 bytes with 0xd5
Code: Select all1000D8AD  |. B1 D5          MOV CL,0D5 ; xor key
1000D8AF  |. 90             NOP
1000D8B0  |> 3088 80010210  /XOR BYTE PTR DS:[EAX+10020180],CL
1000D8B6  |. 40             |INC EAX
1000D8B7  |. 83F8 14        |CMP EAX,14
1000D8BA  |.^72 F4          \JB SHORT filesyst.1000D8B0I hope it's interesting
## Post #4
- Username: Elephantkilla
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Jul 01, 2018 3:29 am
- Post datetime: 2023-01-26T12:58:19+00:00
- Post Title: Mad Riders - passwords for ZIP files

Hi guys. can you help unpack these archives, which also have a password set 
These are archives from two games: "Russian Street Racing" and "Советский Автоспорт Racing Show"

I tried to find a password with the help of programs, but nothing came out. The computer picked up passwords all day and to no avail
[https://disk.yandex.ru/d/bLozU14HCU_bkw](https://disk.yandex.ru/d/bLozU14HCU_bkw)
