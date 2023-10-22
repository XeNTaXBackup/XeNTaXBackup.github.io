## Post #1
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2021-08-25T17:52:47+00:00
- Post Title: EA Los Angeles .ssh format

I'm trying to obtain textures from the following games and I'm alsmost there:

2002 Medal of Honor: Frontline — [SAMPLE1](https://drive.google.com/open?id=1YboL0LCFwsohV0genB7ITG1q5M20A2Tu) ([.ssh noesis preview](https://drive.google.com/open?id=1nL2pAWOcZIksP7lTKiDbUgUAXhGDBpjG)) / [SAMPLE2](https://drive.google.com/open?id=1_wHXH-TsqWArPcA9DzNMLiF0Pxm9GfAl) ([.ssh noesis preview](https://drive.google.com/open?id=1cwszKRrQ9YcSnxpvGiqOsBR1cBaC7i8D))
2003 Medal of Honor: Rising Sun — [SAMPLE1](https://drive.google.com/open?id=1c9l0IpVKJGxNnos9CgxIaPUHjCtn1dTC) ([.ssh noesis preview](https://drive.google.com/open?id=1C3ytR_hPZ2BuVPQP5kGNjsXnRIaTPJZF)) / [SAMLPE2](https://drive.google.com/open?id=1r57P0EQ1Syvz_yXvyyWTym4XT4_c83L0) ([.ssh noesis preview](https://drive.google.com/open?id=1G_CNlsQCZZIzOyYRXk70n33G_D4G4AwN))
2005 Medal of Honor: European Assault — [SAMPLE](https://drive.google.com/open?id=1LxIfgZXxlc30F8YRxGlkRXXMy3J5Ops7) ([.ssh noesis preview](https://drive.google.com/open?id=1k1I0joLDwzH1rtKrt2IrNjJE8afYWlwu))
2007 Medal of Honor: Vanguard — [SAMPLE](https://drive.google.com/open?id=1jzRYr59ASMZ7j_iJAq6gKsxOjqEIs4ik) ([.ssh noesis preview](https://drive.google.com/open?id=1gvTdPSs51odxS9zjRX7QSFHORMSznW06))

All textures are SSH format 2002-2007. It has a weird structure and it's from PS2 so probably files have a "wrong" byte order or something.
I use Acewell noesis script (attached) to view them, but it gives bad result at the moment:


 tex_HarryPotterandtheChamberofSecrets_PS2_ssh.zip
(885 Bytes) Downloaded 27 times



p.s.: I already tried these tools: [http://wiki.xentax.com/index.php/EA_SSH_FSH_Image](http://wiki.xentax.com/index.php/EA_SSH_FSH_Image). none of them seem work that's why I did this thread.
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-08-27T13:50:00+00:00
- Post Title: EA Los Angeles .ssh format

> Reply from Tosyk ↑Thu Aug 26, 2021 1:52 am at Thu Aug 26, 2021 1:52 am
>
> It has a weird structure and it's from PS2 so probably files have a "wrong" byte order or something.
Nope, just ordinary pixel data. 



Begin_HL_ssh.png (77.34 KiB) Viewed 165 times
## Post #3
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-08-27T13:52:04+00:00
- Post Title: EA Los Angeles .ssh format

Noesis script to load this format:


 tex_EA_LosAngeles_ssh.zip
(1.04 KiB) Downloaded 57 times
## Post #4
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2021-08-27T15:52:22+00:00
- Post Title: EA Los Angeles .ssh format

> Reply from Bigchillghost ↑Fri Aug 27, 2021 9:52 pm at Fri Aug 27, 2021 9:52 pm
>
> 
Noesis script to load this format:
tex_EA_LosAngeles_ssh.zipGreat! Appreciate for the help  I carefully checked a lot of examples and the only failed was [that one](https://drive.google.com/open?id=1frA69rSVMD5p6nf5Cg5paMZWXmoZqi9r)
Would you'll be able add to that supported list the textures of this game called Golde Eye Rogue Agent (2001)?
It's from the same company. [Here's example](https://drive.google.com/open?id=1cHXk2VLcw71EbAZNmMHpnibqQHP_VbYx)
## Post #5
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-08-28T10:08:36+00:00
- Post Title: EA Los Angeles .ssh format

> Reply from Tosyk ↑Fri Aug 27, 2021 11:52 pm at Fri Aug 27, 2021 11:52 pm
>
> 
the only failed was that one
Script updated at the same post.

> Reply from Tosyk ↑Fri Aug 27, 2021 11:52 pm at Fri Aug 27, 2021 11:52 pm
>
> 
Would you'll be able add to that supported list the textures of this game called Golde Eye Rogue Agent (2001)?
It's from the same company.
Most of these images are twiddled (except for single_frame_textures.ssh). But unfortunately there's no way to tell whether it's twiddled or not so you'll have to manually change the variable gIsTwiddled at line 4 of the script.
## Post #6
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2021-08-28T11:02:23+00:00
- Post Title: EA Los Angeles .ssh format

thank you! now all the textures work properly.
I created new texture script for Golde Eye Rogue Agent PS2 .ssh files using your script and attached it here just in case
[tex_GoldeEye_RA_ps2_ssh_r2021_08_28.zip](https://xentaxbackup.github.io/file/20708_tex_GoldeEye_RA_ps2_ssh_r2021_08_28.zip)
