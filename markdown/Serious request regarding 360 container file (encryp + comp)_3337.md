## Post #1
- Username: SharingMind
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Feb 02, 2009 10:36 pm
- Post datetime: 2009-02-03T01:55:32+00:00
- Post Title: Serious request regarding 360 container file (encryp + comp)

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: SharingMind
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Feb 02, 2009 10:36 pm
- Post datetime: 2009-02-03T16:33:31+00:00
- Post Title: Serious request regarding 360 container file (encryp + comp)

For those of you who prefer rapidshare. The link is posted as shown below:

[http://rapidshare.de/files/44651264/Item-bin.rar.html](http://rapidshare.de/files/44651264/Item-bin.rar.html)

Thank you,


SharingMind
## Post #3
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-02-03T19:55:14+00:00
- Post Title: Serious request regarding 360 container file (encryp + comp)

(Just a hint: this is Big-Endian)

I don't think it is encrypted, you can still find several plain strings in there, but file data is (for at least some of the files) indeed compressed.
## Post #4
- Username: SharingMind
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Feb 02, 2009 10:36 pm
- Post datetime: 2009-02-03T21:49:57+00:00
- Post Title: Serious request regarding 360 container file (encryp + comp)

> Reply from Rheini
>
> (Just a hint: this is Big-Endian)

I don't think it is encrypted, you can still find several plain strings in there, but file data is (for at least some of the files) indeed compressed.

Thank you for having a look at it. 

We assume it contains 3D models and its corresponding textures. My friend owns the Xbox360 SDK development kit, but he is by no means a master at it, . Maybe there is some code which can decompress this file and extract it?

We would appreciate it if you can help us further,

SharingMind
## Post #5
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-02-03T23:13:02+00:00
- Post Title: Serious request regarding 360 container file (encryp + comp)

Don't know, I'm not familiar with Xbox stuff.
## Post #6
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2009-02-04T10:56:49+00:00
- Post Title: Serious request regarding 360 container file (encryp + comp)

SharingMind, what game is that? I found that the texture is almost the same as N3(Ninety-Nine nights)! Could you share the method to convert the texture!

And about your bin file! I am sure the 3D data isn't compressed but pat of the name seems encrypted but you can still get the model out! 

"XBG" is the 3D model container and the "mesh" is the real 3D data
## Post #7
- Username: SharingMind
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Feb 02, 2009 10:36 pm
- Post datetime: 2009-02-04T13:49:52+00:00
- Post Title: Serious request regarding 360 container file (encryp + comp)

> Reply from fatduck
>
> SharingMind, what game is that? I found that the texture is almost the same as N3(Ninety-Nine nights)! Could you share the method to convert the texture!

And about your bin file! I am sure the 3D data isn't compressed but pat of the name seems encrypted but you can still get the model out! 

"XBG" is the 3D model container and the "mesh" is the real 3D data

Hi Fatduck,

Thank you for having a look at our file. It is not the game N3, though (sorry). We don't mind sharing, but could you elaborate on your question "Could you share the method to convert the texture"? So, we can be of your assistance.

As to our item.bin file could you elaborate as how to extract all its data, including the 3d models aka containers (xbgs)? And if possible repack them?

SharingMind
## Post #8
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2009-02-04T18:22:15+00:00
- Post Title: Serious request regarding 360 container file (encryp + comp)

I know It's no N3, what I said was the texture format are the same!

```
00000000   58 50 52 32 00 00 08 00  00 06 00 00 00 00 00 01   XPR2............
00000010   54 58 32 44 00 00 00 20  00 00 00 34 00 00 00 18   TX2D... ...4....
00000020   00 00 00 00 49 74 65 6D  00 00 00 00 00 00 00 03   ....Item........
00000030   00 00 00 01 00 00 00 00  00 00 00 00 00 00 00 00   ................
00000040   FF FF 00 00 FF FF 00 00  84 00 00 02 00 00 00 53   ....?.....S
00000050   00 3F E1 FF 00 00 0D 10  00 00 02 40 00 04 0A 00   .??.......@....
00000060   00 00 00 00 00 00 00 00  00 00 00 00 00 00 00 00   ................

N3 Header
00000000   00 00 40 00 00 00 40 00  00 03 00 01 00 00 00 00   ..@...@.........
00000010   FF FF 00 00 FF FF 00 00  82 00 00 02 00 00 00 52   ....?.....R
00000020   00 0F E0 FF 00 00 0D 10  00 00 00 00 00 00 02 00   ..?............
00000030   00 00 00 00 00 00 00 00  00 00 00 00 00 00 00 00   ................

```


Look at yours @0x40 and mine @0x10. 
And I already know that :
84/82 (@0x48) related to image size
53/52 (@0x4F) is DDS type
0A/02 (@0x5E) is number of mipmaps

What I really want to know is how you decode the texture! I mean if you can, share the texture format details!

About your bin file, from what I can tell are

```
dword          ofsHeaderSize
dword          ofsDataSize
dword          numberFilesInContainer

```


So for XPR2(container), HeaderSize 0x800, and DataSize = 0x6000
Header Start @0x10 which is TX2D, after Header @0x810
Then texture data Start @0x810 and end @60810

Next contanter is XBG @60810, HeaderSize 0x248 and DataSize 0xE0C and so on...
## Post #9
- Username: SharingMind
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Feb 02, 2009 10:36 pm
- Post datetime: 2009-02-04T18:35:06+00:00
- Post Title: Serious request regarding 360 container file (encryp + comp)

> Reply from fatduck
>
> I know It's no N3, what I said was the texture format are the same!
Code: Select allYour file header
00000010   54 58 32 44 00 00 00 20  00 00 00 34 00 00 00 18   TX2D... ...4....
00000020   00 00 00 00 49 74 65 6D  00 00 00 00 00 00 00 03   ....Item........
00000030   00 00 00 01 00 00 00 00  00 00 00 00 00 00 00 00   ................
00000040   FF FF 00 00 FF FF 00 00  84 00 00 02 00 00 00 53   ....?.....S
00000050   00 3F E1 FF 00 00 0D 10  00 00 02 40 00 04 0A 00   .??.......@....
00000060   00 00 00 00 00 00 00 00  00 00 00 00 00 00 00 00   ................

N3 Header
00000000   00 00 40 00 00 00 40 00  00 03 00 01 00 00 00 00   ..@...@.........
00000010   FF FF 00 00 FF FF 00 00  82 00 00 02 00 00 00 52   ....?.....R
00000020   00 0F E0 FF 00 00 0D 10  00 00 00 00 00 00 02 00   ..?............
00000030   00 00 00 00 00 00 00 00  00 00 00 00 00 00 00 00   ................


Look at yours @0x40 and mine @0x10. 
And I already know that :
84/82 (@0x48) related to image size
53/52 (@0x4F) is DDS type
0A/02 (@0x5E) is number of mipmaps

What I really want to know is how you decode the texture! I mean if you can, share the texture format details!

Ah, ok, I will send you a pm to see if we can help you. As for this thread I'd like it to stay on-topic. We really want to be able to use the item.bin files contents. As stated earlier we will reward the individual who will be able to dhelp us.

Regarding our item.bin file. Were you able to extract the 3D models?


SharingMind
## Post #10
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2009-02-05T09:31:25+00:00
- Post Title: Serious request regarding 360 container file (encryp + comp)

A quick look at Item.bin contains 46 model!

I need the format of the texture, share it please!
[item_all.jpg](https://xentaxbackup.github.io/file/1859_item_all.jpg)
## Post #11
- Username: SharingMind
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Feb 02, 2009 10:36 pm
- Post datetime: 2009-02-05T09:56:58+00:00
- Post Title: Serious request regarding 360 container file (encryp + comp)

> Reply from fatduck
>
> A quick look at Item.bin contains 46 model!

I need the format of the texture, share it please!

Hi Fatduck,

That is great work!!!

We are glad to see what you've managed to accomplish sofar. Respect!

We would need to be able to extract and repack item.bin file. Would you be able to create a script or small gui program which does that?

As to your format question, we replied back to you per pm that we can help you if you guide us as to what you precisely need. I will also forward it per email.

Thank you for your effort sofar, it is greatly appreciated. I'll send you another pm,


SharingMind

****Update: tried to send you an email, but the mail was rejected because the email was not accepted:

Technical details of permanent failure:
Google tried to deliver your message, but it was rejected by the recipient domain. We recommend contacting the other email provider for further information about the cause of this error. The error that the other server returned was: 550 550 Requested action not taken: mailbox unavailable (state 14).

Maybe your email was misspelled? I've send you another pm with the copy of the email.***
## Post #12
- Username: SharingMind
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Feb 02, 2009 10:36 pm
- Post datetime: 2009-02-05T22:14:11+00:00
- Post Title: Serious request regarding 360 container file (encryp + comp)

Fatduck,

Hit me up per email or pm. I think I've found your data,

SharingMind
## Post #13
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-02-06T11:57:35+00:00
- Post Title: Serious request regarding 360 container file (encryp + comp)

Why all the secrecy, SharingMind?
## Post #14
- Username: SharingMind
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Feb 02, 2009 10:36 pm
- Post datetime: 2009-02-06T14:57:21+00:00
- Post Title: Serious request regarding 360 container file (encryp + comp)

> Reply from Mr.Mouse
>
> Why all the secrecy, SharingMind?

Hi MrMouse,

No secrecy at all, I uploaded my file. Fatduck asked me a question, which I have an answer on, but it contains alot of specific data. And does not add to the topic of my thread. I would like to keep this thread clean and on topic, how to extract and repack the item.bin file,

SharingMind

**Update: MrMouse I send you a pm
## Post #15
- Username: humbug
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jun 27, 2010 3:45 pm
- Post datetime: 2010-06-27T19:20:19+00:00
- Post Title: Serious request regarding 360 container file (encryp + comp)

Hi, I was wondering how I could open the xbg/xbt files.

Thanks in advance.
