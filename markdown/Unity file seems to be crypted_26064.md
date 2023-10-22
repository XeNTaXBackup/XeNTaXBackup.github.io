## Post #1
- Username: lishaoran00
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jul 05, 2017 10:11 am
- Post datetime: 2022-12-06T18:11:05+00:00
- Post Title: Unity file seems to be crypted

Hi, I tryed to open this asset file using the last version of (Perfare) AssetStudio but the program couldn't open it, I have an uncrypted version of the file from a previous version of the game, the game name is "庫洛魔法使回憶鑰匙" and is currently in beta. Could anyone take a look?

Crypted


Uncrypted


[https://www.mediafire.com/file/xybid6rj ... d.jpg/file](https://www.mediafire.com/file/xybid6rj22ca4qs/dresscg_s001_01_crypted.jpg/file)
[https://www.mediafire.com/file/1chehuoq ... d.jpg/file](https://www.mediafire.com/file/1chehuoqyh7r9ff/dresscg_s001_01_uncrypted.jpg/file)
## Post #2
- Username: andree
- Rank: veteran
- Number of posts: 149
- Joined date: Sun Jul 09, 2017 8:36 pm
- Post datetime: 2023-03-08T21:59:27+00:00
- Post Title: Unity file seems to be crypted

```

def invert_xor(data: memoryview):
    end_index = len(data) - 1
    for i in range(1024):
        data[i] ^= data[end_index]
        end_index -= 1

fl = memoryview(bytearray(open(pt, "rb").read()))

invert_xor(fl)

open("decrypted.dat", "wb").write(fl)
```

Python is required in order for this to be used.
Give credit to Joseph from the unitypy server for making this.
