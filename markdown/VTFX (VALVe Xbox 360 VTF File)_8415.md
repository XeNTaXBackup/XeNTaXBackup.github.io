## Post #1
- Username: Friendsxix
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Jan 26, 2011 1:09 pm
- Post datetime: 2012-02-28T01:35:58+00:00
- Post Title: VTFX (VALVe Xbox 360 VTF File)

I've been exploring the Xbox 360 VALVe games, and have found the VTF files to be a special version only used in the console versions (The first 4 bytes of the file are VTFX). I would appreciate any help that can be given to help decompress it, and possibly even convert it to the standard VTF format! The file appears to use LZMA compression, too.
This is the format spec:
[https://developer.valvesoftware.com/wik ... ile_format](https://developer.valvesoftware.com/wiki/VTFX_file_format)
This is the regular VTF spec: [https://developer.valvesoftware.com/wiki/VTF#VTF_header](https://developer.valvesoftware.com/wiki/VTF#VTF_header)

Here is a sample file (VTFX): [http://dl.dropbox.com/u/1228269/vtf/v_minigun.360.vtf](http://dl.dropbox.com/u/1228269/vtf/v_minigun.360.vtf)
Here is a standard VTF: [http://dl.dropbox.com/u/1228269/vtf/v_minigun.vtf](http://dl.dropbox.com/u/1228269/vtf/v_minigun.vtf)

Thanks!  

EDIT:
This is also in the Source SDK: [http://dl.dropbox.com/u/1228269/vtf/lzmaDecoder.h](http://dl.dropbox.com/u/1228269/vtf/lzmaDecoder.h)
