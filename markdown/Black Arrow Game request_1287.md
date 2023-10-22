## Post #1
- Username: flawless
- Rank: n00b
- Number of posts: 18
- Joined date: Mon May 30, 2005 8:57 am
- Post datetime: 2005-05-30T01:00:59+00:00
- Post Title: Black Arrow Game request

Ive been struggling to make skins and maps for Rainbow Six 3 Black Arrow but i think all the files are in the umd. any chance of gettin this added? it would help me out alot! i appreciate any help i can get.
## Post #2
- Username: raster
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon May 30, 2005 1:26 pm
- Post datetime: 2005-05-30T05:32:06+00:00
- Post Title: Black Arrow Game request

humm yes pleaz can you pleaz help us me and flawless run an xbox hackers site and we have been hacking rainbow now for some years but we no the main file we nead to unpack is the .umd is ther enny chance of you making it so we can unpack the .umd file.

if you need a coppy of the file i will send you one just email me [rastersworld@msn.com](mailto:rastersworld@msn.com)

and ill send you a coppy.

thanx raster
## Post #3
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-05-30T05:33:28+00:00
- Post Title: Black Arrow Game request

There is a small example of archive?
## Post #4
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-30T06:20:18+00:00
- Post Title: Black Arrow Game request

Yes, or if they are all big , you can use the Filecutter on them, to send (or attach) me the first and last 512Kb (or 1024kb) of the file.  The tool uses a dll that comes with MultiEx Commander though, so if you haven't please install that first. Thanks! 

(Click link in my signature for Filecutter)
## Post #5
- Username: flawless
- Rank: n00b
- Number of posts: 18
- Joined date: Mon May 30, 2005 8:57 am
- Post datetime: 2005-05-30T07:03:17+00:00
- Post Title: Black Arrow Game request

i tried uploading the file but it wont let me (says the page cant be displayd)... is there an email address or something i can send it to? or let you download it off our site?
## Post #6
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-30T07:44:13+00:00
- Post Title: Black Arrow Game request

That's weird. Yes, you can send it to
## Post #7
- Username: flawless
- Rank: n00b
- Number of posts: 18
- Joined date: Mon May 30, 2005 8:57 am
- Post datetime: 2005-05-30T08:22:57+00:00
- Post Title: Black Arrow Game request

thanks, its in the mail now.

*edit* by the way, i seen that you have an unreal engine plug-in, i downloaded and it doesnt work. maybe because i dont have the full version yet? only reason i even check is that this runs on the unreal engine. thought maybe it might work.
## Post #8
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-30T09:10:52+00:00
- Post Title: Black Arrow Game request

Actually, MultiEx Commander has not got a Unreal plugin yet (we are working on a system that will enable that though). I think you refer to Game Extractor. 

Anyway, here's a MultiEx Commander script that will extract the contents of the umd16 file you sent. 

```
SavePos END 0 ;
Math END -= 19 ;
GoTo END 0 ;
SavePos END 0 ;
Get D Long 0 ;
SAvePos TailOffOff 0 ;
Get TailOff Long 0 ;
Get ArSize Long 0 ;
GoTo TailOff 0 ;
Get FileNum Int 0 ;
Set T Long 0 ;
Do ;
Get SSize Byte 0 ;
GetDString FN SSize 0 ;
SavePos FOO 0 ;
Get FO Long 0 ;
SavePos FSO 0 ;
Get FS Long 0 ;
Get D Long 0 ;
SavePos D 0 ;
Math T += 1 ;
Log FN FO FS FOO FSO ;
While D < END ;

```


There are .u and .uax files in there, standard Unreal engine core and sound files.
[umd16.zip](https://xentaxbackup.github.io/file/271_umd16.zip)
## Post #9
- Username: raster
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon May 30, 2005 1:26 pm
- Post datetime: 2005-05-30T16:19:30+00:00
- Post Title: Black Arrow Game request

flawless rasinbow is made with the unreal engen but ther will be some difrence betwean the pc and the xbox.


I have been thrying to unpack with this program by renaming the .umd to .dat, .BSA, .WAD and so on now the program duz start to look like it is unpacking but then when it gets to the end it just thell me to F******.
So i wuld asum that the makers of the program will be abull to add the .umd file strucksher in the ther nice littel program without to much hassel.

but lets just hope that theys nice ppl can help us cuz this will change rainbow as we no it.
## Post #10
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-30T17:18:20+00:00
- Post Title: Black Arrow Game request

Let's call "this program" MexCom, correct?

1. Download the zipped BMS file. 
2. Start MexCom (MultiEx Commander)
3. Choose "Run custom script on..."
4. Select the BMS file
5. Select a .umd16 file

You should find yourself with the contents of the .umd file.
## Post #11
- Username: flawless
- Rank: n00b
- Number of posts: 18
- Joined date: Mon May 30, 2005 8:57 am
- Post datetime: 2005-05-30T19:22:41+00:00
- Post Title: Black Arrow Game request

thanks alot mouse, im tryin it now.
## Post #12
- Username: flawless
- Rank: n00b
- Number of posts: 18
- Joined date: Mon May 30, 2005 8:57 am
- Post datetime: 2005-05-30T20:17:53+00:00
- Post Title: Black Arrow Game request

need the key before i can test, i just donated though so hopefully ill be able to get back to you soon.
## Post #13
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-30T20:32:38+00:00
- Post Title: Black Arrow Game request

It's in the mail and thanks a bundle!
## Post #14
- Username: flawless
- Rank: n00b
- Number of posts: 18
- Joined date: Mon May 30, 2005 8:57 am
- Post datetime: 2005-05-30T22:05:47+00:00
- Post Title: Black Arrow Game request

works good for unpacking everything, only thing is i cant figure out how to repack it to run the game. im sure ill be able to figure it out though... i hope
## Post #15
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-31T06:36:53+00:00
- Post Title: Black Arrow Game request

Well, that's because I haven't supported replacement of files in there yet. I had trouble when I ran it. Do you have some more examples of those files. If so, please send! 

Actually I tried replacing at home and it worked, but just not on your original file. That's weird.
## Post #16
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-31T22:57:14+00:00
- Post Title: 

Check out the WIKI for any and all archive formats and BMS scripts. 

[http://wiki.xentax.com](http://wiki.xentax.com)
## Post #17
- Username: flawless
- Rank: n00b
- Number of posts: 18
- Joined date: Mon May 30, 2005 8:57 am
- Post datetime: 2005-06-01T04:40:01+00:00
- Post Title: 

thanks, that helps out alot... ill have another example hopefully tomorrow, another game on the unreal engine so i hope its the same.
## Post #18
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-06-01T22:00:02+00:00
- Post Title: 

OK, turns out it was a VERY STUPID bug in MultiEx Commander that prevented file importation. It is fixed and a new release will make it possible.
## Post #19
- Username: flawless
- Rank: n00b
- Number of posts: 18
- Joined date: Mon May 30, 2005 8:57 am
- Post datetime: 2005-06-02T03:29:32+00:00
- Post Title: 

cool, thanks... heres another file for you to play with, ive looked everywhere but havent found one to extract it.
[R6Weapons.rar](https://xentaxbackup.github.io/file/274_R6Weapons.rar)
## Post #20
- Username: mrjkwik
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Apr 06, 2005 11:55 am
- Post datetime: 2005-06-15T02:59:38+00:00
- Post Title: 

has it become possible to rebuild these .umd files after extraction yet?  more specifically for splintercell:chaos theory?
