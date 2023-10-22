## Post #1
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2010-10-13T03:41:02+00:00
- Post Title: X360 Gundam Musou 2 *.bin file

Hi everybody! 
Please help me solve my problem
I have some *.bin files from X360 Gundam Musou 2.
I have a question concerning *.bin files
How to convert *.bin to obj file?

*.bin files Import error in Noesisv18,,,



BIN samples:

 BNS2473.7z
(26.55 KiB) Downloaded 26 times





Thank you.
## Post #2
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2010-10-14T06:46:35+00:00
- Post Title: X360 Gundam Musou 2 *.bin file

dword IntegerID  //0x1EDE
dword numRes
dword BlockSize
dword Padding

struct Index {
  dword ofsBlock  //real offset = ofsBlock * BlockSize
  dword ResSize
}

By fatduck

I don't know anything any more.
## Post #3
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2010-10-14T07:12:56+00:00
- Post Title: X360 Gundam Musou 2 *.bin file

> Reply from youngmark
>
> dword IntegerID  //0x1EDE
dword numRes
dword BlockSize
dword Padding

struct Index {
  dword ofsBlock  //real offset = ofsBlock * BlockSize
  dword ResSize
}

By fatduck

I don't know anything any more.

Thank you for your help.	
Could you give us some more details on that.
## Post #4
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2010-10-15T14:12:27+00:00
- Post Title: X360 Gundam Musou 2 *.bin file

I did this model format a while ago at the request of chrrox. It was a quick one-night job, as I recall, and I don't think I ever got the textures mapped properly. I'm not really sure, I haven't looked at it in forever. Here's example loader code. (it won't compile due to external dependencies, but the file structure is in there)

[http://pastebin.com/j3FhfNv3](http://pastebin.com/j3FhfNv3)
## Post #5
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2010-10-16T01:05:08+00:00
- Post Title: X360 Gundam Musou 2 *.bin file

> Reply from MrAdults
>
> I did this model format a while ago at the request of chrrox. It was a quick one-night job, as I recall, and I don't think I ever got the textures mapped properly. I'm not really sure, I haven't looked at it in forever. Here's example loader code. (it won't compile due to external dependencies, but the file structure is in there)

http://pastebin.com/j3FhfNv3

Thank you for your help.	
The example is hard to understand.

In this field, I am as good as a beginner.
