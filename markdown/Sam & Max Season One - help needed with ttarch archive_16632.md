## Post #1
- Username: Diduz
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Aug 02, 2017 10:06 pm
- Post datetime: 2017-08-02T14:51:14+00:00
- Post Title: Sam & Max Season One - help needed with ttarch archive

Hello guys, I find myself in a strange predictament with a Telltale ttarch archive, I wonder if you'll be able to help me out.
But first, some background infos. Years ago I decided to update the Italian version of the Sam & Max Season One (Windows): I thought the published Italian retail dvd-rom edition had too many mistakes to be bearable, so I took action and used Luigi's excellent ttarchext and other tools to correct the italian.langdb files and re-encode them in correct new ttarch archives (version 2, according to ttarchext). I created six patches for the six episodes (actual setups which updated the whole archives) and all went well. TTG put the same version of the episodes on Steam, so all went (and goes) well up there too.   
The problem arose with the new formats used in the updated Telltale Store and GOG packages. My patches don't work any longer on them, and no surprise there: those new Windows ttarch archives of Sam & Max Season One / Sam & Max Save the World are totally different! Ttarchext tells me they're version 8, and even the italian.langdb files are slightly different! So I came to terms with the idea of applying my old corrections in these new files, manually. Ouch.   
Before even looking for updated tools, I tried to edit the new italian.langdb files through a simple hex editor, just to test if the episodes on GOG and the TTStore accepted the modified files. Guess what. They don't. Stubborn as hell.   
I guess I've tried everything, and all I got were games lacking every kind of text (check the attached screen: no fonts whatsoever!) or crashing on desktop. That's what I've tried so far: 1) I put the langdb file in the game directory "as it is"; 2) I recompiled the langdb file in a 0.ttarch, with or without the -x option; 3) I recompiled the whole ttarch archives with the modified langdb in them, with or without the -x option. No. Dice. No. Way. 
Here's another strange thing for you: if I extract the italian.langdb and do the same things I listed, WITHOUT modifying the file in ANY way, I get the same results!   The episodes hang or start without fonts, texts and dialogues. The games seem to react against any attempt to tinker with them.
So, basically: is there a way to modify version 8 ttarch archives without breaking the games? Am I doing something wrong? Guess so. I'd really like to put my updated translation in the GOG and Telltale Stores versions of Sam & Max Season One, because TTG added some nice new touches to S1: the engine is more performing and stable, you can make Sam run around or move faster...
Thanks for your time.  
[SamandMaxNOTESTI.jpg](https://xentaxbackup.github.io/file/13161_SamandMaxNOTESTI.jpg)
