## Post #1
- Username: osdever
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Sep 16, 2017 11:58 pm
- Post datetime: 2017-09-16T19:51:15+00:00
- Post Title: Un-swizzling NFS MW 2005 Xbox 360 textures

Hey everyone, I was working on a mod for the PC version of NFS Most Wanted (2005) which includes Xbox 360 textures. They are twice higher res than the PC version, so they definitely look better. I was able to open all the texture archives properly, but all the DXT textures are so-called swizzled: they are broken to chunks that are all over the place. The chunks are 4x4 pixels, the textures are also offset but it's pretty easy to fix (and I did, I'm sending the original files though). Do you, by any chance, know how to properly un-swizzle them, any scripts, plugins, whatever? I'm pretty sure the question was answered before for billions of times, but I'm kinda new to the modding scene so can you help? Thanks. The textures are there: [https://mega.nz/#!9MpBXJBS!8hmFSH6XwfmD ... d2cPg31f6Q](https://mega.nz/#!9MpBXJBS!8hmFSH6XwfmDFRer5HkY4SKBVMEJjTbRzd2cPg31f6Q). Keep in mind they are headerless so you'll have to copy it over from something. I can't provide you with the dimensions but keep in mind that all TRNS_* textures are 256*2048 and those're actually the only ones important. Any help will be appreciated. Sorry for the archive being pretty big
## Post #2
- Username: osdever
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Sep 16, 2017 11:58 pm
- Post datetime: 2017-09-21T16:36:35+00:00
- Post Title: Un-swizzling NFS MW 2005 Xbox 360 textures

Anyone?
## Post #3
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-09-22T00:57:52+00:00
- Post Title: Un-swizzling NFS MW 2005 Xbox 360 textures

> Reply from osdever
>
> Keep in mind they are headerless....
theres your problem and heres your Noesis python script solution  


 tex_dds.zip
(801 Bytes) Downloaded 126 times


you have to set the format, width, height and data offset in the script by hand,
i currently have it set to open one of your "TRNS_* textures" at 256 wide and 2048 high.
## Post #4
- Username: osdever
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Sep 16, 2017 11:58 pm
- Post datetime: 2017-09-22T15:06:29+00:00
- Post Title: Un-swizzling NFS MW 2005 Xbox 360 textures

Thanks A LOT! Really A LOT, that's awesome.
