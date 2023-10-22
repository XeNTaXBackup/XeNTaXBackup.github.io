## Post #1
- Username: shaska
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Jun 21, 2009 11:05 am
- Post datetime: 2009-09-24T16:05:52+00:00
- Post Title: DEAD SPACE  AUDIOFILE.STR TO WAV HELPMEE!!!!!!!

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: shaska
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Jun 21, 2009 11:05 am
- Post datetime: 2009-09-24T21:52:08+00:00
- Post Title: DEAD SPACE  AUDIOFILE.STR TO WAV HELPMEE!!!!!!!

The contents of this post was deleted because of possible forum rules violation.
## Post #3
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-09-27T21:52:49+00:00
- Post Title: DEAD SPACE  AUDIOFILE.STR TO WAV HELPMEE!!!!!!!

Will check it out.
## Post #4
- Username: Predatory Lootboxes
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Nov 06, 2008 7:51 am
- Post datetime: 2010-03-08T11:33:47+00:00
- Post Title: DEAD SPACE  AUDIOFILE.STR TO WAV HELPMEE!!!!!!!

Any luck with these yet? 


I know by looking in them with a hex editor there is a .sbk reference. But no idea how to get them out.
## Post #5
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-03-08T11:39:38+00:00
- Post Title: DEAD SPACE  AUDIOFILE.STR TO WAV HELPMEE!!!!!!!

Not yet, perhaps you can PM Strobe to check it out.
## Post #6
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2010-03-08T13:27:50+00:00
- Post Title: DEAD SPACE  AUDIOFILE.STR TO WAV HELPMEE!!!!!!!

It looks like the audio is in the same format as the "0x14" type files in Bad Company 2 (for PC, as discussed [here](http://hcs64.com/mboard/forum.php?showthread=18598)) so it may be some well-known EA format that I just don't know how to deal with.  Notably we see this at silence:
00 00 0C 00
4 times.  The 0xC seems to be a consistent offset, I took the average of the first and second 16-bit word here (4 sets) in all the 0x4C blocks throughout creepy_ch04_atrium.str (a nice big file) and the avg. was different by 12.
