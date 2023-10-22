## Post #1
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2014-04-01T13:27:31+00:00
- Post Title: Legend Of Wukong PAK

Hello guys well a old game LOW with PAK format, I try use old bms script of chrox but won't work, so maybe somebody can take a look into files and help me to unpack them?



```
goto 0x19
get offset long
get size long
get zsize long
get baseoff long
get datasize long
get arcsize long
clog MEMORY_FILE offset zsize size
get unk01 long MEMORY_FILE
get unk02 long MEMORY_FILE
get files short MEMORY_FILE
goto 0x12 MEMORY_FILE
get folder3 string MEMORY_FILE
For tmp = tmp != size
get offset long MEMORY_FILE
get size2 long MEMORY_FILE
math offset + baseoff
if size2 == 0
get folder string MEMORY_FILE
else if size2 == 1
get folder2 string MEMORY_FILE
string folder + \
string folder + folder2
else
get name2 string MEMORY_FILE
set name folder
string name + \
string name + name2
log name offset size2
endif
savepos tmp MEMORY_FILE
next
```

[https://www.dropbox.com/s/exmf2bvdoab8d ... g%20PAK.7z](https://www.dropbox.com/s/exmf2bvdoab8dgg/Legend%20Of%20Wukong%20PAK.7z)
