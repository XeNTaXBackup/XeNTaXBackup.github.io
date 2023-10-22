## Post #1
- Username: Luriam
- Rank: advanced
- Number of posts: 46
- Joined date: Mon Jun 25, 2012 3:44 pm
- Post datetime: 2015-10-25T22:48:18+00:00
- Post Title: Secret Ponchos - Audio Extract

- Heey kiids, 's your old pal Christopher Walken. And daym, this game is loads of fun. If only I could, you know, get a closer look at those, audio, files. 

   Alright, jokes aside any of you guys actually played the game ? It's pretty damn good, skill based, beautiful art, and the sound/music is just... vibrant.
Get it ? Vibrant ? Sound ?
Sorry, I sometimes get randomly happy and I have no idea why. 

   Anyway, I've done a little research and as far as I know the game uses an engine called 'Phyre Engine' from Sony Computer Entertainment compatible with both PC and Playstation. It also seem to use FMOD, which I noticed on the splash screen, included below. 



   Here are a few sample files for you to test your magic on, [DOWNLOAD](https://www.dropbox.com/sh/btqowhkkusvn1cs/AADBcHFvDrP7YoQvpEbzJpsQa?dl=0).

   As always, any help would be greatly appreciated!
## Post #2
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2015-10-26T09:10:20+00:00
- Post Title: Secret Ponchos - Audio Extract

Download [FSBExt](http://aluigi.altervista.org/papers/fsbext.zip) from Aluigi

Save the following into a text document and change the file extension to .bat and put it in the same folder as FSBExt and the .phyre files.

Run the batch file and it will output all of the audio for you 

```
pause
```
## Post #3
- Username: Luriam
- Rank: advanced
- Number of posts: 46
- Joined date: Mon Jun 25, 2012 3:44 pm
- Post datetime: 2015-10-26T10:04:27+00:00
- Post Title: Secret Ponchos - Audio Extract

> Reply from brendan19
>
> Download FSBExt from Aluigi

Save the following into a text document and change the file extension to .bat and put it in the same folder as FSBExt and the .phyre files.

Run the batch file and it will output all of the audio for you 
Code: Select allfor %%i in (*.phyre) DO fsbext.exe -o -1 "%%i"
pause

Holy cow, that was fast. Thanks a lot Brendan, you're the best!
