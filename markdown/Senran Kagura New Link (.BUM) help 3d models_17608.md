## Post #1
- Username: aoba200941
- Rank: beginner
- Number of posts: 27
- Joined date: Wed Oct 21, 2015 12:41 pm
- Post datetime: 2018-01-24T06:12:47+00:00
- Post Title: Senran Kagura: New Link (.BUM) help 3d models

hello everyone I would love if you could help with my problem 




 pl19_mdl.zip
(175.66 KiB) Downloaded 95 times


 Thank you so much for all your help
## Post #2
- Username: aoba200941
- Rank: beginner
- Number of posts: 27
- Joined date: Wed Oct 21, 2015 12:41 pm
- Post datetime: 2018-01-24T19:01:40+00:00
- Post Title: Senran Kagura: New Link (.BUM) help 3d models

extrange this model with ninja ripper but how to get the original bones


any comment would be very helpful 
[uiui.png](https://xentaxbackup.github.io/file/13844_uiui.png)
## Post #3
- Username: ramenraisin
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Sep 10, 2017 11:37 pm
- Post datetime: 2018-02-28T21:06:16+00:00
- Post Title: Senran Kagura: New Link (.BUM) help 3d models

I tried to load the models with the same plugin from this thread [viewtopic.php?f=16&t=16034](http://forum.xentax.com/viewtopic.php?f=16&t=16034) but they just crash noesis. No idea how to go about getting them otherwise. Would be helpful to me if you could dump those .obj you extracted but that's on you.
## Post #4
- Username: b59943201
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Nov 14, 2015 1:14 am
- Post datetime: 2018-03-28T04:54:09+00:00
- Post Title: Senran Kagura: New Link (.BUM) help 3d models

Excuse me aoba200941,

Can you tell me how to make .BUM file to .obj file?

thank you Very much！
## Post #5
- Username: aoba200941
- Rank: beginner
- Number of posts: 27
- Joined date: Wed Oct 21, 2015 12:41 pm
- Post datetime: 2018-04-24T19:06:00+00:00
- Post Title: Senran Kagura: New Link (.BUM) help 3d models

> Reply from b59943201
>
> Excuse me aoba200941,

Can you tell me how to make .BUM file to .obj file?

thank you Very much！



nox player and ninja ripper 

since there are no scripts for this game 



yyyy.png (130.47 KiB) Viewed 1166 times
## Post #6
- Username: aoba200941
- Rank: beginner
- Number of posts: 27
- Joined date: Wed Oct 21, 2015 12:41 pm
- Post datetime: 2018-04-24T19:22:10+00:00
- Post Title: Senran Kagura: New Link (.BUM) help 3d models

> Reply from ramenraisin
>
> I tried to load the models with the same plugin from this thread viewtopic.php?f=16&t=16034 but they just crash noesis. No idea how to go about getting them otherwise. Would be helpful to me if you could dump those .obj you extracted but that's on you.

[https://mega.nz/#!aRkCVDZA!NQASAej4NOTF ... Vb0_62BfOg](https://mega.nz/#!aRkCVDZA!NQASAej4NOTFy1NpGmyCtpWJxAkdDEvkOVb0_62BfOg)
## Post #7
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-04-25T00:08:06+00:00
- Post Title: Senran Kagura: New Link (.BUM) help 3d models

I slightly modified chrrox's script to work with your sample. I don't know if it is reliable though, more samples would be good.



Try it yourself on other files. Don't forget to remove chrrox's script before using this.
[fmt_sknl_bum_upd.rar](https://xentaxbackup.github.io/file/14275_fmt_sknl_bum_upd.rar)
## Post #8
- Username: aoba200941
- Rank: beginner
- Number of posts: 27
- Joined date: Wed Oct 21, 2015 12:41 pm
- Post datetime: 2018-04-25T01:05:34+00:00
- Post Title: Senran Kagura: New Link (.BUM) help 3d models

> Reply from akderebur
>
> I slightly modified chrrox's script to work with your sample. I don't know if it is reliable though, more samples would be good.



Try it yourself on other files. Don't forget to remove chrrox's script before using this.



woow is a great job thank you very much
## Post #9
- Username: aoba200941
- Rank: beginner
- Number of posts: 27
- Joined date: Wed Oct 21, 2015 12:41 pm
- Post datetime: 2018-04-25T06:34:25+00:00
- Post Title: Senran Kagura: New Link (.BUM) help 3d models

> Reply from akderebur
>
> I slightly modified chrrox's script to work with your sample. I don't know if it is reliable though, more samples would be good.



Try it yourself on other files. Don't forget to remove chrrox's script before using this.



[https://mega.nz/#!YgAEEbqK!NwscAy9Y-D5e ... EZlUkvZXX8](https://mega.nz/#!YgAEEbqK!NwscAy9Y-D5e1F7F__idAPIkW8s16UlgjEZlUkvZXX8)
[mdl.png](https://xentaxbackup.github.io/file/14274_mdl.png)
## Post #10
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-04-25T11:09:42+00:00
- Post Title: Senran Kagura: New Link (.BUM) help 3d models

The problem was that the model didn't have the expected tag for the root bone. I made it so that the first bone will be used as root. I have updated the attachment in my previous post.

Also I have noticed that the actual reason why the original script doesn't work is that there are multiple bones with no parent in these models. The modification I made basically loads the model by skipping other root bones (only loads the first). So don't trust this script at all for getting the skeleton. There is a high chance that the weights will be messed up, but it might work for some. Still it can be easier than ninjaripper for getting static meshes.

I would need to get more invested in this format and improve myself on noesis to make a proper script. Unfortunately I don't have the time and interest for that. I hope this script can help you a bit as it is. Maybe someone can make something proper later.
## Post #11
- Username: Arymond
- Rank: advanced
- Number of posts: 54
- Joined date: Sun Feb 12, 2012 7:49 am
- Post datetime: 2018-09-26T00:17:45+00:00
- Post Title: Senran Kagura: New Link (.BUM) help 3d models

How did you get the BUM files i only see LZS's in the Directory.

[https://www.dropbox.com/s/r17mogczr26dj ... l.lzs?dl=0](https://www.dropbox.com/s/r17mogczr26dj7x/pl06_model.lzs?dl=0)
## Post #12
- Username: wansf
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Mar 11, 2018 5:56 pm
- Post datetime: 2019-01-19T16:10:01+00:00
- Post Title: Senran Kagura: New Link (.BUM) help 3d models

> Reply from akderebur
>
> The problem was that the model didn't have the expected tag for the root bone. I made it so that the first bone will be used as root. I have updated the attachment in my previous post.

Also I have noticed that the actual reason why the original script doesn't work is that there are multiple bones with no parent in these models. The modification I made basically loads the model by skipping other root bones (only loads the first). So don't trust this script at all for getting the skeleton. There is a high chance that the weights will be messed up, but it might work for some. Still it can be easier than ninjaripper for getting static meshes.

I would need to get more invested in this format and improve myself on noesis to make a proper script. Unfortunately I don't have the time and interest for that. I hope this script can help you a bit as it is. Maybe someone can make something proper later.

i use ur noesis script to export model but somehow the UVs are totally fked up , is that my problem or their protection method?
[Untitled.001_UV.png](https://xentaxbackup.github.io/file/15519_Untitled.001_UV.png)
## Post #13
- Username: wansf
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Mar 11, 2018 5:56 pm
- Post datetime: 2019-01-19T16:10:54+00:00
- Post Title: Senran Kagura: New Link (.BUM) help 3d models

2spooky4me

@Arymond , u need to use quickbms lzs script first
[vdsad.jpg](https://xentaxbackup.github.io/file/15520_vdsad.jpg)
## Post #14
- Username: DarkElfNinja
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri May 31, 2019 7:03 am
- Post datetime: 2019-06-03T21:41:33+00:00
- Post Title: Senran Kagura: New Link (.BUM) help 3d models

> Reply from wansf ↑Sun Jan 20, 2019 12:10 am at Sun Jan 20, 2019 12:10 am
>
> 
i use ur noesis script to export model but somehow the UVs are totally fked up , is that my problem or their protection method?

I'm having the same problem. After using the QuickBMS LZS script to extract the LZS and then exporting the BUM file to OBJ in Noesis, the UVs are completely busted. It appears that the models have at least 2 UVs (or more) and either Noesis or the LZS script is merging them into one UV. I can't tell which is the culprit since I'm really rusty at this type of thing. Has anyone managed to solve this problem?
## Post #15
- Username: wansf
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Mar 11, 2018 5:56 pm
- Post datetime: 2020-04-18T07:05:10+00:00
- Post Title: Senran Kagura: New Link (.BUM) help 3d models

mr.akderebur please help  

more model file in case u need them
[https://www80.zippyshare.com/v/G55ekTgk/file.html](https://www80.zippyshare.com/v/G55ekTgk/file.html)
