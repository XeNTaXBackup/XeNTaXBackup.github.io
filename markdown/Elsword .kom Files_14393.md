## Post #1
- Username: eternaldreamz
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed May 25, 2016 9:19 am
- Post datetime: 2016-05-25T01:34:54+00:00
- Post Title: Elsword .kom Files

I'm not exactly the most savvy person when it comes to encryption or scripts, so I'm wondering if anyone here could help.

Me and a bunch of other people run a wiki for the MMO called Elsword (more specifically the Korean version, as the script still works fine for other versions which are sadly less up to date).
We used quickbms and a by now fairly old script to extract images and the like from these files so we could use them for wiki purposes. This script has stopped working about 2 weeks ago after a patch changed the encryption of the files.

Could anyone help in updating the script?

A sample .kom file and the previously working script can be found here:
[https://www.mediafire.com/?i8q752g9tb7cjrh](https://www.mediafire.com/?i8q752g9tb7cjrh)

Thanks in advance!
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2016-05-26T11:21:28+00:00
- Post Title: Elsword .kom Files

[http://aluigi.altervista.org/bms/kom.bms](http://aluigi.altervista.org/bms/kom.bms)
## Post #3
- Username: eternaldreamz
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed May 25, 2016 9:19 am
- Post datetime: 2016-05-26T21:49:58+00:00
- Post Title: Elsword .kom Files

While that script is indeed more up to date, it still is unable to extract the korean Elsword .kom files properly.

The offset is wrong and while it extracts file names, it does not produce readable file formats.

For example, the file "ComboTree.lua" is extracted as "ComboTree.lu.algo3.114160", and the script shows the error "unknown algorithm 3 at offset 0x0005ffa1 (10696 ->114160)"

Well, at least we can read the file names already now, so it's a start!

It should be noted that certain file types, such as XML and XET are still extractable no problem....too bad there's nothing of useable info in them.
