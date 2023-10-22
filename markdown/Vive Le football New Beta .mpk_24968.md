## Post #1
- Username: CrispX
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Feb 24, 2016 2:55 am
- Post datetime: 2022-01-19T16:18:16+00:00
- Post Title: Vive Le football New Beta .mpk

Hi.
Here's one small file from 7 one's.
I need a script only to extract the textures, i want to grab the team logos only. 
I already try everything.
Thanks.   

[https://www.filemail.com/d/qirmpbmckuxekof](https://www.filemail.com/d/qirmpbmckuxekof) 7 Days only and it will be deleted.
Ask me for all of them if need.
[Image.png](https://xentaxbackup.github.io/file/21650_Image.png)
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-01-19T19:45:29+00:00
- Post Title: Vive Le football New Beta .mpk

That is just raw data for multiple files in single archive.
There is no TOC in your sample.

First file is a TTF font [http://wiki.xentax.com/index.php/OpenType_Font_TTF_OTF](http://wiki.xentax.com/index.php/OpenType_Font_TTF_OTF)
If you'll change extension from MPK to TTF, you'll get a valid font file (+ some data at the end).


Edit: I've just noticed MPKINFO file on your screenshot.
TOC is probably stored there, so you can upload this file as well.
## Post #3
- Username: CrispX
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Feb 24, 2016 2:55 am
- Post datetime: 2022-01-20T08:30:00+00:00
- Post Title: Vive Le football New Beta .mpk

Here's the full package: <link deleted by moderator>
Extract the apk file using 7zip and go to assets folder.
Thanks
## Post #4
- Username: CrispX
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-01-20T16:39:04+00:00
- Post Title: Vive Le football New Beta .mpk

Well, it seems that index file contains some sizes and file hashes.
This is the file format from what I can tell:

```
4 bytes (uint32) - version?  // 2
4 bytes (uint32) - number of entries

num_of_entries *
{
   8 bytes - unknown
   4 bytes (uint32) - file size?
   4 bytes (uint32) - file type?
   4 bytes - unknown
}
```


For now I don't know how to match mpkinfo index with files in those MPK archives.
I'm adding file in the attachment for others to check.
[Resources_mpkinfo.zip](https://xentaxbackup.github.io/file/21653_Resources_mpkinfo.zip)
