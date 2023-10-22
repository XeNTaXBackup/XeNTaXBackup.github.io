## Post #1
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2006-06-13T10:43:11+00:00
- Post Title: File ID

It looks like the most false proof way to recognise the file is the look at File ID, that initial Hex Stamp. I know that FileExt.com has that included in the characteristic and detailed description of each file. However, to make that process of verification faster, perhaps list showing this ID and then file type wold be helpful. Anyone knows if such a list exists, please post the link. 

And then therre are those on line file analysers. One here   
[http://mark0.net/onlinetrid.aspx](http://mark0.net/onlinetrid.aspx).
Any others?

I wonder how such a analyzer works? Does it scan just the begining of the file or it searches for the ID string in the body of the file too. Sometimes the searched and recognisable file is burried inside.
## Post #2
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2006-06-13T19:46:01+00:00
- Post Title: File ID

this initial hexstamp (signature) isn't always accurate, there are many files which don't include one, or some where its not the in the front.  Examples of this are MP3's or JPEGs. Mp3s only have a signature for say "ID2/3" tags, and JPEG's signature is after the first 4 bytes.

But an example of a program like what you posted, is *nix's "file" command.  Under linux you can use "man magic" to find more information on how to add more, including the file that stores the "algo" to figure out a file.

example of an entry: ZIP

```
0 string    PK\003\004  Zip archive data
>4  byte    0x09    \b, at least v0.9 to extract
>4  byte    0x0a    \b, at least v1.0 to extract
>4  byte    0x0b    \b, at least v1.1 to extract
>4  byte    0x14    \b, at least v2.0 to extract
```
## Post #3
- Username: MarcoPon
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jun 13, 2006 8:09 pm
- Post datetime: 2006-06-15T13:06:19+00:00
- Post Title: File ID

My first post here. I came to know about this forum / site trough Dinoguy1000 and seeing some refereer on my site log.
So Hi! to all! 

> Reply from Xela
>
> I wonder how such a analyzer works? Does it scan just the begining of the file or it searches for the ID string in the body of the file too. Sometimes the searched and recognisable file is burried inside.
My [TrID](http://mark0.net/soft-trid-e.html) does something like that. It both checks for patterns on the header and for specific tokens around the file.

Bye!
## Post #4
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2006-06-16T03:18:40+00:00
- Post Title: File ID

Thank you Marco for popping in and reply. 
TRID is
## Post #5
- Username: MarcoPon
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jun 13, 2006 8:09 pm
- Post datetime: 2006-06-18T12:46:43+00:00
- Post Title: File ID

Thanks! 

Bye!
