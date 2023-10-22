## Post #1
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2010-04-06T12:09:23+00:00
- Post Title: how to modify CreateWindowEx to force windowed mode?

I have an old game which I'd like to run in windowed mode.
Shouldn't it be possible to force this by editing the arguments to CreateWindowEx calls or whatever?
## Post #2
- Username: jfwfreo
- Rank: veteran
- Number of posts: 124
- Joined date: Sat Nov 15, 2008 8:31 am
- Post datetime: 2010-04-06T13:32:55+00:00
- Post Title: how to modify CreateWindowEx to force windowed mode?

If the game is a modern game, you will have to hack the Direct3D calls the game makes. Its not easy to add windowed mode to a game that doesn't support it.

CreateWindowEx has nothing to do with windowed mode vs fullscreen mode.
## Post #3
- Username: Uli
- Rank: advanced
- Number of posts: 46
- Joined date: Sat Dec 12, 2009 2:42 am
- Post datetime: 2010-04-06T14:06:16+00:00
- Post Title: how to modify CreateWindowEx to force windowed mode?

Look up something called "D3DWindower" (Website in the Readme for it: [http://www.geocities.jp/menopem/](http://www.geocities.jp/menopem/) )
I use it to force DK2 into window mode, might work for the game your trying to play
## Post #4
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2010-04-06T15:10:51+00:00
- Post Title: how to modify CreateWindowEx to force windowed mode?

It's an old DirectDraw game.
## Post #5
- Username: Uli
- Rank: advanced
- Number of posts: 46
- Joined date: Sat Dec 12, 2009 2:42 am
- Post datetime: 2010-04-06T15:19:18+00:00
- Post Title: how to modify CreateWindowEx to force windowed mode?

> Reply from Rheini
>
> It's an old DirectDraw game.

DXWnd works with DirectDraw games however it was only some versions can't remember which ones
## Post #6
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2010-04-06T15:27:51+00:00
- Post Title: how to modify CreateWindowEx to force windowed mode?

Is there any article or tutorial about how functions need to be hooked?
Would need to statically hook it for debugging it properly.
## Post #7
- Username: Darkstar
- Rank: advanced
- Number of posts: 67
- Joined date: Thu Jun 14, 2007 8:14 pm
- Post datetime: 2010-06-01T11:07:07+00:00
- Post Title: how to modify CreateWindowEx to force windowed mode?

Look for the Microsoft Detours library, available somewhere on research.microsoft.com. It can do function hooking, so you can modify the arguments to CreateWindowEX() there

-Darkstar
## Post #8
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2010-06-01T14:48:03+00:00
- Post Title: how to modify CreateWindowEx to force windowed mode?

I know Detours. I can also directly modify the game executable and/or use a proxy DirectDraw dll.
The only question is what parameters need to be changed and how.
