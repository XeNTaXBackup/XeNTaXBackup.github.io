## Post #1
- Username: WarGrey
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Apr 16, 2021 6:32 am
- Post datetime: 2021-04-15T22:46:53+00:00
- Post Title: Digimon Encounters Encrypted(?) PNG textures

Hello there. Long time lurker here. This forum assisted me a lot, so thank you all for that. 

I've been ripping models from certain Digimon games and this time it's this game's turn. 

Issue at hand:

Textures are encrypted, I suppose, I usually look at the files to see their headers and such to get an idea and google my way to break them but these PNG files are weird. They have no header that human eye can read, so I presume they are encrypted in a different way than I'm used to come across. Here are a couple of them:

[https://www.mediafire.com/file/ksb0rm9c ... s.zip/file](https://www.mediafire.com/file/ksb0rm9c4rq84g6/DigimonEncountersTextures.zip/file) 

Since model format is known Cocos c3b, there is no issues on getting the meshes but textures are just as important, help is much appreciated.
Thank you.
## Post #2
- Username: aspadm
- Rank: advanced
- Number of posts: 52
- Joined date: Thu Nov 26, 2015 3:43 am
- Post datetime: 2021-04-22T21:21:08+00:00
- Post Title: Digimon Encounters Encrypted(?) PNG textures

Files are encrypted with XXTEA algorithm which is commonly used in cocos2d games.

First two bytes is XT signature, which must be skipped before decryption.

Example of image decoding (Python3 + xxtea library):

```

if __name__ == "__main__":
    with open("chr755a01.png", "rb") as f:
        sign = f.read(2) # b"XT"
        data = f.read()
    dec = xxtea.decrypt(data, b"140818\0\0\0\0\0\0\0\0\0\0", padding=False)

    with open("chr755a01.dec.png", "wb") as f:
        f.write(dec)
```
## Post #3
- Username: WarGrey
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Apr 16, 2021 6:32 am
- Post datetime: 2021-09-24T22:11:05+00:00
- Post Title: Digimon Encounters Encrypted(?) PNG textures

Thanks a lot and sorry for late reply. I was busy with other ripping projects. This should be helpful, I don't know anything about Python but I got good and talented friends that do. Thanks a lot again!
