## Post #1
- Username: junk angel
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Jan 14, 2010 11:38 pm
- Post datetime: 2011-04-17T16:58:28+00:00
- Post Title: Combat Arms LTB

Hello, I've recently been trying to decompile models from Combat arms (a lithtech talon based game). I seem to be able to get quite far, actually getting a working model into max. 
Sadly one of the steps I have to use completely removes the UVW coords. The thing is, I have to move the model from and to the LTB format as it is. As there's a tool
[http://www.cote-duke.narod.ru/LTB2X.html](http://www.cote-duke.narod.ru/LTB2X.html)  which converts the LTB to X. But it can't load the cobat arms one, so one has to convert to LTA (ascii based talon format) and then back to LTB with AVP tools. But apparently the LTB>LTA conversion strips the coords. 

Could someone take a look at these two.
[http://dl.dropbox.com/u/6252145/MEI_BODY.ltb](http://dl.dropbox.com/u/6252145/MEI_BODY.ltb)
and 
[http://dl.dropbox.com/u/6252145/working.ltb](http://dl.dropbox.com/u/6252145/working.ltb)
to see if perhaps there's only a small hex change needed to get the LTB2X tool to be able to read them?
## Post #2
- Username: junk angel
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Jan 14, 2010 11:38 pm
- Post datetime: 2011-04-23T23:16:27+00:00
- Post Title: Combat Arms LTB

Well looks like manual unwrapping then
