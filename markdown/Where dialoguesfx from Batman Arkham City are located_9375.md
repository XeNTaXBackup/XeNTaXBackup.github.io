## Post #1
- Username: mikaelN7
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Apr 25, 2012 11:16 pm
- Post datetime: 2012-07-30T15:39:13+00:00
- Post Title: Where dialogue/sfx from Batman Arkham City are located?

I already found a tool to extract from the .upk files but can't find where they dialogue or sound effects are actually located. Anyone have know where to look?
## Post #2
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2012-07-30T23:40:48+00:00
- Post Title: Where dialogue/sfx from Batman Arkham City are located?

Arkham city doesnt use fmod/ogg files like asylum did, it uses .bnk/.wad (multiple .bnk's in a row) with wwise audio. (looks like riff header, but is closer to custom ogg format or something, hcs makes a great tool called ww2ogg)
## Post #3
- Username: montcer9012
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Jul 14, 2012 2:14 pm
- Post datetime: 2012-07-31T23:07:37+00:00
- Post Title: Where dialogue/sfx from Batman Arkham City are located?

But once you located the files there is something more important missing; the packer to repack modified files.
## Post #4
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2012-08-02T15:26:33+00:00
- Post Title: Where dialogue/sfx from Batman Arkham City are located?

Not everything is free. get a wwise sdk. and they also might have checks in place like most major AAA games to prevent modified files from loading.
