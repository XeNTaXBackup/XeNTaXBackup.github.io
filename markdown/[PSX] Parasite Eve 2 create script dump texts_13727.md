## Post #1
- Username: carnage
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Jun 26, 2012 10:21 pm
- Post datetime: 2015-12-27T16:53:37+00:00
- Post Title: [PSX] Parasite Eve 2 create script dump texts

Friends okay with you.
First of all want to leave here my best wishes for merry christmas and a great new year for all forum.
Could anyone help me in this game until today I did not find anything that would be of help to translate this game, many are trying but not tivem success.
Someone would or could create a script to dump / insert texts This Game?
## Post #2
- Username: mdhyena
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Apr 02, 2015 7:26 pm
- Post datetime: 2016-01-12T10:35:36+00:00
- Post Title: [PSX] Parasite Eve 2 create script dump texts

Hello there. A little info here to help You. Game has three types of text: the first will be GUI items (main menu, player menu, inventory, etc) which are images (well, packed images); the second - items descriptions, which are just plain ASCII text with some mark-up symbols; and the last - dialog text, which is basically a binary data with character width table to use with font image followed by encoded text. The encoding varies from one file to another, and depends on font image.

Fonts are stored, if I recall it correctly, as a 4bpp indexed compressed images, CLUTs for them are stored separately.

I linked a program I wrote a while ago, that is capable to extract/unpack most of the data (excluding raw sounds and background FMV movies) from *.CDF files. Just drop any of the CDFs on it. The dialog text is in files with extension "*.04", the actual width table and text in them start somewhere after "CAP2" ascii string.
[PE2Ex04.zip](https://xentaxbackup.github.io/file/10294_PE2Ex04.zip)
## Post #3
- Username: xdrgamelove
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Sep 19, 2017 10:37 pm
- Post datetime: 2017-09-19T15:47:42+00:00
- Post Title: [PSX] Parasite Eve 2 create script dump texts

> Reply from mdhyena
>
> Hello there. A little info here to help You. Game has three types of text: the first will be GUI items (main menu, player menu, inventory, etc) which are images (well, packed images); the second - items descriptions, which are just plain ASCII text with some mark-up symbols; and the last - dialog text, which is basically a binary data with character width table to use with font image followed by encoded text. The encoding varies from one file to another, and depends on font image.

Fonts are stored, if I recall it correctly, as a 4bpp indexed compressed images, CLUTs for them are stored separately.

I linked a program I wrote a while ago, that is capable to extract/unpack most of the data (excluding raw sounds and background FMV movies) from *.CDF files. Just drop any of the CDFs on it. The dialog text is in files with extension "*.04", the actual width table and text in them start somewhere after "CAP2" ascii string.


How to import files? Please help me?
## Post #4
- Username: Morty888
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Apr 15, 2019 3:59 pm
- Post datetime: 2019-04-15T08:05:50+00:00
- Post Title: [PSX] Parasite Eve 2 create script dump texts

> Reply from mdhyena ↑Tue Jan 12, 2016 6:35 pm at Tue Jan 12, 2016 6:35 pm
>
> 
Hello there. A little info here to help You. Game has three types of text: the first will be GUI items (main menu, player menu, inventory, etc) which are images (well, packed images); the second - items descriptions, which are just plain ASCII text with some mark-up symbols; and the last - dialog text, which is basically a binary data with character width table to use with font image followed by encoded text. The encoding varies from one file to another, and depends on font image.

Fonts are stored, if I recall it correctly, as a 4bpp indexed compressed images, CLUTs for them are stored separately.

I linked a program I wrote a while ago, that is capable to extract/unpack most of the data (excluding raw sounds and background FMV movies) from *.CDF files. Just drop any of the CDFs on it. The dialog text is in files with extension "*.04", the actual width table and text in them start somewhere after "CAP2" ascii string.
Your file is broken, please reload ...
## Post #5
- Username: Morty888
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Apr 15, 2019 3:59 pm
- Post datetime: 2019-04-15T08:41:36+00:00
- Post Title: [PSX] Parasite Eve 2 create script dump texts

I found it myself
Drag the file to this
[PE2Ex04.rar](https://xentaxbackup.github.io/file/16040_PE2Ex04.rar)
