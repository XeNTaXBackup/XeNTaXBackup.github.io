## Post #1
- Username: Tempest2395
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon May 13, 2019 6:32 am
- Post datetime: 2019-05-12T22:49:32+00:00
- Post Title: Traveller's Tales PS1 .RAW file format

Hey guys, I'm new to this forum. I thought this would be a great place to ask this question that has stumped me. This file format is included in the following games:

Rascal
A Bug's Life
Toy Story 2
Buzz Lightyear of Star Command
Toy Story Racer
Muppet Racemania

I've tried to open these files in Infranviewer and I've tried countless numbers of parameters but I get nothing recognizable. It's all just indecipherable pixels. I know that they contain raw pixel data with no header or other information. Is there any other way to decode this?
## Post #2
- Username: SlavaVlasov
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Jul 02, 2015 4:00 am
- Post datetime: 2020-06-15T15:20:37+00:00
- Post Title: Traveller's Tales PS1 .RAW file format

So far it is only known that this is a compressed format.
In the PC version of the game "Toy Story 2", the graphics are packaged in mini-archives, but in an uncompressed form. However, something else is interesting: when porting the game, the developers forgot to delete some of the original files from the PS1, as well as several batch files.
[https://tcrf.net/Toy_Story_2:_Buzz_Ligh ... nt_Scripts](https://tcrf.net/Toy_Story_2:_Buzz_Lightyear_to_the_Rescue_%28Windows%29#Development_Scripts)
According to them, the developers had some kind of utility pconv, which seems to uncompress these files. But its developers nevertheless guessed to remove from the final release. Googling the utility has not yet succeeded.
