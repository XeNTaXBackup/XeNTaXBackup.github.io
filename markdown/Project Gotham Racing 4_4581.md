## Post #1
- Username: ALYX
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Apr 08, 2010 2:33 am
- Post datetime: 2010-06-09T09:26:32+00:00
- Post Title: Project Gotham Racing 4

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-06-09T15:58:00+00:00
- Post Title: Project Gotham Racing 4

I see the game and.. surprise to. Very-very quality models.
## Post #3
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2010-06-11T20:39:16+00:00
- Post Title: Project Gotham Racing 4

Most of the data for the car is in the Peugeot_Flux.pak_hrd file. This file contains mostly compressed data chunks with uncompressed data in between. I use the program "offzip" to decompress the data. The decompressed data contains no headers as the header information was already uncompressed.
The compressed data starting at offset 000947ad is almostly certainly the main model's vertex data, however it does not use standard floating point. The compressed data starting at offset 000cf16d is the face array index, which are tristrips that are reset by the bytes "FF FF". This file references a model containing around 17,000 vertexes.  The compressed data starting at 0002b07d contains a dds texture. The smallest compressed chunks contain a model that has 31 vertexes.
Over all there are 118 compressed chunks.
## Post #4
- Username: ALYX
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Apr 08, 2010 2:33 am
- Post datetime: 2010-06-12T14:45:56+00:00
- Post Title: Project Gotham Racing 4

> Most of the data for the car is in the Peugeot_Flux.pak_hrd file. This file contains mostly compressed data chunks with uncompressed data in between. I use the program "offzip" to decompress the data. The decompressed data contains no headers as the header information was already uncompressed.
>
> The compressed data starting at offset 000947ad is almostly certainly the main model's vertex data, however it does not use standard floating point. The compressed data starting at offset 000cf16d is the face array index, which are tristrips that are reset by the bytes "FF FF". This file references a model containing around 17,000 vertexes. The compressed data starting at 0002b07d contains a dds texture. The smallest compressed chunks contain a model that has 31 vertexes.
>
> Over all there are 118 compressed chunks.
Maybe this research helps someone to make a convertor for this game. To bad that i dont know how to to this by myself.
