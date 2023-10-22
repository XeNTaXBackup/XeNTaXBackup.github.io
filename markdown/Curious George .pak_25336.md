## Post #1
- Username: emanuelect
- Rank: n00b
- Number of posts: 16
- Joined date: Sat Oct 16, 2021 9:34 pm
- Post datetime: 2022-05-09T20:56:37+00:00
- Post Title: Curious George .pak

Can you create a script to extract the files from this .pak, I would like to translate the game.
[https://mega.nz/file/etRDRKqY#6PQY3p7ql ... hYz1yC-aX8](https://mega.nz/file/etRDRKqY#6PQY3p7qlUmaSwAI8-uQxNOiEm-iWXwMLhYz1yC-aX8)
[curious.png](https://xentaxbackup.github.io/file/22204_curious.png)
## Post #2
- Username: Rabatini
- Rank: veteran
- Number of posts: 97
- Joined date: Tue Nov 22, 2016 8:13 pm
- Post datetime: 2022-05-10T01:57:06+00:00
- Post Title: Curious George .pak

try this

```
get null long
get name string 
get unknown longlong
for rip = 1 to entries

get offset long
get size long
getdstring name 0x28

log name offset size
next rip
```
## Post #3
- Username: emanuelect
- Rank: n00b
- Number of posts: 16
- Joined date: Sat Oct 16, 2021 9:34 pm
- Post datetime: 2022-05-10T21:03:21+00:00
- Post Title: Curious George .pak

Thank you, the script works, but unfortunately the files of the pc version, are not compatible with those ps2. I wanted to extract the files from the ps2 version and insert them in the pc version, as i did with other games, but this time it was not possible.
