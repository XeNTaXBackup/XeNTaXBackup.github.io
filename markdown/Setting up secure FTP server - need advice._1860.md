## Post #1
- Username: NinjaMuffin
- Rank: VIP member
- Number of posts: 65
- Joined date: Sat Jan 07, 2006 11:52 pm
- Post datetime: 2006-04-21T09:39:30+00:00
- Post Title: Setting up secure FTP server - need advice.

Hi all 

I need to setup a secure FTP server and I was thinking that there might be people on this forum who know about these sort of things...so here I am.

Basically, I need recommendations on what server program to use and possible pros and cons. Also, suggestions on a fast and good router well fit for this purpose would be great.

It needs to be as secure and fast as possible so with that in mind, what do you suggest? Any help on this would be greatly appreciated.

Thank's in advance

Cheers  

N
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2006-04-21T12:46:22+00:00
- Post Title: Setting up secure FTP server - need advice.

Well, I can't help you thee, but I am curious... What do you need it for? Perhaps a game? I'm not trying to be nosy or anything...
## Post #3
- Username: NinjaMuffin
- Rank: VIP member
- Number of posts: 65
- Joined date: Sat Jan 07, 2006 11:52 pm
- Post datetime: 2006-04-21T15:56:01+00:00
- Post Title: Setting up secure FTP server - need advice.

Sorry to disappoint you, but it's not for a game (sorry).  Oh, and it's all perfectly legal and nothing weird, creepy or anything like that.

N
## Post #4
- Username: PXR
- Rank: VIP member
- Number of posts: 61
- Joined date: Thu Mar 24, 2005 2:55 am
- Post datetime: 2006-04-21T22:46:50+00:00
- Post Title: Setting up secure FTP server - need advice.

For what operating system? For windows I'd say [Gene6 FTP Server](http://www.gene6.com/), something a bit more advanced might be [ioFTPD](http://www.inicom.net/pages/en.ioftpd-home.php). If you're running some sort of Linux you can try [vsftpd](http://vsftpd.beasts.org/) or [glFTPd](http://www.glftpd.org/).

A good router.. there's many types of them.. just don't get one with packet inspection and such, that really slowes things down. But if you need a really secure, fast and cheap one, get an old computer and install some sort of linux-router-distribution. Even better, install [OpenBSD](http://www.openbsd.org/) and configure it yourself to a router.
## Post #5
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2006-04-22T02:09:34+00:00
- Post Title: Setting up secure FTP server - need advice.

"Secure FTP" is sooo vague.

i generally don't use FTP because of archaic protocol and implementations. FTP is terrible for what its suppose to do.  And no standard for anything.

are we talking about ftp over ssl, or ftp over ssh?
## Post #6
- Username: NinjaMuffin
- Rank: VIP member
- Number of posts: 65
- Joined date: Sat Jan 07, 2006 11:52 pm
- Post datetime: 2006-04-22T22:10:28+00:00
- Post Title: Setting up secure FTP server - need advice.

Hi

PXR...I'm on PC myself, but as I was just informed some of the users are on Mac. Thank's on your router advice...much appreciated.

Rahly...yeah I guess it is. As it turns out we have some Mac users some have suggested setting using a (SSL) Virtual Personal Network solution instead.

So what do you guys think about VPN...and are there any good ones you can recommend?

If you have any other solution that you think might be better suited, I'm all ears of course.

Thank's again for your help guys.

Cheers

N
## Post #7
- Username: PXR
- Rank: VIP member
- Number of posts: 61
- Joined date: Thu Mar 24, 2005 2:55 am
- Post datetime: 2006-04-22T23:24:30+00:00
- Post Title: Setting up secure FTP server - need advice.

> Reply from NinjaMuffin
>
> Hi

PXR...I'm on PC myself, but as I was just informed some of the users are on Mac. Thank's on your router advice...much appreciated.

Rahly...yeah I guess it is. As it turns out we have some Mac users some have suggested setting using a (SSL) Virtual Personal Network solution instead.

So what do you guys think about VPN...and are there any good ones you can recommend?

If you have any other solution that you think might be better suited, I'm all ears of course.

Thank's again for your help guys.

Cheers

N
If you're just going to transfer files, FTP is a great way to do it (no matter what rahly says ;)). You want it secure; use FTP-SSL (not ssh-ftp, because that's really slow, at least when I've tested it) to get the data encrypted, all the software I mentioned supports it. People using any operating system can connect to a ftp-server (even with ssl), all that is need is a working ftp-client. Check out [http://www.pure-mac.com/ftp.html](http://www.pure-mac.com/ftp.html) for example, it lists several client for MacOS.
## Post #8
- Username: NinjaMuffin
- Rank: VIP member
- Number of posts: 65
- Joined date: Sat Jan 07, 2006 11:52 pm
- Post datetime: 2006-04-23T06:02:35+00:00
- Post Title: Setting up secure FTP server - need advice.

PXR...thank's for the info and the links.

Sounds interesting...as long as it's possible for clients on Mac to use it as well. The server can cost a bit, but I think they'd prefer the clients being free of charge. Dunno how likely that is if they support SSL though.

So what do you think about VPN vs FTP? As you point out, all we really need to do is upload and download files with a high level of security...nothing else.

Thank's again.

Cheers

N
## Post #9
- Username: PXR
- Rank: VIP member
- Number of posts: 61
- Joined date: Thu Mar 24, 2005 2:55 am
- Post datetime: 2006-04-23T08:29:43+00:00
- Post Title: Setting up secure FTP server - need advice.

Then you just have to enforce SSL for both connections and data transfers in the server application. I don't think VPN will be much securer (or better encrypted since it also use SSL).
## Post #10
- Username: NinjaMuffin
- Rank: VIP member
- Number of posts: 65
- Joined date: Sat Jan 07, 2006 11:52 pm
- Post datetime: 2006-04-23T10:54:24+00:00
- Post Title: Setting up secure FTP server - need advice.

Ok, thank's for your help man.

N
## Post #11
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2006-04-24T13:26:38+00:00
- Post Title: Setting up secure FTP server - need advice.

> Reply from PXR
>
> FTP is a great way to do it (no matter what rahly says ;)).

FTP is terrible, using multiple sockets as a cheap way to transfer, which forces you to open up a lot of ports on your firewall, and to top it off, its a pain to set up correct.

Normal FTP (active ftp) works
You connect to the ftp command port (21), you issue a command, then you have to say which ip/port to send data back on, then the server has to connect to to that port in order to send the data response (actual file/file listing).  Problem with that is if the user is behind a firewall, these ports are usually blocked.  PITA IMO!

So they added a command PASV aka (Passive FTP)
Same as above except instead of the server connecting to you for the data transfer, you connect to it.  Fast and easily implemented solution, but terrible, because now, you have open up a range of ports for the server firewall PLUS the ftp command port.  Not to mention the security issues involved in this, for example, if someone connects to that socket before you, they can get the file, bypassing whatever login information is required.

Now because there isn't a way to determine which you are suppose to use, at least programmatically, the user has to decide which to use (ala, if one way doesn't work, use the other).

