## Post #1
- Username: asper
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Dec 11, 2015 3:11 am
- Post datetime: 2017-12-09T10:48:58+00:00
- Post Title: Playstation 2 - Ghost in the Shell Stand Alone Complex .BIN

Hi guys,

I recently played this great game for Playstation 2 and found that .BIN files contains an "fpk" header but it seems a proprietary format (I suppose it means "file PacKage"). I found a script on the forum but it doesn't work (99,9% sure the format is not the same as the supported one by the script tested).

I attach what should be the background music file (BGM.BIN) and a movie file (MOV00EU.BIN) with probably a proprietary subtitle file (MOV00EUS.BIN); is someone able to extract data from those archives ?




Game was released in 2004-2005.

[DOWNLOAD](https://mega.nz/#!npV2kJQb!0CPaE5SwhJD-atAf-tbNsbX1IoPerGxp-bqZvpjfP6g)


THANK YOU VERY MUCH for your attention !!!


EDIT: I figured out BGM.BIN format:
Each audio file starts with "SShd" string; you then skip 8 words to arrive to the SShd file size (little endian word - the word just after another string: "SSbd"). I have problem making a script which will just look for "SShd" header, size and extract all of the files contained in the .BIN, can someone help me please ?
## Post #2
- Username: asper
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Dec 11, 2015 3:11 am
- Post datetime: 2017-12-10T09:44:23+00:00
- Post Title: Playstation 2 - Ghost in the Shell Stand Alone Complex .BIN

Done ! Thanks to a little hint by Luigi !

Extracted stream containers using this script: [http://aluigi.org/bms/resident_evil_bin_fpk.bms](http://aluigi.org/bms/resident_evil_bin_fpk.bms)

Then used VGM Toolbox: 
Misc. Tools -> Extraction Tools -> Strem Tools -> Video Demultiplexer -> Select PSS (PlayStation Stream) -> Drag&Drop the extracted containers -> obtained .m2v (video) + ss2 (audio) files !
## Post #3
- Username: valon
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Sep 22, 2018 10:55 pm
- Post datetime: 2018-09-22T14:56:54+00:00
- Post Title: Playstation 2 - Ghost in the Shell Stand Alone Complex .BIN

Thanks for the link, asper! The main benefit is all [there](http://short.sx/Jxgr). That place keeps it simple. It has the most popular online info. I'm gonna give it a try prtty soon.
## Post #4
- Username: KennethCampbell
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Nov 27, 2018 3:43 pm
- Post datetime: 2018-11-27T07:49:04+00:00
- Post Title: Playstation 2 - Ghost in the Shell Stand Alone Complex .BIN

Well, I also used to play a video game like Battlefield and I know that PS is the amazing console which gives a unique experience to players.
