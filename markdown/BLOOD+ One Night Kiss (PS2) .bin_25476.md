## Post #1
- Username: techtechi
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Mar 26, 2022 10:08 am
- Post datetime: 2022-06-01T19:57:59+00:00
- Post Title: BLOOD+ One Night Kiss (PS2) .bin

can't find any quickbms script to unpack these files, any help? Samples: [https://www.mediafire.com/file/vusootlh ... s.zip/file](https://www.mediafire.com/file/vusootlh24am97x/BLOOD++One+Night+Kiss+bin+files.zip/file)
## Post #2
- Username: techtechi
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-06-01T21:54:25+00:00
- Post Title: BLOOD+ One Night Kiss (PS2) .bin

Hi, here is the file format [http://wiki.xentax.com/index.php/BLOOD% ... t_Kiss_BIN](http://wiki.xentax.com/index.php/BLOOD%2B_One_Night_Kiss_BIN)

and here is my quickbms script to unpack data:
[https://github.com/bartlomiejduda/Tools ... script.bms](https://github.com/bartlomiejduda/Tools/blob/master/NEW%20Tools/BLOOD%2B%20One%20Night%20Kiss/Blood_One_Night_Kiss_BIN_script.bms)
## Post #3
- Username: Rabatini
- Rank: veteran
- Number of posts: 97
- Joined date: Tue Nov 22, 2016 8:13 pm
- Post datetime: 2022-06-01T22:12:20+00:00
- Post Title: BLOOD+ One Night Kiss (PS2) .bin

```
# BLOOD+ One Night Kiss - PS2 (.BIN)
# Version 0.1b

idstring "LF 2"
get unknown long
get entries long
get pointer_table long
get name string
savepos name_table
goto pointer_table
for rip = 1 to entries

	get offset long
	xmath offset "(offset * 0x800)"
	get size long
	savepos table
	log name offset size
	goto name_table
	get name string
	savepos name_table
	goto table

next rip
```
## Post #4
- Username: Rabatini
- Rank: veteran
- Number of posts: 97
- Joined date: Tue Nov 22, 2016 8:13 pm
- Post datetime: 2022-06-01T22:15:09+00:00
- Post Title: BLOOD+ One Night Kiss (PS2) .bin

ohh, ikskoks.
already did it...
