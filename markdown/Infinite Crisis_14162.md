## Post #1
- Username: maharnavi
- Rank: n00b
- Number of posts: 19
- Joined date: Wed Dec 10, 2014 10:46 pm
- Post datetime: 2016-03-30T11:48:40+00:00
- Post Title: Infinite Crisis

Hello i would like to know how to unpack or decompress model and animation files from Infinite crisis.I have the updated Version of Infinite crisis.The file extensions are .pck and .rp
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-04-01T17:47:49+00:00
- Post Title: Infinite Crisis

a small file sample might be helpful (smallest one you have - 
if it's above 10 MB then post a screenshot of the first and the last 1kB in a hex editor.)
## Post #3
- Username: maharnavi
- Rank: n00b
- Number of posts: 19
- Joined date: Wed Dec 10, 2014 10:46 pm
- Post datetime: 2016-04-02T04:38:18+00:00
- Post Title: Infinite Crisis

Here is a sample file
[0xa00000b8.rar](https://xentaxbackup.github.io/file/10667_0xa00000b8.rar)
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-04-02T07:21:58+00:00
- Post Title: Infinite Crisis

thx - it claims to be a DXT1 file.
I tried a solution of 512x512:



0xa00000b8_rp.JPG (142.11 KiB) Viewed 283 times


(dunno why it doesn't work with TextureFinder, even with the first 0x434 bytes cut off)

edit: upps, I see: I was 11 bytes off
## Post #5
- Username: maharnavi
- Rank: n00b
- Number of posts: 19
- Joined date: Wed Dec 10, 2014 10:46 pm
- Post datetime: 2016-04-02T07:38:27+00:00
- Post Title: Infinite Crisis

which 3d software did you use for the rp file
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-04-02T09:14:10+00:00
- Post Title: Infinite Crisis

a modified version of the DDSWithoutD3DX11 project (from MS DirectX SDK), unfinished and unreleased
## Post #7
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-04-02T09:23:03+00:00
- Post Title: Infinite Crisis

weird format, that texture is in three sections and each one has a different shift value.
the top section is shifted by 1079 the midsection by 1084 and the last section by 1089 to look something like this if save each out an crop and combine them  

this was done quickly and is not perfect, you will need spend more time on it
## Post #8
- Username: maharnavi
- Rank: n00b
- Number of posts: 19
- Joined date: Wed Dec 10, 2014 10:46 pm
- Post datetime: 2016-04-02T09:23:59+00:00
- Post Title: Infinite Crisis

There are other files of infinite crisis which has rp extension and some of them are 31 MB and 100 MB long.how can i decompress or view inside of those rp files. if you could create a script for quickbms to decompress models and animations and vfx from infinite crisis
## Post #9
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2016-04-02T15:00:01+00:00
- Post Title: Infinite Crisis

can you post another example .rp file please.

a large file if you can.

(the original filename is after the data "FE_chr_Batman_Gas")
## Post #10
- Username: maharnavi
- Rank: n00b
- Number of posts: 19
- Joined date: Wed Dec 10, 2014 10:46 pm
- Post datetime: 2016-04-02T15:27:01+00:00
- Post Title: Infinite Crisis

Please provide me your gmail address so that i can send it to you through gmail or porivde me your skype address so that i can send  the files to you through skype because the xentax is not letting me upload more than 256 kb and there are other files more than 31 mb and 100 mb
## Post #11
- Username: maharnavi
- Rank: n00b
- Number of posts: 19
- Joined date: Wed Dec 10, 2014 10:46 pm
- Post datetime: 2016-04-03T06:36:19+00:00
- Post Title: Infinite Crisis

Hello you donot need to provide me your email address or skype address.I found a way to send you the big file with rp extension.I splitted the files from 1 to 42 using winrar.You have to download from part 1 to part 42.I will upload one file part by part as it does not allow me to upload more than 256 kb

Mod Edit: Attachment removed
## Post #12
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-04-03T13:27:00+00:00
- Post Title: Infinite Crisis

> Reply from maharnavi
>
> Hello you donot need to provide me your email address or skype address.I found a way to send you the big file with rp extension.I splitted the files from 1 to 42 using winrar.You have to download from part 1 to part 42.I will upload one file part by part as it does not allow me to upload more than 256 kb

Mod Edit: Attachment removed

Hello, I'd like to inform you that it's unacceptable to post 42 times, each with a file attachment resulting in 3 pages of spam. You are free to use an external file-sharing website in these cases. It's simply not feasible for someone to manually download from 42 different posts.

On the side note, thanks so much to those who have contributed so far!
Please continue discussion as normal.

Regards.
## Post #13
- Username: Sankar26
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Apr 03, 2016 10:23 pm
- Post datetime: 2016-04-03T14:34:32+00:00
- Post Title: Infinite Crisis

Hello I am Sankar.I want to decompress some files from Infinite Crisis like model and animation and vfx files.There are many .rp files.their size are 31mb,100mb,1mb,6mb.could anyone please create a quickbms script for me so that I can decompress those files with it.They are too big and xentax is not allowing me to upload more then 256 kb
## Post #14
- Username: Sankar26
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Apr 03, 2016 10:23 pm
- Post datetime: 2016-04-05T08:05:59+00:00
- Post Title: Infinite Crisis

Dear developer and forum administration

I would like to inform you that my son is suffering from autism and he has some desire to make his own gaming 3d model.Please take it on grant to unblock his account.His account username is maharnavi and password is Mod Edit: Sensitive information removed.

With Regards

Papiya Ganguly
