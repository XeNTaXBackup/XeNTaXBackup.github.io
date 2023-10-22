## Post #1
- Username: DGIorio
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Jan 11, 2016 6:12 am
- Post datetime: 2017-10-13T19:49:54+00:00
- Post Title: Noesis help? Hit max_concurrent_rpgeo_contexts

Hi everyone,

I've been doing a script for Noesis and I'm getting this problem: Hit MAX_CONCURRENT_RPGEO_CONTEXTS!

I think it's caused by the number of models that I'm loading, because for isolated models it's working pretty well and when I load a small number of models together it works.
Is there a better way to load multiple models? What I want to do is open multiple models and positionate them.

At the moment I'm using this to open multiple models (but getting error): rapi.rpgCreateContext()
I tried to make a vector (ctx = rapi.rpgCreateContext()), but there is no differences, I still get the same error.

Thanks in advance.
## Post #2
- Username: zheneq
- Rank: advanced
- Number of posts: 43
- Joined date: Fri Jul 17, 2015 1:09 pm
- Post datetime: 2017-10-13T22:23:01+00:00
- Post Title: Noesis help? Hit max_concurrent_rpgeo_contexts

Just put ctx = rapi.rpgCreateContext() in the beginning of your script and never call it again.

And keep the reference to it till the end so that garbage collector does not delete it.
## Post #3
- Username: DGIorio
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Jan 11, 2016 6:12 am
- Post datetime: 2017-10-15T19:29:08+00:00
- Post Title: Noesis help? Hit max_concurrent_rpgeo_contexts

> Reply from zheneq
>
> Just put ctx = rapi.rpgCreateContext() in the beginning of your script and never call it again.

And keep the reference to it till the end so that garbage collector does not delete it.

I'm thankful for your help, it works. Now I can load the models together, I'm just getting error with files with a large amount of models to be loaded, probably because Noesis has a 4GB ram limit.
I don't know if it can be solved, but thank you!
