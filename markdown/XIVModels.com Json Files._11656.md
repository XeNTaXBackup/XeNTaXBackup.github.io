## Post #1
- Username: flarespire
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Jul 24, 2011 7:30 am
- Post datetime: 2014-07-04T09:25:17+00:00
- Post Title: XIVModels.com Json Files.

Thanks to a debugging feature built into Mozilla Firefox, I was able to obtain various .json files that the XIVModels site uses to show its models within the WebGL API. This includes Model Files, The Texture Files and a Material File. In the .zip archive I have provided below there are two models included, these are of the Curtana Atma and Holy Shield Atma, which are relatively small files that should provide a basis for reading these types of file whether through QuickBMS or through Noesis itself using a plugin.

I would really appreciate if someone could look into these files, as they may provide a key into the original game files as well, which would make people from another thread on here very happy and would give them some more info to work from.

.ZIP Archive:
[http://www.mediafire.com/download/8nszi ... +Files.zip](http://www.mediafire.com/download/8nszi6xnqh21sbc/XIVModels.com+Json+Files.zip)

How I got these files:
To start off, I browsed XIVModels.com until I had found the model I wanted, Then I right clicked on the page and selected Inspect Element. From here I clicked on the Network tab of the pane that has appeared at the bottom of the window and clicked on the speedometer Icon in the middle of the first sentence that is displayed in that pane. Once the network caching test had completed for that page, I clicked on the xhr option in the list of either pie chart. Finally, I looked through the list until I found files that ended in .mdl.json, .tex.json and .mtrl.json and right clicked on them and selected the Open in new tab option, then on each file page, after using the information the files had given me on the path structure of the game and setting up those paths somewhere on my PC, I went to File -> Save As, and saved the files in their appropriate locations.

By all means please use this method to grab more of the .json files that you may need to work with this and get something out of it, I will try to compile a bigger source archive in my spare time for people wanting to just download and go with the format research.

~flarespire.
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-07-04T13:35:00+00:00
- Post Title: XIVModels.com Json Files.

They dint preserve the bones so just use any 3d ripper like ninja ripper and you have your models.
## Post #3
- Username: flarespire
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Jul 24, 2011 7:30 am
- Post datetime: 2014-07-04T13:39:43+00:00
- Post Title: XIVModels.com Json Files.

The website is not compatible with any 3D Ripping software, I have tried using things like 3D Ripper DX, Ninja Ripper and even 3D Via Printscreen  in combination with Google Chrome, Firefox and even IE and The capture option does not show up. (I am on a 64-bit system so I'm not sure about global system monitoring in this case.)
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-07-04T13:55:53+00:00
- Post Title: XIVModels.com Json Files.

Well its standard json files.
the stream is base 64 encoded.
so you should be able to convert it to a format like obj without to much trouble.
here is an example json parser in ruby.
[viewtopic.php?f=16&t=8663&hilit=webgl&start=30](http://forum.xentax.com/viewtopic.php?f=16&t=8663&hilit=webgl&start=30)
## Post #5
- Username: flarespire
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Jul 24, 2011 7:30 am
- Post datetime: 2014-07-04T14:07:26+00:00
- Post Title: XIVModels.com Json Files.

Thanks for posting that, However I have very little programming knowledge outside of Actionscript and doing some minor specialized coding in Eclipse, so I have no idea how to utilize what you have posted for my purposes. Would it be possible for you to make a rough BMS Script for this type of file and guide me through it as you go?
## Post #6
- Username: LUBDAR
- Rank: veteran
- Number of posts: 95
- Joined date: Wed Jun 08, 2011 2:14 pm
- Post datetime: 2014-07-05T17:56:43+00:00
- Post Title: XIVModels.com Json Files.

Pardon my misunderstanding, but doesn't this just tell you where the .mdl files are located?
## Post #7
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-07-05T17:59:35+00:00
- Post Title: XIVModels.com Json Files.

This is just a site that hosts model rips of ff 14.
they store it in a custom format .json.
The data is not interesting to me personally at all as they striped anything useful from it.
the most you can get is an obj.
the model data is b64 encoded.
## Post #8
- Username: flarespire
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Jul 24, 2011 7:30 am
- Post datetime: 2014-07-05T18:27:05+00:00
- Post Title: XIVModels.com Json Files.

> Reply from chrrox
>
> This is just a site that hosts model rips of ff 14.
they store it in a custom format .json.
The data is not interesting to me personally at all as they striped anything useful from it.
the most you can get is an obj.
the model data is b64 encoded.
So how exactly would I go about decoding the files so that they become usable, can anyone instruct me on how to do this?
