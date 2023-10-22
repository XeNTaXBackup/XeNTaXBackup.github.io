## Post #1
- Username: XxsimonexX
- Rank: beginner
- Number of posts: 36
- Joined date: Fri Dec 18, 2015 6:17 am
- Post datetime: 2020-11-25T01:24:18+00:00
- Post Title: [SOLVED] Help converting .wem files with vgmstream

Hello!
I'm trying to convert multiple .wem audio files using the script vmgstream ( [https://github.com/vgmstream/vgmstream](https://github.com/vgmstream/vgmstream) )
But i really can't figure out how to do it!
vgmstram only allow to convert a single file at once, does it?
Please help me with that.
Thanks to all!
## Post #2
- Username: 0ther1
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Apr 30, 2020 10:56 am
- Post datetime: 2020-11-25T05:46:55+00:00
- Post Title: [SOLVED] Help converting .wem files with vgmstream

You can use batch script, either run cmd in folder with .wem files and type

```
for %f in (*.wem) do path\to\vgmstream.exe %f
```

Or you can make .bat file in same folder, write inside

```
for %%f in (*.wem) do path\to\vgmstream.exe %%f
```

and run it. Also, in both ways you can add in the end

```
>nul 2>nul
```

to disable vgmstream's output
## Post #3
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2020-11-25T12:27:27+00:00
- Post Title: [SOLVED] Help converting .wem files with vgmstream

If you use Foobar (with the vgmstream plugin), you can convert as many files at once as you like, no need to mess about with command line stuff.
## Post #4
- Username: XxsimonexX
- Rank: beginner
- Number of posts: 36
- Joined date: Fri Dec 18, 2015 6:17 am
- Post datetime: 2020-11-25T19:34:59+00:00
- Post Title: [SOLVED] Help converting .wem files with vgmstream

> You can use batch script, either run cmd in folder with .wem files and type
>
> Code: Select allfor %f in (*.wem) do path\to\vgmstream.exe %f
Thank you so much! Problem solved!
