## Post #1
- Username: !!!!!
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Jun 22, 2009 8:55 am
- Post datetime: 2013-04-06T07:26:07+00:00
- Post Title: Injustice: Gods Among Us FSBs

FSBs are in the sound .XXX archives yet no options I've tried (xmash, fsbii, fsbext, mortal kombat 2011 XXX bms ,unreal package extractor & decompressor) could extract them. PM me if you want a sample .XXX file from it.
## Post #2
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2013-04-06T12:28:22+00:00
- Post Title: Injustice: Gods Among Us FSBs

try fsb extractor. It extracts the xma files but you have to convert them with an xma header.
## Post #3
- Username: !!!!!
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Jun 22, 2009 8:55 am
- Post datetime: 2013-04-06T21:30:34+00:00
- Post Title: Injustice: Gods Among Us FSBs

Thanks for the quick reply OC. Though FSB Extractor didn't work for me, but I found another way of doing it.

Here's the process for the 360 version:
-Open any audio .XXX archive (ex. SND_MUS_name.xxx for music specifically) in a hex editor and look for the FSB5 header. Cut everything before it and save it as an .fsb. There are usually more then one FSB5 container within the archives so check for another header before moving on. If there's another FSB5 header cut everything before it like the last one and save as an .fsb.
-Use [fsbext](http://aluigi.altervista.org/papers/fsbext.zip) to extract the XMAs from the containers.
-Use alphatwentythree's [XMA Transform script](http://forum.xentax.com/viewtopic.php?f=17&t=9023) on the XMAs
-[Towav](http://www.ctpax-x.org/index.php?goto=files&show=24) them and your done
## Post #4
- Username: !!!!!
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Jun 22, 2009 8:55 am
- Post datetime: 2013-04-23T11:06:43+00:00
- Post Title: Injustice: Gods Among Us FSBs

Now on the subject of the PS3 version. When I rip the FSBs with fsbext or fsbextractor some the fsbs converted with towav play incorrectly. They are scrambled. The PS3 version used FSB5 ADPCM. PM me if you interested in a file. I can give the source .XXX, the ripped FSB5 archive, & the corrupted FSB extracted with either program if wanted.
