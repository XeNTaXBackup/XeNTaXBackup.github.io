## Post #1
- Username: EvilWar
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-02-05T21:00:23+00:00
- Post Title: Railroad Tycoon 3 3dp models

Here's a script I wrote to extract stuff from RT3's PK4 files: 

```
Get FileNum Long 0 ;
Savepos Start 0 ;
Set Jump Long FileNum ;
Math Jump *= 74 ;
Math Jump += Start ;
For T = 1 To FileNum ;
Get ID Long 0 ;
Get FileSize Long 0 ;
Get FileROffset Long 0 ;
Get Unknown Int 0 ;
GetDString FileName 60 0 ;
Math FileROffset += Jump ;
Log FileName FileROffset FileSize 0 0 ;
Next T ;

```


I've attached a file that is a 3d-model. (in the zip are unrelated dds and wav files).  

Perhaps someone can take a look.



example.JPG (209.52 KiB) Viewed 443 times


[pk4.zip](https://xentaxbackup.github.io/file/1861_pk4.zip)
## Post #2
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2009-03-21T06:57:43+00:00
- Post Title: Railroad Tycoon 3 3dp models

I added the .3dp and the .pk4/.3dp loader modules to V4.40 and I released the 3D Object Converter v4.40 update.

You can update your installed application (version>=4.0) quickly and easily using the auto-update function (Help/Check for updates).
## Post #3
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-03-21T09:09:49+00:00
- Post Title: Railroad Tycoon 3 3dp models

Great work, Karpati !
## Post #4
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2009-04-29T09:49:23+00:00
- Post Title: Railroad Tycoon 3 3dp models

hello Boss , excuse me that i have very banal question here !
please guide me how should i apply this script ?
because this is the first time i use such scripts , i guess it is not .bms because it has  " ; "
I realy appreciate if you spend your time for answering to me ! thanks a lot .
## Post #5
- Username: shekofte
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-04-29T11:21:06+00:00
- Post Title: Railroad Tycoon 3 3dp models

You can use the script. Save the text as a text file (.txt). 
In MultiEx Commander go to 'Tools' and select the Custom MexScript option. Then point to the .txt file. Then point to the archive to open. Done.
## Post #6
- Username: EvilWar
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Mar 30, 2018 12:18 am
- Post datetime: 2018-08-26T06:19:05+00:00
- Post Title: Railroad Tycoon 3 3dp models

> Reply from Mr.Mouse
>
> Here's a script I wrote to extract stuff from RT3's PK4 files: 
Code: Select allGet Version Long 0 ;
Get FileNum Long 0 ;
Savepos Start 0 ;
Set Jump Long FileNum ;
Math Jump *= 74 ;
Math Jump += Start ;
For T = 1 To FileNum ;
Get ID Long 0 ;
Get FileSize Long 0 ;
Get FileROffset Long 0 ;
Get Unknown Int 0 ;
GetDString FileName 60 0 ;
Math FileROffset += Jump ;
Log FileName FileROffset FileSize 0 0 ;
Next T ;

Your script has a error: First symbol of FileName is lost.
Correct script:

```
Get FileNum Long 0 ;
Savepos Start 0 ;
Set Jump Long FileNum ;
Math Jump *= 74 ;
Math Jump += Start ;
For T = 1 To FileNum ;
Get ID Long 0 ;
Get FileSize Long 0 ;
Get FileROffset Long 0 ;
Get Unknown Byte 0 ;
GetDString FileName 61 0 ;
Math FileROffset += Jump ;
Log FileName FileROffset FileSize 0 0 ;
Next T ;

```
