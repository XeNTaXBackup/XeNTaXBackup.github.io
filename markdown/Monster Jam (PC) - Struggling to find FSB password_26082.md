## Post #1
- Username: gcp345
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Dec 12, 2022 9:26 pm
- Post datetime: 2022-12-12T13:41:34+00:00
- Post Title: Monster Jam (PC) - Struggling to find FSB password

Hello,

For the past couple of days, I have been trying to extract audio from a FSB file and I have had zero luck doing so.  I haven't had any luck being able to find the password for the game.  I have used fsbext and didn't have much luck and and I have tried looking for the password myself using a hex editor.  The game is Monster Jam, from 2007.  It is the PC version of the game.

If anyone would like to take a look at one of the files, I uploaded one to Mega
[https://mega.nz/file/AxJ2HDJT#o8nt80kyf ... y1BtaJ0dS0](https://mega.nz/file/AxJ2HDJT#o8nt80kyfOQFi6CNF-EoZK3YhQQPH4IAhy1BtaJ0dS0)

The only thing I have noticed is each FSB starts with the same 4 characters each time:

```
¸7¯
```

I'm not sure if that's a header or not, I'm fairly new to this sort of thing.  Thank you!
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-12-13T11:56:29+00:00
- Post Title: Monster Jam (PC) - Struggling to find FSB password

The password is:

```
truck/impact/carbody
```


You can use fsbext like this:

```
fsbext.exe -p "truck/impact/carbody" engine01.fsb
```


For future reference I would recommend to always check those two links when you are looking for FSB password:
[http://wiki.xentax.com/index.php/FMOD_Audio_FSB](http://wiki.xentax.com/index.php/FMOD_Audio_FSB)
[https://github.com/vgmstream/vgmstream/ ... fsb_keys.h](https://github.com/vgmstream/vgmstream/blob/master/src/meta/fsb_keys.h)

And also your sample plays fine in foobar2000 with vgmstream plugin (so you don't have to know any passwords, you just drag and drop your files to foobar's window).
## Post #3
- Username: gcp345
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Dec 12, 2022 9:26 pm
- Post datetime: 2022-12-13T12:23:27+00:00
- Post Title: Monster Jam (PC) - Struggling to find FSB password

Than you so much for the help! I will look into those links as well!
