## Post #1
- Username: Machinedramon
- Rank: advanced
- Number of posts: 77
- Joined date: Tue Apr 09, 2019 1:13 am
- Post datetime: 2021-06-28T08:49:23+00:00
- Post Title: Xbox weird Uvs

hi there, if anyone can help me figure out what the uvs are in the next files, would be great!   

two example files provided with the DXT for each one
[files.rar](https://xentaxbackup.github.io/file/20373_files.rar)
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-06-28T12:41:34+00:00
- Post Title: Xbox weird Uvs

There're two uv channels at offset 0x10 and 0x14. The one at 0x14 seems more appropriate for the texture. Need proper scaling and translation to map the coordinates into the (0,1) range though.
[grdgrl_fake02_vb0_uv.png](https://xentaxbackup.github.io/file/20375_grdgrl_fake02_vb0_uv.png)
## Post #3
- Username: Machinedramon
- Rank: advanced
- Number of posts: 77
- Joined date: Tue Apr 09, 2019 1:13 am
- Post datetime: 2021-06-28T17:59:33+00:00
- Post Title: Xbox weird Uvs

did some funky function for it and seems to work???



```
    coord = round((((f.readShort()/(65535/2))-1)*100)/1.5763,4)
    return coord

```
