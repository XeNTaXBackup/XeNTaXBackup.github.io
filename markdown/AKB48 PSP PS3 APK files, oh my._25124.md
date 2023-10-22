## Post #1
- Username: Xr79
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Oct 06, 2013 6:45 am
- Post datetime: 2022-03-07T05:52:57+00:00
- Post Title: AKB48 PSP PS3 APK files, oh my.

Hello there forum people, I have a project I'm working on extracting the sprites from the AKB48 games, they are PSP PS Vita and PS3 games, but they all seem to have the same file form. 
What I have discovered with some help is that they are all Zlib compressed, I'm pretty sure. the APK contains the data and will extract GIMs,  however, these GIMs are corrupted and gives broken files. 
I think the index file might have something to do with it. but in the APK file, you can clearly see, JPG in the hex code text. I've uploaded quite a few sample files here, I'm not sure where to go with this but I feel like it is possible since nothing is encrypted.
[https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1CBvNuS9y8POiSBJu2kUEK_7sd767Ji_j?usp=sharing)
any assitence someone wants to give would be appreciated.
## Post #2
- Username: Rabatini
- Rank: veteran
- Number of posts: 97
- Joined date: Tue Nov 22, 2016 8:13 pm
- Post datetime: 2022-03-11T06:09:57+00:00
- Post Title: AKB48 PSP PS3 APK files, oh my.

> Reply from Xr79 ↑Mon Mar 07, 2022 1:52 pm at Mon Mar 07, 2022 1:52 pm
>
> 
Hello there forum people, I have a project I'm working on extracting the sprites from the AKB48 games, they are PSP PS Vita and PS3 games, but they all seem to have the same file form. 
What I have discovered with some help is that they are all Zlib compressed, I'm pretty sure. the APK contains the data and will extract GIMs,  however, these GIMs are corrupted and gives broken files. 
I think the index file might have something to do with it. but in the APK file, you can clearly see, JPG in the hex code text. I've uploaded quite a few sample files here, I'm not sure where to go with this but I feel like it is possible since nothing is encrypted.
https://drive.google.com/drive/folders/ ... sp=sharing
any assitence someone wants to give would be appreciated.
Hello use this script in all2.apk
will extract all files.
just use 7z file manager to decompress the file, seems the compression is LZMA12.


 AKB48_APK.zip
(358 Bytes) Downloaded 21 times



```

goto 0x07c8

for
get offset long
get zeros long
get unknown long
get zeros long
get size long
get zeros long
getdstring idontknow 0x10
 if OFFSET == 0x0000000 # "ONDINHA PROMOSSAUM PSN" 
    break
     endif

 string NAME p "%08x.7z" offset

log name offset size
next
```
## Post #3
- Username: Xr79
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Oct 06, 2013 6:45 am
- Post datetime: 2022-03-20T04:07:17+00:00
- Post Title: AKB48 PSP PS3 APK files, oh my.

Oh wow I was not expecting a reply from this, thank you much for taking a look I will give it a shot!
## Post #4
- Username: Xr79
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Oct 06, 2013 6:45 am
- Post datetime: 2022-03-20T04:26:46+00:00
- Post Title: AKB48 PSP PS3 APK files, oh my.

Hm I might be doing something wrong, but after I decompress the files they are un named files and even if I rename them they still are nothing files that can't be opened, I think maybe I missed a step? I got 17 thousand files form your BMS script.
## Post #5
- Username: Rabatini
- Rank: veteran
- Number of posts: 97
- Joined date: Tue Nov 22, 2016 8:13 pm
- Post datetime: 2022-03-21T03:29:40+00:00
- Post Title: AKB48 PSP PS3 APK files, oh my.

Inside the compress file, have decompress files, that contains the datas of the game, as per sounds, images.
But, it you will have to figure out.
For example; some files files have the idstring as JPGA

with this script, it will be able to extrack bmp images.
send some decompressed files here, maybe someone cann help u.
i did the hard part...now it should be easy.

```
IDSTRING "JPGA"
findloc OFFSET LONG 0X000000CA
math i = 0
do
#math offset - 0x1E
    goto OFFSET
    get DUMMY long
    findloc NEXT_OFFSET LONG 0X000000CA 0 ""

     if NEXT_OFFSET == ""

        get SIZE asize
    else
        math SIZE = NEXT_OFFSET

    endif
    math SIZE -= OFFSET
    string NAME p= OFFSET SIZE i
    STRING PATH = NAME
math offset - 0x0A
    log "" OFFSET SIZE
    math i += 1
    math OFFSET = NEXT_OFFSET

while NEXT_OFFSET != ""
```
## Post #6
- Username: Xr79
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Oct 06, 2013 6:45 am
- Post datetime: 2022-03-22T18:27:19+00:00
- Post Title: AKB48 PSP PS3 APK files, oh my.

This is very interesting,  thank you again for your help, you did get something from the JPG files it extract I think these are the alpha masking files. 
since they are all white. ah it looks like there is a way to fix them with sage thumbs, DJ normality told me how to do it. it looks like this project is nearing completion.
[00000000.bmp](https://xentaxbackup.github.io/file/21989_00000000.bmp)
