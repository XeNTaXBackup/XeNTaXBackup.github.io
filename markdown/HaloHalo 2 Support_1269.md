## Post #1
- Username: Storm
- Rank: beginner
- Number of posts: 21
- Joined date: Mon May 23, 2005 3:32 am
- Post datetime: 2005-05-22T19:46:35+00:00
- Post Title: Halo/Halo 2 Support?

These would be nice for the .map files. I know there is already quite a lot of editors, but they're all .NET, and .NET crashes my computer cause its the worst thing ever made. And since MultiEx can do everything, why not halo 2 injections?
## Post #2
- Username: UnReAlMaCk
- Rank: VIP member
- Number of posts: 15
- Joined date: Thu May 05, 2005 5:46 am
- Post datetime: 2005-05-26T02:32:44+00:00
- Post Title: Halo/Halo 2 Support?

dude thats the best idea ever, you know how many ppl will use MultiEx if they support halo 2? i mean, think about it, taking files from a .map for halo 2? CrAzY!
## Post #3
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-05-26T03:43:23+00:00
- Post Title: Halo/Halo 2 Support?

Any chance we could get a file to look at please?

If the files are too large, you can use one of our cutter programs to give us the bits of the archive we need. My cutter is at [http://www.watto.org/extract/download/cutter.zip](http://www.watto.org/extract/download/cutter.zip) , and Mr Mouse also has a cutter somewhere (i think you can get his from [http://multiex.xentax.com](http://multiex.xentax.com)). You will need Java installed to use my cutter. When you use any of the cutter programs, it will make a *.zip file that you can email to us.

Thanks mate.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #4
- Username: Storm
- Rank: beginner
- Number of posts: 21
- Joined date: Mon May 23, 2005 3:32 am
- Post datetime: 2005-05-26T05:25:48+00:00
- Post Title: Halo/Halo 2 Support?

Done and done, didn't know what was required of me. Thanks in advance!
## Post #5
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-26T07:33:18+00:00
- Post Title: Halo/Halo 2 Support?

Okay, the request rules are at the top of this forum.  

Anyway, I haven't recieved any files yet. 

Did you send them to  with a MULTIEX subject line?

You can also ATTACH them to this thread by the way.
## Post #6
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-26T11:25:11+00:00
- Post Title: Halo/Halo 2 Support?

In the meantime, here's a script that will extract from the HALO PC DEMO map files. 

```
If MAPType < 256 ;
Get NamesOffset Long 0 ;
Get InfoOffset Long 0 ;
Get FileNum Long 0 ;
GoTo InfoOffset 0 ;
For T = 1 To FileNum ;
Get NamePos Long 0 ;
Math NamePos += NamesOffset ;
SavePos FSO 0 ;
Get FileSize Long 0 ;
SavePos FOO 0 ;
Get FileOffset Long 0 ;
SavePos CP 0 ;
GoTo NamePos 0 ;
Get FN String 0 ;
GoTo CP 0 ;
Log FN FileOffset FileSize FOO FSO ;
Next T ;
Else ;
Set FO Long 0 ;
GoTo EOF 0 ;
SavePos FS 0 ;
Math FS += 1 ;
Set FN String thefile.map ;
Log FN FO FS 0 0 ;
EndIf ;

```

[map.zip](https://xentaxbackup.github.io/file/257_map.zip)
## Post #7
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-05-26T13:24:52+00:00
- Post Title: Halo/Halo 2 Support?

NOTE: Halo 1 had 2 different *.map files - some were maps and others were archives. The script Mr Mouse gave above is for the Halo 1 *.map archives.

Now, the file you sent was an actual map file, with a very similar structure to the maps in Halo 1. The file was not an archive, and I do not know enough about the maps to be able to decode them properly.

Sorry about that 

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #8
- Username: Storm
- Rank: beginner
- Number of posts: 21
- Joined date: Mon May 23, 2005 3:32 am
- Post datetime: 2005-05-27T07:52:58+00:00
- Post Title: Halo/Halo 2 Support?

Alright, thats what I thought. All the halo 2 map editors was basically all hex edit with plugins to help out, not really any extraction at all. I thought.. maybe.. JUST MAYBE.. lol oh well, thanks for trying
## Post #9
- Username: Zico
- Rank: VIP member
- Number of posts: 5
- Joined date: Sun Apr 10, 2005 5:46 am
- Post datetime: 2005-06-03T14:17:25+00:00
- Post Title: Halo/Halo 2 Support?

storm just wait for prometheus: 
[http://www.halodev.org](http://www.halodev.org)

It will be able to do everything!
