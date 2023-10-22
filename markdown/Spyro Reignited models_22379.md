## Post #1
- Username: vihorov
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jul 07, 2020 11:02 pm
- Post datetime: 2020-07-09T09:48:02+00:00
- Post Title: Spyro Reignited models?

Hi everyone, I wanted to know if the character and world models from Spyro Reignited are in a format that some tool can import and export to a common format. 

I am developing a similar platformer game and using those as reference would be a trmendous help in my learning journey. 
I'm more interested in the world maps so that I can study how efficiently the assets (instanced models) were reused throught the map as well as in what ways decals (projected textures) were used.

Thanks.
## Post #2
- Username: Ecelon
- Rank: advanced
- Number of posts: 49
- Joined date: Fri Oct 17, 2014 9:50 am
- Post datetime: 2020-07-10T12:00:09+00:00
- Post Title: Spyro Reignited models?

[https://www.gildor.org/downloads](https://www.gildor.org/downloads)  <<< Tool download

[https://www.gildor.org/projects/umodel/compat](https://www.gildor.org/projects/umodel/compat) <<< Compatibility table!
## Post #3
- Username: vihorov
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jul 07, 2020 11:02 pm
- Post datetime: 2020-07-11T08:58:51+00:00
- Post Title: Spyro Reignited models?

Hi Ecelon,

Any ideas if these model importers and viewers also work with levels?

I tried extract.exe on one of the data files in the Steam game folder. The files are

```
pakchunk1-WindowsNoEditor.pak
pakchunk2-WindowsNoEditor.pak
```


When doing

```
extract pakchunk0-WindowsNoEditor.pak
```

Or trying to decompress first I get this log:

```
Pak ./pakchunk2-WindowsNoEditor.pak: 31623 files, mount point: "/Falcon/", version 4
Found 31623 game files (5 skipped) at path "."
******** pakchunk2-WindowsNoEditor.pak ********
*** ERROR: GetFileSize returns 0x1997CEE58
UnPackage::CreateLoader:pakchunk2-WindowsNoEditor.pak <- UnPackage::UnPackage:pakchunk2-WindowsNoEditor.pak, ver=100000/0, game=0 <- UnPackage::LoadPackage:pakchunk2-WindowsNoEditor.pak <- Main
```


I'm not sure what this means?
Thanks.
