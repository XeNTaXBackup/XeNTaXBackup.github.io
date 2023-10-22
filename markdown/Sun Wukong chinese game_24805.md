## Post #1
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-12-04T17:56:53+00:00
- Post Title: Sun Wukong chinese game

Hello!someone could take a look at this files please, are encrypted, I tried noobs methods like change the header, but didn't work, to be honest don't know much about how to decryption so, Im loss in this task. I attach some samples. If is necessary can attach more just let me know and thanks for your time.  
[https://www.mediafire.com/file/4joiyw20 ... S.zip/file](https://www.mediafire.com/file/4joiyw207fjxcai/SUN_WUKONG_CHINESE_ASSETSBUNDLES.zip/file)
## Post #2
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-12-07T00:45:20+00:00
- Post Title: Sun Wukong chinese game

Hey, I was looking for more information about this game, and since it has had its own app to play it, I'm not sure if it was a web game a long time ago or something similar, the point is that I have been able to get some examples, the bad thing is that It seems that it is still encrypted, and that this format has both the 3d model and the textures (atf-format), maybe someone has already come across such a model, and can give me a hand, anyway thank you very much.    
[https://www.mediafire.com/file/a2ius7vb ... S.zip/file](https://www.mediafire.com/file/a2ius7vb9y61xq7/SUN_WUKONG_CHINESE_GAME_ASSETS.zip/file)
## Post #3
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-12-09T00:23:41+00:00
- Post Title: Sun Wukong chinese game

UPDATE: if I delete some bytes so that the header starts with ATF, the texture can be extracted, which I don't understand is: then the file is encrypted but only partially? Like this : they encrypted the 3d model and just add the texture at the begining or at the end, and called it .e3p  file or how xD   .
Anyways gathering in the files I found a file called appointgods_41551.enc, to be honest is the most suspicious file, Im still checking if it could contain something relevant. Any kind of help would be much appreciated!  

[https://www.mediafire.com/file/pwg0lqkb ... 1.enc/file](https://www.mediafire.com/file/pwg0lqkbp46c1ti/appointgods_41551.enc/file)


UPDATE about appointgods_41551.enc: I may be going crazy but this file contains the filetypes of all the files of the game (swf, e3p, e3o, eff, atf)    

Textures from the samples :
## Post #4
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-12-10T01:23:59+00:00
- Post Title: Sun Wukong chinese game

UPDATE bms script by ALUIGI to decompress the .enc file, if anyone is checking this, hope it helps. I'm still searching any kind of file that decrypts the files(.e3p) in the moment them load ingame (if are encrypted) .   

```
idstring "ZWS+"
get SIZE long
get ZSIZE long
savepos OFFSET
get NAME basename
clog NAME OFFSET ZSIZE SIZE
```

UPDATE .e3p file is not encrypted is compressed by lzma (by aluigi)
## Post #5
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-12-14T05:19:55+00:00
- Post Title: Sun Wukong chinese game

Hello! I'm still looking for this models!! are not high poly but them looks good . I gathered more models :weapons and wings.Hope someone can decompress them, to I can try to get the model with hex2obj or advanced mesh reaper! Thanks in advance   

[https://www.mediafire.com/file/q0bzow1w ... S.zip/file](https://www.mediafire.com/file/q0bzow1whsnlps1/SUN_WUKONG_WEP-WING_ASSETS.zip/file)
