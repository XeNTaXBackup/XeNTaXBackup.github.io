## Post #1
- Username: Kpridwen
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Jun 06, 2010 10:04 pm
- Post datetime: 2010-06-06T15:24:30+00:00
- Post Title: camon hero .bfd

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: XpoZed
- Rank: veteran
- Number of posts: 144
- Joined date: Sun Oct 25, 2009 12:08 am
- Post datetime: 2010-06-06T17:34:11+00:00
- Post Title: camon hero .bfd

Here's the file structure :

```
	?header[4b] {
		0x00000000
	}
	files_in_archive[4b] {
		0x00000038
	}
	structure {
		row[0] {
			begin_of_file[4b]{
				0x00001DC8
			}
			size_of_file[4b]{
				0x000002F6
			}
			file_name[112b] {
				LVUP1.TXT // UNICODE!
			}
		}
		...
		row[n] {
			...
		}
	}
	data {
		...
	}
}
```


P.S.
These TXT's are actualy UTF-16  encoded, so keep that in mind.
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-06-06T20:47:56+00:00
- Post Title: camon hero .bfd

script for quickbms:

```
get FILES long
for i = 0 < FILES
    get OFFSET long
    get SIZE long
    getdstring NAME 0x80
    set NAME unicode NAME
    log NAME OFFSET SIZE
next i
```
## Post #4
- Username: Kpridwen
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Jun 06, 2010 10:04 pm
- Post datetime: 2010-06-06T22:50:29+00:00
- Post Title: camon hero .bfd

The contents of this post was deleted because of possible forum rules violation.
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-06-07T10:34:03+00:00
- Post Title: camon hero .bfd

eh? are you joking or what?
## Post #6
- Username: Kpridwen
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Jun 06, 2010 10:04 pm
- Post datetime: 2010-06-07T11:29:59+00:00
- Post Title: camon hero .bfd

i'm sry for my noobish reply but hey i'm an ultra noob, i've searched whats bms and i've understood your script sry for the trouble, gess i've replyed a litle too fast
## Post #7
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-06-07T11:59:30+00:00
- Post Title: camon hero .bfd

ah ok, I thought you had just not seen my reply at all.
anyway yeah probably I needed to specify the url of quickbms as I did ever in the past although luckily it's the first result on google:
[http://aluigi.org/papers.htm#quickbms](http://aluigi.org/papers.htm#quickbms)
## Post #8
- Username: Kpridwen
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Jun 06, 2010 10:04 pm
- Post datetime: 2010-07-09T09:22:11+00:00
- Post Title: camon hero .bfd

so that game is kind of dead, just like its korean version did, so i'm developing a translation pack for the japanese version, and it would be much easier with a compiler to .bfd.how can i do it?
## Post #9
- Username: Kpridwen
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Jun 06, 2010 10:04 pm
- Post datetime: 2010-07-28T10:27:41+00:00
- Post Title: camon hero .bfd

any1? can any1 point me a good editor for this files, cuze i'm using notepad to edit the encripted files, but it takes ages
