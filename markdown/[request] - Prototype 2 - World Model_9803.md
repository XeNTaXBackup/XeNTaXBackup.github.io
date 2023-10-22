## Post #1
- Username: Kaotix
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jun 21, 2012 8:20 pm
- Post datetime: 2012-10-29T07:05:19+00:00
- Post Title: [request] - Prototype 2 - World Model

I seen that someone has got a few character models. But I cant find how to get the world or where the models for the world are located.
## Post #2
- Username: Nobby
- Rank: veteran
- Number of posts: 109
- Joined date: Thu May 13, 2010 7:35 am
- Post datetime: 2012-11-05T20:21:49+00:00
- Post Title: [request] - Prototype 2 - World Model

unlikely you will ever be able to extract an entire world/level as one complete file, as thats not how game worlds are generally made up.
More often than not they use instancing. So you only use one copy of an object and the game engine is then given markers which represent that object. A good example of this would be street lights. you wouldnt stamp down hundreds of copies of a street light, you would only have one light and a marker to represent that light. you stamp down the marker hundreds of times and the engine knows that where ever that marker appears it should display a street light. Which frees up a lot of overheads for the rest of the game, same with trees and traffic cars and such.

So if you extracted the level you would probably end up with 1 tree model and 1 light model rather than a level that contains hundreds of trees and lights.
## Post #3
- Username: Kaotix
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jun 21, 2012 8:20 pm
- Post datetime: 2012-11-25T19:34:27+00:00
- Post Title: [request] - Prototype 2 - World Model

if the trees and the lights are the only complicated thing, I can deal with that. I just really want the layout with the buildings and land. I can figure out how to place the lights and the trees later.
