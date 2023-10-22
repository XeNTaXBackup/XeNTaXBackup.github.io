## Post #1
- Username: TheFalcon19
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Sep 25, 2019 9:42 pm
- Post datetime: 2021-05-26T03:05:49+00:00
- Post Title: Need help finishing a script, I know what the last steps should do, but can't program it

I'm at the final steps of writing a script for a sequential format where the toc contains relative jump points to models, textures and empties.

The submaterial face index jumps back and forth between different submaterials of different objects, but has a number that lets us know the number of the file in the toc, so we can get to the correct model.

Now what makes things complicated is that up to four vertex blocks can share a single face block.

We do have a number that we can read but the value of the number doesn't mean the number of the vertex block, but instead the number that first appears per model is assigned to the first vertex blocks, the second number that appears is assigned to second vertex block, etc..

```
Test List =  [(10, 0), (210, 0), (10, 0), (10, 0), (220, 0), (120, 1), (120, 1), (120, 1), (20, 1), (20, 1), (20, 1), (20, 0), (20, 1), (190, 0), (200, 0), (230, 0), (120, 2), (120, 1), (120, 1), (120, 1), (120, 1), (120, 1), (120, 1), (120, 1), (120, 1), (120, 1), (120, 1), (120, 1), (120, 1), (120, 1), (120, 1), (120, 1), (120, 1), (30, 0), (30, 0), (30, 0), (30, 1), (30, 1), (120, 0), (120, 0), (120, 1), (40, 1), (40, 1), (40, 1), (120, 0), (120, 1), (120, 0), (60, 0), (50, 1), (50, 1), (60, 1), (60, 1), (80, 1), (80, 1), (80, 1), (80, 1), (80, 1), (70, 0), (70, 0), (70, 1), (70, 1), (70, 1), (70, 1), (70, 1), (70, 1), (70, 1), (70, 1), (70, 2), (70, 3), (70, 3), (90, 1), (90, 1), (90, 1), (90, 1), (90, 1), (90, 1), (90, 1), (90, 1), (90, 1), (90, 1), (90, 1), (90, 1), (90, 1), (90, 1), (90, 1), (90, 1), (90, 1), (120, 1), (120, 0), (120, 1), (120, 1), (120, 1), (120, 1), (120, 1), (120, 1), (120, 1), (100, 1), (100, 1), (100, 1), (100, 1), (100, 1), (100, 1), (110, 0), (110, 0), (120, 0)]
```


This means for example if you look at the list, for model 20 the first number that appears is 1 so every 20, 1 face data should be sent to the first vertex block, 0 appears second so 20, 0 is sent to the second vertex block.

I can't figure out a way to process and transform this data to get a new list of which vertex block to jump to.
