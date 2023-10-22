## Post #1
- Username: mappy2012
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-11-02T00:32:10+00:00
- Post Title: Archlord 2 (apk)

Here is a quickbms script for Archlord 2 APK files
[http://archlord2.webzen.co.kr/main/](http://archlord2.webzen.co.kr/main/)
client files

> http://content4mapa.nefficient.co.kr/we ... hlord2.exe
>
> http://content4mapa.nefficient.co.kr/we ... rd2-1a.bin
>
> http://content4mapa.nefficient.co.kr/we ... rd2-1b.bin
the game uses nif files Gamebryo File Format, Version 20.6.0.0

```
get ftable long
get size asize
math size - ftable
goto ftable
comtype unzip_dynamic
clog MEMORY_FILE ftable size size
get files asize MEMORY_FILE
math files / 0x94
for i = 0 < files
getdstring name 0x80 MEMORY_FILE
get one long MEMORY_FILE
get hash long MEMORY_FILE
get size long MEMORY_FILE
get zsize long MEMORY_FILE
get offset long MEMORY_FILE
clog name offset zsize size
next i

```
