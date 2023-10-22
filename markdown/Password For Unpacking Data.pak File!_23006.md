## Post #1
- Username: brispuss
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue May 28, 2019 11:34 am
- Post datetime: 2020-11-15T01:50:46+00:00
- Post Title: Password For Unpacking Data.pak File!??

I've been trying to unpack a data.pak file from the game [Mystery Case Files - Broken Hour Collector's Edition](https://www.bigfishgames.com/games/11539/mystery-case-files-broken-hour-ce/?pc%22).

I've examined the game data.pak file and it appears to be a password protected zip file (xPK\x03\x04\ . . ). I've tried using a debugger and other tools but I've had no success in finding the password for this data.pak file!

Can anyone find the password for this file please? And if possible mention how the password was obtained (detailed instructions on password recovery would be most helpful!)

Thank you!

EDIT: the data.pak file is 733 MB in size!
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-11-15T14:33:53+00:00
- Post Title: Password For Unpacking Data.pak File!??

Password is 

```
7VtaFesmATpMwtiL7Q79nzOyx2mNzypYmwPR39LY55AuhGxrOcLvCy2SnQje
```


and here you have detailed tutorial how to recover it yourself
[https://zenhax.com/viewtopic.php?f=4&t=59](https://zenhax.com/viewtopic.php?f=4&t=59)
## Post #3
- Username: brispuss
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue May 28, 2019 11:34 am
- Post datetime: 2020-11-15T19:59:38+00:00
- Post Title: Password For Unpacking Data.pak File!??

Thank you very much for your prompt reply and for the password!!

Actually I did follow that tutorial at Zenhax, but I might have done something wrong(?) as the debugger didn't come up with a password!?

According to the results of "scanning" the game with the file data.pak, the results didn't quite come up with what was expected, so it was not clear where to set the debugger breakpoint at. Also, I believe there was a Is a Debugger Present call in the game's executable, so I had to hide the debugger using a plugin. This hiding of the debugger procedure was not mentioned in the tutorial at Zenhax. So I had to "wing it" to try to run the debugger and to try to find the password, but it didn't work out for me.

Thanks again!!
## Post #4
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-11-15T20:31:46+00:00
- Post Title: Password For Unpacking Data.pak File!??

If you have troubles, I may have few tips for you:

1. You could find a DRM-Free version of the game. It is always more simple to debug games which don't have any protection checks.
2. You could run Signsrch and debugger on the same application execution routine. You should read more about ASLR to understand this [https://en.wikipedia.org/wiki/Address_s ... domization](https://en.wikipedia.org/wiki/Address_space_layout_randomization)
3. You could try also other methods like these:
[https://zenhax.com/viewtopic.php?f=4&t=45](https://zenhax.com/viewtopic.php?f=4&t=45)
[https://blog.devolutions.net/2020/08/wh ... -zipcrypto](https://blog.devolutions.net/2020/08/why-you-should-never-use-zipcrypto)
4. You could try first on some games that already have been cracked like "Mini Robot Wars" form aluigi's example to practice.
## Post #5
- Username: brispuss
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue May 28, 2019 11:34 am
- Post datetime: 2020-11-17T08:16:14+00:00
- Post Title: Password For Unpacking Data.pak File!??

Thanks for the extra information! It is useful.

The Mini Robot Wars tutorials (at Zenhax; debugger way and also the non-debugger way) had already been successfully done by me a while ago. So the basic procedure for finding passwords is (sort of) clear. But for this game here, it appears that some other protection/encryption was used, so this made it difficult to understand and difficult to apply appropriate password retrieval procedures.
