## Post #1
- Username: timesnewwoman
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Jul 16, 2021 2:38 pm
- Post datetime: 2021-07-16T06:46:36+00:00
- Post Title: Cookie Run Ovenbreak - Midi Encryption change after Season 6 update

As the title suggests. I want to use the midi files for my own personal uses, but after the Season 6 update the cipher changed from Salsa to something else. I'm not smart enough to figure out which one so I've provided the files in case someone can.
[MIDIs.rar](https://xentaxbackup.github.io/file/20458_MIDIs.rar)
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-07-16T20:24:36+00:00
- Post Title: Cookie Run Ovenbreak - Midi Encryption change after Season 6 update

Do you have some documentation or tools that worked fine with previous encryption?
Do you know how this encryption was reverse engineered before and who did it?
## Post #3
- Username: timesnewwoman
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Jul 16, 2021 2:38 pm
- Post datetime: 2021-07-28T09:50:59+00:00
- Post Title: Cookie Run Ovenbreak - Midi Encryption change after Season 6 update

The original encryption used something called a salsa20 cipher i think? Github user named simontime wrote a tool called gbsalsa to decrypt them but it no longer works thanks to the change in ciphers. 
Based on the byte difference, it might be Blowfish or something similar, but I’m genuinely not smart enough to figure it out.
## Post #4
- Username: timesnewwoman
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Jul 16, 2021 2:38 pm
- Post datetime: 2021-08-25T07:29:12+00:00
- Post Title: Cookie Run Ovenbreak - Midi Encryption change after Season 6 update

from what i'm aware:
-the midis are encrypted in a 24-byte cipher
-they involve fmod somehow, probably
-the game's code is written in java and something else
-the android version specifically also has kotlin for whatever reason

i can send classes3 if needed because that's where a lot of the java stuff is hidden, including some fmod stuff
## Post #5
- Username: timesnewwoman
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Jul 16, 2021 2:38 pm
- Post datetime: 2021-09-17T08:39:37+00:00
- Post Title: Cookie Run Ovenbreak - Midi Encryption change after Season 6 update

[https://github.com/simontime/gbsalsa/bl ... /gbsalsa.c](https://github.com/simontime/gbsalsa/blob/master/gbsalsa.c)
This is the source code of the original tool. You could try contacting the creator to see if he knows anything, but I haven't been able to.
## Post #6
- Username: KookyRawn
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Apr 25, 2020 2:47 am
- Post datetime: 2022-06-24T02:32:46+00:00
- Post Title: Cookie Run Ovenbreak - Midi Encryption change after Season 6 update

With Season 6 coming to an end I have prepared a ZIP file containing all the encrypted MIDIs from Season 6.

Link: [Cookie Run OvenBreak Season 6 Encrypted MIDIs.zip](https://mega.nz/file/9Adl0YTC#5o-HaHupciWxIBXFsz8dUHZHvE11l26sU3pTzBn6iuM)
