## Post #1
- Username: Ligkonakos
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Apr 18, 2019 2:32 pm
- Post datetime: 2019-04-18T12:19:32+00:00
- Post Title: Trouble with some old .mda files [Myth War Online]

I've tried Microsoft Access (2016/2013/2007), even 2003. I also tried renaming the extensions to .tga and using various software to open them, but had zero luck.

I am 100% sure they are image files/models. Someone in the past had an extractor made, however the link has expired. The game was fairly old, at the time of its development it was around 2004-2005. Any leads?

Dropbox link: [https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1DauNy-43HwErPdXxXCm9-iGEPyCIWleM?usp=sharing)

Thanks in advance.
## Post #2
- Username: Drayken
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Dec 26, 2016 10:54 pm
- Post datetime: 2019-04-22T06:35:21+00:00
- Post Title: Trouble with some old .mda files [Myth War Online]

This thread, first reply: [https://forum.xentax.com/viewtopic.php?t=9598](https://forum.xentax.com/viewtopic.php?t=9598) 

If you're logged in you should be able to download the guy's extractor directly from the attached files since that's an upload separate from the dead link. I found it two years ago while I was trying stuff out and I remember you had to create a batch file containing instructions for the run command -- this is also written in the included attachment. You should make a batch file containing the following:

"mdaextractor.exe file.mda" 

This will run the extractor & point it towards whichever file's name you put in as long as it's in the same directory, it will then create a folder of the same name with all the extracted TGAs inside.
## Post #3
- Username: Ligkonakos
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Apr 18, 2019 2:32 pm
- Post datetime: 2019-04-27T08:04:25+00:00
- Post Title: Trouble with some old .mda files [Myth War Online]

If you don't mind me asking, how far did you go with your project?

Also I assume this isn't the right place for discussion, you can PM me your discord if you're up to talk a bit.
## Post #4
- Username: Drayken
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Dec 26, 2016 10:54 pm
- Post datetime: 2019-04-28T13:39:46+00:00
- Post Title: Trouble with some old .mda files [Myth War Online]

Other than some simple fucking around, not very far at all. I did dig through some of the info regarding the RAYS files & it turns out it's proprietary to a game development company named 新瑞狮 (Xinrui Lion/Xiamen Xinruishi Multimedia Co. , Ltd.) which closed down some time in 2003 because of malicious bankruptcy on behalf of the main investor. At the time they were working on a game similar to what Myth War ended up being & some of their employees went on to work for Unigium which would eventually develop Myth War; as such they used their old RAYS development kit. Looking through the incomplete chinese server files shows that they used tools such as 3ds max 6, 3ds max 7 pre-release, IGameExporter for 3ds max 7, Microsoft Visual C++, some headers based on Quake, foundations from Valve etc. Since it references Quake in a couple of places, I reckon the Myth War .map files are using a similar system to Quake's .map which contains information on placement. Still can't seem to find the actual images for in-game maps which I imagine are divided in tiles for faster chunk rendering (speculation).

The MDA files themselves seem to be completely unrelated to Microsoft Access, they're Animation containers (Like a gif is a series of images, an MDA file can both be a container for multiple images just as much as it can be a single animation made out of multiple pictures within its package). They do seem to hold more than just .TGA files though since some have a very large file size while only spitting out very few .tga files on the way out. Finding a way to view the entire arborescence of those .mda files would be pretty useful but since I'm not aware of any way to modify the other's guys extractor, finding out which one of the 新瑞狮/RAYS/Unigium tools were used to package those files would be pretty useful to reverse the process & view all the resources.  

My discord @ is Drayken#3461, I don't have much programming knowledge myself however I'm pretty good when it comes to research.
## Post #5
- Username: Ligkonakos
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Apr 18, 2019 2:32 pm
- Post datetime: 2019-04-28T17:28:23+00:00
- Post Title: Trouble with some old .mda files [Myth War Online]

That's interesting, I've sent you a request.

The only leads I could find was some guy from the audio design team (can't remember the name right now) whom I couldn't really locate, and Richard Chen who was the Director at Unigium. Now he's the Director on Shanghai OOHHOO Games Co., Ltd along with the CEO Ziqiang Chen, who I assume is some sort of relative of his. I did sent him an e-mail inquiring possibilities for retrieval, even if there was a monetary value to it, but I haven't gotten a response as of yet.

I found that they used GameRes as their preferred gamedev site, and they did follow some vanilla steps on that site's "Strategy Game" documentation. Said documentaion could provide useful, maybe even answering some questions regarding .mda, but that's all speculation and I can't find any possible way to retrieve any .pdf or .docs it may have hosted since the site closed last year (?). Regarding .mdas, I would assume they used 3DS Max's suite to export the targa files as a certain filetype and then used a tool or renamed it to .mda.

For any future visitor that may have found this thread, you can contact me at Ligkonakitsa#0286 and we can have a discussion regarding our recent project.
## Post #6
- Username: sammoon
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Dec 31, 2021 4:59 am
- Post datetime: 2021-12-30T21:01:10+00:00
- Post Title: Trouble with some old .mda files [Myth War Online]

hi, were you able to get anything afterwards? I am searching for same thing.

regards
