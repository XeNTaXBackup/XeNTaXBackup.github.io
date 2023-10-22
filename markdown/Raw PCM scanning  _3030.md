## Post #1
- Username: Demander
- Rank: beginner
- Number of posts: 31
- Joined date: Wed Jun 06, 2007 4:59 am
- Post datetime: 2008-04-30T16:45:00+00:00
- Post Title: Raw PCM scanning  ?

Hi everybody 

I was wondering if there is any method how to search raw pcm in files,I made few algos but they are not so successfull in analyzing pcm as I expected.

Is there any characteristics for raw pcm ? How raw pcm stream begins ?
when I was analyzing a raw pcm,I found out that data are pretty random,but there is few hints,in many cases pcm chunk doesnt reach signed word limit... so I was searching with this condition,its successfull in searching files more than 2 sec but maybe there is better method how  to find raw pcm in files.

Any code snippet will be really helpfull,in any language 

Thank you for your answers
## Post #2
- Username: Demander
- Rank: beginner
- Number of posts: 31
- Joined date: Wed Jun 06, 2007 4:59 am
- Post datetime: 2008-05-01T17:12:22+00:00
- Post Title: Raw PCM scanning  ?

Really nobody know this ?
## Post #3
- Username: GameZelda
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Nov 15, 2007 12:56 am
- Post datetime: 2008-05-02T00:06:27+00:00
- Post Title: Raw PCM scanning  ?

I think that there is no safe way except formats... every combination of audio values is valid, so it's impossible to do it with a 100% precision.

Also, a lot of games don't use PCM... in X360, there's XMA, and in PS2, there's XA ADPCM/VAG.

You can also try with some format detector tool...
## Post #4
- Username: Demander
- Rank: beginner
- Number of posts: 31
- Joined date: Wed Jun 06, 2007 4:59 am
- Post datetime: 2008-05-03T11:34:11+00:00
- Post Title: Raw PCM scanning  ?

Thank you for anwer  anyway I'll be using my method and maybe I'll improove my algo.
Is there any way how to detect ADPCM ? I found out that jaeder naub is able to detect ADPCM...
