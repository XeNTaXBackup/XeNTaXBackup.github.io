## Post #1
- Username: ayylmao
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Jun 15, 2015 1:21 am
- Post datetime: 2015-06-22T06:48:54+00:00
- Post Title: Idolm@ster 2 (PS3)

I'd like to pull some files out of Idolm@ster 2 (PS3) such as the game's script or possibly the models (apparently this game uses some of the same formats as the original xbox games so there are already some utilities built for it), but game's resources are all encrypted.  The EBOOT contains some references to AES encryption--more specifically, I've been told that the files are encrypted with AES-192-CBC with IVs inside the file.  And although I don't know how helpful it is, I have noticed that all encrypted resources contain the following hex string near the end of each file:

```
DE 82 02 81 33 C0 80 5E 6E 9A BC 95 62 E0 7D 42 
```

I hope that one of you guys could help figure out the decryption key.

Some resources can be found here (eboot.elf + an encrypted png): mfi.re/?yp4rhyxdyyvyrci,wpbh30399w1kcf9
