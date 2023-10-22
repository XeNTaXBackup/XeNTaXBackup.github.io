## Post #1
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-09-26T04:34:23+00:00
- Post Title: Girl Fight (PS3/360)

Here is a pak extractor for this game.
[https://store.sonyentertainmentnetwork. ... GHT0000001](https://store.sonyentertainmentnetwork.com/#!/en-us/games/girl-fight/cid=UP1012-NPUB30736_00-GIRLFIGHT0000001)
[http://marketplace.xbox.com/en-US/Produ ... 025841123a](http://marketplace.xbox.com/en-US/Product/Girl-Fight/66acd000-77fe-1000-9115-d8025841123a)
This game uses PSSG models.
I am only interested in this game for its engaging plot. 


```
#by chrrox
#Girl Fight (PS3/360)
endian big
get MAGIC long
get FILES long
for i = 0 < FILES
get OFFSET long
get SIZE long
getdstring NAME 0x80
log NAME OFFSET SIZE
next i

```
## Post #2
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2013-09-26T05:09:40+00:00
- Post Title: Girl Fight (PS3/360)

> Reply from chrrox
>
> 
I am only interested in this game for its engaging plot.

Errmm... Boobs??
## Post #3
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2013-09-26T12:10:09+00:00
- Post Title: Girl Fight (PS3/360)

Have to say, the game have an interesting plot
## Post #4
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2013-09-27T00:22:36+00:00
- Post Title: Girl Fight (PS3/360)

I'm only interested in this game for the amazing soundtrack.
## Post #5
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2013-10-09T19:12:29+00:00
- Post Title: Girl Fight (PS3/360)

Anyone figured out how to properly import the models yet?
I tried this: [viewtopic.php?f=16&t=6794&hilit=PSSG](http://forum.xentax.com/viewtopic.php?f=16&t=6794&hilit=PSSG) and it only extracts the textures but doesn't import any model data. A different tool for .pssg's of a different game doesn't work either. I saw a few WIPs on the format on other threads but none of those seem to be released ><
## Post #6
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-10-09T22:06:39+00:00
- Post Title: Girl Fight (PS3/360)

rexil tried my atelier totori ripper on it but said it didnt extract uvs. though i think my magic the gathering tactics was the last time i worked with pssg. pssg is a pain in the ass scene graph format that requires a lot of bookeeping for proper parsing, thats why there are a lot of wips but no completely finished products .

if you guys want this that bad (the models dont look that good do they), i suppose i can update it with new uv format, but cant promise bones or weights.
## Post #7
- Username: artworkplay
- Rank: veteran
- Number of posts: 116
- Joined date: Thu Oct 06, 2011 4:40 am
- Post datetime: 2013-10-10T08:10:47+00:00
- Post Title: Girl Fight (PS3/360)

I like this game for the riveting, emotionally resonant storyline.
## Post #8
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2013-10-10T13:12:24+00:00
- Post Title: Girl Fight (PS3/360)

> Reply from howfie
>
> rexil tried my atelier totori ripper on it but said it didnt extract uvs. though i think my magic the gathering tactics was the last time i worked with pssg. pssg is a pain in the ass scene graph format that requires a lot of bookeeping for proper parsing, thats why there are a lot of wips but no completely finished products .

if you guys want this that bad (the models dont look that good do they), i suppose i can update it with new uv format, but cant promise bones or weights.

Oh no it's fine then >< I was just wondering^^ I'm only interested in one of the characters so there's no need to rework a pain in the ass format just for that^^
Thanks anyway though =)
