## Post #1
- Username: Blasturbator
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Dec 06, 2013 4:12 am
- Post datetime: 2013-12-07T03:32:26+00:00
- Post Title: A small DOS query

If i were using the FOR command in DOS where 

```
FOR [drive:\][directory] %variable IN (set) DO command [command-parameters]
```

What would i put in (set) to make it use folders? (directories if you want to be picky )

Currently I'm doing 

```
for %%b in (*.partsbnd) do
```

And this does all files with the format .partsbnd, how would i go about making that set apply to whole folders as opposed to specific file type sets.
## Post #2
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2013-12-19T14:05:26+00:00
- Post Title: A small DOS query

FOR /F "tokens=*" %%G IN ('dir /B /S /A-D') DO whatever.exe "%%G"
Where the /S option means recursive, and /A-D makes it not pass dir names to whatever.exe.
## Post #3
- Username: Darkstar
- Rank: advanced
- Number of posts: 67
- Joined date: Thu Jun 14, 2007 8:14 pm
- Post datetime: 2013-12-19T18:48:12+00:00
- Post Title: A small DOS query

I wonder what this has to do with DOS, DOS didn't have that feature in its FOR implementation...
