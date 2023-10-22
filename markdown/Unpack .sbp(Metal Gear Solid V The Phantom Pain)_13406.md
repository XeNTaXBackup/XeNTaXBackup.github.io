## Post #1
- Username: nerdyangry
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Aug 31, 2015 6:39 pm
- Post datetime: 2015-10-09T14:37:40+00:00
- Post Title: Unpack .sbp(Metal Gear Solid V The Phantom Pain)

Hi guys. I really need your help. How can unpack .sbp file? 
I would be grateful if you help me solve this "problem"
Example file: 
[https://www.dropbox.com/s/9qn54zke4s4m4 ... common.zip](https://www.dropbox.com/s/9qn54zke4s4m4pc/vox_player_common.zip)
## Post #2
- Username: spider91
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Feb 14, 2011 3:09 pm
- Post datetime: 2015-10-09T15:17:09+00:00
- Post Title: Unpack .sbp(Metal Gear Solid V The Phantom Pain)

Just delete 0x30 bytes at yhe beginning and you will get .bnk, that can be unpacked with Alpha's script.
## Post #3
- Username: nerdyangry
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Aug 31, 2015 6:39 pm
- Post datetime: 2015-10-09T18:45:25+00:00
- Post Title: Unpack .sbp(Metal Gear Solid V The Phantom Pain)

> Reply from spider91
>
> Just delete 0x30 bytes at yhe beginning and you will get .bnk, that can be unpacked with Alpha's script.
So.. How delete 0x30 bytes? HeX Editor?
## Post #4
- Username: spider91
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Feb 14, 2011 3:09 pm
- Post datetime: 2015-10-09T19:11:12+00:00
- Post Title: Unpack .sbp(Metal Gear Solid V The Phantom Pain)

Yes, in hex editor.
## Post #5
- Username: nerdyangry
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Aug 31, 2015 6:39 pm
- Post datetime: 2015-10-09T19:21:23+00:00
- Post Title: Unpack .sbp(Metal Gear Solid V The Phantom Pain)

> Reply from spider91
>
> Yes, in hex editor.
After removal 0x30 bytes, what me need to do?..
## Post #6
- Username: spider91
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Feb 14, 2011 3:09 pm
- Post datetime: 2015-10-09T20:03:24+00:00
- Post Title: Unpack .sbp(Metal Gear Solid V The Phantom Pain)

extract sounds with [this](http://forum.xentax.com/viewtopic.php?f=13&t=4450&p=89662#p89662) script. Then use ww2ogg to decode them into playable oggs.
## Post #7
- Username: nerdyangry
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Aug 31, 2015 6:39 pm
- Post datetime: 2015-10-09T21:52:34+00:00
- Post Title: Unpack .sbp(Metal Gear Solid V The Phantom Pain)

> Reply from spider91
>
> extract sounds with this script. Then use ww2ogg to decode them into playable oggs.

Not working or.. My hands do not grow out of the place.
[fix.png](https://xentaxbackup.github.io/file/9841_fix.png)
## Post #8
- Username: spider91
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Feb 14, 2011 3:09 pm
- Post datetime: 2015-10-10T05:27:58+00:00
- Post Title: Unpack .sbp(Metal Gear Solid V The Phantom Pain)

You need to put script attached [here](http://forum.xentax.com/viewtopic.php?f=13&p=69577#p69577) in same dir where you have script for extracting .bnk files.
