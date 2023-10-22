## Post #1
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2021-12-24T00:55:31+00:00
- Post Title: Ford Racing Off-Road (.PC)

Hello 

I am trying to get cars extracted from game "Ford Racing Off-Road". 

The files are ".PC"

Sample of bronco: [https://cdn.discordapp.com/attachments/ ... BRONCO.zip](https://cdn.discordapp.com/attachments/872879593156116490/923740594524807198/BRONCO.zip)
## Post #2
- Username: MaKiPL
- Rank: advanced
- Number of posts: 60
- Joined date: Sat Sep 13, 2014 9:05 pm
- Post datetime: 2021-12-24T06:36:41+00:00
- Post Title: Ford Racing Off-Road (.PC)

This one’s not that easy. Tried decompressing the textures file with compression search and got no valuable result. Therefore it all says that the file must be ciphered- didn't find XOR patterns so must be something else, interesting. 

The bin file has easy structure of file EOF, hint pointers and casual null terminator strings and... that's all, only names. 

Bad news: the game probably requires reverse engineering to find what the heck is going on with those files.
## Post #3
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-12-24T12:50:47+00:00
- Post Title: Ford Racing Off-Road (.PC)

No, it's just ZLIB compressed data. File format looks like this:

```
x bytes - ZLIB data
```


So you can use offzip to extract data:

```
offzip.exe -a textures.pc
```


Here is the result for textures.pc file [https://i.imgur.com/LCXXCmd.png](https://i.imgur.com/LCXXCmd.png)

And here is the wiki article for future reference [http://wiki.xentax.com/index.php/Ford_R ... ff-Road_PC](http://wiki.xentax.com/index.php/Ford_Racing_Off-Road_PC)
