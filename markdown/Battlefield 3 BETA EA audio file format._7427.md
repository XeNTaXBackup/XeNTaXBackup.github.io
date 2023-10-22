## Post #1
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-09-27T18:16:36+00:00
- Post Title: Battlefield 3 BETA EA audio file format.

I took this file out of the Battlefield 3 BETA build but i can't convert it with ealayer3decoder by zench. Is this some new type of audio file or just XAS with a different header type?

[http://www.sendspace.com/file/cbkyso](http://www.sendspace.com/file/cbkyso)

Ay help is appreciated.
## Post #2
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2011-10-03T08:35:32+00:00
- Post Title: Battlefield 3 BETA EA audio file format.

Looks like XAS with the typical 76 blocks but this variant I have seen before and decode not work proper still... (applies to all x14 forms while x15 has been ealayer3)... managed decode start correctly a little to hear "stand back here" voice before static again and the voice bit speeds up in higher than mono so likely mono data. start header seems to be 24 bytes long to me before xas data. Maybe someone can look closer.
## Post #3
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-10-03T11:34:57+00:00
- Post Title: Battlefield 3 BETA EA audio file format.

Can you send me the XAS header?
## Post #4
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2011-10-07T06:48:54+00:00
- Post Title: Battlefield 3 BETA EA audio file format.

It already has one basicly... just delete the first 8 bytes and change x14 to x04..so its like 16 byte xas header seen in C&C games, but i doubt it has music, likely sound sfx/ambient since there is no streaming format in use and EA like always sets music use the streaming type encoding.
