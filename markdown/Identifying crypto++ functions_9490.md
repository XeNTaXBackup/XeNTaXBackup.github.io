## Post #1
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2012-08-15T19:18:54+00:00
- Post Title: Identifying crypto++ functions

my research covers a lot of encrypted data structures and i often i am stuck when it comes to identifying the actual encryption methods 

for a known compiler (vc++ 6.0), is it possible to create signatures for compiled functions to identify which ones are used?

else, general tips for identifying the algorithm functions?  with so much data, i fallback on string references in my debugger and am not getting anywhere
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-08-15T19:46:14+00:00
- Post Title: Identifying crypto++ functions

crypto++ uses the common algorithms like the others so signsrch will get them.

the only problem is with those that don't use static tables and constants like rc4
## Post #3
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2012-08-15T21:43:07+00:00
- Post Title: Identifying crypto++ functions

i've tried my luck at bruteforcing with quicbms, and the rc4 is the only algorithm which accepts my key length(202 bytes)

i hate being utterly stuck for ideas
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-08-16T13:58:54+00:00
- Post Title: Identifying crypto++ functions

are you sure it's not a proprietary algorithm or an hash one applied over that 202 bytes key for generating one suitable for a block cipher algorithm?
(like md5 of that key to have a 16bytes key)
## Post #5
- Username: mambox
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Wed Mar 24, 2004 9:06 pm
- Post datetime: 2012-08-16T15:11:01+00:00
- Post Title: Identifying crypto++ functions

@Aluigi:i thought you were on vacation, I have not read new posts on your site.

i dont want to pollute the thread,greets.
