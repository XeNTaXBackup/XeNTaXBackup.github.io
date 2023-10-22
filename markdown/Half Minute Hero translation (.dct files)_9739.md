## Post #1
- Username: TheReaperCooL
- Rank: advanced
- Number of posts: 60
- Joined date: Sun Apr 18, 2010 3:18 am
- Post datetime: 2012-10-14T20:58:10+00:00
- Post Title: Half Minute Hero translation (.dct files)

Hello there!

I'm not making this as a duplicate topic, I just want to ask my question here, too, so that maybe someone can help me.

Half Minute Hero just came out on PC, and I thought I'd translate the game. I went through the files (which are stored in appropriately named folders), and found out that the text files are in the cscv folders. They are .dct files.

A guy, namely WRS helped me a bit in extracting the file's contents, but his script gave me an error, and it only cut off the beginning of the file, not extracting text from it. Here is his script:

```

do
  getdstring name 24
  getdstring ext 4
  get size long
  savepos pos
  string fname f= "%s.%s" name ext
  log fname pos size
  math pos += size
  goto pos
while pos < size
```


This gave me an "Invalid operator f" error, so I changed it a bit (I know nothing about these), and deleted the "f=" part in it. This is how it extracted the stuff I talked earlier.

Is it possible to extract the text from the files, write whatever I want to, then import them back in?

I can provide you the first stage's file, which is roughly 519 kbyte, IF I can upload and post it here, that is.
## Post #2
- Username: swuforce
- Rank: veteran
- Number of posts: 121
- Joined date: Fri Nov 06, 2009 3:46 am
- Post datetime: 2012-10-15T09:10:30+00:00
- Post Title: Half Minute Hero translation (.dct files)

i modified the script a little bit. try

```

do
  getdstring name 24
  getdstring ext 4
  get size long
  savepos pos
  string name += "."
  string name += ext
  log name pos size
  math pos += size
  goto pos
while pos < asize
```
## Post #3
- Username: TheReaperCooL
- Rank: advanced
- Number of posts: 60
- Joined date: Sun Apr 18, 2010 3:18 am
- Post datetime: 2012-10-15T19:35:09+00:00
- Post Title: Half Minute Hero translation (.dct files)

Thanks, now it works, and extracts lots of .dat files, like it splits the file and renames them according to what the .dct had inside.

How can I get the text out of these files (or modify the length of the text for instance, so that I can write more stuff in it), and how can I import the .dat's back into the .dct?
