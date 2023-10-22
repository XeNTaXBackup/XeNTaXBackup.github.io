## Post #1
- Username: Nerd42
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Apr 14, 2011 1:03 pm
- Post datetime: 2015-07-12T04:59:34+00:00
- Post Title: Guitar Hero 3 DLC ?

I'm trying to extract the audio from the Modern Rock Track Pack for Guitar Hero III XBox. I know there's ogg rips of it floating around the Internet but I want to make sure I have the highest possible quality audio because I'm going to be wanting to run the resulting wav files through [this thing](http://isse.sourceforge.net/).

wxPirs-1.1 gets me three files, "DLC32.fsb.xen", "DLC28.fsb.xen" and "DLC27.fsb.xen"

I then wrote the following batch file:

> for %%1 in (*.fsb.xen) do songfsbdecrypt %%1 %%~n1
>
> for %%1 in (*.fsb) do fsbext -a %%1
>
> del *.fsb
>
> for %%1 in (*.xma) do towav %%1
>
> del *.xma
This successfully gets some xma files, but ultimately produces a big ol' pack o nothin when towav fails, so apparently there is some step inbetween fbsext and towav which I'm missing, possibly to do with xma_test a.k.a. xma_parse. But I'm not sure what numbers I'm supposed to give it. It's been a while since I played with this stuff.
## Post #2
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2015-07-12T17:56:15+00:00
- Post Title: Guitar Hero 3 DLC ?

Try using Alpha23's XMA Transform BMS script on the XMA files then run them through ToWAV.

You will also need HCS's XMA Parse tool (You will need to rename it from xma_test to xma_parse for the BMS script to find it and work properly)
