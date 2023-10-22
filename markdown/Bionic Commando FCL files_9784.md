## Post #1
- Username: blackfoxeye
- Rank: veteran
- Number of posts: 110
- Joined date: Tue Mar 08, 2011 7:03 pm
- Post datetime: 2012-10-24T08:23:36+00:00
- Post Title: Bionic Commando FCL files

The ".fcl" files contains texture files.

Can anybody help on this? How to unpack or extract these ".fcl" files?
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-10-24T21:48:32+00:00
- Post Title: Bionic Commando FCL files

And where samples ?
## Post #3
- Username: blackfoxeye
- Rank: veteran
- Number of posts: 110
- Joined date: Tue Mar 08, 2011 7:03 pm
- Post datetime: 2012-10-25T08:47:58+00:00
- Post Title: Bionic Commando FCL files

As I have read the forum rules, we should not give a download link to a game file.

> Mr.Mouse, Site Admin Wrote:
>
> 
>
> 2. If possible direct the forum member to a legal demo or other legal file to be examined. 
>
> 
>
> We will not allow linking to any game files that may have copyrights on them. 
>
> Make sure you know the rules. No linking to file sharing sites in this open site.
If you are interested, I will PM you, or let me know how can I send the file to you.
## Post #4
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-10-25T12:22:34+00:00
- Post Title: Bionic Commando FCL files

This rule is almost no one does not observe  Anyway you can send me in pm for download and check.
## Post #5
- Username: dragbody
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Sep 20, 2011 11:33 am
- Post datetime: 2012-10-25T22:22:32+00:00
- Post Title: Bionic Commando FCL files

If you figure out how to unpack the fcl files, please share the results. I've run into the same problem with Terminator: Salvation. Many, many textures are missing from the bundle files.
## Post #6
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2012-10-26T06:55:33+00:00
- Post Title: Bionic Commando FCL files

Unpacking fcl file is easy, simple zlib packages, but handling the inside data, not so much.
## Post #7
- Username: blackfoxeye
- Rank: veteran
- Number of posts: 110
- Joined date: Tue Mar 08, 2011 7:03 pm
- Post datetime: 2012-10-26T07:21:17+00:00
- Post Title: Bionic Commando FCL files

> Reply from evin
>
> Unpacking fcl file is easy, simple zlib packages, but handling the inside data, not so much.

I never used zlib before, so can you please guide little bit, how to extract data using zlib.
I tried but, I think without programming knowledge it's hard to operate. So please guide the procedure.
## Post #8
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2012-10-26T15:29:02+00:00
- Post Title: Bionic Commando FCL files

I attached my tool, I made for Bionic Commando fcl file to unpack 2 years ago. That's all I can help you.
C# source code also included, if somebody want to improve it.

Sourcecode + tool: See below.
## Post #9
- Username: blackfoxeye
- Rank: veteran
- Number of posts: 110
- Joined date: Tue Mar 08, 2011 7:03 pm
- Post datetime: 2012-10-26T16:22:57+00:00
- Post Title: Bionic Commando FCL files

> Reply from evin
>
> I attached my tool, I made for Bionic Commando fcl file to unpack 2 years ago. That's all I can help you.
C# source code also included, if somebody want to improve it.

Thank you very much for the tool, you are really great that, you have made a tool, but it's my bad that, I am getting error message while running.



So, can you please guide me how to run your tool, (I am doing this way by dragging one .fcl file to your exe).
Is this the correct way or how to extract .fcl files using your tool, please please let me know.
## Post #10
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2012-10-26T18:02:50+00:00
- Post Title: Bionic Commando FCL files

It seems, I remembered wrong. This not unpack, this create from the unpacked data fcl file.
To work, create a temp folder. Back in that days, I couldn't create folder from code.

If you send me some smaller fcl file, maybe I can create unpacker part in the code, but because my free time is limited, I can't promise quick progress.
## Post #11
- Username: blackfoxeye
- Rank: veteran
- Number of posts: 110
- Joined date: Tue Mar 08, 2011 7:03 pm
- Post datetime: 2012-10-26T18:26:28+00:00
- Post Title: Bionic Commando FCL files

> Reply from evin
>
> It seems, I remembered wrong. This not unpack, this create from the unpacked data fcl file.
To work, create a temp folder. Back in that days, I couldn't create folder from code.

If you send me some smaller fcl file, maybe I can create unpacker part in the code, but because my free time is limited, I can't promise quick progress.

No worries if it takes long time 

I have PM you the download link.
## Post #12
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2012-11-04T12:16:54+00:00
- Post Title: Bionic Commando FCL files

