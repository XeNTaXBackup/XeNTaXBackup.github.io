## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-12-27T04:21:32+00:00
- Post Title: Magical Ride IAR

Data should not be compressed or encrypted.
I'm guessing the header is 104 bytes followed by the pixel data? Width and height seem pretty easy to see but I don't know what else there is.

Can someone look into this format and provide an outline?
[iar.7z](https://xentaxbackup.github.io/file/4929_iar.7z)
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-09T22:53:31+00:00
- Post Title: Magical Ride IAR

It looks like

```
dword[11] unk
dword uncompressed size? (width * height * 4) or (width * height * 3)
dword null
dword compressed size
dword[3] null
dword width
dword height
dword[6] null
byte[compressed size] pixel data

```


But now I don't know the compression format lol
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-17T21:40:37+00:00
- Post Title: Magical Ride IAR

bump
Models are cute, want to texture them.
## Post #4
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-04-17T22:44:17+00:00
- Post Title: Magical Ride IAR

got a link to the developer's website for the game? i really don't keep track of all these touhou doujin type games.
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-17T22:45:33+00:00
- Post Title: Magical Ride IAR

They're out of business.

[http://www.studio-ego.jp/](http://www.studio-ego.jp/)
## Post #6
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-04-18T12:43:53+00:00
- Post Title: Magical Ride IAR

Ah, this is one of those ones you'll probably have to look into the EXE to reverse the compression. It had some valid deflate blocks but nothing came out looking like image data. Also nothing came out of luigi's comtype program either. Looking at all those initial FF's I thought it might be some type of RLE but nope on that either.
