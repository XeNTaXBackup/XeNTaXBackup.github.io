## Post #1
- Username: gabrielsanches19
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Jun 28, 2021 2:53 pm
- Post datetime: 2022-05-14T13:42:40+00:00
- Post Title: I want to re-import the .wav files to .fsb and then put it back in .bank

I used the "bms" tools to extract the .fsb files from the .bank and then I used the "fsb_aud_extract" to get the .wav files, I would like to know step by step how to do the reverse.
.bank generated two .fsb files
[Screenshot_19.jpg](https://xentaxbackup.github.io/file/22232_Screenshot_19.jpg)
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-05-14T14:44:45+00:00
- Post Title: I want to re-import the .wav files to .fsb and then put it back in .bank

Well, that depends what version of FSB do you have.

FSB4 can be created with FMOD Designer.
FSB5 can be created with FMOD SoundBank Generator.
More info here [http://wiki.xentax.com/index.php/FMOD_Audio_FSB](http://wiki.xentax.com/index.php/FMOD_Audio_FSB)


Then you can reimport FSB to BANK file with quickbms using reimport mode.
(More info here in section 3 --> [http://aluigi.zenhax.com/papers/quickbms.txt](http://aluigi.zenhax.com/papers/quickbms.txt))

OR use FMOD Studio to create banks (more info here [http://wiki.xentax.com/index.php/FMOD_Audio_BANK](http://wiki.xentax.com/index.php/FMOD_Audio_BANK))
