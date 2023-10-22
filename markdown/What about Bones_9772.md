## Post #1
- Username: Valerian
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Jul 20, 2011 6:25 am
- Post datetime: 2012-10-22T14:19:36+00:00
- Post Title: What about Bones?

I was searching in forum for bone information but i couldnt find anything.
What about the bones? how are they stored in a model? the same as vertices? with x,y,z coordinates and other things?
i would like some general information about it
## Post #2
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-10-22T18:26:09+00:00
- Post Title: What about Bones?

I've seen it two ways. First is a list joints along with their parents index and position and rotation transform. Second is an adjacency list representation where a list of joints where each joint stores position, rotation, and child indices. Sometimes names are present, sometimes not. Joint data, like vertex data, can be interleaved or non-interleaved. Positions and rotations can be relative or absolute. 

And, some games joints are easy to extract; others hard. Depends on the engine and game developers.
## Post #3
- Username: Valerian
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Jul 20, 2011 6:25 am
- Post datetime: 2012-10-30T17:31:21+00:00
- Post Title: What about Bones?

> Reply from howfie
>
> I've seen it two ways. First is a list joints along with their parents index and position and rotation transform. Second is an adjacency list representation where a list of joints where each joint stores position, rotation, and child indices. Sometimes names are present, sometimes not. Joint data, like vertex data, can be interleaved or non-interleaved. Positions and rotations can be relative or absolute. 

And, some games joints are easy to extract; others hard. Depends on the engine and game developers.

okay thanks, but how are they usually stored in a model for example?
are they stored as shorts or floats? or anything else? 
i can read the model in 3ds max, it works but i have 32bytes of unknown data in the model, maybe this is the bone data
## Post #4
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2012-11-05T12:43:08+00:00
- Post Title: What about Bones?

Newer games are tending toward float32s as I recall (especially PC games) but older games, usually PS2 or similar console games, use float16s for most decimal data.

I have seen one game that used int16s and did some math on the values to turn them into decimals... but I'd say your best bet is to look for 32 bit floats in newer games and PC games, and 16 bit from ps2 era games.
## Post #5
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-11-05T18:46:02+00:00
- Post Title: What about Bones?

The bone data can be parent-child relative or absolute.
I've seen bonedata stored as Quats, Vectors + Eulers and even the full 4*4 matrices .
Sometimes in quats/eulers you have to swap values with eachother or multipy the w value with (-1).
