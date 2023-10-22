## Post #1
- Username: stani999
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Oct 28, 2020 7:47 pm
- Post datetime: 2020-10-28T12:08:54+00:00
- Post Title: PSP help with audio file exchange

hello, I am currently modding a PSP Game.

I want to exchange background music ( the one I want to exchange to is already in the game files and presented as a .bgp file = .at3 with extra header ) 
I thought renaming the background music file ( new ) to the file name of the old background music file and exchange the old file should work. 
It did ( new music plays in the background) but thing is that there is no looping while playing the game. the music just plays once and then stops...
I did not convert anything, the only thing I did was renaming the audio file
Strangely both music loops infinitely when played in the actual intended situation/moment - that means the code for looping the music infinitely is in the music file, right ?


sadly I can not provide any .bgp or the converted .at3 version because these have " invalid extensions " whenever I try to upload them as an attachment
you can find the .at3 files opened in HxD-Editor in the attachment section
I am trying to change when ever "duelnormal2" should play in the background that "duelboss" instead plays but with infinite looping.

I appreciate any help !
[duelboss.png](https://xentaxbackup.github.io/file/18917_duelboss.png)
## Post #2
- Username: stani999
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Oct 28, 2020 7:47 pm
- Post datetime: 2020-10-28T12:11:11+00:00
- Post Title: PSP help with audio file exchange

can not attach 2 pictures for some reason... here is the duel_normal_2 file picture
[duelnormal2.png](https://xentaxbackup.github.io/file/18918_duelnormal2.png)
## Post #3
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-10-28T12:44:33+00:00
- Post Title: PSP help with audio file exchange

> sadly I can not provide any .bgp or the converted .at3
You can upload some samples to mega.nz, google drive etc.

There is a tool for converting AT3 files in case you would need it 
AT9&AT3 Converter V2.3

As for loopig case, if I were you, I would compare both files (especially headers)
and searched for some differences. There may be some flag resposnible for looping in those files.
