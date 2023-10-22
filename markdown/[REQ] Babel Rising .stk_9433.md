## Post #1
- Username: Gruselgurke
- Rank: advanced
- Number of posts: 72
- Joined date: Sat Mar 31, 2012 1:15 am
- Post datetime: 2012-08-08T00:19:36+00:00
- Post Title: [REQ] Babel Rising .stk

A pretty tower defense like action game that got released today.
[http://store.steampowered.com/app/204840/](http://store.steampowered.com/app/204840/)

All game data is within the BR3D_High.stk which is also nearly uncompressable. So I suspect some sort of encryption + zlib or offest zlib compression. Precomp can't find anything atleast.
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-08T13:47:40+00:00
- Post Title: [REQ] Babel Rising .stk

Xored

```
get SIZE asize
log "decrypted_file.dat" 0 SIZE
```
## Post #3
- Username: namquang93
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Apr 09, 2012 3:40 pm
- Post datetime: 2012-08-09T14:43:49+00:00
- Post Title: [REQ] Babel Rising .stk

> Reply from Ekey
>
> Xored
Code: Select allfilexor "\x23\x3B\x5C\x42" 1
get SIZE asize
log "decrypted_file.dat" 0 SIZE
I used that scrypt but it result a file named decrypted_file.dat only
## Post #4
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-09T16:25:13+00:00
- Post Title: [REQ] Babel Rising .stk

Because this script only for decrypt main archive
## Post #5
- Username: Gruselgurke
- Rank: advanced
- Number of posts: 72
- Joined date: Sat Mar 31, 2012 1:15 am
- Post datetime: 2012-08-09T16:58:49+00:00
- Post Title: [REQ] Babel Rising .stk

Thanks for that!
Compressability stayed the same though, I guess there is still some encryption going on here or the game is very well compressed already.
If unpacking is a lot of work for that game I would reject my request, the game is not that cool that it would be worth the work
## Post #6
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-09T20:58:47+00:00
- Post Title: [REQ] Babel Rising .stk

It looks simple but there is a problem with the calculating offsets files. FileTable begin 0x19 offset

```

for
4 bytes - Name Size
String - FileName
4 bytes - Unknown???
4 bytes - Compressed Size
4 bytes - Uncompressed Size
4 bytes - Unknown???
2 bytes - Unknown (04 00 or 05 00)
next
```
## Post #7
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-28T12:47:09+00:00
- Post Title: [REQ] Babel Rising .stk

[here](http://forum.xentax.com/viewtopic.php?f=10&t=9559&p=77952) script
