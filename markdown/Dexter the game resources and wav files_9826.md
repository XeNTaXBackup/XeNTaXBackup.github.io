## Post #1
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2012-11-03T17:35:03+00:00
- Post Title: Dexter the game resources and wav files

I've been looking through the game files and there is only one archive, a .ifs file.
for audio there are wav files that no program can open and yet the game renders correctly. any idea why?
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2012-11-03T17:57:04+00:00
- Post Title: Dexter the game resources and wav files

> Reply from Devilot
>
> for audio there are wav files that no program can open and yet the game renders correctly. any idea why?

you have 160+ posts and you ask this question? containers and formats vary for almost everything
## Post #3
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2012-11-03T18:50:49+00:00
- Post Title: Dexter the game resources and wav files

the extension is only one. I wonder if there is a special header that I cannot identify. Mediainfo does not help, and even soundforge cannot open it,
## Post #4
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2012-11-04T09:31:48+00:00
- Post Title: Dexter the game resources and wav files

The extension is worthless indicator and simple header check would have told you why all tools failed, it is entirely game engine custom, not an true wav at all.
Due to header being all custom nonsense at start and end of file being extremely unhelpful and raw pcm listening has notable distortion which seems to suggest potentially some form of ADPCM encoding but unknown which one it is.
## Post #5
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2012-11-04T11:50:30+00:00
- Post Title: Dexter the game resources and wav files

so how can I open them?
## Post #6
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2012-11-05T08:16:05+00:00
- Post Title: Dexter the game resources and wav files

if I said the encoding type is unknown, I don't have decoding/opening solution obviously unless you like static mess sound...  
Someone else may crack it or not but as a format its a total mess with inconsistent header sizes and doubt I work trying figure it out besides this initial look, sorry.
