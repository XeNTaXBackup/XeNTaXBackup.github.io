## Post #1
- Username: devqq
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Dec 28, 2017 3:55 am
- Post datetime: 2017-12-27T20:09:48+00:00
- Post Title: They Are Billions

It's a 2D isometric RTS game with a nice art style.

The game's exe can be easily decompiled to readable code with JustDecompile C# decompiler.

So far only looked at the buildings data (there are also animated models, weather effects, particles, terrain etc), there are 3 files for each image archive and also there are variations of this same archive for different graphics qualities, LQ, MQ, HQ.

.dxatlas file, simply opens with winrar, contains an xml that describes all the png's in the binary archive.
.trans file, same as above but contains transparency info, not sure why this info isn't already in the png's.
.dat file, a simple binary archive, I don't think it even uses compression? The code refers to it as SharpSerializer and it reads 'properties' and converts them to C# objects.

The only problem is I never used C# so I am a bit lost on how to extract the png's, so I am hoping someone can assist me.

Attaching a sample of a single image set:
[http://www14.zippyshare.com/v/fpRHGmrO/file.html](http://www14.zippyshare.com/v/fpRHGmrO/file.html)

Thanks
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-12-27T20:42:51+00:00
- Post Title: They Are Billions

rename the extension of the *.dat sample to dds and open with any image editor that supports dds images.
the *.trans and *.dxatlas file can be extracted with 7-zip (right click "Extract to") and opened with any text editor.
## Post #3
- Username: devqq
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Dec 28, 2017 3:55 am
- Post datetime: 2017-12-27T21:32:30+00:00
- Post Title: They Are Billions

> Reply from AceWell
>
> rename the extension of the *.dat sample to dds and open with any image editor that supports dds images.
the *.trans and *.dxatlas file can be extracted with 7-zip (right click "Extract to") and opened with any text editor.

Brilliant!!! thanks. For anyone wondering what can open dds images, its either the nvidia viewer: [http://www.nvidia.co.uk/object/windows_ ... iewer.html](http://www.nvidia.co.uk/object/windows_texture_viewer.html)
or the newest irfanview with the plugin pack. Thanks again!
## Post #4
- Username: UtkuGARIP
- Rank: beginner
- Number of posts: 38
- Joined date: Tue Feb 28, 2017 8:53 am
- Post datetime: 2018-05-28T15:00:58+00:00
- Post Title: They Are Billions

> Reply from AceWell
>
> rename the extension of the *.dat sample to dds and open with any image editor that supports dds images.
the *.trans and *.dxatlas file can be extracted with 7-zip (right click "Extract to") and opened with any text editor.

ZXStrings.dat language file. How do I edit?

[https://my.pcloud.com/publink/show?code ... pmFYu7x3Ny](https://my.pcloud.com/publink/show?code=XZHglj7ZLJ5IPjDu900BQmJgpHpmFYu7x3Ny)
