## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-06-23T19:04:58+00:00
- Post Title: Model scaling

I am writing some scripts to scale models by some factor but don't have any ideas how the new coords are calculated, so I decided to take a couple models and scale them up and down and then analyze the results.

At first I thought it was just

new_x = x * factor
new_y = y * factor
new_z = z * factor

(since I am scaling all three axis proportionally)

But then most of the models with a lot of vertices didn't follow that, so now I am not sure if there is an easy algorithm for it.

Anyone know?
## Post #2
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2011-06-23T20:36:17+00:00
- Post Title: Model scaling

There are meshes and models.
Mesh has vertex .
Model has one or many meshes.
For scaling use global transformations with matrices on model.
