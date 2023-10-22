## Post #1
- Username: Internetakias
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Jul 13, 2013 11:20 am
- Post datetime: 2016-10-18T13:53:19+00:00
- Post Title: Chase: Cold Case Investigations .PAC files

Hello, I'm looking for a way to automate extracting Chase's pac files. I tried writing a BMS script myself since the format is really straightforward, but it didn't work since I lack experience.
Anyway, here's a breakdown of the format, particularly the header:

PS:The files are all bunched up together with no separation, so after a file ends, another one begins with the next offset. Also, that 30 in offset 10 coincidentally happens to be the offset of the first entry in the table of contents (Which is the "L" in L2DM in my picture.)
## Post #2
- Username: Internetakias
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Jul 13, 2013 11:20 am
- Post datetime: 2016-10-18T13:56:26+00:00
- Post Title: Chase: Cold Case Investigations .PAC files

And here's the file that was used in the picture
[http://www43.zippyshare.com/v/b8Z328tE/file.html](http://www43.zippyshare.com/v/b8Z328tE/file.html)
## Post #3
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2016-10-18T22:20:18+00:00
- Post Title: Chase: Cold Case Investigations .PAC files

This should work:

```
get DUMMY long
get DUMMY long
get FILE_COUNT long
goto 0x30

for i = 0 < FILE_COUNT
    getdstring FORMAT_IDENTIFIER 4
    get DUMMY long
    get SIZE long
    get OFFSET long
    getdstring NAME 0x80
    log NAME OFFSET SIZE
next i
```

Here you can look up what each command does:
[http://aluigi.altervista.org/papers/quickbms.txt](http://aluigi.altervista.org/papers/quickbms.txt)

By the way, I think that 0x90 is not a terminator but the size of the subheader.
I skipped all the unknown bytes either with "get DUMMY long" or with the goto command.
## Post #4
- Username: Internetakias
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Jul 13, 2013 11:20 am
- Post datetime: 2016-10-18T22:38:04+00:00
- Post Title: Chase: Cold Case Investigations .PAC files

Thanks and nice catch.
