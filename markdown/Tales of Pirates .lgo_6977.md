## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-15T13:01:28+00:00
- Post Title: Tales of Pirates .lgo

Homepage: [http://top.igg.com/main.php](http://top.igg.com/main.php)

Note: low-quality models. I'm only doing it to look at the format.

Meshes + skeleton (maybe): .lgo files

```
dword meshType? (have seen 0, 1, 2, 3, 4)
dword_2 ???
float_16 matrix?
dword_4 ???


#unk section. Contains materials and what seems to be animations>
dword ???
dword ???
dword sectionSize
dword ???
dword ???
dword ???

<sectionSize number of bytes>

dword unk
dword unk
dword numVerts
dword numIndices

#some variables for now
dword VAR1
dword VAR2
dword VAR3
dword VAR4

<100 bytes>

#unk section
if VAR4 == 4:
   28 bytes
elif VAR4 == 6:
   44 bytes
	
struct vertices {
   float_8
}

#unk section
if VAR4 == 4:
   pass
elif VAR4 == 5:
   numVerts * 4 bytes
elif VAR4 == 1:
   numVerts * 20 bytes

struct face {
   dword_3 indices
}
dword numFaces
dword ???
dword numVerts
dword ???

#IF END OF FILE THEN DONE, ELSE

dword_? ???

struct unk3 { #several different types...only figured out how to skip one of them
   dword index?
   float_16 ???
   Byte_72 nulls
}
96 bytes

EOF
```

[Tales of Pirates.rar](https://xentaxbackup.github.io/file/4494_Tales of Pirates.rar)
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-09T14:12:39+00:00
- Post Title: Tales of Pirates .lgo

Re-visited this format after noting that formats tend to store the number of face indices, and maybe the number of faces.
And then found a small section I overlooked that contained several ints.
## Post #3
- Username: ofkings
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Jan 01, 2018 7:16 am
- Post datetime: 2018-01-05T19:09:14+00:00
- Post Title: Tales of Pirates .lgo

sry to revide topic, but you can view this .lgo files?
## Post #4
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-01-05T23:54:50+00:00
- Post Title: Tales of Pirates .lgo

01010008.lgo  



01010008_lgo.png (24.2 KiB) Viewed 105 times
## Post #5
- Username: ofkings
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Jan 01, 2018 7:16 am
- Post datetime: 2018-01-06T01:29:25+00:00
- Post Title: Tales of Pirates .lgo

teach me master
