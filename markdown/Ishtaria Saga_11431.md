## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2014-04-18T18:41:33+00:00
- Post Title: Ishtaria Saga

closed beta Client (550 MB): [http://its-patch.ngmstudio.co.kr:8024/p ... _setup.exe](http://its-patch.ngmstudio.co.kr:8024/patch/D/DMM_ITS_CBT_Start_setup.exe) 

I ran an archive through offzip and it found a number of matches.

However, all of the chunks were 128 KB, so presumably the game reads a bunch of chunks, decompresses them, and then concatenates it together in some order defined in the file table. Doing some manual combining it does seem to work that way, but the chunks aren't always sequential.

The file table is encrypted.

Sample: [http://www.mediafire.com/download/q3kza ... sample.zip](http://www.mediafire.com/download/q3kza2rbm22dhp3/sample.zip)
Client: [http://www.mediafire.com/download/udaw7 ... /client.7z](http://www.mediafire.com/download/udaw7fyqbe8rhk5/client.7z)
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-04-19T10:29:12+00:00
- Post Title: Ishtaria Saga

Well it's modified MoPAQ format. Tool for decrypting table in attach. Filenames is hashed. Source's included.
[ITSNSFDecrypt_0.1.rar](https://xentaxbackup.github.io/file/7233_ITSNSFDecrypt_0.1.rar)
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2014-04-19T15:51:52+00:00
- Post Title: Ishtaria Saga

The output file doesn't seem to have anything obvious to use. Has a bunch of

```

```


For about 64 KB and then followed by a bunch of random bytes.
## Post #4
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-04-19T17:05:36+00:00
- Post Title: Ishtaria Saga

W.I.P
## Post #5
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-04-20T21:33:32+00:00
- Post Title: Ishtaria Saga

[Done](http://forum.xentax.com/viewtopic.php?f=10&t=11439)
