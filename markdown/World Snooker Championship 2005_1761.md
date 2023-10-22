## Post #1
- Username: zimrahil
- Rank: VIP member
- Number of posts: 5
- Joined date: Sun Mar 05, 2006 7:16 pm
- Post datetime: 2006-03-05T21:14:57+00:00
- Post Title: World Snooker Championship 2005

I notice this hasn't been mentioned in the 12 months since its release so guess its a longshot, but I would sincerely appreciate it if anybody could please look at the wsc2005.dat archive from World Championship Snooker (PC) - I think they contain *.csf *.smm and *.txt files but have no idea on how to extract them

I attach a small part of the dat file, but its full length is 500MB   


Thanks
zim
[snooker dat.zip](https://xentaxbackup.github.io/file/631_snooker dat.zip)
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-03-06T07:18:36+00:00
- Post Title: World Snooker Championship 2005

Okido, have downloaded the file, will take a look soon.  Welcome, by the way!
## Post #3
- Username: zimrahil
- Rank: VIP member
- Number of posts: 5
- Joined date: Sun Mar 05, 2006 7:16 pm
- Post datetime: 2006-03-06T09:21:39+00:00
- Post Title: World Snooker Championship 2005

Hiya. Yep it looks a great site - was referred to it by a mate at another forum   


Thanks for having a look. Any assistance no matter how small much appreciated.
## Post #4
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-03-06T21:54:46+00:00
- Post Title: World Snooker Championship 2005

Here's a script for it, you should be able to extract the files and also replace them using MultiEx Editor hopefully. For the latter, you should add the script (.bms) to your MRF file. See options for Add BMS to MRF. 

```
Get RNum Long 0 ;
For T = 1 To RNum ;
Get U1 Long 0 ;
SavePos FOO 0 ;
Get FO Long 0 ;
SavePos FSO 0 ;
Get FS Long 0 ;
Log "" FO FS FOO FSO ;
Next T ;

```

[dat.zip](https://xentaxbackup.github.io/file/638_dat.zip)
## Post #5
- Username: zimrahil
- Rank: VIP member
- Number of posts: 5
- Joined date: Sun Mar 05, 2006 7:16 pm
- Post datetime: 2006-03-06T22:56:05+00:00
- Post Title: World Snooker Championship 2005

Wow - that was fantastically quick

I need to donate via paypal to get access to adding the script yes ?
Is it 6 "American" dollars ?

Do I use this script to extract the files and then to replace the files back into the dat? 

sorry for being thick, but this is all a bit new to me

Well many thanks for your time, and very happy to donate and help maintain the upkeep of this site
## Post #6
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-03-07T07:35:10+00:00
- Post Title: World Snooker Championship 2005

Thanks for your donation! Well, you should have recieved a code by now. 

It is then that you can add it to your MRF. Also, if you just want to extract files (or even see if it works) you can use the Run custom BMS option. Remember that I didn't have the full archive, only the first and last part. I suspect it will work though, everything looked fine from my end. Too bad they haven't actually saved any filenames in the archive. So they'll come out as mexnoname0, ..1 ..2 etc. There is one unexplained variable though, this might point to an index of filenames OUTSIDE the archive. But that's just guessing.
## Post #7
- Username: zimrahil
- Rank: VIP member
- Number of posts: 5
- Joined date: Sun Mar 05, 2006 7:16 pm
- Post datetime: 2006-03-07T09:14:34+00:00
- Post Title: World Snooker Championship 2005

Thanks for the info

Well will give it a go when I get home from work and will let you know how I get on with the full file. Its the txt files I am most interested in !
## Post #8
- Username: zimrahil
- Rank: VIP member
- Number of posts: 5
- Joined date: Sun Mar 05, 2006 7:16 pm
- Post datetime: 2006-03-07T19:06:35+00:00
- Post Title: World Snooker Championship 2005

Mike

Used the custom BMS file and got a whopping 14533 files.

However most of them get the attached error when I click on them

The ones I can extract I cannot make heads or tails of - it looks like gibberish or is this to be expected, and its because I am a novice   


Sorry for being a drain & thanks so far, but any help much appreciated
Phil
[snooker .jpg](https://xentaxbackup.github.io/file/640_snooker .jpg)
## Post #9
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-03-07T19:18:27+00:00
- Post Title: World Snooker Championship 2005

Ok, please turn off (in Options) "Check file info ascending" and try again. I think that's the problem.
