## Post #1
- Username: Honoire
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Aug 04, 2012 6:29 pm
- Post datetime: 2012-08-04T10:43:02+00:00
- Post Title: Corpse Party - text files

Hi, I'm new to the community but quite addicted to the awesome work of XeNTaX community since months.

I'm not really into source codes or programming or that stuff, it's probably better to say that I'm more of a translator.
With the release of a spin-off for the game Corpse Party (PSP) named Anthology, I was hoping to receive some tips here about how can I have access to the text-files in the game. You probably need a sample but since there are many files to take in consideration, I thought about making a list of them first: someone should be able to recognize where they are from name/size I guess. 

Folder: PSP_GAME
Contains PARAM.SFO (560 bytes) two .png files (for the icon/background) and two folders, SYSDYR AND USRDIR.

Folder: SYSDYR (screen: [http://dumpshare.net/images/994545image.png](http://dumpshare.net/images/994545image.png))

Folder: USRDIR (screen: [http://dumpshare.net/images/281160image2.png](http://dumpshare.net/images/281160image2.png))

If there is something else you need to know, please feel free to tell me and I'll provide info.
Thanks in advance for your patience and interest, if anyone can manage to understand where the text files are packed/create a tool for unpack and repack, it would be awesome: I'm trying to support the Corpse Party mark as much as I can, so that's all.
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-04T11:54:38+00:00
- Post Title: Corpse Party - text files

for unpack CPK.

```
comtype lzss "12 4 2 0 0"
goto 0x00000004
get FCOUNT long
goto 0x00000014
for i = 0 < FCOUNT
   savepos CPOS
   get OFFSET long
   get SIZE long
   get NAME string
   goto OFFSET
   getdstring IDSTR 4
   if IDSTR == "LZSS"
      get FSIZE long
      math OFFSET += 8
      math SIZE -= 8
      clog NAME OFFSET SIZE FSIZE
   else
      log NAME OFFSET SIZE
   endif
   math CPOS += 144
   goto CPOS
next i
```
## Post #3
- Username: Honoire
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Aug 04, 2012 6:29 pm
- Post datetime: 2012-08-04T19:36:01+00:00
- Post Title: Corpse Party - text files

Worked perfectly, thanks.

I found that most if not all of the files are .bin, which usually means they can be almost anything If I remember correctly.
After some research I found those readable with a simple Notepad, and managed to do some modifications.

Any idea about how to repack in .cpk?
## Post #4
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-04T19:54:40+00:00
- Post Title: Corpse Party - text files

Read 3) Reimport the extracted files in QuickBMS readme.
## Post #5
- Username: Honoire
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Aug 04, 2012 6:29 pm
- Post datetime: 2012-08-04T23:29:37+00:00
- Post Title: Corpse Party - text files

Again, thanks for the support.

I managed to unpack/modify/repack the CPK files (the big one was only an archive for many more of them) but unfortunately it seems I can't make the iso work: at first I thought it was about incorrect size, so I tried again with a lower-size output but got the same result.

By the way after searching for a while I found UTF_Tab (UTF_Tab07B5_Special was the complete name I think) and CRI Packed File Maker, which I used to unpack and repack a second time. Same results, the ISO file is recognized by the console but can't load and gives black screen. I'll try to figure out something... anyway, thank you for your precious tips.
