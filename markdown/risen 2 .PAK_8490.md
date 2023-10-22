## Post #1
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2012-03-07T00:49:06+00:00
- Post Title: risen 2 .PAK

[Here](http://dl.dropbox.com/u/9919707/blogs/xentax.com/risen2-pc/meshes.7z) is new .pak archive from risen 2, won't opens with any tools
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-03-07T01:10:04+00:00
- Post Title: risen 2 .PAK

the following is the reply I gave to an user via e-mail, maybe it's useful:

> looks like the files informations (name, offset, size) are encrypted or
>
> similar.
>
> 
>
> anyway the files are almost all compressed with zlib so offzip is ok for
>
> them, obviously you will not have the full filenames but it's for sure
>
> better than nothing for the moment :)
## Post #3
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2012-03-07T01:34:44+00:00
- Post Title: risen 2 .PAK

> Reply from aluigi
>
> anyway the files are almost all compressed with zlib so offzip is ok for
them, obviously you will not have the full filenames but it's for sure
better than nothing for the momenti'm using this command:

```
offzip -S meshes.pak 0 0
```
black screen appears and calculating something, then closed, but what next?

edit:
okay, i've managed to extract bunch of .gar files with this command:

```
offzip -a meshes.pak .\output_folder 0
```

thanks a lot Luigi
## Post #4
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2012-03-12T19:09:15+00:00
- Post Title: risen 2 .PAK

i can't extract 'images.pak' (about 1.5Gb) with all textures, looks like it has different compression method
anyone know how to unpack it?
## Post #5
- Username: jl78
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Apr 27, 2012 8:06 pm
- Post datetime: 2012-04-27T12:10:28+00:00
- Post Title: risen 2 .PAK

update: 
[http://forum.worldofplayers.de/forum/th ... viewfull=1](http://forum.worldofplayers.de/forum/threads/1077129-Risenaut-RisenPAK?p=18844813&viewfull=1)
