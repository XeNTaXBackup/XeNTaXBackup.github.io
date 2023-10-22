## Post #1
- Username: Caesar007
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Apr 25, 2016 12:51 am
- Post datetime: 2016-05-06T03:46:07+00:00
- Post Title: help needed - tga - swizzle (tiling) - xbox

if anyone can help, that will be great.

in attachment:
1. texture file from PC version of RTCW
2. texture file from Xbox version of RTCW without tga file header, as it stored in cachemap file container
3. part of file table, that contains data, needed for tga file header recreation

the texture in Xbox is 2 times smaller, but swizzle (tiling) is used.

please, help to understand, how to convert tga texture from xbox to pc format.

Thanks.

update 08.05.2016
here the file with last discoveries [http://www.filedropper.com/rtcwtow-cach ... n-progress](http://www.filedropper.com/rtcwtow-cachemap-v4-work-in-progress)
I need help in this:
1. TGA - under swizzling (tiling) - possible Morton order;
2. write complete unpacker for cachemap container based on my finding. 

payment - 50$ over PayPal
[flare5.tga_research.7z](https://xentaxbackup.github.io/file/10905_flare5.tga_research.7z)
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-08-03T04:11:21+00:00
- Post Title: help needed - tga - swizzle (tiling) - xbox

hi, this script will open your headerless swizzled Xbox tga texture  


 tex_ReturnToCastleWolfenstein_Xbox_tga.zip
(777 Bytes) Downloaded 69 times



thanks to chrrox for the morton order unswizzle solution
