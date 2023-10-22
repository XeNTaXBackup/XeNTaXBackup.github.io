## Post #1
- Username: theleonx
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Nov 02, 2017 9:03 am
- Post datetime: 2021-05-12T17:45:03+00:00
- Post Title: JoJo ASB/EOH [PS3/PS4] - sound file _ev.xfbin

Yo, i need help with decoding sound setting file from JoJo ASB/EOH.

This file was used for SFX of movements.

This file actually encoded, but not fully, only text part which was used for name of sound, section where it will be used and name of animation.

Naruto storm games using same file for sound effects and it looks fine, but all jojo sounds are encoded 

I leaved in archive 2 files with JoJo and Naruto _ev file.

I also noticed there was used this code 
```
91 8C 91 9B 9A 89 D1 87 99 9D 96
```

it repeats in code of file and sometimes there can be used a bit different values inside of this 91 8C 91 9B 9A 89 D1 87 99 9D 96 

I hope it's possible to decode jojo _ev file like naruto _ev file

Thanks for any help

jojo sound section [https://imgur.com/Fu9wypS](https://imgur.com/Fu9wypS)
naruto sound section [https://imgur.com/nTtvvXz](https://imgur.com/nTtvvXz)
[Files.rar](https://xentaxbackup.github.io/file/20111_Files.rar)
## Post #2
- Username: SutandoTsukai181
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jul 21, 2020 8:11 pm
- Post datetime: 2021-05-20T21:00:02+00:00
- Post Title: JoJo ASB/EOH [PS3/PS4] - sound file _ev.xfbin

Its just a 32 byte string XOR'd with a key with each 4 bytes of the string reversed (as in, read with swapped endianness).
Here's the key: 
```
0x8C919B9A89D187999D9691
```


Decryptor: [https://gist.github.com/SutandoTsukai18 ... b65dc03bd0](https://gist.github.com/SutandoTsukai181/b0edfb32687ea76cb7b21db65dc03bd0)
Encryptor: [https://gist.github.com/SutandoTsukai18 ... 7cbbe6024e](https://gist.github.com/SutandoTsukai181/ac6473f37ee0a3f49232497cbbe6024e)

Also attached them to this post.
[ev_scripts.zip](https://xentaxbackup.github.io/file/20174_ev_scripts.zip)
