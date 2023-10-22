## Post #1
- Username: MaxR84
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Mar 27, 2011 5:30 pm
- Post datetime: 2011-03-27T09:37:26+00:00
- Post Title: Stonekeep pc game - Looking for Tips (and eventually Tools)

Dear all,
I've ever wanted to translate Stonekeep in my language but I've never found the text files, so, I've also asked to different Interplay's personalities without finding someting useful. Do someone knows how to reach those files and how to edit them?
Under data directory there are some group# files without extension.
Thank you in advance!
## Post #2
- Username: MaxR84
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Mar 27, 2011 5:30 pm
- Post datetime: 2011-04-05T20:03:18+00:00
- Post Title: Stonekeep pc game - Looking for Tips (and eventually Tools)

Up!
## Post #3
- Username: MaxR84
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Mar 27, 2011 5:30 pm
- Post datetime: 2012-05-02T10:31:47+00:00
- Post Title: Stonekeep pc game - Looking for Tips (and eventually Tools)

Up!
Please, I need help
## Post #4
- Username: Delacroix
- Rank: advanced
- Number of posts: 70
- Joined date: Thu Sep 15, 2011 9:12 pm
- Post datetime: 2012-05-05T13:16:03+00:00
- Post Title: Stonekeep pc game - Looking for Tips (and eventually Tools)

I support this as I myself am interested. Please advise.
## Post #5
- Username: MaxR84
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Mar 27, 2011 5:30 pm
- Post datetime: 2012-05-05T19:34:46+00:00
- Post Title: Stonekeep pc game - Looking for Tips (and eventually Tools)

Thank you my friend. I'm waiting for a response from the admins
## Post #6
- Username: MaxR84
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Mar 27, 2011 5:30 pm
- Post datetime: 2012-08-10T13:34:03+00:00
- Post Title: Stonekeep pc game - Looking for Tips (and eventually Tools)

Up! Still need help
## Post #7
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2012-08-15T19:39:25+00:00
- Post Title: Stonekeep pc game - Looking for Tips (and eventually Tools)

completely untested. based off source from sau-0.2

```
get nfiles short

# -- files
for f = 0 < nfiles
  getdstring Name 14
  get Off long
  get U1 long
  putarray 0 f Off
next f

goto 2
math nfiles -= 1 # the last file entry just stores eof apparently

for f = 0 < nfiles
  getdstring Name 14
  get Off long
  get U1 long
  math ff = f
  math ff += 1
  getarray Size 0 ff
  math Size -= Off
  log Name Off Size
next f

```

edit

the project also includes some code for the graphics/sprites. here is the source for anyone looking it up: [http://pastebin.com/WrzmvWbV](http://pastebin.com/WrzmvWbV)
## Post #8
- Username: MaxR84
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Mar 27, 2011 5:30 pm
- Post datetime: 2012-08-17T09:33:05+00:00
- Post Title: Stonekeep pc game - Looking for Tips (and eventually Tools)

Thank you for the help, friend. I'm sorry to say that I'm new to this kind of things and I don't know what I must do 
If I've understood well, sau is a package of uncompiled tools for Linux, right? What must I do to gain access to Group files?
## Post #9
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2012-08-17T17:45:12+00:00
- Post Title: Stonekeep pc game - Looking for Tips (and eventually Tools)

the code i posted it a bms script - to run it on your file, you need quickbms which you can get here: [http://aluigi.altervista.org/quickbms.htm](http://aluigi.altervista.org/quickbms.htm)

ive already forgotten about the other source i posted, but its c code which might be useful to convert the graphics for viewing
## Post #10
- Username: MaxR84
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Mar 27, 2011 5:30 pm
- Post datetime: 2012-08-17T18:19:23+00:00
- Post Title: Stonekeep pc game - Looking for Tips (and eventually Tools)

Probably I owe you a drink
