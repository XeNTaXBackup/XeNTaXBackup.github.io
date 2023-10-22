## Post #1
- Username: larisz
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Sep 21, 2016 11:13 pm
- Post datetime: 2016-09-21T15:58:41+00:00
- Post Title: 300 heroes .x files

Hello guys, first I apologize for my English, I am a foreigner and do not speak English

I would like to ask you how can I access the 3d models of this game, I extracted all the files, but I can only see the texture (dds) can not see the models, I believe that is hidden in these (.x files) I already tried use various programs, 3dsmax, maya, directx9 and does not appear to exist program to open these files, you know somehow?

you know some way to extract the models files that (.x files)?

see the image below: 

I thank you for your attention.

here is one of the models with the x file:
[http://www.filedropper.com/072](http://www.filedropper.com/072)
## Post #2
- Username: Naroax
- Rank: beginner
- Number of posts: 30
- Joined date: Sun Aug 31, 2014 1:44 am
- Post datetime: 2016-09-21T16:11:37+00:00
- Post Title: 300 heroes .x files

You should upload a sample file, upload one of those .x files for people to see and help.
## Post #3
- Username: larisz
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Sep 21, 2016 11:13 pm
- Post datetime: 2016-09-21T16:38:08+00:00
- Post Title: 300 heroes .x files

one example:
I uploaded a  "kakashi models" with texture and .x file
[http://www.filedropper.com/072](http://www.filedropper.com/072)
## Post #4
- Username: Naroax
- Rank: beginner
- Number of posts: 30
- Joined date: Sun Aug 31, 2014 1:44 am
- Post datetime: 2016-09-21T16:50:32+00:00
- Post Title: 300 heroes .x files

have you looked at this thread anyway ? : [viewtopic.php?f=16&t=12617](http://forum.xentax.com/viewtopic.php?f=16&t=12617)

they were already discussing this .x format.
## Post #5
- Username: larisz
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Sep 21, 2016 11:13 pm
- Post datetime: 2016-09-21T17:04:53+00:00
- Post Title: 300 heroes .x files

Yes, I looked
but I could not understand anything
 so I came here to create this topic so that anyone could make an initial tutorial, or any solution.
## Post #6
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-09-22T04:34:45+00:00
- Post Title: 300 heroes .x files

after extracting 00001012.dat from 072.x with offzip  



00001012_dat.png (51.34 KiB) Viewed 499 times
## Post #7
- Username: Naroax
- Rank: beginner
- Number of posts: 30
- Joined date: Sun Aug 31, 2014 1:44 am
- Post datetime: 2016-09-22T08:51:35+00:00
- Post Title: 300 heroes .x files

@Acewell, how were you able to extract the dat out of that .x file ? i dragged the .x file to offzip but it just gives me an empty unpacked file.
## Post #8
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-09-22T23:07:09+00:00
- Post Title: 300 heroes .x files

use the command prompt or a bat file and run this

```
offzip -a 072.x c:\offzip
```

like shakotay posted here
[viewtopic.php?p=103783#p103783](http://forum.xentax.com/viewtopic.php?p=103783#p103783)
## Post #9
- Username: larisz
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Sep 21, 2016 11:13 pm
- Post datetime: 2016-09-23T09:45:57+00:00
- Post Title: 300 heroes .x files

I got to extract the .dat file, what should I do now?
## Post #10
- Username: Naroax
- Rank: beginner
- Number of posts: 30
- Joined date: Sun Aug 31, 2014 1:44 am
- Post datetime: 2016-09-23T10:46:46+00:00
- Post Title: 300 heroes .x files

larisz, get Hex2obj, (see signature of Acewell) and copy the settings he showed in that picture and then you'll have your model in OBJ format. Done!
## Post #11
- Username: ssdjxl
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Dec 02, 2016 5:58 pm
- Post datetime: 2016-12-12T04:05:38+00:00
- Post Title: 300 heroes .x files

> Reply from AceWell
>
> after extracting 00001012.dat from 072.x with offzip  
00001012_dat.png
Hello,i have read your message and tried doing it.
    the 19756 19492
          12       99
          131bc  8
          22c      2890
    is for this file.
But i don't know how to find the data which is suitable for another file.
Would you mind tell me the way or the tool that i can use.
## Post #12
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-12-13T11:11:23+00:00
- Post Title: 300 heroes .x files

well offsets and counts will vary from file to file and there is no way i can think to teach that,
you need to know what kind of data you are looking at for this to work, and this just requires
experience. 

if you have no experience in reversing formats you should start with the guide here
[http://wiki.xentax.com/index.php/DGTEFF](http://wiki.xentax.com/index.php/DGTEFF)

also read through the tutorial that comes with Hex2obj and you can also practice with the hundreds
of samples already posted on Xentax.
## Post #13
- Username: ssdjxl
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Dec 02, 2016 5:58 pm
- Post datetime: 2016-12-14T04:56:49+00:00
- Post Title: 300 heroes .x files

> Reply from AceWell
>
> well offsets and counts will vary from file to file and there is no way i can think to teach that,
you need to know what kind of data you are looking at for this to work, and this just requires
experience. 

if you have no experience in reversing formats you should start with the guide here
http://wiki.xentax.com/index.php/DGTEFF

also read through the tutorial that comes with Hex2obj and you can also practice with the hundreds
of samples already posted on Xentax.
OK,thanks!
I will read it and try.
