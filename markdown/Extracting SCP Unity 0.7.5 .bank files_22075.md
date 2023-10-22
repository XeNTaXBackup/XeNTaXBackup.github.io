## Post #1
- Username: 4bit321
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Apr 28, 2020 12:07 am
- Post datetime: 2020-04-27T16:16:45+00:00
- Post Title: Extracting SCP Unity 0.7.5 .bank files

So I've been trying to extract the SCP Unity .bank files, but so far I haven't been very successful. There aren't just .bank files though, there are .streams.bank files and .assets.bank files. It might be just part of the file name and it threw me off but hey, the more you know. Any ideas?
[scpunity.png](https://xentaxbackup.github.io/file/18049_scpunity.png)
## Post #2
- Username: 09williamsad
- Rank: veteran
- Number of posts: 104
- Joined date: Sun Mar 13, 2016 9:09 pm
- Post datetime: 2020-09-12T17:20:20+00:00
- Post Title: Extracting SCP Unity 0.7.5 .bank files

The header "RIFF FEV FMT".
These are unity bank files but they appear to have encryption as the various fsb tools cannot read them.
Samples <Link removed due to site policy>
## Post #3
- Username: hedgsaurus
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Mar 10, 2022 10:39 am
- Post datetime: 2022-03-10T02:49:44+00:00
- Post Title: Extracting SCP Unity 0.7.5 .bank files

Was anybody able to find a way to open these .bank files? I've been trying for a while but I'm not very well versed to be able to figure it out.
## Post #4
- Username: mortalis
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-03-10T20:31:10+00:00
- Post Title: Extracting SCP Unity 0.7.5 .bank files

Samples are not available anymore, so I can't check them, but if they are not encrypted, then foobar2000 with vgmstream plugin should play them without issues. [http://wiki.xentax.com/index.php/FMOD_Audio_BANK](http://wiki.xentax.com/index.php/FMOD_Audio_BANK)
## Post #5
- Username: hedgsaurus
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Mar 10, 2022 10:39 am
- Post datetime: 2022-03-11T01:50:26+00:00
- Post Title: Extracting SCP Unity 0.7.5 .bank files

Worked, thanks!
## Post #6
- Username: mortalis
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jun 27, 2020 3:50 am
- Post datetime: 2023-03-25T21:13:45+00:00
- Post Title: Extracting SCP Unity 0.7.5 .bank files

Thanks for the wiki article.
Also it's possible to use vgmstream tool directly on the .bank files.
For Windows for example, they have a binary package vgmstream-win64.zip with vgmstream-cli command line tool.
This command should extract the audio to wav files:

```
vgmstream-cli.exe -S 0 file.bank
```

If the .bank file contains multiple streams, they will be extracted to separate files.
