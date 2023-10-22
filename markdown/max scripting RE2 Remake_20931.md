## Post #1
- Username: Crazy Potato
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Mar 26, 2018 11:56 am
- Post datetime: 2019-08-08T23:29:45+00:00
- Post Title: max scripting RE2 Remake

I'm getting this error after editing a bit to allow more models to be exporting/imported. I'll provide more info if needed, I'd post them now but I don't even know what to post lol
Being new to max scripting can only get you so far before needing help...
## Post #2
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2019-08-11T17:02:09+00:00
- Post Title: max scripting RE2 Remake

w1 is not defined, !=0 statement won't protect you from undefined variables (0 != undefined).
You will need to define said variable, or use appropriate expression.

So it should be

```
...

```
