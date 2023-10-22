## Post #1
- Username: GordenF
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Jul 16, 2016 6:14 am
- Post datetime: 2020-05-07T15:45:15+00:00
- Post Title: Extracting an N-Gage 2.0 file (Metal Gear Solid Mobile)

Once again I find myself trying to get at files inside an obscure file format that apparently no one else has bothered with.
This time it's Metal Gear Solid Mobile for the N-Gage 2.0 platform for Symbian S60v3 phones.
Finding the game on the internet took me a good while because most of the sites that dealt in games back then have since gone under. Luckily, the folks at the Internet Archive had a collection of N-Gage 2.0 games.

The specific file I have here is an .n-gage file that looks like this in HxD:


This looked like email attachments to me, so I used Python to split the file up:

```

with open("Metal.Gear.Solid.Mobile.n-gage", "rb") as mgs:
	mgsb = mgs.read()

parser = BytesParser()
m = parser.parsebytes(mgsb)

c = 0
for p in m.get_payload():
	with open(f"mgs{c}.bin", "wb") as bin:
		bin.write(p.as_bytes())
	c+=1
```


mgs0.bin seems to be just the N-Gage 2.0 manifest XML.
mgs1.bin seems to be metadata. I'm not sure what kind, since most of the file is just random junk.
There are several PNGs in there, but Photoshop throws the error message "PNG file corrupted by ASCII conversion" for every file I copy out of there.
It'd be great if anyone knew how to fix that, but since it's not what I'm after, /shrugs
mgs2.bin should be the actual game file, as promised by its first few bytes: 
```
Content-ID: <Game>
```

(The "<Game>" is not a placeholder, it's in there, angled brackets and all)

The problem I have is that I can't find the SIS file in there.
I don't need to parse the file itself, that's what SISXplore is for, but I need to be able to identify it in this sea of garbage in order to extract it.
Here's a writeup on the SIS format as of S60v5: [https://sites.google.com/site/i8910wiza ... -sis-files](https://sites.google.com/site/i8910wizard/symbian-s60v5-learningcenter/what-are-sis-files)
It's possible that I can't find it because of a difference between S60v3 and S60v5 SIS files, but this documentation is all I could find.

Has anyone here worked with Symbian files before and could help me with this?
