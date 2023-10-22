## Post #1
- Username: demolos
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Mar 12, 2007 10:38 pm
- Post datetime: 2013-01-17T09:49:47+00:00
- Post Title: Salvation Prophecy .spar files

Hello,

Somebody can try to extract this files? 
[https://dl.dropbox.com/u/68586225/person.spar](https://dl.dropbox.com/u/68586225/person.spar)
[https://dl.dropbox.com/u/68586225/planet.spar](https://dl.dropbox.com/u/68586225/planet.spar)
[https://dl.dropbox.com/u/68586225/ship.spar](https://dl.dropbox.com/u/68586225/ship.spar)
[https://dl.dropbox.com/u/68586225/station.spar](https://dl.dropbox.com/u/68586225/station.spar)

maybe this game use this library:
[http://zziplib.sourceforge.net/](http://zziplib.sourceforge.net/)

Thanks
## Post #2
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2013-01-17T10:32:48+00:00
- Post Title: Salvation Prophecy .spar files

You can use [Aluigi's XOR tool](http://aluigi.altervista.org/mytoolz/xor.zip) for those files, because they are xored zip files.

Usage ex.:

```
xor station.spar station.zip 0x55
```
