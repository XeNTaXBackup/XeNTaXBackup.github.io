## Post #1
- Username: Godxon1
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Jun 06, 2015 2:35 am
- Post datetime: 2017-11-13T21:01:38+00:00
- Post Title: Star Wars Battlefront 2 (2017) - How to extract files?

Hello everyone!
I am trying to extract files from new SWBF II (it is now in Trial), but unfortunately extraction tools for SWBF 2015 ([https://forum.xentax.com/viewtopic.php?f=33&t=13145](https://forum.xentax.com/viewtopic.php?f=33&t=13145)) aren't working. I am especially looking for localization files.

Could anyone look at it?

You can download the game files there (it is with first cas file in each folder only):
[https://mega.nz/#F!vE8zibqK!-6prGm6e0IFS6ZaUwFmEzg](https://mega.nz/#F!vE8zibqK!-6prGm6e0IFS6ZaUwFmEzg)

Thank you very much!
Godxon
## Post #2
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2017-11-14T08:47:43+00:00
- Post Title: Star Wars Battlefront 2 (2017) - How to extract files?

> Reply from Godxon1
>
> Hello everyone!
I am trying to extract files from new SWBF II (it is now in Trial), but unfortunately extraction tools for SWBF 2015 (https://forum.xentax.com/viewtopic.php?f=33&t=13145) aren't working. I am especially looking for localization files.

Could anyone look at it?

You can download the game files there (it is with first cas file in each folder only):
https://mega.nz/#F!vE8zibqK!-6prGm6e0IFS6ZaUwFmEzg

Thank you very much!
Godxon

The game has changed since the beta and has ZSTD compression on it's cat/cas files but Python won't support that by default so you need a wrapper for it which you can find here [https://github.com/sergey-dryabzhinsky/python-zstd](https://github.com/sergey-dryabzhinsky/python-zstd) and [https://github.com/facebook/zstd/releas ... -win32.zip](https://github.com/facebook/zstd/releases/download/v1.3.2/zstd-v1.3.2-win32.zip)

Not sure how to apply these but i thought i'd post them for anyone wanting to try and edit the script to support the game. 

Oh you can find the script here. [https://bitbucket.org/Frankelstner/fros ... tlefront-2](https://bitbucket.org/Frankelstner/frostbite-battlefront-2)
## Post #3
- Username: Godxon1
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Jun 06, 2015 2:35 am
- Post datetime: 2017-11-14T09:40:36+00:00
- Post Title: Star Wars Battlefront 2 (2017) - How to extract files?

> Reply from JakeGreen
>
> Godxon1 wrote:Hello everyone!
I am trying to extract files from new SWBF II (it is now in Trial), but unfortunately extraction tools for SWBF 2015 (https://forum.xentax.com/viewtopic.php?f=33&t=13145) aren't working. I am especially looking for localization files.

Could anyone look at it?

You can download the game files there (it is with first cas file in each folder only):
https://mega.nz/#F!vE8zibqK!-6prGm6e0IFS6ZaUwFmEzg

Thank you very much!
Godxon

The game has changed since the beta and has ZSTD compression on it's cat/cas files but Python won't support that by default so you need a wrapper for it which you can find here https://github.com/sergey-dryabzhinsky/python-zstd and https://github.com/facebook/zstd/releas ... -win32.zip

Not sure how to apply these but i thought i'd post them for anyone wanting to try and edit the script to support the game. 

Oh you can find the script here. https://bitbucket.org/Frankelstner/fros ... tlefront-2
Thank you! I will try the script later today.
## Post #4
- Username: Godxon1
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Jun 06, 2015 2:35 am
- Post datetime: 2017-11-14T14:32:49+00:00
- Post Title: Star Wars Battlefront 2 (2017) - How to extract files?

> Reply from JakeGreen
>
> Godxon1 wrote:Hello everyone!
I am trying to extract files from new SWBF II (it is now in Trial), but unfortunately extraction tools for SWBF 2015 (https://forum.xentax.com/viewtopic.php?f=33&t=13145) aren't working. I am especially looking for localization files.

Could anyone look at it?

You can download the game files there (it is with first cas file in each folder only):
https://mega.nz/#F!vE8zibqK!-6prGm6e0IFS6ZaUwFmEzg

Thank you very much!
Godxon

The game has changed since the beta and has ZSTD compression on it's cat/cas files but Python won't support that by default so you need a wrapper for it which you can find here https://github.com/sergey-dryabzhinsky/python-zstd and https://github.com/facebook/zstd/releas ... -win32.zip

Not sure how to apply these but i thought i'd post them for anyone wanting to try and edit the script to support the game. 

Oh you can find the script here. https://bitbucket.org/Frankelstner/fros ... tlefront-2
Unfortunately I don't know how to use the script. 
It gives me this error:

```
  File "C:\Users\Honza\Desktop\Frankelstner-frostbite-battlefront-2-389512d68cf5\dumper.py", line 44, in <module>
    LZ77 = cdll.LoadLibrary("LZ77")
  File "C:\Python27\lib\ctypes\__init__.py", line 444, in LoadLibrary
    return self._dlltype(name)
  File "C:\Python27\lib\ctypes\__init__.py", line 366, in __init__
    self._handle = _dlopen(self._name, mode)
WindowsError: [Error 126] Uvedený modul nebyl nalezen
>>> 
```
## Post #5
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2017-11-14T18:54:52+00:00
- Post Title: Star Wars Battlefront 2 (2017) - How to extract files?

Godxon1


 LZ77.rar
(11.83 KiB) Downloaded 87 times
## Post #6
- Username: Godxon1
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Jun 06, 2015 2:35 am
- Post datetime: 2017-11-14T19:44:41+00:00
- Post Title: Star Wars Battlefront 2 (2017) - How to extract files?

> Reply from Haoose
>
> Godxon1
LZ77.rar
Thank you, but I still have some issues.

```
Type "copyright", "credits" or "license()" for more information.
>>> 
 RESTART: C:\Users\Honza\Desktop\Frankelstner-frostbite-battlefront-2-389512d68cf5\dumper.py 
layout.toc
abilities.toc

Traceback (most recent call last):
  File "C:\Users\Honza\Desktop\Frankelstner-frostbite-battlefront-2-389512d68cf5\dumper.py", line 298, in <module>
    if "tocRoot" in locals():  dumpRoot(tocRoot)
  File "C:\Users\Honza\Desktop\Frankelstner-frostbite-battlefront-2-389512d68cf5\dumper.py", line 278, in dumpRoot
    dump(fname,targetDirectory)
  File "C:\Users\Honza\Desktop\Frankelstner-frostbite-battlefront-2-389512d68cf5\dumper.py", line 195, in dump
    writePayload(entry, targetPath, sourcePath)
  File "C:\Users\Honza\Desktop\Frankelstner-frostbite-battlefront-2-389512d68cf5\dumper.py", line 243, in casPayload
    LZ77.decompress(catEntry.path,catEntry.offset,catEntry.size, bundleEntry.originalSize,targetPath)
WindowsError: [Error -529697949] Windows Error 0xE06D7363
>>> 
```


I've only edited this: [https://pastebin.com/R3cscWiz](https://pastebin.com/R3cscWiz) in the script.
## Post #7
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2017-11-15T08:55:33+00:00
- Post Title: Star Wars Battlefront 2 (2017) - How to extract files?

It won't work because it's still calling for LZ4 decompression with the LZ77 DLL, it needs ZSTD decompression so you will have to figure out a way to edit the rest of the script before it works.
## Post #8
- Username: kschade45
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Nov 23, 2017 8:49 am
- Post datetime: 2017-11-23T00:53:54+00:00
- Post Title: Star Wars Battlefront 2 (2017) - How to extract files?

Ever find anything out? I've been struggling to get it to work. I've been all over the web trying to find a solid ZSTD.dll file and supporting files to work.
## Post #9
- Username: SaanHolo
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Nov 21, 2017 5:17 pm
- Post datetime: 2017-11-23T01:13:53+00:00
- Post Title: Star Wars Battlefront 2 (2017) - How to extract files?

There's a ZSTD dll from Aluigi that's compiled from the current (9th October 2017) source of zstd, that contains legacy algorithms available [http://aluigi.org/bms/zstd.dll](http://aluigi.org/bms/zstd.dll)

I haven't been able to get the scripts to work though, they go through all the files, creating folders but no actual files are dumped. Anyone else had any luck?
## Post #10
- Username: Godxon1
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Jun 06, 2015 2:35 am
- Post datetime: 2017-11-23T12:28:22+00:00
- Post Title: Star Wars Battlefront 2 (2017) - How to extract files?

There are updated python scripts for SWBF II by Daemon:
[viewtopic.php?f=16&t=17114&start=75](http://forum.xentax.com/viewtopic.php?f=16&t=17114&start=75)
## Post #11
- Username: kschade45
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Nov 23, 2017 8:49 am
- Post datetime: 2017-11-23T17:48:36+00:00
- Post Title: Star Wars Battlefront 2 (2017) - How to extract files?

Nice! Let me know if you get this working. I'm personally only looking for the audio, I'll keep trying.
## Post #12
- Username: arkham45128
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Nov 26, 2017 5:22 am
- Post datetime: 2017-11-25T21:26:20+00:00
- Post Title: Star Wars Battlefront 2 (2017) - How to extract files?

Hi everyone!
I have the game and I want to have ALL the Castillian (From Spain) Spanish voices audio files

Can anyone explain to me what do I have to do?
Or can anyone extract'em and put it on MEGA?

Thanks
## Post #13
- Username: Hashbandit
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Nov 29, 2017 10:08 pm
- Post datetime: 2017-11-29T14:13:14+00:00
- Post Title: Star Wars Battlefront 2 (2017) - How to extract files?

Has anyone gotten this to work??
## Post #14
- Username: kschade45
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Nov 23, 2017 8:49 am
- Post datetime: 2017-11-30T16:18:16+00:00
- Post Title: Star Wars Battlefront 2 (2017) - How to extract files?

Daemon1's tools work just fine! Link to the thread is posted above.
