## Post #1
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-04-01T07:28:02+00:00
- Post Title: Help coding online BMS repository Project

Hi all,

One of the next major things MultiEx in my opinion should be that online BMS repository. 

This should be a complete list of all scripts that are available for MexCom. 

What it should do:

- List all scripts by game name, and by script (as a lot of games use the same archive format).
- Users can click on a link to the script and a new page shows with the actual text of the script, plus a download link for the text and compiled version of the script. Other info would be : date added and added by author. Finally, a marker should show whether the script is "official" (see later). 
- There should be an upload facility for new scripts. Users (authors) will be attached to this script and the script will be in a pre-official stage and show on a sort of "Uploaded scripts" or  "Official authorization pending" page. On this page, registered users should be able to cast a vote "100% Working, 50% working, 0% working" as to the functionality of the script. If a set number of users tested the script succesfully, the script would then be transferred to the "official" list of scripts, and added to a MultiEx Resource File. 
- MultiEx Commander shall be able to download the latest MRF file from the repository at the user's command. 

This way, not only is there a complete overview of the scripts, but also a lot more interactivity and a continuously up-to-date MRF file for everyone to use, without having to wait for the new exe release.

So my question is: should we do this in PHP ? I haven't got a lot of experience with these matters, and have only briefly did something with PHP. But I know I could probably couple the Forum userslist to this new repository and stuff. We'd need HTML and PHP pages then. 

Anyone willing to help out, please join!
## Post #2
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2006-04-01T21:29:15+00:00
- Post Title: Help coding online BMS repository Project

> Reply from Mr.Mouse
>
> One of the next major things MultiEx in my opinion should be that online BMS repository.

Good idea!

> Reply from Mr.Mouse
>
> List all scripts by game name, and by script (as a lot of games use the same archive format).

I still think it would be nice for an integration with the wiki.

> Reply from Mr.Mouse
>
> Users can click on a link to the script and a new page shows with the actual text of the script, plus a download link for the text and compiled version of the script. Other info would be : date added and added by author. Finally, a marker should show whether the script is "official" (see later).

Or maybe an integration with Mexcom, where Mexcom downloads a list of games, and it only downloads a new list when one is available, and allows the user to select BMS's to download.  Possibly using an xml document as transport.

> Reply from Mr.Mouse
>
> There should be an upload facility for new scripts. Users (authors) will be attached to this script and the script will be in a pre-official stage and show on a sort of "Uploaded scripts" or  "Official authorization pending" page. On this page, registered users should be able to cast a vote "100% Working, 50% working, 0% working" as to the functionality of the script. If a set number of users tested the script succesfully, the script would then be transferred to the "official" list of scripts, and added to a MultiEx Resource File.

Like i said, should be integrated into the wiki.  Of course, the edit/post script should be edited so that when you post, it reads the page for a BMS or .BMS file, and checks the database to see if it was edited or changed.

> Reply from Mr.Mouse
>
> MultiEx Commander shall be able to download the latest MRF file from the repository at the user's command.

I think the MRF should only be only on the machine, and should be updated only with the scripts it selected.  With an option for the user to download all the games possible, and auto updating when news ones.

> Reply from Mr.Mouse
>
> So my question is: should we do this in PHP ? I haven't got a lot of experience with these matters, and have only briefly did something with PHP. But I know I could probably couple the Forum userslist to this new repository and stuff. We'd need HTML and PHP pages then.

Seems logical unless you wanna do ASP or .NET.

Client Steps

1. Client starts up, HEAD's the games list url, if modified date is newer than the last downloaded one, then requests the file.
2. Client possibly shows the list of new and/or updated games and their standing.
3. Client downloads all applicable games. updates files as needed.

Server Steps

1. User posts, script looks for BMS scripts, script hashes each script either via MD5 or SHA1, check against past scripts for the game
2. if updated lower the level of the script, reset votes?
3. users Set as an official script if the ratio of percentage voted good and number of votes, is good.
4. Scripts can have several levels, Official, user verified, user unverified.
5. update the client update databases as needed.
## Post #3
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-05-26T06:22:20+00:00
- Post Title: Help coding online BMS repository Project

Well, I think it would be possible to hack MediaWIKI as to do stuff with tags that id a part where a BMS script can be found. 

f.i. 

```
....
</BMS>
```


But what is the best approach ? 

I could hack in php-code to add any new BMS that is posted to a separate MySQL or other db that can be called later. Problem is with editing of already posted scripts, that any updates would also be saved, but I could intercept that in part by looking at a posted version number of the script.

