## Post #1
- Username: jumpjack
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Apr 25, 2020 9:44 pm
- Post datetime: 2020-05-03T12:55:15+00:00
- Post Title: What's the best freeware hex editor for examining models?

I tried 2 dozens of them ans still I can't find the right one for our purposes: reverse engineering of unknown file format.
We need an hex editor capable of looking for dynamic structures and patterns based on offsets, lenghts and pointers.
Any suggestion?
Maybe "010 editor" would be good... but it's 50$!
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-05-04T08:50:20+00:00
- Post Title: What's the best freeware hex editor for examining models?

> Reply from jumpjack ↑Sun May 03, 2020 8:55 pm at Sun May 03, 2020 8:55 pm
>
> 
I tried 2 dozens of them ans still I can't find the right one for our purposes
Why don't you list those you've tried so people can see what options you have left?
## Post #3
- Username: jumpjack
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Apr 25, 2020 9:44 pm
- Post datetime: 2020-05-04T09:00:49+00:00
- Post Title: What's the best freeware hex editor for examining models?

I currently have these installed; some others were just discarded after first start as completely useless:
Binary Viewer
filealyz-2.0.5.57
fileinsight
FlexHex
hex_setup26
hexinator-64-1.12
HxD
winhex
WinMerge-2.14.0
wxHexEditor
wxMEdit-3.1-win32-bin
HEXEdit
BE
free-hex-editor-neo


FlexHex and Hexinator look promising but I am not sure they support dynamic structures and pointers to structures, still studying.

I also just downloaded ghidra_9.1.2_PUBLIC_20200212 from NSA (!): 200 MB, not tested yet.

kaitai-struct-compiler-0.8 is not clear if is a program,  a library or what.
## Post #4
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-05-04T09:33:48+00:00
- Post Title: What's the best freeware hex editor for examining models?

Well, I havn't tried as many as you did, coz I found the one that do just fine after, say 2 attempts.  
I have tried WinHex, which's not convenient enough for me. Also checked FlexHex and Hexinator since you mentioned. My opinion, they're all too old-school and I'm hardly comfortable with their UIs. HexEdit on the other hand, is the one I've been using ever since. It has a build-in calculator, supports deflate data decompression of different headers and also file templates with a simple syntax for you to examine your formats. And I do enjoy its interface which is really helpful for dynamically interpreting the data with human eyes. That would be enough for me. But I see HexEdit is in your list, so what's your opinion of it?
## Post #5
- Username: jumpjack
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Apr 25, 2020 9:44 pm
- Post datetime: 2020-05-04T18:27:18+00:00
- Post Title: What's the best freeware hex editor for examining models?

> Reply from Bigchillghost ↑Mon May 04, 2020 5:33 pm at Mon May 04, 2020 5:33 pm
>
> 
 HexEdit [...] supports deflate data decompression of different headers and also file templates with a simple syntax for you to examine your formats. [...]HexEdit is in your list, so what's your opinion of it?
Maybe it's another "hexedit"? Mine has just basic features. Its extended name is "MiTec Hexadecimal editor".
## Post #6
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-05-04T19:34:45+00:00
- Post Title: What's the best freeware hex editor for examining models?

The hex editor hardly matters. It is the same data after all, no matter what you use to view it. I would suggest focusing more on understanding the data / patterns and trying to implement your findings by coding.

The "features" you mentioned sounds more like the process of programming an actual format reader which is not the purpose of the hex editor. That may be the reason why you are not satisfied with all those hex editors. The closest I can think of is the binary templates of 010, but you already mentioned that yourself.
## Post #7
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-05-05T06:00:55+00:00
- Post Title: What's the best freeware hex editor for examining models?

> Reply from jumpjack ↑Tue May 05, 2020 2:27 am at Tue May 05, 2020 2:27 am
>
> 
Maybe it's another "hexedit"? Mine has just basic features. Its extended name is "MiTec Hexadecimal editor".
It appears so. The one I was talking about was developed by Andrew Phillips but sadly its official site was down long time ago. This is the only download that I could retrieve from its Google cache: [HexEdit5build1349.zip](https://www.mediafire.com/file/b8wb4ainrm20vm3/HexEdit5build1349.zip). 
The source code is still available on Github: [https://github.com/AndrewWPhillips/HexEdit](https://github.com/AndrewWPhillips/HexEdit). 
Also found this on codeproject which contains some more info of its features: [https://www.codeproject.com/Articles/13 ... ile-Editor](https://www.codeproject.com/Articles/135474/HexEdit-Window-Binary-File-Editor).
Though it's for version 4.0 and current version is 5.0.
