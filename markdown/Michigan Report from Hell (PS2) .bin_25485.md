## Post #1
- Username: techtechi
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Mar 26, 2022 10:08 am
- Post datetime: 2022-06-04T01:29:16+00:00
- Post Title: Michigan: Report from Hell (PS2) .bin

This game isn't like BLOOD+'s  bin format, any quickbms scripts that work for this game? Thanks! Samples: [https://www.mediafire.com/file/r8s8vcpx ... s.zip/file](https://www.mediafire.com/file/r8s8vcpx6whz7kj/Michigan+Report+from+Hell+bin+ps2+samples.zip/file)
## Post #2
- Username: Rabatini
- Rank: veteran
- Number of posts: 97
- Joined date: Tue Nov 22, 2016 8:13 pm
- Post datetime: 2022-06-04T02:01:30+00:00
- Post Title: Michigan: Report from Hell (PS2) .bin

Try this:

```
get ENTRIES short
for RIP = 1 to ENTRIES
get OFFSET long
Xmath OFFSET "(OFFSET * 0X800)"
get SIZE long
log "" OFFSET SIZE
next RIP

```


Will extract a lot of file .dat files 
and some of theses files will have another container.

you should extract with this.

```
for RIP = 1 to ENTRIES
get OFFSET long
get Size long
log "" offset size
next RIP
```
