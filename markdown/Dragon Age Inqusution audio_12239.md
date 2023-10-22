## Post #1
- Username: SammyWinss
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Nov 16, 2014 1:57 pm
- Post datetime: 2014-11-16T06:05:41+00:00
- Post Title: Dragon Age Inqusution audio

Hi! I'm hoping someone could help me with extracting DAI audio files. I was able to extract them with BF4 tools, but have a little problem. It seems these files contain more than one stream and EA Layer 3 Extractor only extracts the first one. I've tried to use "ealayer3.exe -s all", but it doesn't seem to work.
[0bb5188deb0c5a2c36e2251b98303f50.zip](https://xentaxbackup.github.io/file/8081_0bb5188deb0c5a2c36e2251b98303f50.zip)
## Post #2
- Username: mappy2012
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Jul 03, 2011 11:40 am
- Post datetime: 2014-11-16T09:05:38+00:00
- Post Title: Dragon Age Inqusution audio

Where can I find BF4 tools？
## Post #3
- Username: SammyWinss
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Nov 16, 2014 1:57 pm
- Post datetime: 2014-11-16T10:05:57+00:00
- Post Title: Dragon Age Inqusution audio

> Reply from mappy2012
>
> Where can I find BF4 tools？

Here: [http://forum.symthic.com/battlefield-4- ... post217245](http://forum.symthic.com/battlefield-4-general-discussion/p217245-extracting-audio-files-from-battlefield-4/#post217245)
## Post #4
- Username: Simguy
- Rank: advanced
- Number of posts: 43
- Joined date: Tue Jul 24, 2007 2:11 am
- Post datetime: 2014-11-20T04:13:07+00:00
- Post Title: Dragon Age Inqusution audio

> Reply from SammyWinss
>
> Hi! I'm hoping someone could help me with extracting DAI audio files. I was able to extract them with BF4 tools, but have a little problem. It seems these files contain more than one stream and EA Layer 3 Extractor only extracts the first one. I've tried to use "ealayer3.exe -s all", but it doesn't seem to work.

How did you get the python script to work? It just throws this error at me: "WindowsError: [Error -529697949] Windows Error 0xE06D7363"
## Post #5
- Username: mappy2012
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Jul 03, 2011 11:40 am
- Post datetime: 2014-11-20T10:20:13+00:00
- Post Title: Dragon Age Inqusution audio

Python 2.7.8 (default, Jun 30 2014, 16:03:49) [MSC v.1500 32 bit (Intel)] on win32
Type "copyright", "credits" or "license()" for more information.
>>> ================================ RESTART ================================
>>> 
layout.toc
frostbackmountains.toc
E:\hexing\dai dump/bundles/ebx/da3/factions/generic/props/textures/prp_josephinebrush_s.ebx

Traceback (most recent call last):
  File "C:\Python27\bf4dumper.py", line 257, in <module>
    if "tocRoot" in locals():  dumpRoot(tocRoot)
  File "C:\Python27\bf4dumper.py", line 248, in dumpRoot
    dump(fname,targetDirectory)
  File "C:\Python27\bf4dumper.py", line 171, in dump
    writePayload(entry, targetPath, sourcePath)
  File "C:\Python27\bf4dumper.py", line 224, in casPatchedPayload
    casPayload(bundleEntry, targetPath, sourcePath) #if casPatchType is not 2, use the unpatched function.
  File "C:\Python27\bf4dumper.py", line 213, in casPayload
    LZ77.decompress(catEntry.path,catEntry.offset,catEntry.size, bundleEntry.originalSize,targetPath)
WindowsError: [Error -529697949] Windows Error 0xE06D7363
>>>
## Post #6
- Username: SammyWinss
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Nov 16, 2014 1:57 pm
- Post datetime: 2014-11-20T12:30:44+00:00
- Post Title: Dragon Age Inqusution audio

This script cannot unpack .cas files. Just delete all the .cas files and it will work. It unpacks all the audio files from /data/win32/loc/
## Post #7
- Username: Simguy
- Rank: advanced
- Number of posts: 43
- Joined date: Tue Jul 24, 2007 2:11 am
- Post datetime: 2014-11-20T22:45:55+00:00
- Post Title: Dragon Age Inqusution audio

Thanks, the script runs now. But all of the ebx files are empty, I don't imagine that that is normal.
## Post #8
- Username: SammyWinss
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Nov 16, 2014 1:57 pm
- Post datetime: 2014-11-21T05:27:04+00:00
- Post Title: Dragon Age Inqusution audio

Found a tutorial: [https://www.youtube.com/watch?v=UVUv_L7m4g8](https://www.youtube.com/watch?v=UVUv_L7m4g8)
## Post #9
- Username: Silvist
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue May 31, 2011 1:30 pm
- Post datetime: 2014-11-22T18:37:47+00:00
- Post Title: Dragon Age Inqusution audio

Hello,

Do these bf4 tools work on more than just audio files? 

Reason I ask is the modding community as a whole would be in your debt lol.

Or do you know if a tool like process explorer or ninja ripper would work for DAI.  I attempted to use them myself,  but I'm unfamiliar with them?

Trying to mainly get a hold of textures and perhaps find a chargen file ^^  Thank you.
## Post #10
- Username: cloudslsw
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Nov 04, 2010 5:37 pm
- Post datetime: 2015-01-30T12:50:30+00:00
- Post Title: Dragon Age Inqusution audio

> abilities.toc
>
> F:\Server\hex\bundles\ebx\da3/party/mage/staff/blink/party_mage_staff_blink_csm.ebx
>
> 
>
> Traceback (most recent call last):
>
>   File "C:\bin\dumper.py", line 366, in <module>
>
>     main()
>
>   File "C:\bin\dumper.py", line 363, in main
>
>     dump(fname,outputfolder)
>
>   File "C:\bin\dumper.py", line 162, in dump
>
>     handlePayload(entry,ebxPath+entry.elems["name"].content+".ebx")
>
>   File "C:\bin\dumper.py", line 320, in deltaCasHandlePayload
>
>     outPath,originalSize)
>
> WindowsError: [Error -529697949] Windows Error 0xE06D7363

anyone knew how to fix?
## Post #11
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-03-29T17:49:00+00:00
- Post Title: Dragon Age Inqusution audio

> Reply from SammyWinss
>
> Hi! I'm hoping someone could help me with extracting DAI audio files. I was able to extract them with BF4 tools, but have a little problem. It seems these files contain more than one stream and EA Layer 3 Extractor only extracts the first one. I've tried to use "ealayer3.exe -s all", but it doesn't seem to work.

The "-s all" option is for multichannel files. It works well, but its not for this case.

It seems those scripts are doing something wrong. In the example you provided, this .chunk file contains 8 DIFFERENT mono audio files, not one.

p.s. i see people at DAI Tools already sorted that out. They are splitting these chunks to individual files.
