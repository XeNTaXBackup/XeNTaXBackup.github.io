## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2013-03-04T05:30:04+00:00
- Post Title: Touhou Card Monsters

This engine seems to be used in several games. 
I don't know what engine it is lol but they all had similar directory structure and configuration file.

I looked through the pak archive and it sort of looks like it is just XOR'd with a 64-byte key since some sections had repeating bytes, but running it through xor didn't produce anything nice. It might be different 64-byte keys for each file, I don't know.

Anyways here's the exe and some other stuff along with a sample archive
Hopefully the key isn't too hard to get and is the same for all of the files..

[http://www.mediafire.com/?jt0fskfv18bri53](http://www.mediafire.com/?jt0fskfv18bri53)

Here are the names of the other games that use the same engine if anyone is interested

東方蒼神縁起
東方百鬼合戦
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-04T07:24:40+00:00
- Post Title: Touhou Card Monsters

First 4 bytes - Table Size. Algo in attach.

See also (very similar)

```
http://www.math.sci.hiroshima-u.ac.jp/~m-mat/MT/VERSIONS/C-LANG/c-lang.html
http://www.stephencalenderblog.com/?p=181
http://www.cplusplus.com/forum/beginner/79754/

http://gcc.gnu.org/bugzilla/show_bug.cgi?id=37573
http://code.google.com/p/keel4all/source/browse/trunk/keel_grt/dllmain.cpp?spec=svn2&r=2

```

[THM_PAKDec.rar](https://xentaxbackup.github.io/file/6237_THM_PAKDec.rar)
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2013-03-04T23:29:37+00:00
- Post Title: Touhou Card Monsters

Thanks, the algorithm look too bad. And the C reference lol
## Post #4
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-02-15T17:38:29+00:00
- Post Title: Touhou Card Monsters

Done. Tool for unpack [here](http://forum.xentax.com/viewtopic.php?f=10&t=11210)
