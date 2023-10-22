## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-01T18:22:42+00:00
- Post Title: Hero online .dxt

I downloaded an MMORPG called hero online and found some dxt files for the textures.
Didn't see anything about it on these forums.

I haven't look at any graphics yet so I don't know how to convert it. Can anyone take a look and maybe tell me how to convert it? Or maybe how to get an idea of what to do in general.

Homepage for anyone interested in the game: [http://hero.netgame.com/](http://hero.netgame.com/)
[DTex.7z](https://xentaxbackup.github.io/file/4409_DTex.7z)
## Post #2
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2011-07-11T19:14:13+00:00
- Post Title: Hero online .dxt

It is a DDS with custom header!

```
char[4]   HeaderID          //"NTF\0"
dword     ImageWidth
dword     ImageHeight
char[4]   DTX_Type
dword     ??
<Image Data>

```


Go and find a program call "TextureFinder". It help to find almost all images in files!
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-12T02:58:21+00:00
- Post Title: Hero online .dxt

Thanks fatduck. I will look into that program. Maybe it will make things easier for me.
## Post #4
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2011-07-14T14:07:30+00:00
- Post Title: Hero online .dxt

Fatduck,

You can download a very useful tool using this link:
[url]http://www.kz_3d.tvn.hu/N3TexViewer.zip[/url]
