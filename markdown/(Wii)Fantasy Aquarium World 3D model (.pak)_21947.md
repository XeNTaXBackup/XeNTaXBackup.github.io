## Post #1
- Username: Ryoutukankiti
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Mar 17, 2020 2:10 pm
- Post datetime: 2020-03-31T04:11:54+00:00
- Post Title: (Wii)Fantasy Aquarium World 3D model (.pak)

I want to Fantasy Aquarium World's 3D model.
At The VG Resource,this game has brres format,so I thought this can extract to brres.
But,there is .pak So, can someone extract .pak file?

[https://drive.google.com/open?id=1jabS8 ... NSyyKOK143](https://drive.google.com/open?id=1jabS8ChIpkwvpmWDrrj9OqNSyyKOK143)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-04-02T08:27:53+00:00
- Post Title: (Wii)Fantasy Aquarium World 3D model (.pak)

Mesh file signature is "JMSH". Using hex2obj (view link in my sig) after unpacking with offzip (search on Xentax):
.



00c594b2-jms.jpg (92.08 KiB) Viewed 55 times

(No time to care for uvs.)
## Post #3
- Username: Ryoutukankiti
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Mar 17, 2020 2:10 pm
- Post datetime: 2020-04-02T16:59:38+00:00
- Post Title: (Wii)Fantasy Aquarium World 3D model (.pak)

> Reply from shakotay2 ↑Thu Apr 02, 2020 4:27 pm at Thu Apr 02, 2020 4:27 pm
>
> 
Mesh file signature is "JMSH". Using hex2obj (view link in my sig) after unpacking with offzip (search on Xentax):
.
00c594b2-jms.jpg(No time to care for uvs.)

I'm never seen offzip,so I tried to use offzip, but I couldn't understand how to use this(I surveyed and I made .bat file.But It was unsuccessful.)
So, teach me how did you use offzip,please?
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-04-02T20:24:47+00:00
- Post Title: (Wii)Fantasy Aquarium World 3D model (.pak)

offzip -a -z -15 fishdata.pak D:\test

(Guess, output folder "test" must be created in case it does not exist.)
## Post #5
- Username: Ryoutukankiti
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Mar 17, 2020 2:10 pm
- Post datetime: 2020-04-03T02:32:19+00:00
- Post Title: (Wii)Fantasy Aquarium World 3D model (.pak)

> Reply from shakotay2 ↑Fri Apr 03, 2020 4:24 am at Fri Apr 03, 2020 4:24 am
>
> 
offzip -a -z -15 fishdata.pak D:\test

(Guess, output folder "test" must be created in case it does not exist.)

Thanks!well done!
