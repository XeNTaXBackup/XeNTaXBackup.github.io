## Post #1
- Username: NKCSS
- Rank: advanced
- Number of posts: 76
- Joined date: Tue Oct 09, 2007 5:19 am
- Post datetime: 2007-10-14T13:21:12+00:00
- Post Title: Feedback about new application idea


## Post #2
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2007-10-14T14:51:00+00:00
- Post Title: Feedback about new application idea

i think we must to try
## Post #3
- Username: Dinoguy1000
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2007-10-17T19:55:41+00:00
- Post Title: Feedback about new application idea

One more step option: Step to next field, for files whose formats are partially or completely known. Also, perhaps collapse all step options down to one button with a dropdown menu. Other than that, it looks very interesting.
## Post #4
- Username: NKCSS
- Rank: advanced
- Number of posts: 76
- Joined date: Tue Oct 09, 2007 5:19 am
- Post datetime: 2007-10-17T20:14:42+00:00
- Post Title: Feedback about new application idea

> Reply from Dinoguy1000
>
> One more step option: Step to next field, for files whose formats are partially or completely known. Also, perhaps collapse all step options down to one button with a dropdown menu. Other than that, it looks very interesting.

Not realy sure what you mean, this tool would try to interpret the entire signature from it's current position

so, if you had the following HEX: 01 23 45 67 89 0A BC DE FF FB 01 23 45 67 89 0A BC DE

(FF FB = Mpeg 1 Layer III Sync Frame)

and the signature would be 

```
0       2       Byte      MP3 Sync Frame       HEX
1       1       Byte      MP3 Tag Data         HEX (you'd want to see it as bits, but don't have a good example at this time)

```


So, if you start, you'd get:

MP3 Sync Frame: 0123
MP3 Tag Data: 45

Since this is not what we are looking for, and the 2nd byte also doesn't start with the first half of the pattern nor the Tag Data hold the first part of the TAG we are looking for (FF), we skip 3 bytes and get:

MP3 Sync Frame: 6789
MP3 Tag Data: 0A

Same deal, skip 3 bytes and get:


MP3 Sync Frame: BCDE
MP3 Tag Data: FF

We nog have part of what we want visable (might be a match!) in the Tag data, so we move 2 bytes to position the FF in the first part of the Sync frame and get:

MP3 Sync Frame: FFFB
MP3 Tag Data: 01

Yay, we found our mp3 sync frame!

That was kind of the idea behind the manual skipping of bytes (this would of cource be better with the scan,but it's just discovery at this point).
## Post #5
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-10-17T20:38:00+00:00
- Post Title: Feedback about new application idea

This type of signature scan is something also found probably in Strobe's Jaeder Naub (included in MultiEx Commander as well) scanning code. You could try and PM him about it to discuss such issues.
