## Post #1
- Username: nalri
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Dec 29, 2011 3:04 am
- Post datetime: 2011-12-28T19:39:08+00:00
- Post Title: Game Asset Compression

Hi guys 
I am wondering if I may ask for some advice on a game asset.

The file has the extension .GEO, I have been unable to open it in any 3D Modling software I have on my machine "3DSMAX/MAYA/HOUDINI" 
The asset was taken from a now dead MMO called Tabula Rasa. I used the decompressor I found on these forum's to be able to decompress the original GLM that were on the game disc and this gave me the .GEO file. I have a feeling that the original meshes are still compressed inside the .GEO I have used a hex editor to try to determine what compression was used so that I may be able to get at the original mesh but I unable to determine this.

Would someone with more experience be able to take a look at the file and point me in the right direction


many thanks.
[Beerkeg1.rar](https://xentaxbackup.github.io/file/4933_Beerkeg1.rar)
## Post #2
- Username: nalri
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Dec 29, 2011 3:04 am
- Post datetime: 2011-12-29T13:34:46+00:00
- Post Title: Game Asset Compression

after going through the wiki on the site I think that the file is encrypted and not compressed as i had first though.

unfortunatly I lack the required experience to de crypt it
## Post #3
- Username: nalri
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-12-29T16:22:06+00:00
- Post Title: Game Asset Compression

its just a simple model file not compressed or encrypted.
## Post #4
- Username: nalri
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Dec 29, 2011 3:04 am
- Post datetime: 2011-12-30T01:36:26+00:00
- Post Title: Game Asset Compression

Hi chrrox thanks for taking a look and letting me know

I still cant get the file into any modeling software, even tryign to open it with polytrans wont work it give the message that it cant read the file header...very confusing indeed.
## Post #5
- Username: nalri
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-12-30T01:44:05+00:00
- Post Title: Game Asset Compression

normal modeling software can not just open it you need to make a converter to a format your 3d program understands.
## Post #6
- Username: nalri
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Dec 29, 2011 3:04 am
- Post datetime: 2011-12-30T10:44:43+00:00
- Post Title: Game Asset Compression

Thanks again  chrrox

I will look today and see if I can learn how to write a converter.

I know that the models were created using 3DSmax as while I was searching for information I came across an old artists blogs who worked on the project and also some old job adverts from the design studio that worked on the project advertising for 3D Artists that use 3DSmax.

The studio must have had used some kind of inhouse converter or plugin. I did find this resource that describes the file format ."GEO" and I have attached it to this post, if I understand corrrectly tho that a ".GEO" file is a Houdini file but Houdini was not used by the Design Studio. I also downloaded copy of Houdini but it was unableto open the file.
[HoudiniGPDlib1.0.zip](https://xentaxbackup.github.io/file/4938_HoudiniGPDlib1.0.zip)
## Post #7
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-12-30T21:11:48+00:00
- Post Title: Game Asset Compression

Post more GEO files, of varying sizes (small ones, medium ones, maybe a large one) and different "types" (if they are grouped in different folders, maybe the folder makes it obvious what kind of models are in there)

I have looked at the documentation but I doubt it is the same thing.
If you look at the GEO file, you will see many 4-char strings like NOBP, ESKP, TADB, or LOVB.

It would appear to be a chunk-based format.

In particular, there's a chunk called "XDNI" followed by a bunch of face indices, and there's a chunk called "LCED" followed by a bunch of vertex data.

The document doesn't mention anything of these so I don't think it's a houdini file.
## Post #8
- Username: nalri
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Dec 29, 2011 3:04 am
- Post datetime: 2011-12-30T23:38:48+00:00
- Post Title: Game Asset Compression

Thanks for having a look finale00 

I've attached other file. I could not attach a large file as the forum is limiting the size of file I am able to upload. I think ive tried almost every converter on the net today with no success.
[one.rar](https://xentaxbackup.github.io/file/4939_one.rar)
## Post #9
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-12-31T01:10:07+00:00
- Post Title: Game Asset Compression

Upload it to some common filehosting site like mediafire.

The new file you uploaded contains a bunch of DDS images  (12 of them), among other things.
Maybe everything uses the ".geo" extension.
## Post #10
- Username: nalri
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Dec 29, 2011 3:04 am
- Post datetime: 2011-12-31T02:23:36+00:00
- Post Title: Game Asset Compression

Thanks guys for taking time to help me out on this!

I uploaded a selection of files to Mediafire.

[http://www.mediafire.com/download.php?abkzj4ts5x762ki](http://www.mediafire.com/download.php?abkzj4ts5x762ki)

I have been running checks on the other files with TrID but I'm not having any luck in determining the file types as some of them are coming up as 30 - 40% matches
## Post #11
- Username: nalri
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Dec 29, 2011 3:04 am
- Post datetime: 2012-01-04T11:12:30+00:00
- Post Title: Game Asset Compression

I took the liberty of emailing a couple of artists that worked ont he game and asked them about working on Tabula Rasa, long shot I know but writing custom importers for 3dsMax is well out my expertise range.
