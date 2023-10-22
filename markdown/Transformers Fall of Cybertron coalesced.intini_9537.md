## Post #1
- Username: oveja
- Rank: beginner
- Number of posts: 23
- Joined date: Thu Feb 24, 2011 4:35 am
- Post datetime: 2012-08-23T21:23:42+00:00
- Post Title: Transformers: Fall of Cybertron coalesced.int/ini

Unfortunately, xor password is changed.
('as;dwepo2345098]qw]{}p2039458pseasdfzcvvp;aseiurwefsdcfszdcvn' is wrong password)
I don't know how to find the xor password.
Is there any way i can get help or hints?
[Coalesced.7z](https://xentaxbackup.github.io/file/5708_Coalesced.7z)
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-25T14:18:47+00:00
- Post Title: Transformers: Fall of Cybertron coalesced.int/ini

XOR key the same.

```
0049935D    8D49 00         LEA ECX,DWORD PTR DS:[ECX]
00499360    8B06            MOV EAX,DWORD PTR DS:[ESI]
00499362    66:8B0C5D F0D16>MOV CX,WORD PTR DS:[EBX*2+16ED1F0]                 as;dwepo2345098]qw]{}p2039458pseasdfzcvvp;aseiurwefsdcfszdcvn
0049936A    66:310C78       XOR WORD PTR DS:[EAX+EDI*2],CX
0049936E    8D0478          LEA EAX,DWORD PTR DS:[EAX+EDI*2]
00499371    8D43 01         LEA EAX,DWORD PTR DS:[EBX+1]
00499374    99              CDQ
00499375    B9 3D000000     MOV ECX,3D
```


Use [this](http://aluigi.altervista.org/papers/bms/cybertron_coalesced.bms) script.

PS: For Decrypt INI remove line 4 from script -> endian big
## Post #3
- Username: oveja
- Rank: beginner
- Number of posts: 23
- Joined date: Thu Feb 24, 2011 4:35 am
- Post datetime: 2012-08-25T18:41:41+00:00
- Post Title: Transformers: Fall of Cybertron coalesced.int/ini

thank you.
but coalesced.int is can't decrypt...
## Post #4
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-25T19:33:44+00:00
- Post Title: Transformers: Fall of Cybertron coalesced.int/ini

Can you send INT file ?
## Post #5
- Username: oveja
- Rank: beginner
- Number of posts: 23
- Joined date: Thu Feb 24, 2011 4:35 am
- Post datetime: 2012-08-25T21:07:31+00:00
- Post Title: Transformers: Fall of Cybertron coalesced.int/ini

here it is.

[https://rapidshare.com/files/2959814439/Coalesced.int](https://rapidshare.com/files/2959814439/Coalesced.int)

and is there any way to re-encrypt?
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-08-25T22:08:02+00:00
- Post Title: Transformers: Fall of Cybertron coalesced.int/ini

the endianess of this file is different, I guess this one is for PC while the other one I tested the previous time was for x360.
anyway script updated:
[http://aluigi.org/papers/bms/cybertron_coalesced.bms](http://aluigi.org/papers/bms/cybertron_coalesced.bms)
## Post #7
- Username: static77
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Aug 20, 2012 1:37 pm
- Post datetime: 2012-08-26T08:19:55+00:00
- Post Title: Transformers: Fall of Cybertron coalesced.int/ini

aluigi, script works great! 
How to re-encrypt it back?
## Post #8
- Username: vitoci
- Rank: beginner
- Number of posts: 21
- Joined date: Fri Nov 11, 2011 2:24 am
- Post datetime: 2012-08-27T04:34:18+00:00
- Post Title: Transformers: Fall of Cybertron coalesced.int/ini

Aluigi, encrypt .ini,
please!!
## Post #9
- Username: jbeckman
- Rank: advanced
- Number of posts: 43
- Joined date: Wed May 16, 2007 12:13 pm
- Post datetime: 2012-08-27T08:49:37+00:00
- Post Title: Transformers: Fall of Cybertron coalesced.int/ini

Won't the shortcut example included with QuickBMS allow for "repacking" the file back as a encrypted version if used?
(Might need to be done from the command prompt or such.)

Haven't tried it though, probably should as there's some stuff I'd like to reconfigure, also I believe it needs the file to be either the same size or smaller than the original for it to work.
## Post #10
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-08-27T11:49:32+00:00
- Post Title: Transformers: Fall of Cybertron coalesced.int/ini

you can't use the reimport script because it's not an archive, the out file gets generated.

it's possible to write a script for doing the opposite job but there are too much compatibility problem with this format, for example some versions use big and others little endian and then some files uses a particular thing on the size of the lines (unicode stuff if I'm not in error).
## Post #11
- Username: static77
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Aug 20, 2012 1:37 pm
- Post datetime: 2012-08-27T12:04:19+00:00
- Post Title: Transformers: Fall of Cybertron coalesced.int/ini

> Reply from aluigi
>
> you can't use the reimport script because it's not an archive, the out file gets generated.

it's possible to write a script for doing the opposite job but there are too much compatibility problem with this format, for example some versions use big and others little endian and then some files uses a particular thing on the size of the lines (unicode stuff if I'm not in error).
So, it means that decryption is useless, if we can't turn file back
## Post #12
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-08-27T18:45:49+00:00
- Post Title: Transformers: Fall of Cybertron coalesced.int/ini

no, it means that you can write the re-encrypter by yourself.

the format is very easy but there are only those 2 boring things I have explained before.
and I'm not interested in writing a re-encrypt script that must be manually modified by the user for making it compatible with the version of game or the ini file he uses.
## Post #13
- Username: KJTR
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Jul 02, 2015 4:55 pm
- Post datetime: 2015-07-02T09:31:54+00:00
- Post Title: Transformers: Fall of Cybertron coalesced.int/ini

> Reply from aluigi
>
> no, it means that you can write the re-encrypter by yourself.

the format is very easy but there are only those 2 boring things I have explained before.
and I'm not interested in writing a re-encrypt script that must be manually modified by the user for making it compatible with the version of game or the ini file he uses.
<this is not allowed in our board> if you make a tool able to decrypt and then encrypt the ini for xbox version. Aslo If we modify something in the INI, do we have to modify the other file it relates to? Or does the game just not check?
[Screen Shot 07-02-15 at 02.17 AM.PNG](https://xentaxbackup.github.io/file/9369_Screen Shot 07-02-15 at 02.17 AM.PNG)
