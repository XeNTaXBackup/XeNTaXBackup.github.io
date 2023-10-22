## Post #1
- Username: Dazz
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Mar 17, 2011 7:10 pm
- Post datetime: 2012-03-24T13:35:42+00:00
- Post Title: Dengeki Gakuen RPG - Cross of Venus

I've had a lot of requests for me to look into ripping from this game, but so far I'm not having much luck. It doesn't use standard formats, so I was hoping somebody here might be able to help me out.

3 example files:
[http://www.spriters-resource.com/dazz/btl_ch_syana.pack](http://www.spriters-resource.com/dazz/btl_ch_syana.pack)
[http://www.spriters-resource.com/dazz/btl_ch_hero.pack](http://www.spriters-resource.com/dazz/btl_ch_hero.pack)
[http://www.spriters-resource.com/dazz/b ... okuro.pack](http://www.spriters-resource.com/dazz/btl_ch_dokuro.pack)

They seem pretty simple, with the file names appearing at the start of the archive name, but I'm not sure about anything beyond that... Because I'm a bit of a noob.

Could anyone help me out?
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-24T16:20:21+00:00
- Post Title: Dengeki Gakuen RPG - Cross of Venus

Hmm, why does it look like the data is stored in both big and small endian?

The first three integers are just 

```
int32 null
int32 numFiles
int32 dataOffset

```


But then the file entries...look like they're little endian?

```
char[len] filename
#14 bytes

```


Maybe I'm not looking at it right...
## Post #3
- Username: Dazz
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Mar 17, 2011 7:10 pm
- Post datetime: 2012-03-27T13:59:34+00:00
- Post Title: Dengeki Gakuen RPG - Cross of Venus

Is that not a viable possibility? Or is it just something that hasn't really been seen before?
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-27T16:22:31+00:00
- Post Title: Dengeki Gakuen RPG - Cross of Venus

I guess it is possible, but I don't know why people would do it...
