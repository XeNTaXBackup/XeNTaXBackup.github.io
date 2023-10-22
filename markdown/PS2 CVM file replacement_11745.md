## Post #1
- Username: Brandondorf9999
- Rank: n00b
- Number of posts: 14
- Joined date: Sat May 12, 2012 10:08 am
- Post datetime: 2014-08-03T22:33:43+00:00
- Post Title: PS2 CVM file replacement

I've been trying to find a working tool that will allow me to replace the files inside the cvm file without any problems and the hex values to decrypting the file in the header is hard to find and I want to make this editable without corrupting it. The game I was trying to modify with the cvm files and it's files I've edited is Sonic Heroes which I've edited the arc files using HxD editor. The CVM files are in the ps2 iso disc and none of the tools I've downloaded will avoid such problems when replacing files in the cvm files. Here are the following softwares I've tried with their errors and bugs:

Apache 3.10.6 - (While attempting to replace a file in the cvm, the program crashes and leaves only 1 byte to the modified cvm file, the software and the website are now discontinued and there won't be any updated versions of Apache ever since that website has been shutdown)

DkZ Studio (It does not allow me to overwrite the cvm file and corrupts the cvm file after saving a seperate copy)

The older versions of Apache don't support cvm files.

I'm also trying to find a cvm rebuilder program that can rebuild files into the cvm file in-order to pre-pare for rebuilding the playstation 2 image. If anyone knows which tools can do these, please show me the tools that will do this job.
## Post #2
- Username: SILENTpavel
- Rank: advanced
- Number of posts: 54
- Joined date: Fri Aug 05, 2011 12:53 pm
- Post datetime: 2014-08-05T16:54:16+00:00
- Post Title: PS2 CVM file replacement

> Reply from Brandondorf9999
>
> Apache 3.10.6 - (While attempting to replace a file in the cvm, the program crashes and leaves only 1 byte to the modified cvm file, the software and the website are now discontinued and there won't be any updated versions of Apache ever since that website has been shutdown)
Actually you can replace any file in ps2 iso with HxD (add nulls to end of the file, to match with original size in bytes) without other tools, but if you want:
Apache v2.0 build 48134 - 2004
https://www.mediafire.com/?0nie49t9o85kqgy
oldest stable release, only one rule: it can replace files, if size will be 100% same as original, not smaller, not bigger.
Apache3 PREVIEW - 2005
https://www.mediafire.com/?cc6oasar59cbg6x
best version of Apache, it can replace files, that smaller or same as original without troubles (uncheck "update TOC" and "ignore..." on replace dialog before replacing)

also don't try to use other versions. like Apache3 2007 - it is unstable as hell.
## Post #3
- Username: Brandondorf9999
- Rank: n00b
- Number of posts: 14
- Joined date: Sat May 12, 2012 10:08 am
- Post datetime: 2014-08-06T01:00:16+00:00
- Post Title: PS2 CVM file replacement

> Reply from SILENTpavel
>
> Brandondorf9999 wrote:Apache 3.10.6 - (While attempting to replace a file in the cvm, the program crashes and leaves only 1 byte to the modified cvm file, the software and the website are now discontinued and there won't be any updated versions of Apache ever since that website has been shutdown)
Actually you can replace any file in ps2 iso with HxD (add nulls to end of the file, to match with original size in bytes) without other tools, but if you want:
Apache v2.0 build 48134 - 2004
https://www.mediafire.com/?0nie49t9o85kqgy
oldest stable release, only one rule: it can replace files, if size will be 100% same as original, not smaller, not bigger.
Apache3 PREVIEW - 2005
https://www.mediafire.com/?cc6oasar59cbg6x
best version of Apache, it can replace files, that smaller or same as original without troubles (uncheck "update TOC" and "ignore..." on replace dialog before replacing)

also don't try to use other versions. like Apache3 2007 - it is unstable as hell.

The support for CVM is only on the latest version of Apache 3 which they stopped development of their software and that's hard work on HxD and I want to replace them quickly rather than having to go through the hex editing process.
## Post #4
- Username: SILENTpavel
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-08-06T01:51:29+00:00
- Post Title: PS2 CVM file replacement

from what i remember of cvm its just an iso with extra header data.
so you can just remove the extra data turn it into an iso and edit it all you want then just add the header back.
## Post #5
- Username: Brandondorf9999
- Rank: n00b
- Number of posts: 14
- Joined date: Sat May 12, 2012 10:08 am
- Post datetime: 2014-08-06T02:57:15+00:00
- Post Title: PS2 CVM file replacement

> Reply from chrrox
>
> from what i remember of cvm its just an iso with extra header data.
so you can just remove the extra data turn it into an iso and edit it all you want then just add the header back.

What are the offsets and values in it so that I can look into it and do that?

EDIT: That worked, I think the header is in the beginning of the file, I can now replace files.
