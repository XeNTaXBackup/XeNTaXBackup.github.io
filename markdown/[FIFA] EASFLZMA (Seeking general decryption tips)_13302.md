## Post #1
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2015-09-09T19:02:07+00:00
- Post Title: [FIFA] EASF/LZMA (Seeking general decryption tips)

Hi,
I have never dealt with encryption outside regular zlib compression
I recently found this[blog](https://fifa15gamemodding.wordpress.com/) claiming to have cracked the encryption but there is no tool available at the moment
I really have no clue as to how to apply this knowledge
Any tips?

Here is an example file of the before and after
[board.rar](https://xentaxbackup.github.io/file/9717_board.rar)
## Post #2
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2015-09-10T01:56:28+00:00
- Post Title: [FIFA] EASF/LZMA (Seeking general decryption tips)

[correct link](https://fifa15gamemodding.wordpress.com/about/)

Some guy managed to do it using the games exe

```

is 'EASF'
call keygen addr (addr1);
check filesize; (example: ZSIZE: 432, SIZE=8640)
FileChunk(name:\"[...]%s\", block:%d, size:%dk) 
FileChunk(name:\"%s\", block:%d, size:%dk) 
get and read EASF filesize (432);
generate aes 128 key;
call genkey/setkey addr (addr2);
handshake with assetcryptokeys + keyID;
genkey/setkey to EASF file that is being read;
open handle/decrypted; (filesize = 8640)
closefile when needed (if);

```
