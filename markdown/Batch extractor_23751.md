## Post #1
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2021-04-16T08:46:45+00:00
- Post Title: Batch extractor

Hi, I got all .segm from B2S files
Now I want extract them, is there a way to do it with a sort of .Bat file? I want  convert all them in one click
I tried creating a .bat file myself but no luck
here what I wrote:

> @echo off
>
> 
>
> b2s_DC.exe C:\Users\zagor\Desktop\TrueAncestor_EDAT_Rebuilder_v1.65\*.segm
>
> 
>
> echo done!

Thank you in advance
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-04-16T10:12:44+00:00
- Post Title: Batch extractor

Use something like these lines
@echo off
for %%f in (*.segm) do b2s_DC.exe %%f

in a .bat or .cmd file.

If you execute it in the *.segm folder there should be no worries with path names assumed the exe to be in said path.
Else try for %%f in (C:\Users\zagor\Desktop\TrueAncestor_EDAT_Rebuilder_v1.65\*.segm) do b2s_DC.exe %%f

(Couldn't test this so don't blame me.)
## Post #3
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2021-04-16T10:57:18+00:00
- Post Title: Batch extractor

> Reply from shakotay2 ↑Fri Apr 16, 2021 6:12 pm at Fri Apr 16, 2021 6:12 pm
>
> 
Use something like these lines
@echo off
for %%f in (*.segm) do b2s_DC.exe %%f

in a .bat or .cmd file.

If you execute it in the *.segm folder there should be no worries with path names assumed the exe to be in said path.
Else try for %%f in (C:\Users\zagor\Desktop\TrueAncestor_EDAT_Rebuilder_v1.65\*.segm) do b2s_DC.exe %%f

(Couldn't test this so don't blame me.)

Oh God! It worked perfectly! Thank You very much||
