## Post #1
- Username: Barny
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Jan 24, 2009 11:18 pm
- Post datetime: 2009-01-24T16:12:04+00:00
- Post Title: Smash Online *.npk

Hello World 

This is about a free2play online tennis game called "Smash Online".
The download file size is like 160MB ([http://tennis.gamigo.com/](http://tennis.gamigo.com/))
Edit: [http://tennis.gamigo.com/downloads/Setu ... 080109.exe](http://tennis.gamigo.com/downloads/Setup_for_Gamigo_English_20080109.exe)

The game folder contains only one big compressed file "Resource.npk" which is 150MB.

I can't find a solution to open/extract this archive. 
Usually Nebula2 SDK would to the trick for *.npk files, but it doesn't work with this one saying: 

```
nNpkFileWrapper: could not parse table of contents in file 'C:/...'!
```


Btw: Game Extractor or MultiEx Commander couldn't open this *.npk archive. 

I hope you guys can help with this one! Would be great! 
Oh and btw, this forum is awesome!  Never saw anything like this. Great idea!
## Post #2
- Username: Barny
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Jan 24, 2009 11:18 pm
- Post datetime: 2009-01-28T22:50:40+00:00
- Post Title: Smash Online *.npk

According to fatduck, this whole archive can only be decomprossed/extracted witz LZO. 
Unfortunately this doesn't work with usual LZO scripts for win32. If I am not mistaken this procedure requires an visual c/c++ compiler?

LZO:
[http://www.oberhumer.com/opensource/lzo/](http://www.oberhumer.com/opensource/lzo/)

I really hope you guys can help
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-04-27T20:13:22+00:00
- Post Title: Smash Online *.npk

you can find a script [here](http://aluigi.org/papers/bms/smash_online.bms).

it doesn't handle the folders because it's not clear the method used by the game (I have given a very quick look only to resource.npk without any deeper research)
## Post #4
- Username: Barny
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Jan 24, 2009 11:18 pm
- Post datetime: 2009-04-27T21:47:44+00:00
- Post Title: Smash Online *.npk

Bugtest, thank you very much! it worked! I'm really amazed  You are my hero!!! THANKS
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-04-28T00:11:21+00:00
- Post Title: Smash Online *.npk

I have also added support for the folders, I don't know to what I was thinking previously for not noticing them :)
the link is the same, just refresh it to see the new version
## Post #6
- Username: Barny
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Jan 24, 2009 11:18 pm
- Post datetime: 2009-04-28T05:53:44+00:00
- Post Title: Smash Online *.npk

the new script works like a charm  its so interesting to look into these folders! thank you!!!
