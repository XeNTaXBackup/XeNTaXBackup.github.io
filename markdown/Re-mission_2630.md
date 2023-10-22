## Post #1
- Username: diegoc
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Dec 03, 2006 1:22 am
- Post datetime: 2007-05-24T21:02:55+00:00
- Post Title: Re-mission

Can you tell me how I can open/see the .pak files, please?

[http://www.re-mission.net/index.php](http://www.re-mission.net/index.php)

a little example
[Resource.rar](https://xentaxbackup.github.io/file/1184_Resource.rar)
## Post #2
- Username: diegoc
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Dec 03, 2006 1:22 am
- Post datetime: 2007-05-25T13:45:23+00:00
- Post Title: Re-mission

Any solution , please
## Post #3
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2007-05-25T17:44:59+00:00
- Post Title: Re-mission

This one is very easy, no compression inside so I can help you guy.   

```
DWORD		numObject
DWORD		?? just 0 pad
{
 CHAR[40] 	fileName
 CHAR[220] 	?? just 0 pad
 DWORD		??
 DWORD		ofsObject
 DWORD		?? just 0 pad
 DWORD		?? just 0 pad
 DWORD		?? just 0 pad
 DWORD		lengthObject
 CHAR[36] 	?? just 0 pad
}
```
## Post #4
- Username: diegoc
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Dec 03, 2006 1:22 am
- Post datetime: 2007-05-25T19:44:35+00:00
- Post Title: Re-mission

Thanks   

But How I include this datas in the MultiEx Commander? 

Thanks
## Post #5
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2007-05-25T21:32:31+00:00
- Post Title: Re-mission

I though you know how to program!?
try this script in MultiEx Commander (not sure if it works, I am new to it as well)

```
Game   : 	Re-mission        
Archive: 	PAK
+-----------------------------------------------+
Get FOO Long 0;
Get DATACOUNT Long 0;
Get FOO Long 0;
For i = 1 To DATACOUNT;
 SavePos FPOINTER 0;
 Get FILENAME String 0;
 Math FPOINTER += 264;
 GoTo FPOINTER 0;
 Get FILEOFFSET Long 0;
 Math FPOINTER += 16;
 GoTo FPOINTER 0;
 Get FILELENGTH Long 0;
 Math FPOINTER += 40;
 GoTo FPOINTER 0;
 Log FILENAME FILEOFFSET FILELENGTH 0 0;
Next i ;
```
## Post #6
- Username: diegoc
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Dec 03, 2006 1:22 am
- Post datetime: 2007-05-26T05:57:43+00:00
- Post Title: Re-mission

Thanks

I included in RunMexcript on  and select pak archive but i have a error : Multiex3 could not process
I checked this code in Scriptor version but not work 

ANy idea, please?
## Post #7
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2007-05-26T10:17:40+00:00
- Post Title: Re-mission

Sorry diegoc,
It was my typo mistake. I add comment and spaces after test! 

Here is a working version
[RE-Mission_mexscript.rar](https://xentaxbackup.github.io/file/1190_RE-Mission_mexscript.rar)