FTP is a nightmare.

Now comes FTP over SSH, great idea if there ever was one. FTP and Shell are handled over port 22, including SCP (Secure Copy).  The server has to open up a single port, no ranges, and you don't have to worry secondary connections, as commands and data are transfered through the same socket.  Socket is encrypted, and no secondary connections are bypass login security.

Personally, I use winscp, which also has ftp over ssh support, to connect to all my server machines, esp over the internet.  FTP is usually turned off.

FTP is an ancient beast, that needs to be put to rest.
## Post #12
- Username: NinjaMuffin
- Rank: VIP member
- Number of posts: 65
- Joined date: Sat Jan 07, 2006 11:52 pm
- Post datetime: 2006-04-24T18:43:31+00:00
- Post Title: Setting up secure FTP server - need advice.

Rahly,

Thank's for your reply.

Yeah I understand the problems of regular FTP. However, the thing I was thinking about was FTP over SSL. I can't see you mentioning FTP over SSL in your latest post...so how does that in your view compare to FTP over SSH? Does FTP over SSL also open up a whole bunch of ports etc?

To perhaps easier understand the specifics of my problem, I'm on a Windows machine which will be the "server". Users are on Windows and Mac so both will have be available as clients.

We will just need to upload, download and share files...nothing more. The simpler, safer and easier the better.

Any recommendations?

Thank's again.

Cheers

N
## Post #13
- Username: PXR
- Rank: VIP member
- Number of posts: 61
- Joined date: Thu Mar 24, 2005 2:55 am
- Post datetime: 2006-04-24T20:23:43+00:00
- Post Title: Setting up secure FTP server - need advice.

> Reply from Rahly
>
> Not to mention the security issues involved in this, for example, if someone connects to that socket before you, they can get the file, bypassing whatever login information is required.
If we ignore the fact that sockets can be binded to a specific ip-address, how big of a chance is it that this actually happens? If it's gonna work, the "hacker" has to (probably) hammer multiple ports on the server under a longer period to find the one that is open for data-transfer, in say, like the time of zero to one second before the real client "grabs the slot". Such hammering could easily be stopped automatically by a firewall. So unless the "hacker" knows what port and socket to connect to or actually got the same ip-address as the client, I don't think it's really possible.


