## Post #1
- Username: GXavs
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Feb 19, 2010 6:19 pm
- Post datetime: 2010-03-05T01:55:08+00:00
- Post Title: [X360] Just Cause 2 Demo .arc file

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2010-03-06T09:06:31+00:00
- Post Title: [X360] Just Cause 2 Demo .arc file

Have not looked at the 360 version, but the PC demo's .tab file is a table of files in the .arc, there are no filenames (as far as I've seen), the .tab has what appears to be a hash of the filename stored for each entry.

Table file is like:

dword unknown <-- probably indication of how .arc is padded
(for rest of file)
dword file_namehash
dword file_offset
dword file_size
## Post #3
- Username: Sheen
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Mar 03, 2010 2:29 am
- Post datetime: 2010-03-06T18:28:40+00:00
- Post Title: [X360] Just Cause 2 Demo .arc file

Have you tried to open that file with extractARC?

Regards.
[ExtractArc.rar](https://xentaxbackup.github.io/file/2847_ExtractArc.rar)
## Post #4
- Username: civaman
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Mar 22, 2010 3:17 pm
- Post datetime: 2010-03-22T09:34:14+00:00
- Post Title: [X360] Just Cause 2 Demo .arc file

Can't extract with ExtractArc.   Help!!

(Just Cause 2 is Amazing Game...!!)
## Post #5
- Username: twisted
- Rank: veteran
- Number of posts: 100
- Joined date: Tue Apr 24, 2007 6:25 am
- Post datetime: 2010-03-22T10:51:43+00:00
- Post Title: [X360] Just Cause 2 Demo .arc file

you can extract a lot of files from the arc file using offzip, then your left with a lot of sarc files which seem similar to just cause 1 but the multiex plugin for the original doesnt seem to be able to open them.
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-03-22T17:45:15+00:00
- Post Title: [X360] Just Cause 2 Demo .arc file

try the following script, it worked with the pc version:
[http://aluigi.org/papers/bms/justcause2.bms](http://aluigi.org/papers/bms/justcause2.bms)
if doesn't work upload the tab file and I will take a look
## Post #7
- Username: civaman
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Mar 22, 2010 3:17 pm
- Post datetime: 2010-03-23T04:26:00+00:00
- Post Title: [X360] Just Cause 2 Demo .arc file

that script doesn't work.
uploaded tab file. here  [http://www.megaupload.com/?d=7E8EM57E](http://www.megaupload.com/?d=7E8EM57E)
thanks aluigi!
## Post #8
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-03-23T08:39:09+00:00
- Post Title: [X360] Just Cause 2 Demo .arc file

no problem, exactly as I imagined it uses big endian (native on x360) so I have updated the previous script.
refresh the link
## Post #9
- Username: Cryptonia
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Aug 20, 2009 12:11 am
- Post datetime: 2010-03-24T00:31:00+00:00
- Post Title: [X360] Just Cause 2 Demo .arc file

to the pc version, works he with the unpacked archives by script? or i must add it back, my filenames for pc version was sometimes a little strange
## Post #10
- Username: civaman
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Mar 22, 2010 3:17 pm
- Post datetime: 2010-03-24T02:37:50+00:00
- Post Title: [X360] Just Cause 2 Demo .arc file

It Works! Thanks aluigi!! TT
## Post #11
- Username: Microsnakey
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Mar 09, 2010 5:29 am
- Post datetime: 2010-03-27T20:33:17+00:00
- Post Title: [X360] Just Cause 2 Demo .arc file

How do I repack it into an arc
## Post #12
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2014-03-30T21:19:37+00:00
- Post Title: [X360] Just Cause 2 Demo .arc file

> Reply from aluigi
>
> try the following script, it worked with the pc version:
http://aluigi.org/papers/bms/justcause2.bms
if doesn't work upload the tab file and I will take a look

I know it is old topic but Aluigi script does not work  , can you please update it to make it work with JC2 X360 ? thx
