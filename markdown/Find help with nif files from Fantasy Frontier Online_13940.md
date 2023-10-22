## Post #1
- Username: 123zerocyj
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Jun 04, 2015 10:27 pm
- Post datetime: 2016-02-08T13:11:16+00:00
- Post Title: Find help with nif files from Fantasy Frontier Online

I'm playing a game called Fantasy Frontier Online these days.The model 

of this game uses the NIF file.Some of them can be opened by Noesis,but 

some of them cant.These NIF files version is 20.3.1.1

Noesis error log is :
Traceback (most recent call last):
  File "D:\noesisv4177\plugins\python\fmt_gamebryo_nif.py", line 2129, in nifLoadModel
    if nif.loadAll() == 0:
  File "D:\noesisv4177\plugins\python\fmt_gamebryo_nif.py", line 1415, in loadAll
    if self.loadObjects() == 0:
  File "D:\noesisv4177\plugins\python\fmt_gamebryo_nif.py", line 1345, in loadObjects
    nifObjectLoaderDict[object.typeName](object, bs)
  File "D:\noesisv4177\plugins\python\fmt_gamebryo_nif.py", line 689, in loadTriShapeData
    self.geomTriListData = bs.readBytes(self.geomNumTriIndices*2)
  File "D:\noesisv4177\plugins\python\inc_noesis.py", line 124, in readBytes
    return noesis.bsReadBytes(self.h, numBytes)
OverflowError: Python int too large to convert to C long

This is the file [https://onedrive.live.com/?id=7A9D4FE7B ... E7BB17ED27](https://onedrive.live.com/?id=7A9D4FE7BB17ED27%21105&cid=7A9D4FE7BB17ED27)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-02-08T15:01:49+00:00
- Post Title: Find help with nif files from Fantasy Frontier Online

> Reply from 123zerocyj
>
> These NIF files version is 20.3.1.1read here:
[https://github.com/niftools/nifxml/pull/47](https://github.com/niftools/nifxml/pull/47)

For some unknown reasons there was a 10 month period of inactivity up to now (but I didn't bother to search for more infos).
(Don't even know why it took so long for those guys to understand that it's big endian and half floats.  
It started here in August 2014, AFAICS: [http://niftools.sourceforge.net/forum/v ... =10&t=5909](http://niftools.sourceforge.net/forum/viewtopic.php?f=10&t=5909))

This is a point cloud from your nif but I'm quarreling with the face indices atm:



FantFrontOnl-b1706_nif.JPG (21.33 KiB) Viewed 167 times



(btw: I've had a deja vu looking at this Pikachu pic but I'm too lazy to search my HD for a similar one.)
## Post #3
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2016-02-08T16:57:40+00:00
- Post Title: Find help with nif files from Fantasy Frontier Online

You should provide 20.3.1.1 files that do load for reference.

Oh look, jonwd7. I wonder how quickly NifSkope would happen to support 20.3.1.1 immediately following Noesis, after failing to do so for this long.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-02-08T17:27:11+00:00
- Post Title: Find help with nif files from Fantasy Frontier Online

> Reply from shakotay2
>
> (Don't even know why it took so long for those guys to understand that it's big endian and half floats.well, Mr shakotay, and I don't even understand WHY it took 2.5 hours to understand that this nif is not big endian?  (well, I was fooled by the vertices starting at an odd address...)



FantFrontOnl-b1706_nif_.JPG (119.94 KiB) Viewed 157 times


(HF_UV for uvs preview only! For mesh display and saving as .obj HF_all is needed.)

> Reply from MrAdults
>
> You should provide 20.3.1.1 files that do load for reference.yeah, that would have been really helpful (but guess those FF online nifs that loaded were <> version 20.3.1.1).

(Aha, seems there's an endianess  flag in nif files for versions > 20.0.0.3.)
from fmt_gamebryo_nif.py:

```
				     self.isLittleEndian = bs.readUByte() > 0
			else:
				     self.isLittleEndian = True
```


While for NDSNIF it's always little endian.
## Post #5
- Username: 123zerocyj
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Jun 04, 2015 10:27 pm
- Post datetime: 2016-02-10T03:06:01+00:00
- Post Title: Find help with nif files from Fantasy Frontier Online

> Reply from MrAdults
>
> You should provide 20.3.1.1 files that do load for reference.

Oh look, jonwd7. I wonder how quickly NifSkope would happen to support 20.3.1.1 immediately following Noesis, after failing to do so for this long.

you mean I should upload more 20.3.1.1 nif files?(sorry my ENGLISH is poor  ...)
## Post #6
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2016-02-10T10:17:44+00:00
- Post Title: Find help with nif files from Fantasy Frontier Online

> Reply from 123zerocyj
>
> MrAdults wrote:You should provide 20.3.1.1 files that do load for reference.

Oh look, jonwd7. I wonder how quickly NifSkope would happen to support 20.3.1.1 immediately following Noesis, after failing to do so for this long.

you mean I should upload more 20.3.1.1 nif files?(sorry my ENGLISH is poor  ...)
Yes, please. I don't like to support a NIF variant without many reference samples, and I'm too lazy to download and extract their free client.

I would like:

- More 20.3.1.1 files, especially any that load, but also more that don't.
- More files from this game that load, whether they're 20.3.1.1 or not.
## Post #7
- Username: 123zerocyj
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Jun 04, 2015 10:27 pm
- Post datetime: 2016-02-16T12:34:41+00:00
- Post Title: Find help with nif files from Fantasy Frontier Online

> Reply from MrAdults
>
> 123zerocyj wrote:MrAdults wrote:You should provide 20.3.1.1 files that do load for reference.

Oh look, jonwd7. I wonder how quickly NifSkope would happen to support 20.3.1.1 immediately following Noesis, after failing to do so for this long.

you mean I should upload more 20.3.1.1 nif files?(sorry my ENGLISH is poor  ...)
Yes, please. I don't like to support a NIF variant without many reference samples, and I'm too lazy to download and extract their free client.

I would like:

- More 20.3.1.1 files, especially any that load, but also more that don't.
- More files from this game that load, whether they're 20.3.1.1 or not.

Sorry,keep you waiting.I have upload some of the 20.3.1.1 nif files.I just find one of them can be opened by Noesis and others cant.This is the link
[https://onedrive.live.com/?id=7A9D4FE7B ... E7BB17ED27](https://onedrive.live.com/?id=7A9D4FE7BB17ED27%21265&cid=7A9D4FE7BB17ED27)
