## Post #1
- Username: Troopermanaic
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Jul 01, 2011 11:29 pm
- Post datetime: 2012-07-13T01:46:30+00:00
- Post Title: Another crack at .DET mostly understood

deleted topic by OP
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-07-13T02:34:29+00:00
- Post Title: Another crack at .DET mostly understood

I think they may have developed the models using .x tools or something, but then they probably exported it to their custom DET format which holds more information than what the direct3d specs provide.

And they may be parsing it and converting it internally to .x for whatever renderer they use.
For example, I got up to the point where it said "script" but then had no clue what to do with those sections.
## Post #3
- Username: Troopermanaic
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Jul 01, 2011 11:29 pm
- Post datetime: 2012-07-13T02:54:42+00:00
- Post Title: Another crack at .DET mostly understood

you are right and I partially know what to do with this data. I am interested, I know that that data can be replaced because I already imported a fugly sphere but is there a way to properly import 3d data to a .det file. That would at least give us custom 3d at the moment while we still research how the rest of it works.
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-07-13T04:37:15+00:00
- Post Title: Another crack at .DET mostly understood

You might be able to replace the vertex data and face data with custom values without touching the rest of the model.

Don't know, might work.
It may also shed some light to how to determine which set of vertices goes with which set of indices.
## Post #5
- Username: Troopermanaic
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Jul 01, 2011 11:29 pm
- Post datetime: 2012-07-13T08:28:10+00:00
- Post Title: Another crack at .DET mostly understood

Its extremely interesting to me because in another game I am able to do this as long as I name specific parts of mesh the same as the 3d file's animation bones that are named after and line up the joints of said bones. It will appear in game as if it was a 3d file that was meant to be part of the game. I am hoping that I could replace all 3d aspects of a .DET seeing that I know I could make it work as a new file. I am confidant that I can add MS to the game but I need to re import back into the file. I basically want to replace the 3d coding of the file. I have attempted this without knowing it 100% completely and had good results. 

I am hoping someone with a better eye of the way this encryption works will explain where the coding "of the 3d aspect" starts and ends. I know im close I just need help. Im ripping my hair out over this.
