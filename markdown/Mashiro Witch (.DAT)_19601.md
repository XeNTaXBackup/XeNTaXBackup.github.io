## Post #1
- Username: grubbinaround
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Mar 07, 2019 8:26 am
- Post datetime: 2019-03-07T19:08:38+00:00
- Post Title: Mashiro Witch (.DAT)

Trying to unpack some .DAT files for a Square Enix mobile Unity game. For some reason, a massive portion of the gameplay assets are in the .DAT format, including mundane stuff like .PNGs, and none of the standard Unity rippers (AssetStudio, UBAE, utinyripper) seem to work. If anybody could help or tell me what I'm doing wrong, that would be much appreciated. 


Samples:
[https://drive.google.com/open?id=1C6UQS ... dn9a-KkYhl](https://drive.google.com/open?id=1C6UQSlsNmLhpKqgYnVzNRrdn9a-KkYhl)
Pretty sure these are all 3D models, since they're in the same size range as other .objs I found earlier. Not seeing anything that would be helpful in a hex editor such as an obvious header or filetype in the string. 



When using the script from here: [https://forum.xentax.com/viewtopic.php? ... 69#p144504](https://forum.xentax.com/viewtopic.php?f=16&t=18869#p144504) from Bigchillghost for dat unpacking, I get:

> - error in src\file.c line 487: fdnum_open()
>
> Error: No such file or directory
>
> 
>
> Last script line before the error or that produced the error:
>
>   8   open "." Name 1
