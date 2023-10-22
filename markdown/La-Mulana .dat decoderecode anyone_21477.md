## Post #1
- Username: hexaae
- Rank: advanced
- Number of posts: 44
- Joined date: Fri May 20, 2016 6:23 am
- Post datetime: 2019-12-08T08:27:41+00:00
- Post Title: La-Mulana .dat decode/recode anyone?

Is there a tool to decode and recode La-Mulana language files?
We have the Italian translation complete but NIGORO is not replying emails to add Italian language support, so I'm looking for a simple tool to decode/encode files like
grif.dat
script_code.dat

Files attached [https://1drv.ms/u/s!ApMUGr0cuN39gcUmtf8 ... Q?e=qXNyHH](https://1drv.ms/u/s!ApMUGr0cuN39gcUmtf8viDH_8AV6dQ?e=qXNyHH)
## Post #2
- Username: hexaae
- Rank: advanced
- Number of posts: 44
- Joined date: Fri May 20, 2016 6:23 am
- Post datetime: 2019-12-08T08:29:10+00:00
- Post Title: La-Mulana .dat decode/recode anyone?

Just found there's a python script... but I never used Python myself: [https://github.com/archagon/la-mulana-h ... er-decoder](https://github.com/archagon/la-mulana-hd-text-encoder-decoder)
Can someone very kindly convert it to a simple decode/recode exe tool maybe?
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-12-08T10:39:03+00:00
- Post Title: La-Mulana .dat decode/recode anyone?

> Reply from hexaae ↑Sun Dec 08, 2019 4:29 pm at Sun Dec 08, 2019 4:29 pm
>
> Can someone very kindly convert it to a simple decode/recode exe tool maybe?There is a (more or less) working solution, try to use it.

For windows blender 2.75 for example these changes are required:

in def decode_block(b):

```
                s = "{FF}"
            else:
                s = chr(o)
```


in def decode(fin, fout):
        b = fin.read(o//2)

result:


 script_out_cmd.zip
(84.85 KiB) Downloaded 25 times



(Re-encoding has another caveat, don't have the time to care for it now.)
## Post #4
- Username: hexaae
- Rank: advanced
- Number of posts: 44
- Joined date: Fri May 20, 2016 6:23 am
- Post datetime: 2019-12-18T20:40:17+00:00
- Post Title: La-Mulana .dat decode/recode anyone?

Thank you. But need a re-encode too...
## Post #5
- Username: piratesephiroth
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Nov 08, 2009 6:05 pm
- Post datetime: 2020-12-02T00:39:35+00:00
- Post Title: La-Mulana .dat decode/recode anyone?

> Reply from hexaae ↑Thu Dec 19, 2019 4:40 am at Thu Dec 19, 2019 4:40 am
>
> 
Thank you. But need a re-encode too...
I made a tool for that. It's based on that python script and accepts basically the same decoded files.

[https://github.com/piratesephiroth/LaMu ... ses/latest](https://github.com/piratesephiroth/LaMulanaScript/releases/latest)
