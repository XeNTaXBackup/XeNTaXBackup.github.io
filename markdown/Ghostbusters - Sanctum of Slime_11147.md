## Post #1
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2014-01-20T03:17:02+00:00
- Post Title: Ghostbusters - Sanctum of Slime

I've run through a few of these files myself and not been able to do much. These are in the PC port of Sanctum of Slime, not sure about the other versions. I am hoping to convert them to usable format so I can view them better and perhaps create a few animations and such with them. Could someone please take a look at them and let me know what can be done?

[https://www.dropbox.com/s/t7lfg4qsczmp1 ... ayboss.zip](https://www.dropbox.com/s/t7lfg4qsczmp1cx/subwayboss.zip)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-01-20T18:57:46+00:00
- Post Title: Ghostbusters - Sanctum of Slime

> Reply from Doctor Loboto
>
> Could someone please take a look at them and let me know what can be done?use hex2obj on the cmf files.



GB_cmf.JPG (38.49 KiB) Viewed 76 times


As you can see from the test.obj file:
v -1.883467 -47.763863 0.540619 
v -1.380253 -46.160984 0.161061 
v -1.469345 -46.066879 0.078369 

v 0.000000 0.100000 -0.000074 
v 0.000000 0.900000 0.000000 
v 0.406281 0.000000 0.000000 
v 0.783051 0.000000 0.000000 
v 0.783046 0.000000 0.000000 
v 0.677277 0.067770 0.677277 

there seems to be a new submesh or a new data block after vertex 161.
So reduce the face index count to 493.
An UV pos of 12 didn't give the desired uv map.

But it's up to you to dig deeper.
## Post #3
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2014-01-21T00:28:14+00:00
- Post Title: Ghostbusters - Sanctum of Slime

Oh, wow, that's pretty cool actually. But unfortunately I'm very much a fool when it comes to this sort of thing. Is there any specific way to get the models out directly afterwards and a way to determine the start-address? Is it the same for all of them?

[https://www.dropbox.com/s/tj70wbc7dsq58qc/dumazu.zip](https://www.dropbox.com/s/tj70wbc7dsq58qc/dumazu.zip)
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-01-21T00:44:50+00:00
- Post Title: Ghostbusters - Sanctum of Slime

> Reply from Doctor Loboto
>
> But unfortunately I'm very much a fool when it comes to this sort of thing. Yes, I know.   (That's lazy people's common excuse who expect other people doing their work.)

> Is there any specific way to get the models out directly afterwards and a way to determine the start-address?Read the tut included with hex2obj.

> Is it the same for all of them?Maybe.
For submeshes (if any) it's not.
## Post #5
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2014-01-21T00:46:42+00:00
- Post Title: Ghostbusters - Sanctum of Slime

All right. Thank you for your help, very much so. I'll see what I can do with this. I'm gonna have to do some research again but I'll figure something out. Thanks again, I appreciate it.
