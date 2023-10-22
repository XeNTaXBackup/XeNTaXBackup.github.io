## Post #1
- Username: MurraySkull
- Rank: advanced
- Number of posts: 48
- Joined date: Sun Nov 26, 2006 10:48 am
- Post datetime: 2018-02-19T11:10:36+00:00
- Post Title: Super Mario Run

[https://www.mediafire.com/file/wsw8kwau ... %20BGM.zip](https://www.mediafire.com/file/wsw8kwaujairrwi/Super%20Mario%20Run%20correct%20BGM.zip)

They seem to be encrypted with AES keys. There's functions like DeALSetting$$get_OggEncryptionAesKey and AssetBundleSetting$$get_SimpleEncryptionKey

I am convinced that the secret lies in libDeALWrapper.so, you can see the disassembly here: [https://www.mediafire.com/file/40wrvvcq ... per.so.txt](https://www.mediafire.com/file/40wrvvcqkcrbvuq/libDeALWrapper.so.txt)
