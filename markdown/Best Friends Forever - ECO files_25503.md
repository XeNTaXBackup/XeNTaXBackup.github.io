## Post #1
- Username: sandmanfan98
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Oct 05, 2017 4:06 pm
- Post datetime: 2022-06-07T09:46:34+00:00
- Post Title: Best Friends Forever - ECO files

The files were originally XML suggested by the fact that Water Bugs, another Retro64 game with the same format, has an executable to convert XML's to ECO.

Samples + converter
[https://mega.nz/file/VsdhWLKZ#KF4rT-OzV ... S6iLhvlQzs](https://mega.nz/file/VsdhWLKZ#KF4rT-OzVcCN0i5uCLls4jB8Ld9VYzuiRS6iLhvlQzs)
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-06-07T20:12:54+00:00
- Post Title: Best Friends Forever - ECO files

This "Encrypto!" converter is a nice find.
I did a little research and it seems that encryption algorithm is currently unknown (undocumented),
but I've gathered some information here [http://wiki.xentax.com/index.php/Retro64_ECO](http://wiki.xentax.com/index.php/Retro64_ECO)

I may take a look at this encryption method later (but i can't promise anything).
## Post #3
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2022-06-07T22:37:18+00:00
- Post Title: Best Friends Forever - ECO files

Here is quickbms script, which is doing the same as the tool, but both ways (decryption/encryption). You can set key and direction in the script manually.



 encrypto_eco.zip
(425 Bytes) Downloaded 18 times
## Post #4
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-06-07T23:14:54+00:00
- Post Title: Best Friends Forever - ECO files

It turns out "Encrypto" uses symetric XOR algorithm, so it is possible to encrypt/decrypt using the same logic.

Here is my tool for converting XML to ECO and ECO to XML
[https://github.com/bartlomiejduda/Tools ... ECO%20Tool](https://github.com/bartlomiejduda/Tools/tree/master/NEW%20Tools/Retro64/Retro64%20ECO%20Tool)

As I have checked "Water Bugs" and "Best Friends Forever" use the same key which is 49152.

I've also updated the wiki article.
