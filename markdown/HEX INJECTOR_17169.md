## Post #1
- Username: halfway
- Rank: beginner
- Number of posts: 27
- Joined date: Thu Aug 24, 2017 1:50 pm
- Post datetime: 2017-10-21T03:19:07+00:00
- Post Title: HEX INJECTOR

guys, i need to inject some byte's to a big file with a hex address
need a tool or patch. who can help me?
## Post #2
- Username: Acewell
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2017-10-21T11:57:24+00:00
- Post Title: HEX INJECTOR

I can help you. I have written simple script for that a while ago.


 HEX_INSERTER.zip
(873 Bytes) Downloaded 34 times



Just specify valid values at the end of the script and then run it to REPLACE hex values.
But if you want to INSERT hex values, first you have to insert "00" values by hex editor (In hex workshop you can do it massivly with a few clicks)
and then replace zero values with your bytes.

One more thing, in my tool bytes are inserted after they are read from file (dds texture in my example),
so you need to keep your bytes as a file to insert them correctly.

Also, I don't guarantee that my tool will work in your case. You can easily mess up things if you deal with hex values.
