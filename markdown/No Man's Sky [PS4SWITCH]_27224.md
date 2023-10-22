## Post #1
- Username: dvoika
- Rank: beginner
- Number of posts: 31
- Joined date: Sat Nov 08, 2014 4:19 am
- Post datetime: 2023-09-21T05:48:10+00:00
- Post Title: No Man's Sky [PS4/SWITCH]

Hey guys how are you  
I'm trying to translate the game no mans sky into my native language but for ps4/switch. 
*.pak "HGPAK" is different from the PC version  ...
I have created a working BMS script but only for files without compression...would someone here be proficient and modify the script for files with compression? I don't know if it's oodle or zstd, in the attachment I send NMSARC.Font.pak without compression and NMSARC.Language.pak with compression.

```
comtype zstd

IDstring HGPAK
goto 0x0000010
get FILES long

print "%FILES%"

goto 0x0000040

for i = 0 < FILES

get OFFSET_file long
get DUMMY long
get SIZE_file long

get DUMMY long
get DUMMY long
get DUMMY long
get DUMMY long
get DUMMY long

log "" OFFSET_file SIZE_file 

next i
```

[https://drive.google.com/file/d/1ODiwdc ... sp=sharing](https://drive.google.com/file/d/1ODiwdcyLXt3IMXnrSS82LsDOPyyziggp/view?usp=sharing)

edit: monkeyman192 create python tools [https://github.com/monkeyman192/HGPAKtool](https://github.com/monkeyman192/HGPAKtool)
