## Post #1
- Username: sempaisaito
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Aug 21, 2015 12:07 pm
- Post datetime: 2015-08-21T04:26:36+00:00
- Post Title: FFOnline Aka AuraKingdom Quickbms - Nif

Hello I really need help and don't know where to get started, but first let me explain what I'm doing.

I've been extracting models from aura kingdom since closed beta days. Where I made animation videos with the model on a program called MMD. 
My process was Extract .pkg with QuickBMS > open Nif file with nifskope export as obj > rigged object to be able to move.

Gaining popularity on my videos I have attain permission form the publisher AeriaGames to be able to edit/mod their client and extract their files for art related use. 
"Example: [https://www.youtube.com/watch?v=7yGFa-YbZVI](https://www.youtube.com/watch?v=7yGFa-YbZVI)" 

The issue I'm face with at the moment is quickbms script is outdated, Because even though I can extract the files. For some reason now when I try to open the models in nifskope i would get an error like this """failed to load file header (version 14000005, 20.0.0.5)"" ".

The other issue is the script isn't extracting everything from the game. Though there's no point if I can't  view it and extract the model into an object.

Any help with this would be appericated here is the quickbms script I'm using.

Thanks in advance.!

```
#   Eden Eternal
#   Kitsu Saga
#   Dragon Slayer
# script for QuickBMS http://quickbms.aluigi.org

comtype unzip_dynamic
getdstring DUMMY 260
getdstring SIGN 32
math PKG_OLD = -1
get FULLSIZE asize
do
    get DUMMY long
    get OFFSET long
    get DUMMY long
    get ZSIZE long
    getdstring DUMMY 0x28
    get SIZE long
    getdstring NAME2 260
    getdstring NAME 260
    get DUMMY long
    get PKG long
    get DUMMY long
    if PKG != PKG_OLD
        string PKG_NAME p= "pkg%03d.pkg" PKG
        open FDSE PKG_NAME 1
        math PKG_OLD = PKG
    endif
    string NAME += NAME2

    goto OFFSET 1
    get TMP1 byte 1
    get TMP2 byte 1
    if TMP1 == 0x88 && TMP2 == 0x1c
        savepos OFFSET 1
        math ZSIZE -= 2
    endif
    clog NAME OFFSET ZSIZE SIZE 1
    savepos CURR
while CURR < FULLSIZE
```
## Post #2
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2015-08-21T04:58:21+00:00
- Post Title: FFOnline Aka AuraKingdom Quickbms - Nif

Go here, it's easier to contact aluigi there han here:

[http://zenhax.com/index.php?sid=5b67b91 ... 8726a21ec3](http://zenhax.com/index.php?sid=5b67b917d2bc24e87904da8726a21ec3)

Also you can get fully rigged models with noesis and just avoid the job of doing it in blender or pmx editor.
## Post #3
- Username: sempaisaito
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Aug 21, 2015 12:07 pm
- Post datetime: 2015-08-21T06:57:15+00:00
- Post Title: FFOnline Aka AuraKingdom Quickbms - Nif

Thank you for replying, may I ask you to expand on what you said about getting rigged model by using noesis? mind providing a link to a tutorial? or giving me some keyword related to what your saying so I can research it myself?.
