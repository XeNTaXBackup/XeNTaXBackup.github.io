## Post #1
- Username: KWEH
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jan 29, 2019 6:45 pm
- Post datetime: 2019-01-29T10:54:01+00:00
- Post Title: FFXIII Trilogy - extracting cinematics (PS3)

Hi there,

I recently repurchased XIII/XIII-2 for PS3 with the intention of extracting the pre-rendered movies. My BD drive didn't have the chipset required to read them, so I had to settle for finding an iso.

I've tried a few vague guides and can't seem to extract anything from the movie.ps3.bin file. None of the disc image or modding tools are able to detect the files contained within, and the guy who put vidsquish together only mentions using the RPCS3 quickstart guide to find how to backup your disc, but makes no mention of how to extract the video files.

Can anyone tell me what I need to do to extract these files for playback on PC? Would greatly appreciate pointing in the right direction!

(Bonus optional question - is there a working procedure to do the same with Type-0 HD & XV's cinematics from PS4 discs?)
## Post #2
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-01-31T03:55:13+00:00
- Post Title: FFXIII Trilogy - extracting cinematics (PS3)

> Reply from KWEH
>
> Can anyone tell me what I need to do to extract these files for playback on PC? Would greatly appreciate pointing in the right direction!
If your talking about the PS3/XBox360 Disc versions you need to use Noesis, it can dump every single archive the games have in to file/folder structure, characters/textures/sounds/pre-rendered footage so on and so forth for FFXIII, FFXIII-2 or FFXIII-LR.

For example on FFXIII its a different story for extraction of movies, btw, only intro movie is in gorgeous studio quality at 1920x1080p high bitrate, the rest of them are decent studio quality to very poor quality rendered in-game at 1280x720p and saved on to the disc.

I haven't done these steps in a few years, lets see if I remember them correctly 

Open up your .wmp videos one at a time in any hex editor, and search for the following text PAMF0041 and see how many instances it finds.
That's where the header for the videos start which they are PAM Sony format (PlayStation Advanced Movie), if there is only one instance you simply have to delete what's in front of PAMF0041 and save it as a example.pam video.
If it finds more than one PAMF0041 instance then start selection from it until you reach next PAMF0041 with a bunch of FFFF in front of it, and save selection also as a example.pam video.

After that done, you open up VGMToolbox and under Stream Tools\ Video Demultiplexer make sure you select:
-Format: PAM(PlayStation Advanced Movie), 
-Extract Audio-Video, 
-Add Header to Output
Then drag and drop your newly created example.pam you did in hex earlier and it will demultiplex both video and audio, video will be a .264 elementary stream while audio will be a ATRAC3+ 6ch with .aa3 header, all left is to convert the .aa3 audio to a known format using foobar2000/vgmstream, and you can then mux back video and audio you converted to either mkv or m2ts or mp4, you get the idea.

have fun
