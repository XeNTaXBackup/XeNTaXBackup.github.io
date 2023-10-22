## Post #1
- Username: Wakka387
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Apr 02, 2015 2:06 pm
- Post datetime: 2015-05-02T04:53:53+00:00
- Post Title: Midnight Club 3 PCK Files

I was hopin someone could help me with the pck files from Midnight club 3?

Im hoping to unlock them so that I can use the city models and textures for a project me and a few people are working on...

Im still a bit new to the whole reverse engineering archives so I cant do it myself.

Anyway here is one of the pck's.

[https://dl.dropboxusercontent.com/u/185 ... _clear.pck](https://dl.dropboxusercontent.com/u/18575411/Random/atlanta_dawn_clear.pck)
## Post #2
- Username: Wakka387
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2015-05-02T12:59:04+00:00
- Post Title: Midnight Club 3 PCK Files

I see no filenames or filetable to suggest that this file is multiple files packed into one. It is most likely not intended to be extracted.

Regards.
## Post #3
- Username: Wakka387
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Apr 02, 2015 2:06 pm
- Post datetime: 2015-05-02T22:05:21+00:00
- Post Title: Midnight Club 3 PCK Files

> Reply from Gh0stBlade
>
> I see no filenames or filetable to suggest that this file is multiple files packed into one. It is most likely not intended to be extracted.

Regards.
then, is it just a compressed file or anything?

is there any way to open it?
## Post #4
- Username: Wakka387
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2015-05-04T20:45:43+00:00
- Post Title: Midnight Club 3 PCK Files

> Reply from ss4gogeta0
>
> Gh0stBlade wrote:I see no filenames or filetable to suggest that this file is multiple files packed into one. It is most likely not intended to be extracted.

Regards.
then, is it just a compressed file or anything?

is there any way to open it?

No it is not compressed.
## Post #5
- Username: Wakka387
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Apr 02, 2015 2:06 pm
- Post datetime: 2015-05-05T05:56:46+00:00
- Post Title: Midnight Club 3 PCK Files

> Reply from Gh0stBlade
>
> ss4gogeta0 wrote:Gh0stBlade wrote:I see no filenames or filetable to suggest that this file is multiple files packed into one. It is most likely not intended to be extracted.

Regards.
then, is it just a compressed file or anything?

is there any way to open it?

No it is not compressed.
hmm, well I did find these...



they seem rather large for a simple ppf file plus the fact that I cannot open them with ppf o matic seems to tell me that they are some other type of file...  Me thinks that maybe it is where the model for the city is... and if not then maybe its textures...



here ya go
[Tokyo_midnight_clear.ppf](https://db.tt/gJ3egRoB)
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-05-05T07:03:52+00:00
- Post Title: Midnight Club 3 PCK Files

> Reply from ss4gogeta0
>
> Me thinks that maybe it is where the model for the city is... and if not then maybe its textures...the great "maybe"...
I would suggest to start with smaller files.

You could use TextureFinder to decide what might be texture and what could be other data:



tokyo_midnight.JPG (193.81 KiB) Viewed 113 times
## Post #7
- Username: Wakka387
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Apr 02, 2015 2:06 pm
- Post datetime: 2015-05-06T23:14:08+00:00
- Post Title: Midnight Club 3 PCK Files

> Reply from shakotay2
>
> ss4gogeta0 wrote:Me thinks that maybe it is where the model for the city is... and if not then maybe its textures...the great "maybe"...
I would suggest to start with smaller files.

You could use TextureFinder to decide what might be texture and what could be other data:
tokyo_midnight.JPG

took the day off from school to learn how to use it, and ended up playing around with it abit... I know where most of the textures are stored... 

Assets.dat in the Texture folder (UI Textures)



Assets.dat in the Textures folder of any specific vehicle (NPC Vehicle Textures & Models)



Assets.dat main folder in each of the .dats for specified vehicles (Player Vehicle texture & model [Theory])




My biggest issue is trying to find the City models... which is why im trying to access [Tokyo_midnight_clear.ppf](https://db.tt/gJ3egRoB)

as it is the last place that I can think of looking since it doesnt seem to be in the Assets.dat folder
## Post #8
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2021-04-23T03:20:29+00:00
- Post Title: Midnight Club 3 PCK Files

So this issue was never solved with the vehicle .pck files? 

Karpati made a importer [https://zenhax.com/viewtopic.php?f=5&t=15135](https://zenhax.com/viewtopic.php?f=5&t=15135)

Ghostblade mentioned no header but is there away to pull the data out maybe VGM toolbox or a script ? I searched for the string SKIN but couldnt find it. Any help ?

.pck sample
[https://drive.google.com/file/d/1mcO5hK ... sp=sharing](https://drive.google.com/file/d/1mcO5hKdvCrq3ltn0VsdCS_15-TM2Ct7d/view?usp=sharing)
