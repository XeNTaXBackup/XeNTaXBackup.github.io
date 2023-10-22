## Post #1
- Username: CheloXL
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Apr 10, 2011 1:41 am
- Post datetime: 2012-10-11T15:46:16+00:00
- Post Title: IPhone/IPad PNG Fixer

Hi everybody,

Since I was tired of looking for a tool that can convert iPhone/iPad iPngs(tm)  to standard pngs and found none that works reliably, I decided to create one from scratch. After a couple of hours, [here you have it](http://forum.xentax.com/blog/?p=478).

It is a console application, so do not expect any fancy graphics. And since I created it for myself, it also doesn't has any help.

How to use: The application accepts one/more file(s)/directory(ies) as arguments. Any file you pass will be first checked to see if it is really a png file and then converted. Any directory you pass will be scanned recursively for .png files inside, and all the found files will be then converted.

You can drag the application to your desktop (or create a shortcut to it) and simply drag/drop files/folders from windows explorer.

The application requires .net 4.5 as I'm making use of the task parallel library to convert multiple files at once.

Technical info:

iPngs are invalid pngs. They not only have an invalid chunk type (CgBI) but also the IDAT chunk (the chunk that has the actual image data) is missing both the first 2 bytes (that indicate the type of compression used... PNG has only one type of compression, but you need those anyways) and the last 4 bytes, that are the checksum (Adler32) of the uncompressed data.

iPngs also use another "feature" of the PNG format: They split the actual image data into several IDAT chunks. That it is actually a feature of the PNG format, and that's where all the other decoders fail: The specification clearly states that the boundaries between IDAT chunks do not need to be related to the deflate block boundaries. All the other decoders assume that, and while that may be true for most IDAT chunks, they are not true for others and then the decoding fails.

iPngs have the R/B colors swapped, so after fixing all the above, you have to decompress the iPng into a bitmap, swap the colors and convert the bitmap back into a (now correct) png. You can't do the swapping directly on the decompressed deflated data because pngs also employs "filters" that are used to pre-compress data.

Basically, what I'm doing on the fixer is:
1) Read the PNG into chunks.
2) Check if I have a CgBI. If I have one, remove it and set the "isIphone" variable to true.
3) Combine all the existing IDAT chunks into one.
4) If "isIphone", add to the IDAT the compression method info/Adler32 CRC.
5) Create a bitmap in memory with the fixed PNG, if "isIphone", fix colors
6) Save the bitmap back to disk, as PNG.
[IPngDecoder.7z](https://xentaxbackup.github.io/file/5896_IPngDecoder.7z)
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2012-10-11T20:43:05+00:00
- Post Title: IPhone/IPad PNG Fixer

Great! But can you also upload the file?
## Post #3
- Username: CheloXL
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Apr 10, 2011 1:41 am
- Post datetime: 2012-10-11T21:53:43+00:00
- Post Title: IPhone/IPad PNG Fixer

Mmm... I put a link to the tools page on the xentax blog (so if I update it I don't have to maintain 2 versions)... is that ok?
## Post #4
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2012-10-12T05:12:18+00:00
- Post Title: IPhone/IPad PNG Fixer

But i could not download it from the tools blog? Said something about no file found.
## Post #5
- Username: CheloXL
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Apr 10, 2011 1:41 am
- Post datetime: 2012-10-12T13:09:50+00:00
- Post Title: IPhone/IPad PNG Fixer

Ok, not sure why.. seems to be a problem on the blog, because I uploaded the file again and I also get the error. Anyways, I attached the file to the original post now.
## Post #6
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2012-10-12T13:48:26+00:00
- Post Title: IPhone/IPad PNG Fixer

Just tried it with a test account, worked fine though. Upload should work for you. Odd. I uploaded it now to the post at the blog. You must browse to the file, and then click Publish (or Update Post). It should have done it.
## Post #7
- Username: CheloXL
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Apr 10, 2011 1:41 am
- Post datetime: 2012-10-23T15:53:55+00:00
- Post Title: IPhone/IPad PNG Fixer

The file is attached to the first post. Also, on that same post, there is a link to a tools page where you can also find the tool...
## Post #8
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2012-11-04T02:15:30+00:00
- Post Title: IPhone/IPad PNG Fixer

[out]
## Post #9
- Username: CheloXL
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Apr 10, 2011 1:41 am
- Post datetime: 2012-11-06T20:50:42+00:00
- Post Title: IPhone/IPad PNG Fixer

The application needs .net 4.5. Make sure that you have it installed before you try to run it. Didn't check on XP since I do not have it to test. But it works fine under W7 x32 and x64.
## Post #10
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2012-11-07T01:38:01+00:00
- Post Title: IPhone/IPad PNG Fixer

XP isn't a supported operating system for .NET Framework 4.5 according to the download page.
[http://www.microsoft.com/en-us/download ... x?id=30653](http://www.microsoft.com/en-us/download/details.aspx?id=30653)
## Post #11
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2012-11-07T12:03:55+00:00
- Post Title: IPhone/IPad PNG Fixer

[out]
