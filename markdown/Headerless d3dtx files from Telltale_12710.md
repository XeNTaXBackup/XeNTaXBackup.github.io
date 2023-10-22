## Post #1
- Username: Nerd42
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Apr 14, 2011 1:03 pm
- Post datetime: 2015-03-22T19:35:20+00:00
- Post Title: Headerless d3dtx files from Telltale?

I'm trying to extract textures from Poker Night 2. Not models ... just textures. I think the trouble is the d3dtx files are missing some kind of header.

RandomTBush seems to have [developed something](http://forum.xentax.com/viewtopic.php?f=16&t=11687) to put on the header. But it requires 3DS Max and I don't have 3DS Max. Can anybody figure out what it's doing so I could duplicate the results using free tools? I can't figure out his source code.
## Post #2
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2015-03-22T21:56:54+00:00
- Post Title: Headerless d3dtx files from Telltale?

I'll be working on a version of the texture converter that works in QuickBMS before the end of the month.
## Post #3
- Username: Nerd42
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Apr 14, 2011 1:03 pm
- Post datetime: 2015-03-23T16:58:30+00:00
- Post Title: Headerless d3dtx files from Telltale?

> Reply from RandomTBush
>
> I'll be working on a version of the texture converter that works in QuickBMS before the end of the month.Oh, awesome. I'm excited to get it
## Post #4
- Username: Nerd42
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Apr 14, 2011 1:03 pm
- Post datetime: 2015-04-05T02:03:17+00:00
- Post Title: Headerless d3dtx files from Telltale?

> Reply from RandomTBush
>
> I'll be working on a version of the texture converter that works in QuickBMS before the end of the month.Did you mean the end of March or April?
## Post #5
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2015-04-07T23:11:29+00:00
- Post Title: Headerless d3dtx files from Telltale?

> Reply from Nerd42
>
> RandomTBush wrote:I'll be working on a version of the texture converter that works in QuickBMS before the end of the month.Did you mean the end of March or April?Sorry, some important matters popped up last week that I had to attend to. I'll do what I can to have it ready soon.
## Post #6
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2015-04-12T22:52:29+00:00
- Post Title: Headerless d3dtx files from Telltale?

[I think this should work](https://dl.dropboxusercontent.com/u/27874399/Telltale_D3DTX.zip), I was able to convert almost all of the textures from Poker Night 2 with it (a couple of them are odd, two have PNGs embedded in them which confuses the script and the other is an obscure pixel format) and haven't been able to test any of the other games yet, since I uninstalled them to free up disk space and it'll take a while for me to re-download. Lemme know if there are any problems (which there probably will be, knowing my luck).
## Post #7
- Username: Nerd42
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Apr 14, 2011 1:03 pm
- Post datetime: 2015-04-13T02:07:48+00:00
- Post Title: Headerless d3dtx files from Telltale?

It worked perfect. 0 errors. Thanks! 

For anyone else trying this kind of thing: I don't know if this is the "correct" way to do it, but I got it working by writing this batch file: 
> for %%i in (*.d3dtx) do quickbms "Telltale_D3DTX_PN2_TWD_TWAU.bms" "%%i" output

Then I used [XNconvert](http://www.xnview.com/en/xnconvert/) to batch convert everything to .png
[Telltale_D3DTX.zip](https://xentaxbackup.github.io/file/9011_Telltale_D3DTX.zip)
