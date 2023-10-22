## Post #1
- Username: spont
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed May 30, 2012 9:13 pm
- Post datetime: 2012-05-30T14:56:27+00:00
- Post Title: Rollcage/Rollcage Stage II

Hi,
  Last month I came across the decompression algorithm for the Rollcage Archive file on the wiki.  ([LINK](http://wiki.xentax.com/index.php?title=Rollcage_2_IMG)) I tried implementing it, fixed a bug or two, and added the results of the subsequent research on the texture/model files.

Granted - a lot of it won't make sense unless you've got sample data to work through - but I have the feeling though, that I'm murdering the style-guide!  I tried to follow the formatting and style already there, but is there a standard for this that I could copy from?  Should I go ahead and style it till it looks good to my eyes?  Any feedback would be useful.

I probably should have registered earlier, since now I have too many questions 

From what I've seen, the data formats are the same for Rollcage 1 + 2.  How best to handle that?  Redirect?  Rename?  Add a note?
The model and texture files have their own format -- should they be on a separate page each?
I wrote some code to handle the extraction - first in C++, then Java.  Is that of interest to anyone?

Progress-wise, we've identified the car + track models and extracted the textures.  For the cars, we've found the texture coords and identified vertex indices in what seem to be face-definitions, but the normals and vertices themselves are still unknown.  The track models are baffling.  A lot of the early leg-work is already done, but I'm a n00b at this and I think that perhaps with a little experienced assistance we could nail this format quickly.
