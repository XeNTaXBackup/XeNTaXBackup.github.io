## Post #1
- Username: Ezzio100
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Oct 19, 2020 7:42 am
- Post datetime: 2020-12-31T19:26:11+00:00
- Post Title: Some problem with normals or backface culling

Hello, i have a problem with a model i ripped from the game sengoku basara 4. the probleim is this missin vertices all over the model, it works in normal view and rendering, but when im going to use it in a game it looks like the one in the third pic. is there any way to fix this? flipping normals doesnt help.

this is how it looks normally: [https://imgur.com/a/HwLNGD5](https://imgur.com/a/HwLNGD5)

this is how it looks when rendered: [https://imgur.com/a/nU6hK4P](https://imgur.com/a/nU6hK4P)

and this is the big problem: [https://imgur.com/a/WbSc6dX](https://imgur.com/a/WbSc6dX)
## Post #2
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2021-01-03T11:42:25+00:00
- Post Title: Some problem with normals or backface culling

SB4 is a PS3 title afaik. They use some weird flips for faces.
You can fix that, by flipping/inverting face itself. Or by checking '2-sided' in material properties.