About FTP over SSH, I believe you, it's more secure. But how about the performance?

When I tested some while ago (with WinSCP) to transfer several gigabytes of data via LAN (100Mbps), I got speeds of about 1MBps - not acceptable. Later I tried transfering with standard SSL-FTP, the speed bursted to 10-11MBps. I don't know, maybe I did something wrong (transfered from my linux server to my windows desktop btw). 


> Reply from NinjaMuffin
>
> Does FTP over SSL also open up a whole bunch of ports etc?
Yeah, it does, FTP over SSL is exactly the same as usual FTP. The main difference is the that you send some extra commands before starting a transfer, to iniate the SSL-encryption of the data.
## Post #14
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2006-04-25T01:23:50+00:00
- Post Title: Setting up secure FTP server - need advice.

> Reply from NinjaMuffin
>
> I can't see you mentioning FTP over SSL in your latest post...so how does that in your view compare to FTP over SSH? Does FTP over SSL also open up a whole bunch of ports etc?

similar, with similar problems as normal ftp.  Although, PXR has it wrong.  SSL is negotiated BEFORE commands are sent, or its not SSL.  SSL was designed for transparency for sockets, a simple replace of function names and you are done.  If its AFTER, then ftp would have had to been reengineered.  This is why sftp has a different port (not 21, but 115).  Now as to performance issues, not 100% sure, i know ftp over ssl encrypts the command channel, this is so things like username and password are encrypted, but i'm not sure if encrypts all the data channels, or maybe it only encrypts the channel if its in "ASCII" mode, i'd have to go look it up.  IF so, then ftp over ssl would be faster in file transfers than ftp over ssh, because EVERYTHING is encrypted in ssh, this requires more CPU on each end.

> Reply from NinjaMuffin
>
> To perhaps easier understand the specifics of my problem, I'm on a Windows machine which will be the "server". Users are on Windows and Mac so both will have be available as clients.

This is even WORSE, because ftp was never designed for windows systems, and all the windows ones i know EMULATE a unix directory for ftp gui client compatibilty, but there is no STANDARD or LAW, that says the directory listings have to be in any particular format.  Directory listing are just a file transfer of a text file, so it can be in ANY format the server deems it to be in.  This is why some clients have problems with other servers.  Yet Another Reason why ftp is terrible.

> Reply from PXR
>
> If we ignore the fact that sockets can be binded to a specific ip-address, how big of a chance is it that this actually happens? If it's gonna work, the "hacker" has to (probably) hammer multiple ports on the server under a longer period to find the one that is open for data-transfer, in say, like the time of zero to one second before the real client "grabs the slot". Such hammering could easily be stopped automatically by a firewall. So unless the "hacker" knows what port and socket to connect to or actually got the same ip-address as the client, I don't think it's really possible.

Your first comment has no bearing on this.  BINDING to an ip address is only for ip addresses of attached adapters, NOT an incoming socket's ip address.  This chance is pretty high nowadays, thousands, if not more, "hackers" are using port scanners, and ones that are automated, and store data from connected sockets for analysis later.

> Reply from PXR
>
> When I tested some while ago (with WinSCP) to transfer several gigabytes of data via LAN (100Mbps), I got speeds of about 1MBps - not acceptable. Later I tried transfering with standard SSL-FTP, the speed bursted to 10-11MBps. I don't know, maybe I did something wrong (transfered from my linux server to my windows desktop btw).

Further supports my belief that the data channels aren't encrypted, but only the command channel is.  Also please note this also depends on your encryption key as well, a bigger one, requires more time for encoding.  If you are using a 256 SSL key, and a 1024 SSH key, which is a factor of 4x.  Basically here, you are trading speed for security.
## Post #15
- Username: NinjaMuffin
- Rank: VIP member
- Number of posts: 65
- Joined date: Sat Jan 07, 2006 11:52 pm
- Post datetime: 2006-04-25T07:21:10+00:00
- Post Title: Setting up secure FTP server - need advice.

Thank you both for your input. This is extremely helpful to me and I truly appreciate it.

Putting the size of the encryption key aside, the question whether the data channel is encrypted or not is certainly interesting. If it's not, then there seems to be a trade-off between speed and security.

