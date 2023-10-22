## Post #1
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2013-07-04T19:13:37+00:00
- Post Title: DARK [.darkpack]

This game just released on Steam and I suspect the texts are in the "LocText_en.darkpack" ( [http://rghost.net/47215158](http://rghost.net/47215158) ).
Could somebody take a look on it? Thank you
## Post #2
- Username: swuforce
- Rank: veteran
- Number of posts: 121
- Joined date: Fri Nov 06, 2009 3:46 am
- Post datetime: 2013-07-04T20:27:36+00:00
- Post Title: DARK [.darkpack]

Quickbms script for unpack

```
get tablesz long
get files long
for i = 0 < files
get offset long
get null long
get unk long
get null long
get size long
get namesz long
getdstring name namesz
log name offset size
next i
```
## Post #3
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2013-07-05T08:55:06+00:00
- Post Title: DARK [.darkpack]

Thanks, the bms script works great, the game uses the texts when reimported with quickbms (however I have to watch out to not exceed the original filesize):)
## Post #4
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-07-05T11:53:19+00:00
- Post Title: DARK [.darkpack]

> Reply from lostprophet
>
> Thanks, the bms script works great, the game uses the texts when reimported with quickbms (however I have to watch out to not exceed the original filesize):)

I was thinking to make repacker but i dont know someone allready working on it
## Post #5
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2013-07-05T13:55:31+00:00
- Post Title: DARK [.darkpack]

> Reply from michalss
>
> lostprophet wrote:Thanks, the bms script works great, the game uses the texts when reimported with quickbms (however I have to watch out to not exceed the original filesize):)

I was thinking to make repacker but i dont know someone allready working on it
Well, I would appreciate a repacker  (since the reimport feature of Quickbms has the size limit).
## Post #6
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2013-07-05T14:02:54+00:00
- Post Title: DARK [.darkpack]

The format is pretty easy, If I have the time I'll try something
## Post #7
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2013-07-06T06:32:47+00:00
- Post Title: DARK [.darkpack]

It looks like the reimport feature for Quickbms cuts some texts, so I'll wait for a proper repacker then.
## Post #8
- Username: SileniusLegard
- Rank: n00b
- Number of posts: 19
- Joined date: Sun Jul 25, 2010 7:00 am
- Post datetime: 2013-07-06T13:27:02+00:00
- Post Title: DARK [.darkpack]

> Reply from Vash
>
> The format is pretty easy, If I have the time I'll try something

Wow, that would be great, thank you very much.
## Post #9
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2013-07-06T14:32:05+00:00
- Post Title: DARK [.darkpack]

I'm on it..


[EDIT]
Ok, here a first version. At the moment it only unpacks, I'm sharing this because I only tried on this one file and I can't be sure it works with all of them.
[https://www.dropbox.com/s/tbv2qhmk0o0e8 ... Packer.exe](https://www.dropbox.com/s/tbv2qhmk0o0e8a6/DarkUnPacker.exe)

I had to use Visual Studio 2012 to compile it, you might need the libraries
## Post #10
- Username: Herdell
- Rank: veteran
- Number of posts: 103
- Joined date: Mon Dec 14, 2009 3:35 am
- Post datetime: 2013-07-06T21:45:40+00:00
- Post Title: DARK [.darkpack]

> Reply from Vash
>
> ...I'm sharing this because I only tried on this one file and I can't be sure it works with all of them.
I've tried your tool on a 2gb file (Data.darkpack) and it worked well extracting 11.000+ files with proper filenames and folders.

So, yes, your tool works fine with another files from DARK game than LocText_en.darkpack.
## Post #11
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2013-07-06T22:39:10+00:00
- Post Title: DARK [.darkpack]

Doesnt work for me on the data.darkpack. what libraries do i need?
## Post #12
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2013-07-07T10:21:57+00:00
- Post Title: DARK [.darkpack]

These should do the trick:
[http://www.microsoft.com/en-us/download ... x?id=30679](http://www.microsoft.com/en-us/download/details.aspx?id=30679)

SOrry for taking my time, I'm just rusty with C and I'm kinda of experimenting on new stuff  


[EDIT]
Here's the complete version. Once again, if you could test it on the biggest files would be better

[http://www.mediafire.com/download/2n6bs ... Packer.exe](http://www.mediafire.com/download/2n6bs4bq6t717wf/DarkUnPacker.exe)
## Post #13
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2013-07-07T15:16:18+00:00
- Post Title: DARK [.darkpack]

So I think I'm doing something wrong.
1. I unpacked the LocText_en.darkpack with DarkUnPacker.exe
2. I modified the texts.csv file.
3. When I try to run the "DarkUnPack.exe -m LocText_en.darkpack", it says "Cannot open the file LocText_en.tbl".

The LocText_en.tbl is there, along with the "LocText_en" directory.
## Post #14
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2013-07-07T15:46:36+00:00
- Post Title: DARK [.darkpack]

Be sure to run the tool outside the LocText_en dir and be sure that the tbl file isn't somehow locked... I wouldn't know what else to say, I tried with that file and it came out correct
## Post #15
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2013-07-07T15:55:35+00:00
- Post Title: DARK [.darkpack]

> Reply from Vash
>
> Be sure to run the tool outside the LocText_en dir and be sure that the tbl file isn't somehow locked... I wouldn't know what else to say, I tried with that file and it came out correct
I'm using Win8 x64, UAC is turned off, I tried it on C:, D:, E:, always the same trouble. I'll try it on a virtual Win7.
## Post #16
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2013-07-07T16:30:57+00:00
- Post Title: Re: DARK [.darkpack]

I have Win8 x64 too but your UAC is not off, you should handle something in the registry. 
Try and push WIN+X (the windows button on your left) and choose Command Prompt (administrator) and try with that, but I don't think it'll do the trick since it's an error on reading, not on writing...
## Post #17
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2013-07-08T19:04:49+00:00
- Post Title: Re: DARK [.darkpack]

> Reply from Vash
>
> I have Win8 x64 too but your UAC is not off, you should handle something in the registry. 
Try and push WIN+X (the windows button on your left) and choose Command Prompt (administrator) and try with that, but I don't think it'll do the trick since it's an error on reading, not on writing...
Thanks, got it to work
## Post #18
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2013-07-09T08:04:58+00:00
- Post Title: Re: DARK [.darkpack]

That's..just..really?   
Windows 8 >_>
## Post #19
- Username: XpoZed
- Rank: veteran
- Number of posts: 144
- Joined date: Sun Oct 25, 2009 12:08 am
- Post datetime: 2013-07-11T11:20:07+00:00
- Post Title: Re: DARK [.darkpack]

There's also a Unpakke module for .darkpack files...
## Post #20
- Username: stVALVe
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Apr 06, 2014 1:11 pm
- Post datetime: 2014-12-27T04:08:07+00:00
- Post Title: Re: DARK [.darkpack]

So we able to extract .model files but how to open them? Is there any Noesis script or something?
