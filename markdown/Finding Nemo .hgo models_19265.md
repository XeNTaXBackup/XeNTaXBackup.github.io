## Post #1
- Username: MegaSpeedXtreme
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Jun 14, 2018 7:58 am
- Post datetime: 2019-01-04T23:37:50+00:00
- Post Title: Finding Nemo *.hgo models

hi, i been not be able to get access into finding nemo *.hgo model files. the thing is i can't find everything and also the bone structures, so i need help with this because it's too hard so if anyone can get access into these *.hgo model files for finding nemo model files and find it's vertices, faces and bones that was been rigged by ages ago when it was released. the thing is there a header and a idstring and i don't know what the others are so can someone get access into this file format please because i been struggling with this file format. if ony there was a hgo import to get access to these files in 3ds max 
[diver and nigel.zip](https://xentaxbackup.github.io/file/15415_diver and nigel.zip)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-01-05T17:24:16+00:00
- Post Title: Finding Nemo *.hgo models

"bone structure", well, yeah, maybe start with the vertices first which look a little bit strange to me:



Nigel_upps.png (19.06 KiB) Viewed 89 times
## Post #3
- Username: MegaSpeedXtreme
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Jun 14, 2018 7:58 am
- Post datetime: 2019-06-14T14:35:31+00:00
- Post Title: Finding Nemo *.hgo models

ok, i might have to start this again.

```

Struct FindingNemoChars
(
	fileid= "",
	filesize,
	idstring = ""
)

fn ReadFixedString bstream fixedLen =
(
   local str = ""
   for i = 1 to fixedLen do
   (
	  str0 = ReadByte bstream #unsigned
	  str+= bit.intAsChar str0
   )
   str
)

fn filesize =
(
	
)
	

global fname = getOpenFileName \ 
caption:"Open Model" \
types:"Finding Nemo Char Models (*.*)|*.*|*.*|*.*" \
historyCategory:"char for hgo"
global st = timestamp() --get start time in milliseconds

global f = fopen fname "rb"
global filename = GetFilenameFile fname
global filepath = getFileNamePath fname
global filetype = getFilenameType fname

GC()
FClose f
EnableSceneRedraw()

Print ("Done! ("+((((timestamp())-st)*0.001)as string)+" Seconds)")
```


now the problem is, now how do i ignore the whitespace where it says 20 20 20 20 20 20 because i can't ignore the whitespace for some reason i don't know what the fn or the function called to get all the way to start to the end, i haven't written the whole entire structure because i don't know what's next after LBTN, it's like this file format is really confusing.

because on 0x4 it says the filesize for the 34 bit integer on readlong, so on 0x0 it starts with 0 and then you have to ignore the whitespace at the end of the file format and i don't know what that is called for fn or function.
## Post #4
- Username: MegaSpeedXtreme
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Jun 14, 2018 7:58 am
- Post datetime: 2019-06-15T06:43:00+00:00
- Post Title: Finding Nemo *.hgo models

i thought you were very helpful, but it turns out you are not helping out and not giving much information about *.hgo models import and all there structure and not releasing the *.hgo import script to get access all the models in maxscript. i asked how do i ignore whitespace and you standed there doing nothing. you just made me upset now, go away i don't want to talk to you anymore.
## Post #5
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2019-06-16T17:55:12+00:00
- Post Title: Finding Nemo *.hgo models

Grow up will ya?
## Post #6
- Username: MegaSpeedXtreme
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Jun 14, 2018 7:58 am
- Post datetime: 2019-06-16T20:49:48+00:00
- Post Title: Finding Nemo *.hgo models

i am, all i want is a *.hgo import in maxscript that can access all the *.hgo import in finding nemo model files. like anemone.hgo, angelfsh.hgo, angler.hgo, BigClam.hgo, biggrey.hgo, blenny.hgo, bloat.hgo, BlueFish.hgo, bones.hgo, Bruce.hgo, bubble.hgo, bubbles.hgo, nemo.hgo, dory.hgo etc. which i been asking, if somebody can release the *.hgo import maxscript i would able get access into every files and save it into a *.fbx file format. like there rigged models.
