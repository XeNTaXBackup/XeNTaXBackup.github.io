## Post #1
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2010-09-11T02:02:51+00:00
- Post Title: Resident Evil 5 PS3 .arc won't extract.

Okay, apparently someone named Chrrox made a Resident Evil 5 extractor for the PS3 version. The problem I'm having is that it will not extract my Ps3 .arc files. I think it's because it doesn't have an "SFH" header. Can someone take a look at this?

Thanks.


[Extractor](http://www.mediafire.com/?3875txhjviwfb6o)
[Extractable ARC](http://www.mediafire.com/?kxa52xhwe7is0oe)
[Unextractable ARC](http://www.mediafire.com/?9l8pyxzklwvs39w)
## Post #2
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2010-10-07T00:19:27+00:00
- Post Title: Resident Evil 5 PS3 .arc won't extract.

Hello friends anyone could see it?
## Post #3
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2010-10-07T18:10:32+00:00
- Post Title: Resident Evil 5 PS3 .arc won't extract.

as i have seen the sfh header mark files that are disc optimised (aligned to 130xxx) bytes blocks to get better disc access, to extract those files you need first to remove the sfh header + a 16 byte long block every 130xxx bytes to get the original file that can then be extracted using chroxx bms script
## Post #4
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2010-10-07T20:04:44+00:00
- Post Title: Resident Evil 5 PS3 .arc won't extract.

The contents of this post was deleted because of possible forum rules violation.
## Post #5
- Username: caws
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Mar 02, 2008 2:57 am
- Post datetime: 2010-10-11T22:40:36+00:00
- Post Title: Resident Evil 5 PS3 .arc won't extract.

The contents of this post was deleted because of possible forum rules violation.
## Post #6
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2010-10-12T03:33:42+00:00
- Post Title: Resident Evil 5 PS3 .arc won't extract.

The contents of this post was deleted because of possible forum rules violation.
## Post #7
- Username: caws
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Mar 02, 2008 2:57 am
- Post datetime: 2010-10-12T04:15:02+00:00
- Post Title: Resident Evil 5 PS3 .arc won't extract.

The contents of this post was deleted because of possible forum rules violation.
## Post #8
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2010-10-12T05:48:17+00:00
- Post Title: Resident Evil 5 PS3 .arc won't extract.

Thanks friend,

let's hope the advances in tools.
## Post #9
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2010-10-12T05:53:18+00:00
- Post Title: Resident Evil 5 PS3 .arc won't extract.

> Reply from caws
>
> 
The endianess is different, that's why evin's tool doesn work.

And because the DMC4 msg2 is not equal with RE5 msg2. Something changed except the characters.

But I know, that someone made a RE5 compatible msg2 tool for pc.
## Post #10
- Username: caws
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Mar 02, 2008 2:57 am
- Post datetime: 2010-10-12T06:16:06+00:00
- Post Title: Resident Evil 5 PS3 .arc won't extract.

> Reply from evin
>
> caws wrote:
The endianess is different, that's why evin's tool doesn work.

And because the DMC4 msg2 is not equal with RE5 msg2. Something changed except the characters.

But I know, that someone made a RE5 compatible msg2 tool for pc.

I did one for my team. LOL. I'm doing some changes on it to support the PS3 msg files.

For now i've stopped the work on the msg2 coz i found a weird file inside this MsgResource_e.arc

The unpacker i posted unpacks all files OK but not the mes_stage1_e.MSG2, its weird, inside the msg2 it says that the file should have a size of 149768bytes, but it only decompresses 116763bytes, if anyone discovers somethin please tell me, rigth now is 3:15AM in my country and i really need to sleep. LOL
## Post #11
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2010-10-12T07:53:07+00:00
- Post Title: Resident Evil 5 PS3 .arc won't extract.

I talked about the GV RE5 msg2 tool. (You know the team)
You mean 3:15AM? Because people sleep at night, not at afternoon.
## Post #12
- Username: caws
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Mar 02, 2008 2:57 am
- Post datetime: 2010-10-12T13:17:12+00:00
- Post Title: Resident Evil 5 PS3 .arc won't extract.

> Reply from evin
>
> I talked about the GV RE5 msg2 tool. (You know the team)
You mean 3:15AM? Because people sleep at night, not at afternoon.

yeah yeah, it was 3:15 in the morning, i was too sleepy LOL!

GV did one but they never release their tools.
## Post #13
- Username: caws
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Mar 02, 2008 2:57 am
- Post datetime: 2010-10-14T18:34:38+00:00
- Post Title: Resident Evil 5 PS3 .arc won't extract.

Here, i corrected a bug, it hapenned because of that 20000h stuff...

i still haven't tested my repacker so i cant release it..
[RE5 PS3 .ARC Tool V0.6.rar](https://xentaxbackup.github.io/file/3533_RE5 PS3 .ARC Tool V0.6.rar)
## Post #14
- Username: mauzerX
- Rank: advanced
- Number of posts: 57
- Joined date: Thu Jul 01, 2010 8:48 pm
- Post datetime: 2010-10-15T19:42:27+00:00
- Post Title: Resident Evil 5 PS3 .arc won't extract.

caws,what *.arcs it will unpack?I'd tryed ps3 chris models,but it will give me a error...
## Post #15
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2011-03-30T16:29:14+00:00
- Post Title: Resident Evil 5 PS3 .arc won't extract.

Can anyone help?
## Post #16
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2011-03-30T18:25:48+00:00
- Post Title: Re: Resident Evil 5 PS3 .arc won't extract.

Could you upload again the msg2 files?
## Post #17
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2011-03-30T19:09:47+00:00
- Post Title: Re: Resident Evil 5 PS3 .arc won't extract.

The contents of this post was deleted because of possible forum rules violation.
## Post #18
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2011-03-31T19:08:57+00:00
- Post Title: Re: Resident Evil 5 PS3 .arc won't extract.

This tool can convert the PS3 MSG2 file into PC format and back. And you can use the re5 msg2 tool.
After you done, convert the new file back into ps3 format.
[RE5Endian.zip](https://xentaxbackup.github.io/file/4140_RE5Endian.zip)
## Post #19
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2011-03-31T19:18:23+00:00
- Post Title: Re: Resident Evil 5 PS3 .arc won't extract.

Thanks ...

Wow! Very Good!!

it worked, I test the PS3 today.

Thanks ...

What command to repacker the arc, with the bms?
## Post #20
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2011-03-31T20:05:34+00:00
- Post Title: Re: Resident Evil 5 PS3 .arc won't extract.

[viewtopic.php?f=13&t=4003](http://forum.xentax.com/viewtopic.php?f=13&t=4003)
## Post #21
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2011-04-01T01:16:32+00:00
- Post Title: Re: Resident Evil 5 PS3 .arc won't extract.

Evin, I'm using MSG2Editor.exe you posted for DMC4, it extracts the text files when I spend most of txt to msg2 the file exits reset.

I'm doing right?
## Post #22
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2011-04-01T08:19:16+00:00
- Post Title: Re: Resident Evil 5 PS3 .arc won't extract.

No, because that's not compatible with RE5. I made that for Devil May Cry 4 only.
## Post #23
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2011-04-01T10:55:54+00:00
- Post Title: Re: Resident Evil 5 PS3 .arc won't extract.

Evin Thanks.

I got to work, the file must be renamed to MSG2 and I have to use the tool that made the GV, there's sure, I'm just the problem to remount. Arc

Can anyone help me please?
I tried several combinations via bms, please light.

Edit:

Guys have been doing more testing here and found that gold version uses the arc that is installed on the hd VG and it is different from others, ferramneta the caws of error for him, since the script runs more bms of this error in the final.

is that this file is to do a better tool?

Sorry we are wanting to get too éque renting this game for PS3.


[Msg2Resource_e.rar](https://xentaxbackup.github.io/file/4145_Msg2Resource_e.rar)
## Post #24
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2011-04-23T00:30:40+00:00
- Post Title: Re: Resident Evil 5 PS3 .arc won't extract.

The contents of this post was deleted because of possible forum rules violation.
## Post #25
- Username: vadim
- Rank: advanced
- Number of posts: 41
- Joined date: Fri Apr 09, 2010 11:15 pm
- Post datetime: 2011-08-29T01:55:15+00:00
- Post Title: Re: Resident Evil 5 PS3 .arc won't extract.

HI
is it possible to repack CoreResource.arc?
Really need to repack CoreResource.arc 
Help please 


[CoreResource.arc](http://www.megaupload.com/?d=H1K59O5F)
