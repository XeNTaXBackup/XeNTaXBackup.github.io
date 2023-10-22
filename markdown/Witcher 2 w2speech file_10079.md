## Post #1
- Username: tomatofarmer
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu May 17, 2012 7:54 pm
- Post datetime: 2013-01-25T11:03:13+00:00
- Post Title: Witcher 2 w2speech file

The w2speech files contain localized dialogue. It would be great to be able to extract a specific dialogue for use in mods (like the Witcher 2 experience in Skyrim).

Does anyone know what format the audio is stored? 

(updates)

I think it's MPEG layer 2 @ 48000 (or at least it can be decoded as that). There are at least 21,568 individual samples in there.

A voice over (VO) in the game is referenced as:

VO_<1>_<2>_<3>

1 = id of voice tag
2 = ??? set or scene # ???
3 = line number

example:
VO_TRIS_300202_0343 (from q104_triss_interaction_oneliner.w2scene)
1 = Triss
2 = ??? (all voice overs in a scene usually have the same number e.g. 300202)
3 = Line_343

I'm having a hard time figuring out where that second number is stored. In scenes,it appears to be a set of related dialogues but I can't find a corresponding entry in the w2strings file. I also can't seem to find a reference for non-scene voice overs (like background chatter in a town). 

I think I'm missing a mapping index that joins the two. It's possibly embedded in the w2speech file - there's about another 120MB or so that is unaccounted for. Any ideas/help?

Is anyone participating in the RedKit beta that could share some light?
## Post #2
- Username: micTronic
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Dec 16, 2020 6:28 am
- Post datetime: 2021-12-06T08:14:54+00:00
- Post Title: Witcher 2 w2speech file

Sorry to necro this topic, but there is little information available on w2speech files out there, and I'd really love to extract some of the voiceovers.

@tomatofarmer, did you by any chance manage to learn more about the file format of w2speech files? The header is still not clear to me, but I'm not an MP3 expert, so I'm not sure how to find the individual samples inside these large files...

Or maybe anyone else is aware of a tool that has been released in the meantime which might do the job? gibbed RED tools don't seem to be able to. There are tools for the successor's w3speech, but the format appears to be entirely different.
## Post #3
- Username: micTronic
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Dec 16, 2020 6:28 am
- Post datetime: 2021-12-07T17:01:35+00:00
- Post Title: Witcher 2 w2speech file

Back to answer my own question...

After some experimentation, it seems that REDkit will actually extract all speech right after being installed. Easy enough
## Post #4
- Username: nikich340
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Dec 06, 2021 11:16 am
- Post datetime: 2021-12-09T02:41:37+00:00
- Post Title: Witcher 2 w2speech file

It only contains already extracted samples. You still can't extract, for example, russian w2speech.
## Post #5
- Username: micTronic
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Dec 16, 2020 6:28 am
- Post datetime: 2022-03-17T10:33:37+00:00
- Post Title: Witcher 2 w2speech file

In Steam, just change your language to the one you wish to extract.
Then start the editor, or run the command

```
"<YourSteamLibrary>\steamapps\common\the witcher 2\bin\editor.exe" exportstrings exportvo
```

(this is what it does on first start anyway). It will extract whichever language you have selected.
