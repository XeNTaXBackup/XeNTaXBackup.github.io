## Post #1
- Username: lache
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Sep 28, 2021 3:40 pm
- Post datetime: 2022-01-17T07:17:28+00:00
- Post Title: GuJian2 - unpacking .mod files

Have been struggling FOR A FEW MONTHS with the 10 year-old chinese RPG game "GuJian2" T__T

I want to substitute the main characters with the BOSS team.

However the ready made .mod file has only 1 boss. If I add other bosses I cannot change the interface & text & icons because that ready made .mod file already got those files. I cannot add files with same names. So I want to extract the .mod files and edit them. Although I tried veeeeery hard to make a new .mod of that boss, I failed to fix those skills effects.

The original mod maker lost the prepacked since the game is old enough.
I desperately need those files  .gfx .lua .bank (.bank.bak) .table etc... 

1. the file list in .mod   [https://www.mediafire.com/file/yftupmiy ... d.txt/file](https://www.mediafire.com/file/yftupmiy48y7rda/file_list_in_mod.txt/file) 
2. the .mod of boss   [https://www.mediafire.com/file/gubg47v9 ... s.mod/file](https://www.mediafire.com/file/gubg47v9d8ueiql/boss.mod/file) 
3. the program for packing   (modMaker)    [https://www.mediafire.com/file/1tbsswru ... r.exe/file](https://www.mediafire.com/file/1tbsswruvfg9rjg/gujian2modmaker.exe/file)
4. the program to use .mod in game  (modManager)   [https://www.mediafire.com/file/ba3i5cb4 ... r.exe/file](https://www.mediafire.com/file/ba3i5cb4jp0p6pt/Gujian2ModManager.exe/file)  , it will generate a mods.zpkg in the game directory  [https://www.mediafire.com/file/5fglabtg ... .zpkg/file](https://www.mediafire.com/file/5fglabtgh3g23pz/Mods.zpkg/file) 

Either unpack the .mod or the .zpkg will get what i need.

Thanks a lot.
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-01-17T21:31:57+00:00
- Post Title: GuJian2 - unpacking .mod files

File format of MOD archives isn't too complicated.
Here is the description [http://wiki.xentax.com/index.php/GuJian2_MOD](http://wiki.xentax.com/index.php/GuJian2_MOD)

But the real issue is that data is encrypted or compressed with unknown algorithm.

I can only assume that files are rather being encrypted during packing and not compressed,
because result file stored in MOD archive is always equal or bigger 
than original file (which shouldn't happen when the file is compressed).

I tried to use compression scanner, but I didn't get any good results.

Once someone will reverse engineer decryption method, writing a program/script to unpack data should be easy.
## Post #3
- Username: lache
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Sep 28, 2021 3:40 pm
- Post datetime: 2022-01-18T04:03:19+00:00
- Post Title: GuJian2 - unpacking .mod files

> Reply from ikskoks ↑Tue Jan 18, 2022 5:31 am at Tue Jan 18, 2022 5:31 am
>
> 
File format of MOD archives isn't too complicated.
Here is the description http://wiki.xentax.com/index.php/GuJian2_MOD

But the real issue is that data is encrypted or compressed with unknown algorithm.

I can only assume that files are rather being encrypted during packing and not compressed,
because result file stored in MOD archive is always equal or bigger 
than original file (which shouldn't happen when the file is compressed).

I tried to use compression scanner, but I didn't get any good results.

Once someone will reverse engineer decryption method, writing a program/script to unpack data should be easy.

Many thanks for your efforts.
Hoping that one day a script will come up.
