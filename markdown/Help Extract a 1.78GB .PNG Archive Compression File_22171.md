## Post #1
- Username: petventh18
- Rank: beginner
- Number of posts: 35
- Joined date: Sat Mar 25, 2017 8:40 am
- Post datetime: 2020-05-19T01:03:24+00:00
- Post Title: Help Extract a 1.78GB .PNG Archive Compression File?

EDIT: The second game is another game I found was using .PNG format to contain their assets as well... 
Games:
斗破苍穹手游 | Battle Through the Heaven Mobile Game | Breaking the Sky 
[https://dp.qq.com/main.shtml](https://dp.qq.com/main.shtml)
Game File (1.78GB): [https://drive.google.com/file/d/1Dg-mOc ... sp=sharing](https://drive.google.com/file/d/1Dg-mOcwGOudgJFHlnAnzltz8e1B7fAqh/view?usp=sharing)



御剑情缘 | Yu Jian Qing Yuan 
[http://yj.zlongame.com](http://yj.zlongame.com)
Game File (1.09 GB): [https://drive.google.com/file/d/1vGP1qT ... sp=sharing](https://drive.google.com/file/d/1vGP1qTquQCWZmmPtL00I3xcLVKNhkqYi/view?usp=sharing)

-------------------------------------------------------------------------------------------------------------------------------------------------------------
I always thought PNG is an image file format... didn't know it can be used as some kind of Archive Data Compression format too.
Anyway, I got this BIG .png file (1.78GB) after I tried to extract some assets from a Unity Game APK File to use in AssetStudio...well, obviously I wasn't successful this time because simply changing the extension to .rar or .zip won't work either. 

Most game will have their resources in .obb format inside the APK file but this time, I'm really stump since it uses .png...
If anyone know how to extract files from a .png file then please help out a brother, huh?
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-05-25T02:42:15+00:00
- Post Title: Help Extract a 1.78GB .PNG Archive Compression File?

You should at least show the game name so people can know what they're dealing with.

> Reply from petventh18 ↑Tue May 19, 2020 9:03 am at Tue May 19, 2020 9:03 am
>
> 
I always thought PNG is an image file format... didn't know it can be used as some kind of Archive Data Compression format too.
Coz it's not a PNG at all.

> Reply from petventh18 ↑Tue May 19, 2020 9:03 am at Tue May 19, 2020 9:03 am
>
> 
Here is the file
Link is dead.
## Post #3
- Username: petventh18
- Rank: beginner
- Number of posts: 35
- Joined date: Sat Mar 25, 2017 8:40 am
- Post datetime: 2020-05-30T03:21:31+00:00
- Post Title: Help Extract a 1.78GB .PNG Archive Compression File?

> Reply from Bigchillghost ↑Mon May 25, 2020 10:42 am at Mon May 25, 2020 10:42 am
>
> 
You should at least show the game name so people can know what they're dealing with.
............
Link is dead.

Ah my bad, I have updated the game info above... and I forget to check the link after I posted cuz Google Drive need an extra dumb step/click before you can make the link shareable.
Everything should be fine now.
## Post #4
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-05-30T11:38:36+00:00
- Post Title: Help Extract a 1.78GB .PNG Archive Compression File?

The directories of the png archive from this game should probably be encrypted. You might use this script to extract things compulsively:
[http://aluigi.altervista.org/bms/monste ... r_nifs.bms](http://aluigi.altervista.org/bms/monster_hunter_nifs.bms)

The 2nd game uses a different container format which can be unpacked with this script:
[viewtopic.php?p=154110#p154110](viewtopic.php?p=154110#p154110)
## Post #5
- Username: petventh18
- Rank: beginner
- Number of posts: 35
- Joined date: Sat Mar 25, 2017 8:40 am
- Post datetime: 2020-05-31T01:06:06+00:00
- Post Title: Help Extract a 1.78GB .PNG Archive Compression File?

> Reply from Bigchillghost ↑Sat May 30, 2020 7:38 pm at Sat May 30, 2020 7:38 pm
>
> 
The directories of the png archive from this game should probably be encrypted. You might use this script to extract things compulsively:
http://aluigi.altervista.org/bms/monste ... r_nifs.bms

The 2nd game uses a different container format which can be unpacked with this script:
viewtopic.php?p=154110#p154110

Ah thanks a lot... the second script work perfectly... The Monster Hunter Nifs script ran into some memory allocation problem so I'm not sure if it's because of the encryption as you have said or just really running out of memory (I have 32Gb RAM)...but this is what quickbms said

```

Error: memory allocation problem
       Access is denied.
```
## Post #6
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-06-01T05:55:48+00:00
- Post Title: Help Extract a 1.78GB .PNG Archive Compression File?

Try this one.
[tencentNifsExtractor.zip](https://xentaxbackup.github.io/file/18260_tencentNifsExtractor.zip)
## Post #7
- Username: petventh18
- Rank: beginner
- Number of posts: 35
- Joined date: Sat Mar 25, 2017 8:40 am
- Post datetime: 2020-06-02T02:56:06+00:00
- Post Title: Help Extract a 1.78GB .PNG Archive Compression File?

> Reply from Bigchillghost ↑Mon Jun 01, 2020 1:55 pm at Mon Jun 01, 2020 1:55 pm
>
> 
Try this one.
Thank you for the script but it's still the same as before. Encounter the memory allocation problem.
But for this specific game, I found that if you install the game and pulled the game data from your phone to your PC then there's no need for any tool for extraction at all because all the assets will be in unity assets and AssetStudio will be able to read them perfectly.

But I still must thank you for the big help Bigchillghost... really appreciate it.
## Post #8
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-06-02T03:25:22+00:00
- Post Title: Help Extract a 1.78GB .PNG Archive Compression File?

> Reply from petventh18 ↑Tue Jun 02, 2020 10:56 am at Tue Jun 02, 2020 10:56 am
>
> 
Thank you for the script but it's still the same as before. Encounter the memory allocation problem.
Well, I tested it with the 4gb version of QuickBMS myself and it worked perfectly.

> Reply from petventh18 ↑Tue Jun 02, 2020 10:56 am at Tue Jun 02, 2020 10:56 am
>
> 
...install the game and pulled the game data from your phone to your PC...
Good.
## Post #9
- Username: petventh18
- Rank: beginner
- Number of posts: 35
- Joined date: Sat Mar 25, 2017 8:40 am
- Post datetime: 2020-06-02T23:44:06+00:00
- Post Title: Help Extract a 1.78GB .PNG Archive Compression File?

> Reply from Bigchillghost ↑Tue Jun 02, 2020 11:25 am at Tue Jun 02, 2020 11:25 am
>
> 
petventh18 wrote: ↑Tue Jun 02, 2020 10:56 am
Thank you for the script but it's still the same as before. Encounter the memory allocation problem.

Well, I tested it with the 4gb version of QuickBMS myself and it worked perfectly.
Oh crap basket... You're right. I was just being dumb as I was under the impression that since the file was under 2GB, so I never try the QuickBMS 4GB version... 
Damn... I was too careless and ending up wasting so much of everyone's time...Thank you very much, man... Really appreciate your help.
## Post #10
- Username: petventh18
- Rank: beginner
- Number of posts: 35
- Joined date: Sat Mar 25, 2017 8:40 am
- Post datetime: 2020-07-29T06:09:01+00:00
- Post Title: Help Extract a 1.78GB .PNG Archive Compression File?

> Reply from Bigchillghost ↑Mon Jun 01, 2020 1:55 pm at Mon Jun 01, 2020 1:55 pm
>
> 
Try this one.


 tencentNifsExtractor.zip
(1018 Bytes) Downloaded 18 times

Hey there man, I apologize for bothering you again...but I ran into a small issue while using your script for this new TenCent game. 


The script work great for extracting the textures and sprites but look like it can't extract the models for some reason... Probably because it was using a different algorithm for its compression. So if you have some free time...then please take a quick look at this game and see if it's possible to extract the rest of the content.
Thanks

Game: Qin's Moon World | 秦时明月世界
Game site: [https://qsmy.qq.com/](https://qsmy.qq.com/)
Game file (756 MB): [https://drive.google.com/file/d/1UgCfd6 ... xyVj0/view](https://drive.google.com/file/d/1UgCfd6Arw3trTV5yCvTt6DiF0PexyVj0/view)
## Post #11
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-07-29T15:22:51+00:00
- Post Title: Help Extract a 1.78GB .PNG Archive Compression File?

> Reply from petventh18 ↑Wed Jul 29, 2020 2:09 pm at Wed Jul 29, 2020 2:09 pm
>
> 
The script work great for extracting the textures and sprites but look like it can't extract the models for some reason... Probably because it was using a different algorithm for its compression.
There's a conflict situation where according to the flag the data should be compressed while it appears not. Adding this particular line before the loop should just do the trick.

```
comtype zlib_noerror
```

At least the next output (0000124a.unity3d) can be loaded correctly by Asset Studio.
[tencentNifsExtractor.zip](https://xentaxbackup.github.io/file/18530_tencentNifsExtractor.zip)
## Post #12
- Username: petventh18
- Rank: beginner
- Number of posts: 35
- Joined date: Sat Mar 25, 2017 8:40 am
- Post datetime: 2020-07-29T18:17:50+00:00
- Post Title: Help Extract a 1.78GB .PNG Archive Compression File?

Thanks a lot for the help... it work great.
## Post #13
- Username: cwyou123
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jun 21, 2022 7:31 pm
- Post datetime: 2022-06-21T13:27:17+00:00
- Post Title: Help Extract a 1.78GB .PNG Archive Compression File?

> Reply from Bigchillghost ↑Tue Jun 02, 2020 11:25 am at Tue Jun 02, 2020 11:25 am
>
> 
petventh18 wrote: ↑Tue Jun 02, 2020 10:56 am
Thank you for the script but it's still the same as before. Encounter the memory allocation problem.

Well, I tested it with the 4gb version of QuickBMS myself and it worked perfectly.
petventh18 wrote: ↑Tue Jun 02, 2020 10:56 am
...install the game and pulled the game data from your phone to your PC...

Good.
Have tried numerous .bms file to unpack these .ifs file through quickbms, but no success.



8E052B9D-9CEF-4544-8F58-B29.png (140.29 KiB) Viewed 184 times
