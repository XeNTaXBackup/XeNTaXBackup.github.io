## Post #1
- Username: Rainman
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Jun 05, 2014 8:55 pm
- Post datetime: 2014-06-05T22:51:56+00:00
- Post Title: Star Citizen now Encrypting ....

Star Citizen (Cryengine) has released their Arena Commander module, and have now encrypted their 'scripts.pak' which is preventing modders from continuing their work.
Ive seen talk on here about decrypting cryengine .pak files, and was wondering if anyone could help? I have no idea how to get the key needed myself. 
So any help would be appreciated
## Post #2
- Username: masterX244
- Rank: beginner
- Number of posts: 31
- Joined date: Tue Aug 17, 2010 12:48 am
- Post datetime: 2014-06-13T17:30:52+00:00
- Post Title: Star Citizen now Encrypting ....

poked a bit around in the depth of this forum (remembered that there was something related to cryengine and encryption)
[viewtopic.php?f=10&t=9818&hilit=crysis+encrypt&start=30](http://forum.xentax.com/viewtopic.php?f=10&t=9818&hilit=crysis+encrypt&start=30)

(goin to post more details here if i get more dug out)
## Post #3
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2014-06-15T13:40:42+00:00
- Post Title: Star Citizen now Encrypting ....

It's the same method Crysis 3 uses with a different key. The Star Citizen key is:

```
    0x30, 0x81, 0x89, 0x02, 0x81, 0x81, 0x00, 0xF4, 0x6F, 0x92, 0x32, 0x80, 0xAC, 0x43, 0x08, 0x86, 0x8C, 0x30, 0x99, 0x76, 0x4B, 0x7F, 0xE4, 0xFB, 0x4F, 0x54, 0xFD, 0x26, 0xFB, 0xFF, 0x5F, 0xE1, 
    0x02, 0x92, 0x57, 0x1D, 0xFA, 0x14, 0xF7, 0x69, 0xB3, 0xE3, 0xE4, 0x96, 0x76, 0x7B, 0x6E, 0x5F, 0xA7, 0x9E, 0x8B, 0x7C, 0xF2, 0xB7, 0xAE, 0xFF, 0x96, 0x67, 0x30, 0xE8, 0xA4, 0x48, 0x3F, 0x28, 
    0x80, 0xEF, 0x75, 0xA1, 0x87, 0xBB, 0xCC, 0x7D, 0x1D, 0x56, 0x8C, 0xD6, 0xE4, 0x13, 0x07, 0xFF, 0x52, 0x64, 0x15, 0xD5, 0xEC, 0x1F, 0x63, 0xA1, 0x47, 0xD6, 0xD8, 0x6F, 0xD3, 0xF2, 0x54, 0xB8, 
    0x8F, 0xC5, 0x6C, 0xB9, 0x39, 0xDA, 0x19, 0xA8, 0x3F, 0x67, 0xC1, 0xBA, 0x52, 0x3E, 0xF4, 0x45, 0x7C, 0x55, 0xB5, 0xE7, 0xCD, 0x4E, 0xEA, 0x6D, 0x2B, 0x35, 0x97, 0x4A, 0x96, 0x80, 0x29, 0xFA, 
    0xEE, 0xAD, 0xD4, 0xCE, 0x73, 0x36, 0xAF, 0x02, 0x03, 0x01, 0x00, 0x01, 
} ;
```
