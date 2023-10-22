## Post #1
- Username: Athari
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Dec 16, 2011 1:32 pm
- Post datetime: 2013-07-05T02:26:35+00:00
- Post Title: XnaConvert: converting XNB files to PNG (All XNA versions)

There's already a tool for converting XNB files to PNG ("XNB Exporter"), but it has all sorts of issues: to convert a whole directory, you need to copy executable file; only XNA 4.0 is supported; it has no command line options etc. So I wrote a tool which has everything I need. (Also I wanted to play around with MEF, but that's unrelated.)

Features

Converting Texture2D XNB files to PNG images.
All versions of XNA are supported: 1.0, 2.0, 3.0, 3.1, 4.0.
Command line.
Supported games (all are available on Steam)

Terraria (XNA 4.0)
Dust: An Elysian Tail (XNA 4.0)
Capsized (XNA 3.1)
Blueberry Garden (XNA 3.0)

XNA 1.0 and 2.0 were not tested, but they should work. If you find any games implemented using these versions, please let me know. Installing all XNA redists is probably optional, but I haven't tested that scenario.

The tool converts only Texture2D files, but XNB files can contain pretty much any data. Out of the box, that's also fonts, sound banks and other stuff. I have no immediate plans to implement converting these (these objects don't have "Save" methods, so it would require much more code), but pull requests are welcome (the program is written in VS 2012, C# 5.0, .NET 4.5).

[Download XnaConvert from GitHub](https://github.com/Athari/XnaConvert/releases)
[Documentation and sources on GitHub](https://github.com/Athari/XnaConvert)
## Post #2
- Username: MiRiKan
- Rank: advanced
- Number of posts: 67
- Joined date: Fri Jul 25, 2014 1:28 pm
- Post datetime: 2014-08-25T03:15:56+00:00
- Post Title: XnaConvert: converting XNB files to PNG (All XNA versions)

Thanks.
XNA is still not dead.
## Post #3
- Username: Athari
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Dec 16, 2011 1:32 pm
- Post datetime: 2014-08-25T08:02:23+00:00
- Post Title: XnaConvert: converting XNB files to PNG (All XNA versions)

> Reply from MiRiKan
>
> Thanks.
XNA is still not dead.
Definitely not. MonoGame took its place and pretty successfully, I think. Still, no serious advancement (besides adding support for a huge list of platforms) can't be good.
