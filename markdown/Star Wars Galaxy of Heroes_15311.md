## Post #1
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2016-09-30T18:08:11+00:00
- Post Title: Star Wars Galaxy of Heroes

So i have just about downloaded every Unity extractor out there and none seem to be working for this game but just at the start of this month they released a update and everything was just the same now just this week a Rogue One update was released that seemed to completely change everything.

The game does run on 5.3.5p which i guess no tool out there atm supports.

Now in the past in the shared/ cache folder contained in each folder a CAB file with said characters inside them but now they are _data files that from looking in hex contains or is a CAB file cause at the end you can see the real Cab files name and even look through it and see various textures and bones...ect, so my guess is this is probably a encrypted Cab file.

But they also have a new file in here that when looking at it also contains every character so i'm not sure which is which.

Since everything was small i just uploaded them for someone to take a look.

Any help would be greatly appreciated.

[http://www.mediafire.com/file/p6l8osej0 ... yCache.rar](http://www.mediafire.com/file/p6l8osej0lfnpan/UnityCache.rar)
[http://www.mediafire.com/file/2e6utl917 ... meData.rar](http://www.mediafire.com/file/2e6utl917jaxtr8/GameData.rar)
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-09-30T21:06:21+00:00
- Post Title: Star Wars Galaxy of Heroes

UnityEX can open the __data files and you can export files from them   
[http://www.zoneofgames.ru/forum/index.p ... opic=36240](http://www.zoneofgames.ru/forum/index.php?showtopic=36240) 

it does not support compressed meshes yet though
so you can't export the mesh as source, only as compressed data  

UnityCache\Shared\0b7c13d0d3ca8a9fc57b33b5671356f0e0e9606f\__data
has a lot of characters in it
## Post #3
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2016-09-30T21:39:00+00:00
- Post Title: Star Wars Galaxy of Heroes

Yeah i'm mainly looking for a couple of new characters added to this update, sucks how it takes so much work just to get out the ones you want or other stuff from unity games.

Although it's even more annoying they update their games to newer unity version instead of just sticking to 1 version and going with it.........

It sucks they went from having named unity files with the characters name on them to CAB files to now _data files it's like they are trying to make it impossible for me to extract them.
## Post #4
- Username: CrownCityMisfit
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri May 26, 2017 5:51 am
- Post datetime: 2017-08-03T22:42:04+00:00
- Post Title: Star Wars Galaxy of Heroes

Any more info on an extraction process for GoH?

Cheers.
## Post #5
- Username: SickAlice
- Rank: advanced
- Number of posts: 52
- Joined date: Mon Jul 23, 2012 9:02 am
- Post datetime: 2017-08-29T06:37:42+00:00
- Post Title: Star Wars Galaxy of Heroes

Some progress here. I open the data files in Assets Bundle Extractor, unpack and save as an .asset file. Then open that one in Unity Studio. The exported models I'm getting are simply .mesh in extension, not sure how to open them past that.
## Post #6
- Username: SickAlice
- Rank: advanced
- Number of posts: 52
- Joined date: Mon Jul 23, 2012 9:02 am
- Post datetime: 2017-09-03T00:03:44+00:00
- Post Title: Star Wars Galaxy of Heroes

DevXUnity-UnpackerTools can open and extract/change the models accordingly however it's paysoft when it comes to export so I don't have access yet if anyone wants to check that out. Else here's some extracted stuff if anyone wants to play with it. The model in question should be the one with the extension .model.

[https://onedrive.live.com/?authkey=%21A ... 051B80B2EF](https://onedrive.live.com/?authkey=%21AC_UkpyE-VVSNrI&id=756B9A051B80B2EF%21107&cid=756B9A051B80B2EF)
## Post #7
- Username: CrownCityMisfit
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri May 26, 2017 5:51 am
- Post datetime: 2017-09-22T01:41:35+00:00
- Post Title: Star Wars Galaxy of Heroes

> Reply from SickAlice
>
> Some progress here. I open the data files in Assets Bundle Extractor, unpack and save as an .asset file. Then open that one in Unity Studio. The exported models I'm getting are simply .mesh in extension, not sure how to open them past that.

I have only had success opening and exporting .mesh files with XNALara tools:

[http://www.core-design.com/community_xps.html](http://www.core-design.com/community_xps.html)

I have only had success opening and exporting .mesh files with XNALara tools:

[http://www.core-design.com/community_xps.html](http://www.core-design.com/community_xps.html)

If you have any luck, let me know, and I can help you build the GoH model library. It may require exporting FBX files from XPS, then relinking textures in Max (or whatever), then exporting another FBX with bones and textures (hopefully) intact. If you can't save the bones, you can always autorig at Mixamo. I have an Adobe account for that.

I REALLY want these models!

THIS guy is a character artist on the game...

[https://sketchfab.com/noahbench/collect ... -of-heroes](https://sketchfab.com/noahbench/collections/star-wars-galaxy-of-heroes)


Thanks.
## Post #8
- Username: SickAlice
- Rank: advanced
- Number of posts: 52
- Joined date: Mon Jul 23, 2012 9:02 am
- Post datetime: 2018-02-19T22:00:05+00:00
- Post Title: Star Wars Galaxy of Heroes

I have yes. The current version of UnityEx has a right click to convert feature. So load the file, select the model, convert to a easier one.

Going to edit in something. I take request but in this case I won't for as anyone who played with this game knows it is huge pain to find any files, needles in a barn of haystacks really. Else I have problems with that method sometimes. Another method that does work especially if you can't find a usable format is to extract said file as is, open up AssetsBundleExtractor and with that open a different package that does normally work for you, import the extracted file over one in the other package (I can't remember off hand but you may need to rename it match the donor) then export it and the program will trip up and convert it as if it was the other file type. That works nine times of ten though know it's a bit of process.
## Post #9
- Username: Silhouette35
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Dec 29, 2019 7:03 am
- Post datetime: 2019-12-28T23:13:56+00:00
- Post Title: Star Wars Galaxy of Heroes

Was this ever figured out?  I am desperately looking for some Star Wars models to use in Unity.
## Post #10
- Username: SickAlice
- Rank: advanced
- Number of posts: 52
- Joined date: Mon Jul 23, 2012 9:02 am
- Post datetime: 2020-04-15T01:28:31+00:00
- Post Title: Star Wars Galaxy of Heroes

Yeah I did and I see several models floating about the web. I haven't been working on this lately so I'll have to double check when I got time but the process was you first have to Extract the asset file. Then load the file that's extracted to get at the models.
## Post #11
- Username: AntonGru
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Apr 14, 2020 12:21 am
- Post datetime: 2020-04-15T07:05:02+00:00
- Post Title: Star Wars Galaxy of Heroes

troopers are fire!
## Post #12
- Username: SickAlice
- Rank: advanced
- Number of posts: 52
- Joined date: Mon Jul 23, 2012 9:02 am
- Post datetime: 2020-04-16T00:06:47+00:00
- Post Title: Star Wars Galaxy of Heroes

Here ya go friends.

1. Have android emulator with game installed as well a file browser. I use Root Explorer, it bypasses most security but whatever works for you. 

2. In file explorer program go to sdcard/Android/data/ and copy the folder named "com.ea.game.starwarscapital_row" then paste it into the folder where you download files from the emulator to your pc hard drive. If you don't know how to do this you'll need to go find that tutorial first.
       - Alternatively you can go inside the com.ea.game.starwarscapital_row directory and from there /files/UnityCache/ and copy the folder named Shared instead. This is where the games models are stored if you want to skip the rest however other files are located elsewhere you may have interest in. It's your call.



3. Go outside and watch the seasons change. This will take some time.

4. As above you know have a "com.ea.game.starwarscapital_row" folder where you're emulator downloads files, mine is in downloads as I use Memu. If you haven't already download and install AssetStudio. I believe the last version would be 1.14.30. This is a version I know works perfectly for this one and much else.

5. Using AssetStudio navigate to the folder (File > Load Folder) /com.ea.game.starwarscapital_row/files/UnityCache/Shared/. Inside this you find several named folders that contain the games various art from images, models and textures. For characters find folders that begin with "char_". For my example I will pick "char_quigon_pre". There will be another folder inside this or any other represented with a long string name. Open that folder for your Load Folder selection.



6.) AssetStudio will take a moment and load (compile) the contents of the package inside of the folder. It won't take long since it's a model and texture. In the Scene Hierarchy tab you will find something like this for any model, open it up and select it as I have here to make sure you grab everything connected to this model.



7.) Go to Export and select an option for "selected". I've been using Export selected objects (split) for this. You'll now have to save this thing on your hard drive. However you wish. I made a folder just for SWGOH myself and and inside I make a separate folder for every model. This helps keep the right files together as well makes sure it will display in a program like Noesis with it's texture applied correctly. It will spit out an FBX and some texturing pngs and you will end get something like this.



Fin, no fuss no muss. Have fun.
## Post #13
- Username: Andaeriel
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Mar 12, 2019 2:44 pm
- Post datetime: 2021-07-08T02:13:32+00:00
- Post Title: Star Wars Galaxy of Heroes

I've got up until the Model extraction but I am really interested in reusing their animations.
Did anyone manage to get them working and merged with the FBX or even exported as SMD?
