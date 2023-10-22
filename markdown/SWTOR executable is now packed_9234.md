## Post #1
- Username: tlvenn
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Mar 12, 2012 9:11 pm
- Post datetime: 2012-07-09T03:39:00+00:00
- Post Title: SWTOR executable is now packed

Since the 1.3 patch, the StarWars The Old Replublic client (swtor.exe) is now packed and cant be reversed out of the box. I was wondering if someone has started to work on it and could share some intel. I tried various PE tool to identify which packer they have used with no luck.

Thanks in advance.
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-07-09T09:28:16+00:00
- Post Title: SWTOR executable is now packed

Upload main executable with all dll's and send me in PM. I do not want to download 30GB :}
## Post #3
- Username: tlvenn
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Mar 12, 2012 9:11 pm
- Post datetime: 2012-07-09T09:42:16+00:00
- Post Title: SWTOR executable is now packed

Sent ! Thanks in advance..
## Post #4
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-07-09T10:09:20+00:00
- Post Title: SWTOR executable is now packed

You sent msg without link.
## Post #5
- Username: tlvenn
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Mar 12, 2012 9:11 pm
- Post datetime: 2012-07-09T16:14:18+00:00
- Post Title: SWTOR executable is now packed

Weird, I included a zip as attachment to the message....

Sending you another msg with a link this time.
## Post #6
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-07-09T16:59:02+00:00
- Post Title: SWTOR executable is now packed

So executable not packed. Original Entry Point on 00C2E774
## Post #7
- Username: tlvenn
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Mar 12, 2012 9:11 pm
- Post datetime: 2012-07-10T02:11:07+00:00
- Post Title: SWTOR executable is now packed

Ya I noticed the entry point there but even when telling Ida about the image base address, I end up with pretty much all text segments with no code (all grey instead of blue):
> [https://dl.dropbox.com/u/45839385/ida-swtor.png](https://dl.dropbox.com/u/45839385/ida-swtor.png)

Steps I do :

1) Open the executable in Ida
2) In the options, I check "Manual Load" then click OK
3) Ida prompts for the new image base, i then enter "0x00C2E774"
4) I then proceed to load all the segments
5) At the end, IDA warns me that the imports segment seems to be destroyed, hinting at a packed file.

If it's not packed, I am guessing I do it wrong when it comes to manually loading the segments. Can you help me out ? Thanks !
## Post #8
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-07-10T08:38:24+00:00
- Post Title: SWTOR executable is now packed

> Reply from tlvenn
>
> 3) Ida prompts for the new image base, i then enter "0x00C2E774"
Image base always 00400000 

For me Olly and IDA work fine.



0082E774 + Image base 00400000 = 00C2E774



Here IDA - Loaded corrected adresses

[http://oi50.tinypic.com/2dj56ww.jpg](http://oi50.tinypic.com/2dj56ww.jpg)
## Post #9
- Username: Caboose
- Rank: advanced
- Number of posts: 67
- Joined date: Sat Sep 19, 2009 1:20 am
- Post datetime: 2012-07-10T14:24:41+00:00
- Post Title: SWTOR executable is now packed

@Ekey You can tell the exe is packed by looking at the IDA image you provide.
## Post #10
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-07-10T14:51:17+00:00
- Post Title: SWTOR executable is now packed

Exe cleared and not packed.
## Post #11
- Username: tlvenn
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Mar 12, 2012 9:11 pm
- Post datetime: 2012-07-10T16:20:29+00:00
- Post Title: SWTOR executable is now packed

Thanks for the info Ekey !

Could you explain how you load properly the exe into IDA plz ? No matter what i try, I dont end up with the same result as yours...
Also, could you elaborate what you mean by "The exe is cleared not packed" ?

Thanks in advance !
## Post #12
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-07-10T17:28:28+00:00
- Post Title: SWTOR executable is now packed

For IDA 6.1 nothing hard. Run IDA, open swotr.exe , in opened window ->



just press OK and wait when dissasembling finished.
## Post #13
- Username: tlvenn
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Mar 12, 2012 9:11 pm
- Post datetime: 2012-07-11T03:12:31+00:00
- Post Title: SWTOR executable is now packed

Ok this is embarassing, I dont know how but I end up giving you an old version which is not packed yet at this point....   

Here is a link to the latest version which I believe is packed: [https://dl.dropbox.com/u/45839385/retailclientV2.7z](https://dl.dropbox.com/u/45839385/retailclientV2.7z)

Sorry about that.....
## Post #14
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-07-11T08:17:43+00:00
- Post Title: SWTOR executable is now packed

> Reply from tlvenn
>
> Here is a link to the latest version which I believe is packed: https://dl.dropbox.com/u/45839385/retailclientV2.7z
So yes this version is packed or obfuscated. I do not know what this.
## Post #15
- Username: tlvenn
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Mar 12, 2012 9:11 pm
- Post datetime: 2012-07-13T07:23:10+00:00
- Post Title: SWTOR executable is now packed

Yeah figured that much 

It's been a long time since I didnt mess up with PE. So I am guessing the next steps are to find the original OEP and from there, dump the process from OllyDump and reconstruct the IAT ?
Looks like it gonna be fun....
## Post #16
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-07-13T08:38:37+00:00
- Post Title: Re: SWTOR executable is now packed

> Reply from tlvenn
>
> So I am guessing the next steps are to find the original OEP and from there, dump the process from OllyDump and reconstruct the IAT ?
You can try. I am not sure that all IAT will be corrected.
