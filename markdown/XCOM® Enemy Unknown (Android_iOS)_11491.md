## Post #1
- Username: Barbos
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue May 06, 2014 10:47 pm
- Post datetime: 2014-05-07T14:43:18+00:00
- Post Title: XCOM®: Enemy Unknown (Android\iOS)

Game: XCOM®: Enemy Unknown (Android)
Unpack script for cache (*.obb):

```
idstring "UE3AndroidOBB"
get FILES long
for i = 0 < FILES
	get NAMEZ long
	GetDString NAME NAMEZ
	get OFFSET long
	get DUMMY long
	get SIZE long
	log NAME OFFSET SIZE
next i
```


but I can not find the key to decrypt the file: Coalesced_INT.bin 
Coalesced_INT.bin (Android) [http://rghost.ru/55012685](http://rghost.ru/55012685)
Coalesced_INT.bin (iOS) [http://rghost.ru/55012703](http://rghost.ru/55012703)
