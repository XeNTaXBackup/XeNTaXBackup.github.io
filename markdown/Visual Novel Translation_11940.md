## Post #1
- Username: Kventin Dorvard
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Sep 12, 2014 5:20 pm
- Post datetime: 2014-09-12T10:05:34+00:00
- Post Title: Visual Novel Translation

Hello everyone.
I need help with translating [Rewrite](https://en.wikipedia.org/wiki/Rewrite_%28visual_novel%29) (Key's visual novel) into Russian. 
Problem is: all texts in the game output in [fullwidth](http://en.wikipedia.org/wiki/Halfwidth_and_fullwidth_forms) form. That makes Russian texts very difficult to understand.
I guess, in order to solve this problem I'll need to modify game engine itself, but I don't know where to start.
Game engine is SiglusEngine.
## Post #2
- Username: basil
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Mar 29, 2010 3:00 am
- Post datetime: 2014-09-12T10:31:28+00:00
- Post Title: Visual Novel Translation

Edit: Whoops I'm dumb, I didn't realize the English translation also uses a fixed-width font.

P.S. Can you show me a screenshot of full-width, hard-to-read Russian text?  And under your screenshot, can you type the same text (so I can see how it looks normally)? Maybe we can think of something...
## Post #3
- Username: Kventin Dorvard
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Sep 12, 2014 5:20 pm
- Post datetime: 2014-09-12T11:10:36+00:00
- Post Title: Visual Novel Translation

Sure.

English translation: [http://i66.fastpic.ru/big/2014/0912/c1/ ... fd55c1.png](http://i66.fastpic.ru/big/2014/0912/c1/aaf03183894e8d78f576a20cb7fd55c1.png)
Russian translation: [http://i66.fastpic.ru/big/2014/0912/87/ ... 4c0c87.png](http://i66.fastpic.ru/big/2014/0912/87/2e35707d846da00a5aef95d0574c0c87.png)

How it should be:
Котаро
"Ауч!"
Мужчина:
"Не ушибся?"

Сидящий рядом Луис обращается ко мне на ломанном английском.
Ему двадцать пять. Смуглая кожа. Лицо покрыто татуировками.
Но не смотря на его пугающее лицо, у него добрые глаза.
Он высок, где-то на голову выше меня.
И один из моих немногих друзей.
При мне он ещё ни разу не ударился головой в дороге. (this line you don't see because there are no free space for it on current game page)
## Post #4
- Username: basil
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Mar 29, 2010 3:00 am
- Post datetime: 2014-09-12T11:39:53+00:00
- Post Title: Visual Novel Translation

[(Screenshots rehosted on imgur for those who prefer that)](http://m.imgur.com/a/EGnEn)

Yikes, that really is some huge spacing! But not all monospace Russian/Cyrillic looks that bad, right? Would you be satisfied with having the same width as the English characters?
## Post #5
- Username: Kventin Dorvard
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Sep 12, 2014 5:20 pm
- Post datetime: 2014-09-12T15:57:10+00:00
- Post Title: Visual Novel Translation

The problem is with fullwidth itself. The Game any proportional font or monospace font is outputs in fullwidth form. But I managed to find a temporary solution. I had created a new font, based on fullwidth OsakaMono and replaced it halfwidth Katakana with Cyrillic characters.

How it was before: [http://imgur.com/9RYM7P7](http://imgur.com/9RYM7P7)
And how it looks now: [http://imgur.com/qhjNJkv](http://imgur.com/qhjNJkv)

But it is not the best solution, because I need replace all Cyryllic characters in game scripts to halwidth Katakana...
## Post #6
- Username: basil
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Mar 29, 2010 3:00 am
- Post datetime: 2014-09-15T04:33:22+00:00
- Post Title: Visual Novel Translation

I guess this won't solve this specific problem, but have you seen this entry on the [Amaterasu Translations FAQ page](http://amaterasu.tindabox.net/index.php?page=FAQ)?

> Q: Can I use some of your translated scripts and tools to start a Spanish/French/Italian/etc translation project?
>
> 
>
> A: Just talk to me and I'll send you whatever I have. I'm all for more VNs getting translated into more languages.
>
> However, there is no guarantee that the hacker who made our tools will be willing to modify or support those tools for your project, so be sure to get your own hacker.

edit: I just came across repository for a Russian translation of Rewrite that never really got off the ground. I don't think they translated any of the actual script, just some game EXE text: [http://i.imgur.com/loa4n4m.png](http://i.imgur.com/loa4n4m.png) (Google the filename in my screenshot if you want to check it out.)

Also, one of the readme files there has a message from the English (not Russian) translation team:

> Reply from readme!.txt
>
> If a serious translator comes along and wants to start up a project,
I can be found on IRC: Nagato on irc.rizon.net (can be found in #Ammy,
almost always idling on Rizon so /msg would also be fine).

I'm really sorry if this is all useless or stuff you already know.
## Post #7
- Username: Kventin Dorvard
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Sep 12, 2014 5:20 pm
- Post datetime: 2014-09-15T14:45:47+00:00
- Post Title: Visual Novel Translation

As I had said already, I found a temporaty solution. Now text from 1st post is displaying like this: [http://imgur.com/WfLkzBU](http://imgur.com/WfLkzBU)

It is working, so we decided not to dig deeper the game code.

Thanks for your help and advices, but we already contacted Amaterasu Translations. Nagato said he did not study SiglusEngine and can not help us.
