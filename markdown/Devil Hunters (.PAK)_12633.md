## Post #1
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2015-02-22T15:57:12+00:00
- Post Title: Devil Hunters (*.PAK)

Official Site: [here](http://www.lhogame.com/main.html)
Download: [here](http://dhdl.frozenpeak.net/clients/liehun_full_0224.exe)

```
# 
# Written by Ekey (h4x0r)
# 
# script for QuickBMS http://quickbms.aluigi.org

goto -0x8
get FILETABLE long
get STRTABLE long

goto FILETABLE
get FILES long
get DUMMY long
get DUMMY long
get DUMMY long
savepos TEMP

goto STRTABLE
get FLAG byte # some flag crypt/compress? 

for i = 0 < FILES
    get NAME string
    putarray 0 i NAME
next i

goto TEMP

for i = 0 < FILES
    get SIZE long
    get ZSIZE long
    get OFFSET long
    get UNKN long
    get DUMMY long
    get DUMMY long
    get DUMMY long
    savepos ETEMP
   
    getarray NAME 0 i
    if SIZE == ZSIZE
        log NAME OFFSET SIZE
    else
        math OFFSET += 8
        clog NAME OFFSET ZSIZE SIZE
    endif
next i
```
## Post #2
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2015-02-26T18:02:57+00:00
- Post Title: Devil Hunters (*.PAK)

Hi Ekey My friend, thank you very much for the great work, the script runs very well, how to extract the cache folder material.cache , ask for help, here is a sample file [https://mega.co.nz/#!iNBHkI4Z!bbcMquqc6 ... fKQX81nivs](https://mega.co.nz/#!iNBHkI4Z!bbcMquqc6GnQxK5YZDZ73afpUf17MG9QefKQX81nivs) thanks again
[BaiduShurufa_2015-2-27_2-0-21.jpg](https://xentaxbackup.github.io/file/8765_BaiduShurufa_2015-2-27_2-0-21.jpg)
## Post #3
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2015-02-26T19:21:45+00:00
- Post Title: Devil Hunters (*.PAK)

Hi
Here is an importer for rigged models and animations from this game.
It requires Blender version 249b and Python 2.6.6.
How to use:
1.from game cache folder copy material.cache (~19mb ) to folder, where is Blender249.blend.
2.run Blender249.blend
3.in Blender Text Window press alt+p and select:
- *.mesh file for import textured models (if material.cache exists in Blender249.blend folder). Use mesh files from an original location.
- *.skeleton file for unpacking animations to new folder "..._animfiles" and for import skeleton. Sometimes must to scale meshes to fit to skeleton.
- anim files  - for import animation
[Blender249[DevilHunters][PC][mesh][skeleton][2015-02-26].zip](https://xentaxbackup.github.io/file/8766_Blender249[DevilHunters][PC][mesh][skeleton][2015-02-26].zip)
## Post #4
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2015-02-26T20:01:39+00:00
- Post Title: Devil Hunters (*.PAK)

Hi Ekey My friend The problem has been solved, thank you very much for your help
Once again, thank you very much for the great work Ekey and Szkaradek123. Scripting tool runs perfectly, thanks again.
[model (2).jpg](https://xentaxbackup.github.io/file/8767_model (2).jpg)
