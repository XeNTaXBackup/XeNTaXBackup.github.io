## Post #1
- Username: nightwolf1982
- Rank: veteran
- Number of posts: 158
- Joined date: Fri May 05, 2017 2:19 pm
- Post datetime: 2017-05-11T07:58:36+00:00
- Post Title: Force Unleashed 2 Endor DLC Jedi Leia

Been driving myself nuts with this the last few days; I'm trying to extract the Jedi Leia model from the TFU2 Endor DLC (Xbox 360), and getting no where.  So now I'm asking, can anyone get this model?  I'm at my wits end, trying to figure out the 360 files.

This is the Leia I'm after:

[http://img.photobucket.com/albums/v421/ ... 37852b.jpg](http://img.photobucket.com/albums/v421/Neolilangel/Force%20Unleashed%20Leia/lines_zps7337852b.jpg)
## Post #2
- Username: nightwolf1982
- Rank: veteran
- Number of posts: 158
- Joined date: Fri May 05, 2017 2:19 pm
- Post datetime: 2017-05-18T07:41:06+00:00
- Post Title: Force Unleashed 2 Endor DLC Jedi Leia

Still looking for help here.  I have the Endor files, and I've copied out what should be the Jedi leia file, but it isn't loading in Noesis.  I'm not sure if it's compressed, encrypted, or even complete though.  Can anyone help?

Edit:  added the leiajedi file.
[leiajedi.7z](https://xentaxbackup.github.io/file/12905_leiajedi.7z)
## Post #3
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2017-05-18T09:07:47+00:00
- Post Title: Force Unleashed 2 Endor DLC Jedi Leia

Yup, it's the model. Though, as I remember it's missing index buffer, it's in other place. I remember I had to combine them in order to get models
## Post #4
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-05-18T09:15:03+00:00
- Post Title: Force Unleashed 2 Endor DLC Jedi Leia

leiajedi_gto.png (16.01 KiB) Viewed 190 times


not sure about indices or UVs, seems there is only a head mesh in this file
the first 12 bytes in the stride look like normals though
## Post #5
- Username: nightwolf1982
- Rank: veteran
- Number of posts: 158
- Joined date: Fri May 05, 2017 2:19 pm
- Post datetime: 2017-05-18T10:00:26+00:00
- Post Title: Force Unleashed 2 Endor DLC Jedi Leia

That's further than I've managed.

OK, went back and dug through the Endor file, but what I posted is the only gto data that references Leia Jedi.  Everything else is either a filename or a scripting reference.  At this point I'm utterly stumped.
## Post #6
- Username: nightwolf1982
- Rank: veteran
- Number of posts: 158
- Joined date: Fri May 05, 2017 2:19 pm
- Post datetime: 2017-05-20T12:14:53+00:00
- Post Title: Force Unleashed 2 Endor DLC Jedi Leia

OK, what's the index buffer?  How would I locate it?  Like I said, the references for Jedi Leia I've found are either the model, filenames, or scripting calls.

Edit:  Found what appear to be material references, maybe these are the index buffer?
[leiajediUC.7z](https://xentaxbackup.github.io/file/12919_leiajediUC.7z)
## Post #7
- Username: nightwolf1982
- Rank: veteran
- Number of posts: 158
- Joined date: Fri May 05, 2017 2:19 pm
- Post datetime: 2017-05-21T12:56:43+00:00
- Post Title: Force Unleashed 2 Endor DLC Jedi Leia

Seriously, could use some help/info here.
## Post #8
- Username: nightwolf1982
- Rank: veteran
- Number of posts: 158
- Joined date: Fri May 05, 2017 2:19 pm
- Post datetime: 2017-05-21T14:04:54+00:00
- Post Title: Force Unleashed 2 Endor DLC Jedi Leia

OK, the UC files I posted are apparently xml files.  At least, that's what the BMS script I have extracts them as.  So, back to square negative one it seems.
