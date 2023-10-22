## Post #1
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2010-07-28T22:47:21+00:00
- Post Title: QuickBMS help?

[out]
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-08-01T14:09:35+00:00
- Post Title: QuickBMS help?

for the interpretation of the results received by peid krypto you must refer to its manual.
I suggest you to make the test also with [signsrch](http://aluigi.org/mytoolz.htm#signsrch) to know if the results and the signatures match

now if you want to set a binary key there is no problem because the key in the Encryption field is handled as a C string so if you want to use a key composed by the bytes 0x11 0x22 and 0x33 you must use "\x11\x22\x33"

for using the md5 of a string as key I suggest to wait some hours when I will release a new version of quickbms (0.4.6a) with a small enhancement that will allow to do the whole operation simply using:

```
encryption md5 ""
string TMP E= TMP # 'E' is different than 'e'!
encryption xtea QUICKBMS_HASH
get SIZE asize
log "decrypted_file.dat" 0 SIZE
```
you can do it already now with the current version of the tool but it's more laborious because you should use a memory file, so it's better to wait :)

if the 16bytes key is located in the file you must simply read it as a variable and then specifying its size otherwise Encryption will take the length of the key till the first NULL byte as size:

```
encryption xtea KEY "" 0 16
...
```
## Post #3
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2010-08-01T21:04:02+00:00
- Post Title: QuickBMS help?

[out]