Also, MultiEx Commander should be able to load up somehow all the BMS in the wiki. Either by directly accessing the database (which I don't know anything about, and that would be insecure, as crackers could crack that part of MultiEx Commander and a security breach is then present). Better would be then to have a sort of list feature at the website, that makes it possible to download a freshly created MRF type based on the current contents of the WIKI of file that MexCom can download and use, n'est -pas? 

You see I have no knowledge of secure ways to address webbased databases from within a stand-alone program, and I really don't have the time to get into that.
## Post #4
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2006-05-26T23:15:16+00:00
- Post Title: Help coding online BMS repository Project

> Reply from Mr.Mouse
>
> Well, I think it would be possible to hack MediaWIKI as to do stuff with tags that id a part where a BMS script can be found. 

f.i. 
Code: Select all<BMS GAME="DOOM20" ARC="PK10" AUTHOR="IDSOFTHATER" VERSION="1.2.0"> 
....
</BMS>

But what is the best approach ?
i think that is the BEST approach, although, you could check the block tags for code and "test" if there is a BMS script by a simple parse

> Reply from Mr.Mouse
>
> I could hack in php-code to add any new BMS that is posted to a separate MySQL or other db that can be called later. Problem is with editing of already posted scripts, that any updates would also be saved, but I could intercept that in part by looking at a posted version number of the script.

i was thinking that an update/add of a new article (ala wiki) would test for script, then check the database, md5 the script, and check it against the current one in the database, that way you can test for changes to the script.  I was thinking a simple database/table like Article, Unique Id (multiple scripts), Last Update Date, MD5, Script itself, or with a post you can save to a file on the server, where Script itself would then be filename.  That would make it nice for just script backups.

After that you can update the database to include things like "valid user votes/total votes" maybe a "total admin votes" where admin votes count for more.  Then like if total votes > 100 and ratio of votes > 75% then it becomes an official supported game.  If script gets updated then all votes are set to 0, and it becomes unofficial again.

> Reply from Mr.Mouse
>
> Also, MultiEx Commander should be able to load up somehow all the BMS in the wiki. Either by directly accessing the database (which I don't know anything about, and that would be insecure, as crackers could crack that part of MultiEx Commander and a security breach is then present). Better would be then to have a sort of list feature at the website, that makes it possible to download a freshly created MRF type based on the current contents of the WIKI of file that MexCom can download and use, n'est -pas? 

You see I have no knowledge of secure ways to address webbased databases from within a stand-alone program, and I really don't have the time to get into that.

Well i was thinking you'd just make a completely NEW script that would read out of the database, that Mexcom could call, that creates like a simple xml document.  A script to get the supported games list, and then a script to get specific scripts.  This could also apply to plugins.
## Post #5
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-05-27T15:53:21+00:00
- Post Title: Help coding online BMS repository Project

Allright, I'll do something like that. 

It's fairly easy to implement the new tags, it turns out, IF WE HAD MEDIAWIKI 1.5 OR HIGHER installed, which we DON'T, so we must upgrade A.S.A.P.!!! 

I just have to write some php code then to add the found BMS script to a new database. I still think that version numbers in a tag-argument should be needed to check a script is not simply edited for wiki layout purposes and then added to the database as a new one. The MD5 would not help here. 

I'm thinking of maybe let the user vote for a script from within MexCom, you know , if a users choses to use an unofficial script, MexCom could ask for a vote after it was used on a file. Like "Did this script work for you?" and then run a webscript adding an aye or a naye for that script. 

MexCom would then in part be an online tool. All official scripts could each release be added to the MexCom install in an MRF file for offline use. 

I still have to do a lot, though. I'm more or less done with a first language (Dutch) release, but I need to fix multiex itself to be able to parse text scripts to BMS, so no Scriptor is needed to parse it first. 

I have to work on that MRF manager a bit, cause there's some strange behaviour. 

I'm implementing Strobe's Jaeder Naub to scan any unsupported files for media, and it works for now, but that will require some time as well. 

And then some other stuff. Would be nice to have this WIKI support also in the coming version.
## Post #6
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2006-05-27T22:34:00+00:00
- Post Title: Help coding online BMS repository Project

> Reply from Mr.Mouse
>
> I just have to write some php code then to add the found BMS script to a new database. I still think that version numbers in a tag-argument should be needed to check a script is not simply edited for wiki layout purposes and then added to the database as a new one. The MD5 would not help here.

I think you missed something here.  The Version thing is good, but the md5 is ment to capture changes.  If say a user adds information to the page, but didn't change the script. If you check the md5 for that script, and its the same, there is no need to update the script, nor let users know there is an update.  If they did change the script, you'll know about it, you'll be able to reset the votes, because the new changes will be "unproven", and let user know there is a new version, maybe you wanna test it out because it didn't work before, etc etc etc.  You could use another hash like SHA1 or whatever, i just used md5 as an example.  Like a checksum for the data in it.
