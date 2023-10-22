## Post #1
- Username: StarkNebula
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Jan 24, 2013 12:06 pm
- Post datetime: 2014-03-20T03:34:55+00:00
- Post Title: AV/SEGA TPL Format

After some fiddling around with HxD, references from YAGCD, and GXGMA source files I've made a chart of what is what inside Amusement Vision TPL files (F-Zero GX/AX, Super Monkey Ball 1 & 2, presumably Virtua Striker, etc.) The only thing left to solve is exactly how the 0x06-0x07 offsets work; why on 0x07 00-0F appear interchangeable with no significant variance in file format, style, etc. Also, while I haven't described the storage format of the image files, that is information you can look up on [YAGCD under 15.35 (TPL Texture Header)](http://hitmen.c02.at/files/yagcd/yagcd/chap15.html) as well as tpl.cpp from GXGMA source code (src.)
