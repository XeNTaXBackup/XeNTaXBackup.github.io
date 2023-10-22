## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-08T18:21:31+00:00
- Post Title: Touhou Maihana

Damn per-face UV's 
Have to get those in before I can texture it properly.

Uses .geo format same as croixleur. This plugin should be better than the one I wrote for the other game. Or it might be a different version of the format; don't have the other game on me to check.
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-26T01:00:53+00:00
- Post Title: Touhou Maihana

Alright imm mode down, textures in.
## Post #3
- Username: anime663
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Jun 04, 2012 8:45 am
- Post datetime: 2012-10-03T18:51:26+00:00
- Post Title: Touhou Maihana

How did you extract the .vol files?
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-10-03T20:26:15+00:00
- Post Title: Touhou Maihana

```

startfunction unpack_vol

  get FILES long
  for i = 0 < FILES
    get OFFSET long
    get SIZE long
    putarray 0 i OFFSET
    putarray 1 i SIZE
  next i

  for i = 0 < FILES
    getarray OFFSET 0 i
    getarray SIZE 1 i
    goto OFFSET
    if SIZE > 0
      getdstring NAME 32
      getdstring EXT 8
      string NAME += EXT
      savepos OFFSET
      log NAME OFFSET SIZE
    endif
  next i
endfunction

callfunction unpack_vol

```


Not correct but it does the job.
## Post #5
- Username: anime663
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Jun 04, 2012 8:45 am
- Post datetime: 2012-10-03T20:52:19+00:00
- Post Title: Touhou Maihana

How do I get it to work? Sorry I'm not exactly the best at scripts and things like that.
## Post #6
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-10-03T22:45:44+00:00
- Post Title: Touhou Maihana

Use it with quickbms [http://aluigi.altervista.org/quickbms.htm](http://aluigi.altervista.org/quickbms.htm)
## Post #7
- Username: anime663
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Jun 04, 2012 8:45 am
- Post datetime: 2012-10-03T22:51:58+00:00
- Post Title: Touhou Maihana

thank you ^^