Compability with clients using another OS (such as Mac) is of course also very important in this case. I've been recommended using Cygwin, which if I understand it is a sort of Linux environment for Windows. Why would Cygwin be so helpful in this regard? The guy that recommended it also recommended using SSH...but I haven't heard back from him yet so I have no clue about the details.

Thank's again for your replies...greatly appreciated.

Cheers

N
## Post #16
- Username: PXR
- Rank: VIP member
- Number of posts: 61
- Joined date: Thu Mar 24, 2005 2:55 am
- Post datetime: 2006-04-25T12:19:46+00:00
- Post Title: 

> Reply from Rahly
>
> Although, PXR has it wrong.  SSL is negotiated BEFORE commands are sent, or its not SSL.
Oops, of course, I was thinking of ssl-fxp (you send CPSV instead of PASV).

> Reply from Rahly
>
> Now as to performance issues, not 100% sure, i know ftp over ssl encrypts the command channel, this is so things like username and password are encrypted, but i'm not sure if encrypts all the data channels, or maybe it only encrypts the channel if its in "ASCII" mode, i'd have to go look it up.
I don't really know how it works, but in all ftp-client software I've tested you are able to choose if you want to encrypt the file data as well as the command channel. In the server you should be able to enforce not only encryption of the command channel, but also the data ones. Never seen anything about encryption of files only when in ASCII-mode though, it always encrypt no matter what mode (perhaps this can differ). Here's a sample from the config of ioFTPD btw:

```

Require_Encrypted_Auth  = *
Require_Encrypted_Data  = !*
Certificate_Name        = certificatename
Explicit_Encryption     = True
Encryption_Protocol     = SSL3
Min_Cipher_Strength     = 128
Max_Cipher_Strength     = 256
```

Here you're able to choose if SSL should be required or not (* means all and a ! before it will make it "negative"). Specific users who should be (not) forced to use SSL can also be set up easily..

> Reply from Rahly
>
> Your first comment has no bearing on this.  BINDING to an ip address is only for ip addresses of attached adapters, NOT an incoming socket's ip address.  This chance is pretty high nowadays, thousands, if not more, "hackers" are using port scanners, and ones that are automated, and store data from connected sockets for analysis later.
Okey, I kinda guessed about the binding.  But anyway, it should be possible to restrict other ip-addresses than the client's ip to download the current file. Yes, I know that portscanning occurs automatically and so on, but I still can't believe that anyone of those actually will connect to the correct port on the server in that really short period it's open for clients. 

This shouldn't be a problem anyway if the filedata is encrypted.

> Reply from Rahly
>
> PXR wrote:When I tested some while ago (with WinSCP) to transfer several gigabytes of data via LAN (100Mbps), I got speeds of about 1MBps - not acceptable. Later I tried transfering with standard SSL-FTP, the speed bursted to 10-11MBps. I don't know, maybe I did something wrong (transfered from my linux server to my windows desktop btw). 

Further supports my belief that the data channels aren't encrypted, but only the command channel is.  Also please note this also depends on your encryption key as well, a bigger one, requires more time for encoding.  If you are using a 256 SSL key, and a 1024 SSH key, which is a factor of 4x.  Basically here, you are trading speed for security.
When I transfered with FTP I used SSL for both commands and file data, probably with a SSL key of 256bit. In WinSCP I used the standard settings, I've got no idea how big of a key that was used in that case.
## Post #17
- Username: NinjaMuffin
- Rank: VIP member
- Number of posts: 65
- Joined date: Sat Jan 07, 2006 11:52 pm
- Post datetime: 2006-04-25T16:29:30+00:00
- Post Title: 

Thank's for the reply. I really appreciate you both taking your time to explain this. You bringing up many arguments for and against the different methods is also very helpful.

Thank's

N
## Post #18
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2006-04-26T00:43:07+00:00
- Post Title: 

> Reply from PXR
>
> Okey, I kinda guessed about the binding.  But anyway, it should be possible to restrict other ip-addresses than the client's ip to download the current file. Yes, I know that portscanning occurs automatically and so on, but I still can't believe that anyone of those actually will connect to the correct port on the server in that really short period it's open for clients. 

This shouldn't be a problem anyway if the filedata is encrypted.

Port scanning is very very cheap, esp with the way new scanners work, sending an connect, without waiting for an ack.  Anyone with a fast enough connection can do 1000s of ports in under a second, and if that connect packet hits the port before you do, you are actually on the backburner.

Actually it doesn't matter, SSL is negotiated per SOCKET not per SESSION.  SSL was designed against middle man attacks not connection stealing.  So what happens with ftp can happen with ssl-ftp.  The way you avoid this, is by having a single socket.
