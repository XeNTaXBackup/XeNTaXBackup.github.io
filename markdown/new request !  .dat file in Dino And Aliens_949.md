## Post #1
- Username: digitalmad
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Oct 15, 2004 8:57 am
- Post datetime: 2004-10-15T01:12:23+00:00
- Post Title: new request !  .dat file in "Dino And Aliens"

Dino And Aliens can be downloaded from[http://zone.msn.com/en/root/deluxe.htm? ... _lnk&ln=en](http://zone.msn.com/en/root/deluxe.htm?code=110225310&genre=Puzzle&RefId=123456&Session=&origin=pindex_mp_lnk&ln=en)

animations.dat,characters.dat,geomobjs.dat,textures.dat and levels are all i want to extract,Can you help me?Thanks.
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-10-16T13:51:59+00:00
- Post Title: new request !  .dat file in "Dino And Aliens"

This will let you extract the stuff as it is saved in the files. Note that you will have to find out for yourself the format of each separate file. For instance, .JPGs are files the authors saved in the archive, but they have done something to the format, so you can't readily show them as JPGs. 

Get the dat.bms attached here and run Custom BMS On.. option in MultiEx Commander. 

If you're interested in that sort of thing, this is the script it represents:

SavePos START 0 ;
GoTo EOF 0 ;
SavePos END 0 ;
GoTo START 0 ;
Do ;
Get FN String 0 ;
Get FS Long 0 ;
SavePos FO 0 ;
SavePos START 0 ;
Log FN FO FS 0 0 ;
Math START += FS ;
GoTo START 0 ;
While START <= END ;


Anyway, it may not work using the custom bms option, so I will add it to the online base soon. When I do, I'll post it here, and you can use the update function from MultiEx Commander to download it to your computer.
[dat.zip](https://xentaxbackup.github.io/file/79_dat.zip)
## Post #3
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-10-17T00:24:39+00:00
- Post Title: new request !  .dat file in "Dino And Aliens"

Mr.Mouse,thanks your quick reply.
it can not run.
I'm interesting at MultiEx Commander.but I dont know how to write MultiEx Scripts.where's the toturials.thanks again.
## Post #4
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-10-18T20:27:42+00:00
- Post Title: new request !  .dat file in "Dino And Aliens"

What does not run exactly? Please be more specific. 

Anyway, you can get the mc.rf file to use here, then you can just select Dino and Aliens from inside MultiEx Commander. 

[viewtopic.php?p=5366#5366](http://forum.xentax.com/viewtopic.php?p=5366#5366)
## Post #5
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-10-19T04:57:48+00:00
- Post Title: new request !  .dat file in "Dino And Aliens"

thanks a lot!
I had extracted the files.but they have done something to the format.how could I can show them?and what tools can open .msh file?
thanks again.
## Post #6
- Username: digitalmad
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Oct 15, 2004 8:57 am
- Post datetime: 2004-10-19T16:00:12+00:00
- Post Title: new request !  .dat file in "Dino And Aliens"

Mr mouse:
I think that the files extracted from .dat files still are encoded.
Because there is a file "arrow.tga"  in texture.dat.it should be mouse's pics.
I copied the game's sreen and found mouse's pics is 32*32 in dimention.
But arrow.tga is bigger than 60kb.

and I opened arrow.tga with Hex Workshop,found it"s not a ASCII file.
## Post #7
- Username: Brandondorf9999
- Rank: n00b
- Number of posts: 14
- Joined date: Sat May 12, 2012 10:08 am
- Post datetime: 2012-05-12T02:34:51+00:00
- Post Title: new request !  .dat file in "Dino And Aliens"

I tried to do that but its not doing the scripts right. Could someone update the instructions for this please?
## Post #8
- Username: Bogus
- Rank: advanced
- Number of posts: 75
- Joined date: Sat Oct 30, 2010 6:57 pm
- Post datetime: 2012-07-19T12:04:17+00:00
- Post Title: new request !  .dat file in "Dino And Aliens"

is script to this game for quickbms
[viewtopic.php?f=10&t=9178](http://forum.xentax.com/viewtopic.php?f=10&t=9178)
this script decrypts files
