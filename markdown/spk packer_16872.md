## Post #1
- Username: the101gamer
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu May 11, 2017 10:51 pm
- Post datetime: 2017-08-15T22:12:14+00:00
- Post Title: spk packer?

I unpacked an spk file from Bleach Soul Resurreccion for PS3 and it left me with a few .unk files, anyway I want to pack these unk files back into the spk format, does anyone have a solution?

I unpacked the spk by using quickbms and this script

findloc start string "\x0\x0\x0\x1"
print "%start%"

goto start
endian big
set i 0
for i
savepos offset
get name basename
string name + _
string name + i
string name + .unk
getdstring one 0x14
get size long
math size + 0x20
log name offset size
math offset + size
goto offset
next i