The tool can unpack/repack Grin fcl files.
Unpack may not works anytime, because not all fcl file correct. Probably some kind of protection, I don't know.
Repacked files probably won't works in the game, I don't know why. Probably also protection.
These problem needs to solve somebody else, I won't.

I attached the updated program and the source code.
[FCL_Grin.zip](https://xentaxbackup.github.io/file/5967_FCL_Grin.zip)
## Post #13
- Username: dragbody
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Sep 20, 2011 11:33 am
- Post datetime: 2012-11-04T13:56:20+00:00
- Post Title: Bionic Commando FCL files

> Reply from evin
>
> The tool can unpack/repack Grin fcl files.
Unpack not works anytime, because not all fcl file correct. Probably some kind of protection, I don't know.
Repacked files probably won't works in the game, I don't know why. Probably also protection.
These problem needs to solve somebody else, I won't.

I attached the updated program and the source code.

Based on my tests, the program extracts many .dat files and one .zl from the .fcl files before crashing. Also, the program extracts the dat files to folder "temp." If a "temp" folder is already present in the directory the program is being run from, it will not start. Renaming the previous "temp" folder works just fine.
## Post #14
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2012-11-04T14:53:19+00:00
- Post Title: Bionic Commando FCL files

The tool unpack only .zl files. The .dat files are the uncompressed .zl files. The latest .zl file is where the tool crash. That .zl file contain incorrect Zlib compression (No header or encryted or dummy data).
Before the actually work, the tool delete the temp folder. At least, it should be.
## Post #15
- Username: blackfoxeye
- Rank: veteran
- Number of posts: 110
- Joined date: Tue Mar 08, 2011 7:03 pm
- Post datetime: 2012-11-04T17:11:07+00:00
- Post Title: Bionic Commando FCL files

After running this tool, I got ".fcl_unp" files.

So after that, how to extract texture data from it?
## Post #16
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2012-11-04T17:57:18+00:00
- Post Title: Re: Bionic Commando FCL files

Need a ripper. I used to use JaederNaub.
## Post #17
- Username: blackfoxeye
- Rank: veteran
- Number of posts: 110
- Joined date: Tue Mar 08, 2011 7:03 pm
- Post datetime: 2012-11-04T18:37:31+00:00
- Post Title: Re: Bionic Commando FCL files

Thank you very very much "evin".  Thank you for everything.

You are Awesome
## Post #18
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2012-11-05T03:47:46+00:00
- Post Title: Re: Bionic Commando FCL files

AWESOME!

I hope that in the future we can extract .diesel models 

thanks Evin
## Post #19
- Username: blackfoxeye
- Rank: veteran
- Number of posts: 110
- Joined date: Tue Mar 08, 2011 7:03 pm
- Post datetime: 2012-11-05T07:21:49+00:00
- Post Title: Re: Bionic Commando FCL files

> Reply from evin
>
> The tool unpack only .zl files. The .dat files are the uncompressed .zl files. The latest .zl file is where the tool crash. That .zl file contain incorrect Zlib compression (No header or encryted or dummy data).
Before the actually work, the tool delete the temp folder. At least, it should be.

There are total 57 .fcl files.
This tool only works with 18 files, and with the remaining 39 files the tool is crashing because the latest .zl file contain incorrect Zlib compression as said by evin.

So is it possible to skip that .zl file and we can continue to get the ".fcl_unp" file. 
The command prompt stops working and no way to get the .fcl_unp file.
## Post #20
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2012-11-05T16:45:07+00:00
- Post Title: Re: Bionic Commando FCL files

I updated the pack in my earlier post.
Tool now always delete the temp folder, even if not empty.
Now unpack the "corrupted" files too, but not unpack the not zlib compressed chunks, just paste into the unpacked file!
## Post #21
- Username: blackfoxeye
- Rank: veteran
- Number of posts: 110
- Joined date: Tue Mar 08, 2011 7:03 pm
- Post datetime: 2012-11-05T17:01:13+00:00
- Post Title: Re: Bionic Commando FCL files

> Reply from evin
>
> I updated the pack in my earlier post.
Tool now always delete the temp folder, even if not empty.
Now unpack the "corrupted" files too, but not unpack the not zlib compressed chunks, just paste into the unpacked file!

Now your tool is working great. 

Thank you very very much "evin"
## Post #22
- Username: dragbody
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Sep 20, 2011 11:33 am
- Post datetime: 2012-11-07T14:28:05+00:00
- Post Title: Re: Bionic Commando FCL files

The program works great and I've been able to gather many of the texture files I've been missing. Thank you very much Evin!
