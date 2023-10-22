## Post #1
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2011-05-06T06:02:10+00:00
- Post Title: Smmething is wrong with PM notifications by email!

I've turned off notifications of PMs in my settings, as well as turned off receiving email from admins, and even deleted the PM that I keep getting the notification for, yet I keep getting a notification email for the PM approx. every 1-2 minutes, and I've set a filter on my email to send them to a different folder of my email, and have been clearing them out every couple of hours or so, but I get about 150 every two to three hours.

I don't know if I'm the only one with the problem, but please see if you can find the problem.  I don't know if maybe getting a few more PMs will help stop the problem, but you've sent me one PM since it's been happening, yet it is still happening.  Please HELP!!!
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2011-05-06T07:59:00+00:00
- Post Title: Smmething is wrong with PM notifications by email!

I don't have such an issue. Are you sure it is send by our server?
## Post #3
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2011-05-06T15:12:25+00:00
- Post Title: Smmething is wrong with PM notifications by email!

> Reply from Mr.Mouse
>
> I don't have such an issue. Are you sure it is send by our server?
The emails are coming from [forum@xentax.com](mailto:forum@xentax.com) and came after the PM you first sent me, and it only notifies me of that one PM, and I've even deleted the PM, and changed my settings, yet the notifications keep coming.
## Post #4
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2011-05-06T15:34:15+00:00
- Post Title: Smmething is wrong with PM notifications by email!

Like some kind of loop?
## Post #5
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2011-05-06T17:10:49+00:00
- Post Title: Smmething is wrong with PM notifications by email!

I'm having this exact same problem all day yesterday. I have recieved over 2000+ notifications of a reply in only 2 topics in the last 24 hours, and it's really annoying since my phone pings every time I get an email. There is a definite issue with the notification system right now.

I'm only subscribed to two threads that these are coming from:

[viewtopic.php?f=16&t=5394](http://forum.xentax.com/viewtopic.php?f=16&t=5394)

And [viewtopic.php?f=16&t=4501](http://forum.xentax.com/viewtopic.php?f=16&t=4501)
## Post #6
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2011-05-06T17:33:47+00:00
- Post Title: Smmething is wrong with PM notifications by email!

Yeah, I keep getting notifications over and over and over for the same PM, and it's good to see that it's happening to someone else, because it might be easier to figure out if it's not just me with the problem, but sorry to hear you have a problem too.
## Post #7
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2011-05-06T18:09:22+00:00
- Post Title: Smmething is wrong with PM notifications by email!

Found what seems to be a solution to this problem:
[http://www.phpbb.com/community/viewtopi ... &t=1586305](http://www.phpbb.com/community/viewtopic.php?f=46&t=1586305)

From that thread:

> Well you are running on a Windows 2003 server under IIS so first I would suspect the permissions on the /cache folder are incorrect and the queue.php file is looping because it cannot be deleted. Make sure you have given the IUSR_xxx web user in IIS Full Control of the /cache folder in your phpbb folder.

I've also found these threads too:
[http://www.phpbb.com/community/viewtopi ... &t=1225745](http://www.phpbb.com/community/viewtopic.php?f=46&t=1225745)
[http://www.phpbb.com/community/viewtopi ... &t=2032585](http://www.phpbb.com/community/viewtopic.php?f=46&t=2032585)

It seems to be an issue of the queue.php file not ever deleting, so the server must be set up to have FULL control of the ./cache folder.
## Post #8
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2011-05-06T18:56:17+00:00
- Post Title: Smmething is wrong with PM notifications by email!

Yeah, I know. I've informed our host, as they moved us to a new server. There is something fishy with the cache, and I've asked our contact to help out.
## Post #9
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2011-05-06T19:29:20+00:00
- Post Title: Smmething is wrong with PM notifications by email!

> Reply from Mr.Mouse
>
> Yeah, I know. I've informed our host, as they moved us to a new server. There is something fishy with the cache, and I've asked our contact to help out.
Ok, that's cool.  I'm surprised there are only two of us with a problem, although be prepared for more until they fix it.
## Post #10
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2011-05-06T19:38:53+00:00
- Post Title: Smmething is wrong with PM notifications by email!

Has it stopped?
## Post #11
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2011-05-06T20:22:04+00:00
- Post Title: Smmething is wrong with PM notifications by email!

> Reply from Mr.Mouse
>
> Has it stopped?
Yes, I was just coming back to report it is fixed now.
## Post #12
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2011-05-06T20:24:14+00:00
- Post Title: Smmething is wrong with PM notifications by email!

Good.
## Post #13
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2011-05-06T21:28:09+00:00
- Post Title: Smmething is wrong with PM notifications by email!

Thank you for taking care of it quickly.
## Post #14
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2011-05-06T21:31:15+00:00
- Post Title: Smmething is wrong with PM notifications by email!

Not a problem. We can't have brienj in trouble, now can we.
## Post #15
- Username: maxfire02
- Rank: Banned
- Number of posts: 10
- Joined date: Thu May 19, 2011 11:39 am
- Post datetime: 2011-05-26T13:56:19+00:00
- Post Title: Smmething is wrong with PM notifications by email!

Hi!

It is good to hear that annoying PM by email has been stopped  

well what was wrong with the cache?  and how can we get prevention against such a mess?   and does it happen if we only subscribe or choose reply notification?  

your answers to these questions will be very helpful so that i and the other users can beware from this chaotic situation  

Thanks
