## Post #1
- Username: aagems
- Rank: advanced
- Number of posts: 75
- Joined date: Thu May 31, 2012 1:07 am
- Post datetime: 2013-12-30T18:56:39+00:00
- Post Title: Dead or Alive 4 SFD Video Format problem

Hi,i have a problem with doa4 sfd video.When i use vgm toolbox to demux it,the video output (m2v format) only show blocky video with yellow and purple color when i play it with vlc.I tried cube media player to convert it to general format (avi) but the result are same.Does anyone know whats wrong with this video format?any help will be appreciate  

the image is like this
[](http://www.imagesup.net/pm-1113884371068.png)
## Post #2
- Username: aagems
- Rank: advanced
- Number of posts: 75
- Joined date: Thu May 31, 2012 1:07 am
- Post datetime: 2014-01-05T18:33:14+00:00
- Post Title: Dead or Alive 4 SFD Video Format problem

Okay,here the smallest file sample that i can upload

[https://www.dropbox.com/s/ik7e5j8t9941d ... _vi_hd.rar](https://www.dropbox.com/s/ik7e5j8t9941dj4/ninja_vi_hd.rar)

you can demux it with vgmtools and get a messy video that i describe above    i hope anyone can figure it out what is the problem with this video (encrypted maybe??)
## Post #3
- Username: aagems
- Rank: advanced
- Number of posts: 75
- Joined date: Thu May 31, 2012 1:07 am
- Post datetime: 2014-01-07T15:17:43+00:00
- Post Title: Dead or Alive 4 SFD Video Format problem

Alright,problem solved.I tried demux it using vgmtoolbox and mux it to mkv using tmpgenc.The video result is normal
## Post #4
- Username: MiLØ
- Rank: veteran
- Number of posts: 114
- Joined date: Sun Dec 11, 2011 3:00 pm
- Post datetime: 2014-01-15T12:09:41+00:00
- Post Title: Dead or Alive 4 SFD Video Format problem

What did you do in tmpgenc to mux it into mkv to make result normal?
## Post #5
- Username: aagems
- Rank: advanced
- Number of posts: 75
- Joined date: Thu May 31, 2012 1:07 am
- Post datetime: 2014-01-18T05:46:16+00:00
- Post Title: Dead or Alive 4 SFD Video Format problem

Okay,here's what i do:
1.demuxing the sfd using video demultiplex tools in vgmtoolbox,got m2v and adx file
2.convert the adx file to wav using pes sound converter
3.muxing into mkv using tmpgenc video mastering works 5,i use simple multiplexing in mpeg tools section,the result is normal and proper video color.no specific setting.
i havent tried it using other software,so i dont have an alternative for tmpgenc video mastering works.
