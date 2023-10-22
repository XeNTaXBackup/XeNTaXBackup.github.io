## Post #1
- Username: Cryptonia
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Aug 20, 2009 12:11 am
- Post datetime: 2009-08-22T20:27:53+00:00
- Post Title: zlib problem?

hi i have a problem

also i want to change some files in a games whos use it


also i exact with offzip the zlib data(zlibed and unpacked)

so and for a test i recompresed the file but my problem is, file is bigger than the orginal, and this is shit when i must inject them later for change the textures in the game

the samples

orginal zlib
mypacket zlib
unpacked file
[http://www.xup.in/dl,19742179/dir.7z/](http://www.xup.in/dl,19742179/dir.7z/)
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-08-22T21:32:12+00:00
- Post Title: zlib problem?

the problem is that zlib is not so good for compressing because even setting the max factor (9) its result will be ever not much optimized in terms of size.
for example the implementation of the zlib inflate adopted by 7-zip is a lot more optimized.

I found the same problem of the low results of zlib when I wrote my packzip tool and was really very very irritating.
## Post #3
- Username: Cryptonia
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Aug 20, 2009 12:11 am
- Post datetime: 2009-08-22T21:49:43+00:00
- Post Title: zlib problem?

> Reply from Bugtest
>
> the problem is that zlib is not so good for compressing because even setting the max factor (9) its result will be ever not much optimized in terms of size.
for example the implementation of the zlib inflate adopted by 7-zip is a lot more optimized.

I found the same problem of the low results of zlib when I wrote my packzip tool and was really very very irritating.

yap am frind had this problem ² but inject bigger files than orginal is shit like u overwritte existing data from other data


7zip support zlib? how`?

i packed the file with 7zip to the zip format and got the smaler file
## Post #4
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2009-10-01T02:41:57+00:00
- Post Title: zlib problem?

IDK if this will help you, but I felt I had to try and help you, because thanks to you, I found out about the Offzip program.  Many thanks for that.  But anyway, download this tool:

[http://www.parkenet.com/apl/ZlibToolDemo.htm](http://www.parkenet.com/apl/ZlibToolDemo.htm)

You can set the compression level you want easily when recompressing a file.  Try setting it to the max, which is 9.  I have only had a few times that I could not compress a file smaller than the original one I was replacing.  If that still won't compress enough for you, there are some other tricks to try, especially if it is a DDS file.  I hope it works for you.   

Edit:  I went ahead and downloaded your files and was able to expand your compressed file, then I compressed it with the max compression and it compressed down to 1.86MB, which is a little bigger than your needed 1.85MB, if I get some extra time, I'll see if I can get that down for you.
## Post #5
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-10-01T06:00:20+00:00
- Post Title: zlib problem?

Hey brienj! Good to see you!
## Post #6
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2009-10-01T09:41:16+00:00
- Post Title: zlib problem?

> Reply from Mr.Mouse
>
> Hey brienj! Good to see you!
Hey, thanks.
## Post #7
- Username: Cryptonia
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Aug 20, 2009 12:11 am
- Post datetime: 2009-10-01T17:19:09+00:00
- Post Title: zlib problem?

well this 1.86 mb i not the problem we get the same size but its must smaler or same size

with dds and mipmap i know this trick but like on wav is this method a little shit okay delet 2 ms from it will work i think
## Post #8
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2009-10-02T00:37:28+00:00
- Post Title: zlib problem?

> Reply from Cryptonia
>
> well this 1.86 mb i not the problem we get the same size but its must smaler or same size

with dds and mipmap i know this trick but like on wav is this method a little shit okay delet 2 ms from it will work i think
I did not even notice there was a wav file in there, but taking off that much from the wav file prolly would do it.  Also, in the text part, if there are some letters that you can change, to be the same letters, or especially if you can remove any unneeded spaces, that would help compression.  Actually, any repetitive values in the whole file will help compression.  You have  very little to have to shrink it, you should easily be able to do it.  Good luck!

Thanks again for mentioning the Offzip program, it is exactly the type of program I have been dreaming about, and it even came with source code.  I love it.    

BTW, thanks to this program, I may be posting some pics of some hacks I might be doing on some Xbox 360 games.  Before I had this program, I didn't have the motivation to do everything by hand in a hex editor.  Funny that such a small little command-line program can make me be so happy.
