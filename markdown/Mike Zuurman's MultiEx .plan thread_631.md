## Post #1
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-03-26T12:16:13+00:00
- Post Title: Mike Zuurman's MultiEx .plan thread

]==========================================[

From now on, any stuff on my planning/progression list for MultiEx Commander will be posted here. So there. 


Plans for 4.0.0 : here 

Plans for 4.0.1 : here

}=========================================={
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-03-26T19:37:37+00:00
- Post Title: Mike Zuurman's MultiEx .plan thread

Plans/Progression for MultiEx Commander 4.0.0

- Conversion of old scripts to new ones I have completed the automatic conversion of old DOS multiex 2 scripts into multiex 3. I had to write a converter to do it. Turns out the multiex 3 script lacked certain abilities that were possible in the old script, so I had to add these capabilities to the multiex 3 arsenal. These script commands include :
 * If/Else/Endif 
 * Do/While 
 * CleanExit
 * NotEOF

- Removal of code for multiex.exe. This left me with a list of new scripts, and renders the usage of multiex.exe unnecessary. In fact, it renders all DOS support routines useless, so I removed them. Good riddens.   

- The converted new scripts have not yet all been tested on Game Resource Archives (GRA), so in the new release there will probably be some converted scripts that have not been "certified". Here's the list of all converted scripts (certified and not certified). 

Certified

Abomination The Nemesis Project
Actua Soccer 1 
Actua Soccer 2 
Actua Soccer 3 
Age of Empires 2
Ascendancy
Betrayal at Krondor
Black and White
Conflict: Freespace
Crusader: No Remorse
Descent
Dune 2
Echelon
Empire 2
Master of Magic 
Master of Orion
Master of Orion 2
ThunderHawk
Total Annihilation
Twilight CD
US Navy Fighters
Warcraft 2
Worms 1

Not certified

Apache Longbow
Baldur's Gate 1
Blair Witch Project
Call to Power
Close Combat 4
Cultures
Daikatana
Dark Reign
Delta Force Landwarrior
Descent 3
Escape from Monkey Island
Evil Islands
Final Fantasy 7
Giants Citizin Kabuto
Gunlock 
Heroes Chronicles series
Heroes of Might and Magic 3
Hidden and Dangerous
Homeworld
Homeworld Cataclysm
Hostile Waters
Imperialism II
Kingdom o Magic 
Lemmings Revolution
Micro Machines 2
Mortyr
Nascar Heat
Outlive
Planescape: Torment
Rage of Mages
Red Baron 3D
Sim Theme Park 
Star Trek: BOTF
Starlancer
Sudden Strike
Theme Park World
Tombraider 3
Warcraft 1

- Esthetic changes  Both in code and operation some elegant changes have been made. For instance, MultiEx Commander is now fully resizable, instead of being that Maximize/Block/Minimize foolishness. The code has been cleaned up a bit as well. I also fixed some bugs in the "Use custom BMS on..." option, and fixed the File Association preferences. Somehow during compilation of last time, the compiler corrupted, destroying a lot of some forms, I had te redo them, and a bug slipped in the File Association preferences, among other things. I should have probably checked them more thoroughly prior release of 3.9.70. 

- Plans? Yes, I plan to fix any more bugs that got in during the compiler crash. Also, I will add the scripts for new games (such as in the SCRIPTS thread here on the forum). Add even beter debugging. And I really want to do an overhaul of the way the importation works, and make it more universal. There are only so many ways to do a GRA format, right?   

- More plans? About the plugin feature that is already in the previous release, I will try to find time to document how anyone who can create ActiveX DLL's can plug their DLL so MultiEx Commander can use it to Open Archives. Basically all MultiEx Commander would do in this instance is ask the DLL to do everything for him. MultiEx Commander would just pick up the list of GRA contents produced by the DLL to show to the user, but code to extract, import and create new is in the DLL. Yeah, I need to document that. 

Okay, so I'll just leave it at that for now.
## Post #3
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-04-01T08:53:10+00:00
- Post Title: Mike Zuurman's MultiEx .plan thread

Progress problems

Progress is a little slow these days, since I just bought an upgrade (good enough , MSi kt6 delta + AMD 2600+), but I can't get the Ethernet adapter to work. Options are now : Re-install Windoze and try again. if that won't work, take the whole thing to the doctors to fix, for free of course. I hope to be able to work on the new release of MultiEx Commander again some time next week.   

I did finish a script for Port Royale though, it's in the SCRIPTS thread.
## Post #4
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-04-02T07:51:29+00:00
- Post Title: Mike Zuurman's MultiEx .plan thread

Turns out it was the Micro$#@$@ Windoze softwhere that screwed things up. Reinstall got my internet back up. So now I can start installing all other software again.
## Post #5
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-04-04T10:39:04+00:00
- Post Title: Mike Zuurman's MultiEx .plan thread

New game added: Far Cry *.PAK files
## Post #6
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-05-15T22:51:54+00:00
- Post Title: Mike Zuurman's MultiEx .plan thread

Okay, have been busy with the following:

- Removing any usage of that Micro$oft script from hell, sccrun.dll, in MultiEx Commander, by rewriting any and all routines in this dll that are called by MultiEx Commander myself. 
-Removing the "voilently forced online usage" as some moron called it, but I can relate somehow to his feelings, so I like to use his terminology. Mind you, I got enough messages from people they still found the silent downloading a bit "unsettleing", so I will remove that in the next release. Luckily, I was smart enough to anticipate such a thing, and did not remove any routines in the previous release that enabled offline supported, but merely forced online usage only. It is now back to the MRF (MultiEx Resource File) method. 
-I am however updating it so the user can choose when to look for new versions of this MRF file on the net ("on startup", "weekly", "monthly", "never"). I will add the option to check wether there are new versions, by demand of the user. So he can choose "Never" in the automatic feature, but if he hears of a new version of this small resource file, he can simple click "Check for updates" in the program. 
-I am also enhancing dll-plugin support for Painkiller, that will serve as a default for future dll plugins, with import, AND CREATE support. This might take some time. It may not be completely finished prior to the release. A leading Dutch magazine will in all probability do a feature in the October issue, so I will have to release a new version soon, because these people are working on new issues three months ahead of schedule!

So far....
## Post #7
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-05-17T15:40:08+00:00
- Post Title: Mike Zuurman's MultiEx .plan thread

- Okay, I have completely removed any traces of references to the VileSystemObject in MultiEx Commander, screw sccrun.dll.
- Worked on the File Importation window, to make it more straightforward to use, with multiple resource/file previews incoporated. 
- Need to do more Game support (there are a number of request still waiting to be examined and if possible implemented)
- Need to implement the painkiller.dll plugin fully in the Importation Window with Create support as well, it I can get this done, then I can really just plugin future dlls. 
- Offline usage mode is main mode again
- Need to recode the update from website function to something better
## Post #8
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-05-26T07:20:56+00:00
- Post Title: Mike Zuurman's MultiEx .plan thread

- Making good progress on the new importation window:
 > has a file list at the left hand side and the game resource archive's content in the right list
 > two buttons in between the two lists allow quick-extract and quick-replace
 > above each list is a preview window, that will show you a preview of the files/resources you click on 
 > the window is fully resizable
 > a toolbar is at the top of the window, displaying buttons like View (open a file/resource in its associated executable in Windoze), Import Targets, Delete selection, Clear Targets, Create New Archive etc. 
 > The Batch-import option will now be a tool from within this window. 

Thus, when you start MultiEx Commander, you will open a supported archive in the main window. Here you can do the "classic" stuff such as extract single resources or a selection of resources, Preview resources and Execute Resources (View) from within a program associated with it in Windows. 
If you want to do more (Replace resources and, if supported, add/delete,  and create whole new archives) you switch to the Advanced Window (the new File Importation window). I think that will be the core of the program for serious users. Users that just want to preview resources or extract them will not be bothered with these advanced options, and can simply use the Basic Window instead! 

I think that is all pretty cool, don't you think?
## Post #9
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-06-02T07:10:36+00:00
- Post Title: Mike Zuurman's MultiEx .plan thread

Progress is slowed down again. 

The to-do list is much longer than I can handle at this moment. 

Time is not on my side. Well, it is, actually, but for things that have higher priority. 

I did work on a way to have a DLL plugin tell MultiEx Commander what variables it expects whenever MultiEx Commander would want it to create a new GRA. I think I have almost got the right solution, with MultiEx Commander presenting the user with options to choose from prior creation that were specified by the DLL.
## Post #10
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-06-03T08:13:36+00:00
- Post Title: Mike Zuurman's MultiEx .plan thread

In a free moment I created a draft of the new logo of MultiEx Commander franchise, as the old and lame "Face" will be removed in the new version. 

This is the draft:






I think that will be cool enough.   

Intriguingly, the sign looks a lot like [the old USB logo](http://www.xentax.com/html/oldc64snapshots.html)I used in the time...
## Post #11
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-06-03T20:51:13+00:00
- Post Title: Mike Zuurman's MultiEx .plan thread

Ahhh some progress again! 

I have finished the Plugin->MultiExCommander->User->MultiExCommander->Plugin interface for creation of new archives!

I can now select "Create new..." when the plugin supports creation (MultiEx Commander will ask the plugin to cough up support Info) and then the user is presented with a UniForm (pun intended) that will handle the plugins request regarding information the user must specify so succesful creation of a new archive can occur. UniForm will return this info to MultiEx Commander, that will use it to command the plugin to do its thing. After the plugin gives control back to MultiEx Commander and says "Yep, all is well in ArchiveCreationLand" MultiEx Commander will open the new archive, completing the whole operation! 

 

Now only millions of options left to code. . . .
## Post #12
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-06-09T06:58:18+00:00
- Post Title: Mike Zuurman's MultiEx .plan thread

Well, made progress. 

- worked a bit on the new logo
- rewrote the "Automatic Update From internet" function, have to test it  though. In principle, the user can now select in "options" at what interval MultiEx Commander should check for new updates : At Startup, Weekly, Monthly or Never. When it will check, the user will also see a list of new things when there are new things available. MultiEx COmmander will use either one file (MRF) with all the scripts or will use plugins for operation. it will no longer use standalone scripts from the web. 
It will also still be possible to actively tell MultiEx Commander to start checking immediately. 
- have succesfully implemented the Painkiller.DLL,with some minor code to add. 

I still have to:

- revamp the layout 
- create new versions of other plugin DLLs
- Add new formats

But these are the lowest priority. Every core function has to work to full satisfaction before I will turn to aesthetics or quantity of supported game resource archives.
## Post #13
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-06-18T23:30:32+00:00
- Post Title: Mike Zuurman's MultiEx .plan thread

- Layout revamped! You will believe it when you see it. Looks good now!
- Web update interface done and tested (almost)
- Implemented the "Batch job from directory" importation tool into the new MultiEx Editor.

Still have to :
-add new formats
-test the MRF update from web option
-test the new exe from web option

I think the next release will be a huge leap forward in MultiEx Land.
## Post #14
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-06-23T09:11:28+00:00
- Post Title: Mike Zuurman's MultiEx .plan thread

Final testing stage commenced. 

Will release betaversion soon. Target: 1st of july.
## Post #15
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-06-28T23:22:41+00:00
- Post Title: Mike Zuurman's MultiEx .plan thread

Release is imminent. Just some website update.
## Post #16
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-06-29T08:56:20+00:00
- Post Title: 

VERSION 4.0.0 IS A FACT! 

Go to [http://multiex.xentax.com](http://multiex.xentax.com) to grab the new release, or use the build-in option to download the patch. 

Should work! 

Meanwhile, take a look at the screenshots over there, the middle one is the new MultiEx Editor.
## Post #17
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-07-08T07:30:55+00:00
- Post Title: 

Plans for MultiEx Commander v4.0.1

I need to quick-fix a bug in the extraction of files without an extension!
## Post #18
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-07-08T07:31:34+00:00
- Post Title: 

Done! 

I have released v4.0.1 that fixes the extraction bug.
## Post #19
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-11T21:19:55+00:00
- Post Title: 

We have a new developer on board, Rahly, you can find him on the forum here as well. He is making good progress on a Plugin Manager, an interface between the Commander and Plugins. Plugins, mind you, that will be much better than the dll's I created. Rahly really knows what he's doing. Not a bad thing at all *grin*   

Visit [http://sourceforge.net/projects/mexcom](http://sourceforge.net/projects/mexcom) for the clean Commander source code and the whole project. If you'd like to join in, or join the discussion about the code, feel free to start a new topic in the Code Talk forum.
## Post #20
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-11-01T09:15:58+00:00
- Post Title: 

Watto ([http://www.watto.org](http://www.watto.org)) and I finished The Definitive Guide To Exploring File Formats. Check [http://www.xentax.com](http://www.xentax.com)
## Post #21
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-01-03T11:42:28+00:00
- Post Title: 

As of January 2005 the plan is:

- New version (with registration code needed for some features of MultiEx Commander) 
- New Pluginsystem by Rahly
- New games supported
- Improved usage of editing features of MultiEx Commander (MultiEx Editor)
- Inclusion of the "New archive" option as accessible from the Main window. 

Registration is needed to support the project. Thus, users that donate once ($5 or other means of donation) are rewarded a serial code as a token of appreciation, to unlock features. 

That's the plan. This means that some part of MultiEx Commander will no longer be open source. (The serial code thingy of course) Yet, users could still try to build their own binaries of the source code. The binaries we create will all be requiring registration before some features will be available.
## Post #22
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-03-03T08:34:32+00:00
- Post Title: 

Allright, here's an update:

- Fixed the bug in "Use Custom BMS" option (extract/preview), works normally now 
(is behind serial code as of the next release). 

- Added new "Create Archive" feature that will enable the user to create new archive formats (if supported) from scratch (from a directory, recursively). 
 Currently, there's support for those MultiEx Plugins that support creation and ZIP based game archives. 
(is behind serial code as of the next release). 

- Added the Registration implementation (serial code unlocks features). 

- Added the CTRL+A (select all) option in the main window (finally!)

- Added new games for support (almost 20 of them!), I am aiming at 200 in total for the next release (currently about 190). Thanks to a lot of people who helped out. They will all be mentioned in a to-create Acknowledgements screen and of course recieve a serial code for their "donation" of support! 

- Rewrote the "Update from web" option as it was buggy. 
(is behind serial code as of the next release). 

- Have worked on implementing Rahly's Pluginmanager, but we are stranding on a crucial error in communication between MexCom and the manager, and will in all probability not be able to include it in the upcoming release. We will have to figure out what is going on. 

- Miscellaneous fixes and polishes
## Post #23
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-03-03T22:46:12+00:00
- Post Title: 

- Fixed errors in MexScriptor and in MultiEx.dll :

  No more disappearing EndIfs (a matter of stating 1 instead of 2  )

  Multiple If statements will now be carried out as they should:
  in logical order and without crashing.
## Post #24
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-03-28T10:34:58+00:00
- Post Title: 

New release is a fact...

[viewtopic.php?t=1131](http://forum.xentax.com/viewtopic.php?t=1131)

Soon I will also release a new MexBinder. Will have to wait a bit. Note that the new MRF files are no longer compatible with the old ones, so MexBinder will not work with the new ones.
## Post #25
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-07-29T21:47:56+00:00
- Post Title: 

The plan is to release MexCom 4.2 in august.
## Post #26
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-09-01T07:52:56+00:00
- Post Title: 

And in august it was! Just. The 28th.   

Anyway, what is there for the future?

Well, we released the first version of MexCom to include Rahly's Pluginmanager (RPM), that will enable you to just stick in plugins (not COM) that offer functions RPM expects so it can act as an interface to MexCom. 

You can still create ActiveX plugins as well (read a thread here at the forum, or read the MexCom Manual). Over at the Code Talk forum you can discuss how to create RPM plugins. 

So, the future will hopefully see effective use of the RPM with lots of nice plugins. 

Also, I'm currently working implementing other languages. This is NOT hard, yet WILL take time. It's a no-brain job to code, boring stuff. But the result will be great. I'm creating a program for translators to use, so they can then save the language file and I can include it readily in MexCom. It's time for a multi-language version, as the vast majority of the world doesn't speak English at all.  

I will make myself clean up more and more code and fully integrate my new Debugger/Error handler that I created for the new 4.2 version. 

Of course, more and more formats will be supported. I may turn my eye to multiex.dll to support more script commands that will enable it to support a wider range of game archives. 

Also on my to-do list is an overhaul of the MultiEx Editor. I'll have to think about what I wish it to become. May take a little thought. 

Well, that's it for now. More to follow, probably.
## Post #27
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-12-26T22:51:13+00:00
- Post Title: 

Okay, so a small update. It has been long, but you know that I have become a father now, as my daughter Anna was born on sept 12 2005. So that took a lot of my time naturally. I am, however, working on a new version of MexCom, one that will also include the new language option, and a lot of new games supported. 

Thanks to PXR and KorNet, the new games-list will become larger and larger. 

One thing I must add is that I like to be accurate in the games MexCom supports, and I consider a game not supported when I haven't seen it but is thought to have a similar format as another game. Also, if resources are still compressed or encrypted, this is something I really want to include in the support, and if I can't I will consider the support flawed. 

You know, it's easy to add games, but it's the thoroughness of research and support that counts. 

Hopefully, I will always find the time to do just that. 

Meanwhile, the WIKI is excellent, and a lot of people help out. Very good stuff. Truly homebase for this type of info.
## Post #28
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-12-27T04:27:28+00:00
- Post Title: 

> Reply from Mr.Mouse
>
> One thing I must add is that I like to be accurate in the games MexCom supports, and I consider a game not supported when I haven't seen it but is thought to have a similar format as another game. Also, if resources are still compressed or encrypted, this is something I really want to include in the support, and if I can't I will consider the support flawed. 

You know, it's easy to add games, but it's the thoroughness of research and support that counts.

Thanks for your vote of encouragement :S - I noticed this on the wiki too and it doesn't particularly bother me if you want to use this as a marketing ploy or whatever, but somehow every time I read this it always seems to be a direct target at my program :S . I do understand what you are saying though, and I do agree with it - MexCom does have a slightly better reputation in terms of the games that it supports - so feel free to use this as a slogan or whatever, but maybe word it in such as way as it says "MexCom has 100% accuracy" rather than "MexCom has 100% accuracy, unlike everyone else".

I realise that GE fails on a few games, but the majority of the games work without a problem. For those that do not work, I always put in as much effort as I can in order to rectify the problem quickly - like you, I would prefer to have it all working properly - whats the point in having a program that doesn't do what it says.

And in regards to the decompression not being supported in several games - I know that it isn't really beneficial to most people to have compressed files, and that it is not correct to say that these games are fully supported, thus the reason why I don't say there are any "fully supported" games. These games do offer some degree of support - as they allow the files to be extracted, just not in a readable manner. I leave these plugins in the program because there are people out there who work on the decompression algorithms that like to have a fully compressed single file rather than having to locate all the files in the archive themselves.

Everything that you are saying though is correct - you do have better support for your program, you do work on it more than I work on the backend of GE, and that is the reason why your program still gets the majority of the internet community support. I don't really have time to do the things I want with GE, no matter how much I want to - I have GE versioning plans for the next 5 updates to 2.0, but no time to do them. I barely have enough time to analyse and write plugins for the games people request. I also have a bunch of other minor game-related programs that I had expected to have completed months ago, but none of them have gone past my sketches on a piece of paper. Your program does have plenty of benefits over GE - even simple things which you are probably not aware of such as a much better interface, internet updates, and better (and more) file replace support than GE. If I were you, I wouldn't be feeling any pressure to try and "out-do" GE because, even though it may not appear so, MexCom is the superior program - so I ask you please try not to put down GE just to put your program in the spotlight - feel free to brag about all the things that make your program great, but not by saying that "GE doesn't do this, therefore MexCom is better".

Note: This is not really an attack on you, it is just clarifying a few points - sorry if it sounds attacking or whatever. If you want to clarify anything with me, or ask any questions that may be more appropriate elsewhere, perhaps send me an email.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #29
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-12-27T08:07:40+00:00
- Post Title: 

Watto, as you well know, I really like GE, so there's no problem with that.

As a matter of fact, I do not have any problems with you or the program, instead I think we have a very fruitful thing going on with this active forum, the WIKI and let's not forget the DGTEFF. I really like what you do and I'm sure all agree here.  

I realise now the 100% accuracy bit might be a bit bloating, so I removed the sharp edges of the words at the WIKI. Sorry if you took this personally, that was not my intention at all.  

The last post in this thread was more of a personal reminder. Like you, I have very little time, and there are a million things I'd like to do with MexCom. I shall just have to take things slowly but surely. Again like you, I want my games supported 100% and this is not the case for all of them yet. This bugs me, and that is also why I get irritated when people like Sly come in here, show off their extractor and not let us know how the decompression works.  

If you wish,we can chat some more about this via MSN/email.
## Post #30
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-12-27T08:40:32+00:00
- Post Title: 

Thats fine - I understand what you are saying, and I agree - its just that the relationship we have on these forums/wiki are kinda... competitive. Every time I post something here, I always have to be careful not to post anything relating to GE, because one of the main reasons for this site (from your perspective) would be to promote MexCom (which is understandable). I guess it just kinda hit a bit of a raw nerve thats all - I don't mind you promoting MexCom but I dislike advertising that is based around telling things that are wrong with the competition rather than telling things that are good about a product.

Anyway, enough about that. Sorry if I mis-interpreted your remarks. Oh, and yeah I dislike people who just come in purely to brag - at least we have some kind of collaborative input towards game archive editing.

OK, I think that'll do on this matter. Keep up the good work 

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #31
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-12-27T12:06:47+00:00
- Post Title: 

When to await following release MultiEx Commander v4.3.0?
## Post #32
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2005-12-29T00:21:30+00:00
- Post Title: 

And perhaps a sampling of new features we can expect?
## Post #33
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-12-29T06:58:56+00:00
- Post Title: 

I am not sure about Mr Mouse, but I usually decline to mention dates or features for an upcoming release, because you can't always tell when and what will be in the next update. Also, if you mention it, you get bombarded by emails constantly asking when the next release is due. If he does the same as I do, he won't say anything until it has been released - avoids much annoyance.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #34
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-12-29T21:08:02+00:00
- Post Title: 

I think Mr.Mouse it will write that will be in the new version
## Post #35
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-03-26T19:20:47+00:00
- Post Title: 

Those of you wondering what's going on, well I have been doing the following:

* Translation of MexCom to Dutch and writing code to do that. I will ask the help of Friends of MultiEx to translate it to other languages. These language files are simple text files, that can be edited in Notepad. 

* Adding new stuff to the BMS script, in accordance with Janusz' implementation of BMS on Linux with Fusepak ( [http://fusepak.sourceforge.net/bms.php](http://fusepak.sourceforge.net/bms.php) ) (thanks Mike Melanson)
It now supports: 
- Arbitrary whitespace (  just make sure you end a statement with ; and it will work, you could use multiple lines for a single statement)
- Comments (denoted by a # )
- Strings in between quotes, thus : IDString 0 "&h00&h1eBLAH  BLAH";
  This way any string van be made. 
- Codes for non-standard characters in a string (see above) : use "&h" to denote one. The code is followed by a hexadecimal byte value (e.g. &h2e)
- Improved various routines

I probably want MultiEx.dll to be able to convert/compile the script to BMS (binary format) itself, without the need for the scriptor to be called first to compile it. The scriptor will remain handy for writing a script, but once you have it, it might be good to use it as is in multiex.dll. I will have to work on this. 

I have to take a good look at the BMS Manager in MexCom, I don't think it is stable. This has been on my to do list for the next release quite some time now. 

What I also would like to create is an online repository of BMS files and scripts that people can upload new scripts to that MexCom then can use. This is an idea that Rahly had a long time ago and I think it should be set up. That would make life a lot easier. Uploaded BMS files / scripts could then be added to the "standard" or "official" MultiEx Resource File once a set number of Aye votes have been given by users confirming the BMS file worked for them. Any webcoders want to participate in doing this? Perhaps  we need PHP code to do this?

So, the MultiEx project is still very much alive, even though it is not so out in the open.
## Post #36
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2006-03-27T00:32:39+00:00
- Post Title: 

Sounds like you've really been busy!  I'm quite sure the whitespace update will be a welcome one among many people!  

I'd love to see what I can do with the online database, though I'm not sure I'll be of much help... I have almost no experience working with PHP. Perhaps my skills would be better used coding the page(s) the end user will see?
## Post #37
- Username: PXR
- Rank: VIP member
- Number of posts: 61
- Joined date: Thu Mar 24, 2005 2:55 am
- Post datetime: 2006-03-27T19:22:39+00:00
- Post Title: 

PHP and such isn't really my specialty, but at least I can translate language files into swedish.
## Post #38
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2006-03-27T22:17:07+00:00
- Post Title: 

PXR reminded me, I can do Spanish for ya.
## Post #39
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-03-28T04:57:46+00:00
- Post Title: 

NinjaMuffin also opted for Swedish, perhaps PXR and him can split the work.  

Spanish is also needed! It is just a matter of editing a text file. I will come back to this soon. Thanks a bundle all!!
## Post #40
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-03-28T13:57:46+00:00
- Post Title: 

I can help to translate to spanish
## Post #41
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2006-03-28T23:59:33+00:00
- Post Title: 

Thanks, I'll need the help, I'm only a Spanish 3 student in high school... *sheepish grin*
## Post #42
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-05-04T08:05:48+00:00
- Post Title: 

Those of you wondering what's going on:

- Captain and I are busy working on a new front-page. This will be the main portal to get to BMS scripts, general news, tools etc. The blog I have used so far will NOT be used. 
- Working on hacking the WIKI system so we can get tagged BMS scripts in the WIKi in a separate database. 
- Working on MexCom V4.3 (new languages, Strobe's JN support etc. etc. )
## Post #43
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2006-05-05T12:47:21+00:00
- Post Title: 

Heh, the blog didn't live long, did it?

Is there going to be some feature in the new version of MexCom allowing you to load the BMSes from the WIKI, or is that even planned for sometime in the future?
## Post #44
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-05-05T17:18:39+00:00
- Post Title: 

> Reply from Dinoguy1000
>
> Heh, the blog didn't live long, did it?

Is there going to be some feature in the new version of MexCom allowing you to load the BMSes from the WIKI, or is that even planned for sometime in the future?

The blog didn't live long, cause there were too many bugs in it, and to fix it and adapt it would cost much more time than the new solution. 

As for BMS loaded from the WIKI, that is certainly an option that is seriously considered.
## Post #45
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-07-02T22:33:19+00:00
- Post Title: 

...that much so that the next release will feature the "load scripts from wiki" option. 

And a huge number of other changes. Too much to go into now. It does take up all my time, that's why game archive research is slowed. (See [http://www.xentax.com/?p=90](http://www.xentax.com/?p=90) ). My apologies.
## Post #46
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-07-20T22:14:14+00:00
- Post Title: 

Got myself a full day (morning to the early hours) of coding time and these features are more or less in now:

- multiex.dll can now compile text scripts to BMS itself, no need for a Scriptor to compile them, just feed the actual text format and the BMS will be compiled in-multiex. Handy , because:
- webcode for the Xentax WIKI adds the BMS extension to it (idea: Rahly), making it possible for users to add their text scripts (that can be compiled to BMS) to the wiki pages, that will be stored in a database at the wiki site. This way, any new scripts that are created can be added to a global database, so:
- MexCom can retrieve an extract from the Wiki MultiEx BMS database, so it is always up to date with current events there. This way, the text scripts can be readily fed to multiex.dll and hence archives processed
- A rudimentary support for scanning of files for media is in by using Strobe's adapted Jaeder Naub. This still has a bug in JN that needs fixing though (Strobe??)
- Dutch language support is coming along fine. When the new release is out I will ask people to create other language files.
- I have started work on a secret feature-project too  
- Rahly reminded me I've got to change to Load archive dialog to a more sane one instead of listing hundreds of archives in the Select archive drop down menu. Working on a solution, cause I also have to incorporate WIKI based resources. 
- The WIKI BMS base will feature official and non-official scripts. Any new scripts will need approx. 5 votes to be labelled official. Users that are satisfied with how the new scripts process their archives can then vote Aye, if a script fails to process correctly, they can vote Naye, subtracting a vote from the total. Official scripts should then always work without problems on the archives in question. Neat huh? Again Rahly's idea! 

So far so good. I hope to make the new release possible at the end of august.
## Post #47
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2006-07-23T02:36:26+00:00
- Post Title: 

So much to do, huh?

I'm just wondering, for the Load archive, how hard would it be to write a format sniffer of some type that attempts to make an educated guess at what format the archive is in? *being somewhat of a programmer, realizes how hard it WOULD be and saves the other programmer the time of throwing stuff at him*  

As for the voting on BMSes thing, I've been reconsidering the categories I made on the WIKI and am now curious as to whether it could be hacked to add the format to a pre-existing category should some condition be true (or false, depending on your needs). In the case of BMSes, I see it working like this: On new format pages without a BMS script, the WIKI adds the page to the 'BMS_None' category. For new or updated BMSes, the WIKI automatically adds the page to the 'BMS_Untested' category. After so many user yeas or nays, the WIKI then removes the Untested tag and adds either a 'BMS_User_Approved' or 'BMS_User_Rejected' category tag, after which it's up to an Admin/Bureaucrat/project leader to test the script themselves and confirm the yea or nay votes. In the case the script works, the 'User_Approved' tag is removed, and the WIKI sticks a 'BMS_Official' category tag on it. Otherwise, the BMS script is removed from the page (since it's unfunctioning, but perhaps keeping a copy on the Talk page) and the category is reset to 'BMS_None'. Category names and whatnot are up for review, of course...
## Post #48
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-07-29T20:22:11+00:00
- Post Title: 

> Reply from Dinoguy1000
>
> So much to do, huh?

I'm just wondering, for the Load archive, how hard would it be to write a format sniffer of some type that attempts to make an educated guess at what format the archive is in? *being somewhat of a programmer, realizes how hard it WOULD be and saves the other programmer the time of throwing stuff at him*

Yes, well, like I said, Rahly also sort of suggested I'd change the Load Archive thing, as the type-list is getting huge.  I think I'll just show the type-list according to the extension current file that the user clicks on in the Open dialogue. I probably have to rewrite the whole Open dialogue though.  This feature will however reduce the list considerably. Perhaps I add an Open (extension), Open... and Open As... checkbox in the dialogue. So, when you click on Open (extension), the list will be updated according to the current extension of the file selected, Open... and the files shown in the folder will adapt to the format you select in this one, and the Open As... will be show all files in the folder and you may select to open them as a certain format, regardless of extension. 

A format sniffer is of course something I've considered a long while ago. But I abandoned it for the time being, as it would require a lot of work to do it right. I had once created that MexScan program that would also scan ID-strings (magic words, header identifiers, whatever you call them) to detect the format. But that was in DOS and I never really made use of it. Still, it is an option on the list, be it somewhere near the bottom. 

About the BMS and WIKI pages, I think that may be an option indeed. It reminds me I have to save the wiki-page that the BMS was posted on also in my database.
## Post #49
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-08-26T16:29:47+00:00
- Post Title: 

Okay, version 4.3 is now in beta fase. I expect a release within about two weeks. The Dutch version will be released a couple of weeks later. 

More details later, but you can read this post at the wiki on the BMS tagging feature: 

[http://wiki.xentax.com/index.php/BMS_to_Wiki](http://wiki.xentax.com/index.php/BMS_to_Wiki)
## Post #50
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2006-08-27T19:50:12+00:00
- Post Title: 

Does this mean V. 4.3 has a language-independant-friendly interface, or is that still to come?

I've got some comments on the page, but I'll post them on the WIKI in a minute (on the Talk page).
## Post #51
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-08-31T08:13:48+00:00
- Post Title: 

What you mean with language-independent-friendly? 

The English stuff is translated to Dutch, and will be translated to other languages. If you mean you can use it without even knowing the current language, then no. I do not wish to deviate from the layout as it is now for the time being. 

The new Dutch version is currently under review by a Belgian hard-copy magazine, and they will have the first release of the new version on their DVD. 

I will tweak some more and give them the final DVD version on the 4th of september. 

They plan to discuss it in the october issue. 

The new version has (among other stuff) :

- A new Load Archive dialog created from scratch. This will make it possible to include scanning of directories for known formats. As it is at the moment, users can select Extension based filtering of directories or no filtering. The first will show only those files with extensions known by MexCom. Could be handy. 
- Version 1.0 of WIKI support. Any new BMS entry at the WIKI is immediately available to the online user of MexCom. Users select the source file: local MRF (that holds the 'official' scripts) or online (WIKI scripts). In the future this may lead to online-only, but not the near future. 
- Strobe's Jaeder Naub is implemented as File Scanner. If JN finds media, you can use MultiEx Commander to select to extract which files ! 

I hope it'll work to everyone's satisfaction.
## Post #52
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2006-09-05T00:47:39+00:00
- Post Title: 

What I meant is whether you had all text items moved to an external language pack file... I should have been clearer, that was my fault.

As to the Belgian review/release... That's awesome!  Yet another milestone in MexCom's history!
## Post #53
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-09-20T18:05:39+00:00
- Post Title: 

The new version of MultiEx Commander, 4.3, will be released Sunday the 1st of October.
## Post #54
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2006-09-20T22:41:53+00:00
- Post Title: 

> Reply from Mr.Mouse
>
> The new version of MultiEx Commander, 4.3, will be released Sunday the 1st of October.
If anyone is willing to lend me a hand Il try and do a Japanese Language translation of Multi Ex.
But im not sure QUIET how it would work though, Would I have a LIMIT to do it in or what?
Its written in Visual Basic isnt it?
No wait, im thinking Game Extractor, no wait, if strobe is coding things into it then it MUST be VB right?
Anyways contact me if your interested and find a person to help me along with a Japanese Language release of Mulit ex
## Post #55
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-09-21T09:40:55+00:00
- Post Title: 

> The English stuff is translated to Dutch, and will be translated to other languages
If you need help with spanish...
## Post #56
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-11-07T08:31:33+00:00
- Post Title: 

It will finally have to happen. The next MultiEx Commander version will be online only. In this day of age practically anyone will have online access anyway. 

Pirates, crackers, and warez dudes are forcing this decision on me. Online scripts will enable easy blacklisting of keys. Those of you who helped with the program, donated some money or helped out in any other way are insulted by those who downloads cracks or serials. 

I will probably be forced to remove all MexScripting tools from the program as well. Seeing that it is used rather infrequently anyhow and it mostly comes down to me to add new scripts, nobody else needs those tools. 

It's a shame, as my original idea was to provide tools for anyone with programming knowledge to support with ease their own favourite games. 

I will have to rethink everything over it seems.
## Post #57
- Username: PXR
- Rank: VIP member
- Number of posts: 61
- Joined date: Thu Mar 24, 2005 2:55 am
- Post datetime: 2006-11-08T09:29:33+00:00
- Post Title: 

> Reply from Mr.Mouse
>
> It will finally have to happen. The next MultiEx Commander version will be online only. In this day of age practically anyone will have online access anyway. 

Pirates, crackers, and warez dudes are forcing this decision on me. Online scripts will enable easy blacklisting of keys. Those of you who helped with the program, donated some money or helped out in any other way are insulted by those who downloads cracks or serials. 

I will probably be forced to remove all MexScripting tools from the program as well. Seeing that it is used rather infrequently anyhow and it mostly comes down to me to add new scripts, nobody else needs those tools. 

It's a shame, as my original idea was to provide tools for anyone with programming knowledge to support with ease their own favourite games. 

I will have to rethink everything over it seems.
This is a very sad decision indeed. I'll never enjoy some sort of online tool as much as a standalone program. I don't want to be doing everything online, it's a privacy concern. And if the mexscripting tools will be removed, guess I'll just stick with an older version.

One idea though, is to only let registred users (which supported the program, including donated money) to get support and come up with game requests. Whatever the software, as long as it has a price.. pirates will crack it and use it for free - these are no news.
## Post #58
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-11-08T10:00:47+00:00
- Post Title: 

> Reply from PXR
>
> This is a very sad decision indeed. I'll never enjoy some sort of online tool as much as a standalone program. I don't want to be doing everything online, it's a privacy concern. And if the mexscripting tools will be removed, guess I'll just stick with an older version.

One idea though, is to only let registred users (which supported the program, including donated money) to get support and come up with game requests. Whatever the software, as long as it has a price.. pirates will crack it and use it for free - these are no news.

Yeah, I haven't changed anything yet, so I'm just thinking this over. Savage also came up with some ideas. 

I know that there will always be hackers/crackers, but if I let the scripts be downloaded when needed, at least I can have control over who gets what, just by looking at the regkey. This would render the program useless to those that have a blacklisted regkey. 

The problem is the following. 

1. Downloads and site usage increase monthly, raising costs needed to sustain the website. 
2. Donations are really rather non-existent, besides those that wish to have a regkey. If there's nothing in return in some form of key, people do not donate. MultiEx Commander, and tools of similar ilk, have a rather limited audience, it operates in a niche. Only those that wish to modify their games might find an interest in it, but they do not wish to have to pay for it. This also has never been the general idea behind the project anyhow, but there's a limit to how much one can do for free. A website costs money, traffic costs money. 
3. We offer support for users that wish new games included, and analyze archives they provide. Now, to me, this costs time, time I have very little these days, I have a busy job and a family. Luckily, it's a hobby of mine to do that, its like a mindpuzzle, so I enjoy it. But there is obviously very little in return (and certainly no donations in general). People come in, ask for this or that game, this sometimes succeeds and they leave with a "thank you bye". Actually, most hits we get at this website are at this very forum. So the forum generates a lot of traffic as well, and traffic, as we have seen, costs money. 

So you see there are some things that need solutions. I welcome any idea on how to improve the situation. We're not in it for the money, otherwise we'd have quit this project a long time ago, because the amount of work and costs that go in there will never be payed back. We're in it because we love doing it. But nevertheless have bills to pay, and if I have to choose to spend an evening analyzing some obscure file for nothing or spend time with my family, visits friends or do tasks needed for my payed job and career there, the choice I make is obvious.
## Post #59
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-11-08T11:18:42+00:00
- Post Title: 

> Reply from Mr.Mouse
>
> 
The problem is the following. 
1. Downloads and site usage increase monthly, raising costs needed to sustain the website.

About the downloads is not a problem, it's a lot of fileshares servers, like rapidshare, megaupload, megashares etc etc to upload

> 2. Donations are really rather non-existent, besides those that wish to have a regkey. If there's nothing in return in some form of key, people do not donate. MultiEx Commander, and tools of similar ilk, have a rather limited audience, it operates in a niche. Only those that wish to modify their games might find an interest in it, but they do not wish to have to pay for it. This also has never been the general idea behind the project anyhow, but there's a limit to how much one can do for free. A website costs money, traffic costs money.
It's a lot of free services with unlimited space and bandwith and few SQl for free


> 3. We offer support for users that wish new games included, and analyze archives they provide. Now, to me, this costs time, time I have very little these days, I have a busy job and a family. Luckily, it's a hobby of mine to do that, its like a mindpuzzle, so I enjoy it. But there is obviously very little in return (and certainly no donations in general). People come in, ask for this or that game, this sometimes succeeds and they leave with a "thank you bye". Actually, most hits we get at this website are at this very forum. So the forum generates a lot of traffic as well, and traffic, as we have seen, costs money. 
>
> .
This the complex point
Of course the work it's not FREE or freeware, and you like more people here spends your free time examining file formats and explaning

Depends of every author, i suggest some open source licenses

But it's just suggestions and some ideas
## Post #60
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-11-08T11:44:09+00:00
- Post Title: 

We wish to have full control over our website, so outsourcing our hosting/websites to "free" agents is never an option.  

Besides, you'll be annoyed by the huge amount of ads you'll see if we did. Nothing is ever for free.
## Post #61
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2006-11-08T20:17:57+00:00
- Post Title: 

My suggestion to help was going to be ads... In any case, I guess you've looked into running ads in the past, right?

As far as cracks are concerned, look at it this way: at least MexCom is good enough that there is an apparent demand for cracks for it.  

In any case, going online with MexCom should only be used as an absolute last resort, since this means that all files to be opened have to be completely uploaded to the server (unless theres something I don't know, which there probably is), and considering that most of them are not just big, but huge, this will result in huge bandwidth usage jumps s well as lots of PO'd people who have to sit through a full upload.
## Post #62
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-11-08T22:05:39+00:00
- Post Title: 

> Reply from Dinoguy1000
>
> My suggestion to help was going to be ads... In any case, I guess you've looked into running ads in the past, right?

As far as cracks are concerned, look at it this way: at least MexCom is good enough that there is an apparent demand for cracks for it.  

In any case, going online with MexCom should only be used as an absolute last resort, since this means that all files to be opened have to be completely uploaded to the server (unless theres something I don't know, which there probably is), and considering that most of them are not just big, but huge, this will result in huge bandwidth usage jumps s well as lots of PO'd people who have to sit through a full upload.

No no, people will need to download the scripts to open the files they have on their harddrives. That's what I meant with online.  So, the wiki BMS scripts.
## Post #63
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2006-11-09T03:17:56+00:00
- Post Title: 

Aah, that makes sense...
## Post #64
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-10-21T13:26:59+00:00
- Post Title: 

[http://www.xentax.com/?p=176](http://www.xentax.com/?p=176)

MultiEx Commander v4.3.1 released!  A minor update, yes, but nonetheless. The beginning of something beautiful.
## Post #65
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2008-10-21T16:41:31+00:00
- Post Title: 

Looks pretty nice! I'm a bit sad to see the Wiki support go, but without an updated plugin, I suppose it was inevitable. BTW, I still intend to attempt something with that eventually (but first I've got to learn PHP  )...
## Post #66
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-10-12T12:02:46+00:00
- Post Title: 

Okay, 

I've slowly picked up the project. I intend to do a final release based on the current code in the near future and then move on to a another language. 

Things on my mind: 

1. Online use only (get formats from xentax server instead of local resource file), check of donation gift (serial) online when starting
2. Rudimentary support for QuickBMS script by wrapper for Aluigi's excellent program
3. Better implementation of Game Extractor Java plugins. 
4. More ease of use for the user
5. Make Jaeder Naub scanning work with the new version of JN, or leave it out. 
6. Away with pro-tools, like MRF manager and stuff. 
7. Away with About music. 
8. More ease of use (did I say that already?)
## Post #67
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2010-10-12T21:22:01+00:00
- Post Title: 

And now, a series of questions to bug you with. =D

> Reply from Mr.Mouse
>
> I intend to do a final release based on the current code in the near future and then move on to a another language.

Does that mean you'll be rewriting the program in another language, or will you be dropping MexCom development (for a while, at least) after this release? Which language are you switching to (or have you decided yet, or do you want to say at this time)?

> Online use only (get formats from xentax server instead of local resource file), check of donation gift (serial) online when starting

Will this be the same mechanism used previously, or will you be doing something different? And does this mean offline MexScripts will be ignored altogether?

Also, about time validation was managed online; I assume you'll be coding yourself up a nice web-based frontend license management tool, to track abuse?  

I should really redownload and reinstall MexCom; that's one thing I never did after getting my laptop.
## Post #68
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-10-21T15:11:22+00:00
- Post Title: 

New version is out. More to come !
## Post #69
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-11-02T09:50:53+00:00
- Post Title: 

I'm working on another update that will bring the version to 4.5. Some new features will be in there that'll hopefully be handy to all. At the moment you can already use QuickBMS scripts from MultiEx Commander as well (using quickbms as intermediary, in the package). Gives an easy interface for extracting certain files at will.

Also, Jaeder Naub is now no longer in the package. I will have to discuss with Strobe on a new implementation, because it seems that the new JN no longer works with MultiEx Commander.
## Post #70
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2010-11-02T16:32:49+00:00
- Post Title: 

Cool, will this be the first release written after switching languages?
## Post #71
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-11-02T16:57:35+00:00
- Post Title: 

no
## Post #72
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-12-02T08:10:47+00:00
- Post Title: 

I've also recently updated the MultiEx Editor window for the 4.5 release:



multiex editorv2.jpg (341.62 KiB) Viewed 126 times
## Post #73
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2013-08-03T23:17:09+00:00
- Post Title: 

Long time no update here. But I got round to fixing a couple of bugs. New version 4.5.1 is out!

[http://www.xentax.com/?p=792](http://www.xentax.com/?p=792)
## Post #74
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2016-03-27T22:58:15+00:00
- Post Title: 

Even though the project is dead, check out the Let's MultiEx series I did to help you reverse engineer game resource archives. 

[https://www.youtube.com/playlist?list=P ... GrVNJ2kS2f](https://www.youtube.com/playlist?list=PLP26ZYnLb5EVqqBHDgltL6oGrVNJ2kS2f)
## Post #75
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2022-11-18T09:14:01+00:00
- Post Title: 

And with the final release last week, we close this thread as well. 

[https://multiex.xentax.com/](https://multiex.xentax.com/)

Get the last, fully offline version if you wish.
