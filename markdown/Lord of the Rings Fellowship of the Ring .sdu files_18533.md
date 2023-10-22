## Post #1
- Username: Puterboy1
- Rank: mega-veteran
- Number of posts: 204
- Joined date: Fri Mar 02, 2018 10:05 am
- Post datetime: 2018-08-02T02:55:34+00:00
- Post Title: Lord of the Rings: Fellowship of the Ring .sdu files

Can anyone help me extract these?: [https://drive.google.com/open?id=1sVkba ... pcVBM7JA3q](https://drive.google.com/open?id=1sVkbaRM-jTVU0xcAdobklEpcVBM7JA3q)
## Post #2
- Username: Pingu
- Rank: veteran
- Number of posts: 116
- Joined date: Sat Apr 16, 2016 10:15 am
- Post datetime: 2018-08-02T05:08:44+00:00
- Post Title: Lord of the Rings: Fellowship of the Ring .sdu files

The format is just headerless VAG files with names strung together. You have two options:

- Wait until someone writes a script to support it. Here's the format for it, I'm just lazy to write BMS to support it (For anyone who wants to implement BMS for this):

```
goto 0x10

for each loop while The current position != end of file:
uint16- name length
name string name length
uint16- reference name size
string - reference name (length = uint16 prior)
seek 0x4c to size.
uint32 - size

```


From here is hard to implement the proper offset. To do so, seek through bytes until they don't equal 0. Change position by -1, and then by -0x10 to get the proper offset. Save that position Log. Then seek the size of the file to get to the next entry. Or manually set a file count (in this case 0xFDD).


Or simply run this file through PSound as it's headerless VAG. Maybe I'll write a tool to handle this more clearly in the future.
