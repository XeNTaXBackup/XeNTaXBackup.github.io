## Post #1
- Username: Rygdea
- Rank: n00b
- Number of posts: 19
- Joined date: Mon Aug 16, 2010 7:27 pm
- Post datetime: 2012-01-25T02:41:02+00:00
- Post Title: ADX. Music has Static Over it.

Samples:
[http://dl.dropbox.com/u/12804628/PSO2/S ... IN_001.adx](http://dl.dropbox.com/u/12804628/PSO2/Stuff/LD1_MAIN_001.adx)
[http://dl.dropbox.com/u/12804628/PSO2/S ... IN_002.adx](http://dl.dropbox.com/u/12804628/PSO2/Stuff/LD1_MAIN_002.adx)
[http://dl.dropbox.com/u/12804628/PSO2/S ... IN_003.adx](http://dl.dropbox.com/u/12804628/PSO2/Stuff/LD1_MAIN_003.adx)

Can Anyone help me with removing the static from this? They are from a CPK file in Phantasy Star Online 2. (Well I believe it to be a CPK.)

Several Music Files are split into several tiny pieces inside the "CPK." I put up 3 of them above.
## Post #2
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2012-01-28T02:05:55+00:00
- Post Title: ADX. Music has Static Over it.

This is CRI's new (as of PSO2) "type 9" ADX encryption. It is slightly harder to brute force the keys out of it, due to raw bits of the keystream no longer being directly exposed as in "type 8".  As my guessadx readme said back in 2008:
> I'd like to note that this method could have been defeated if the LCG had only
>
> 13-bit random values. This would not have rendered the files as completely
>
> unlistenable as the 15-bit randomness, but it would still have sounded like
>
> noise. We would have been stuck with far less efficient keyfinding methods if
>
> this was the case. However this would result in the encrypted audio being
>
> recognizable as the original song, just very noisy, which would reveal this as
>
> the lousy encryption it is.It seems like they took my advice, but I was right in that it is still lousy.

The files can be played cleanly with vgmstream ([http://hcs64.com/vgmstream.html](http://hcs64.com/vgmstream.html)) r967 or later, as it has the PSO2 key built in.
