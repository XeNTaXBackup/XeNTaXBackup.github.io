## Post #1
- Username: bluearms
- Rank: beginner
- Number of posts: 29
- Joined date: Wed Oct 13, 2010 4:48 am
- Post datetime: 2015-05-01T08:19:45+00:00
- Post Title: Dynasty warriors 8 PC

There is already python script to unpack and repack.
I just reprogrammed to quickbms and some type checking code inserted to distinguish which is which.

Because lots of data are generated, make sure subdirectory is made and use that as a output.

for example
make sure this script and quickbms.exe is copied in the installed directory (where linkdata.idx and linkdata?.bin is.)
and run

mkdir out
quickbms dw8-pc.bms linkdata.idx out

g1m format has updated and old script for dynasty warriors 7 does not work.
g1t format seems same and you can use it, but main model texture seems not in the main archive, 
and there is also some padded format which contains G1M and G1T together.

some uncompressed (linkdata.idx marked as uncompressed) generated *.dat seems compressed and it is not handled yet though compressed block (linkdata.idx marked as compressed) is decompressed and generated to *.unz if it is not g1m or g1t.



 dw8-pc.rar
(2.82 KiB) Downloaded 436 times



P.S.
there was a bug in uncompressed block type checking. reuploaded.
or just fix at line 263

  goto 0x14 2 seek_cur
to
  goto 0x12 2 seek_cur

P.S.
For unhandled outputs.
the formats are simple.
If first 4 bytes are not some ID, then count and offset size blocks.
All g1m files are in fact 2 combined files with g1m and g1t.

If first embedded data offset is 0x14 and points to 4 and "MDLK" appears somewhere, then there is a another level embedded data which starts with count and size block (no offset in this case)

I found some file contains large number of g1m or g1t format embedded. extracting all of them seems pointless.
## Post #2
- Username: bluearms
- Rank: beginner
- Number of posts: 29
- Joined date: Wed Oct 13, 2010 4:48 am
- Post datetime: 2015-05-01T08:23:17+00:00
- Post Title: Dynasty warriors 8 PC

Similar script for dynasty warriors 7 PC japanese version.


 dw7-pc.rar
(3.15 KiB) Downloaded 225 times
## Post #3
- Username: adol365
- Rank: advanced
- Number of posts: 70
- Joined date: Fri Nov 21, 2014 7:21 pm
- Post datetime: 2015-05-04T11:20:49+00:00
- Post Title: Dynasty warriors 8 PC

Thanks a lot
## Post #4
- Username: JohnWason
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Aug 17, 2016 10:17 pm
- Post datetime: 2016-08-17T16:17:59+00:00
- Post Title: Dynasty warriors 8 PC

Sorry,may be it's a annoyed thing for you,but I have some question about this
1.But I can't understand how to use it to extract the Dynasty Warriors 8 PC models,Is it just like other games such as Dead Or Live 5 
2.The vision of game is Dynasty Warriors 8 OR  Dynasty Warriors 8 Xtreme Legends ？On PC just have  Dynasty Warriors 8 Xtreme Legends I was play it use all my part time 
3.In my mind :The way to extrat models is put the quickbms in the GAME FILE like data dir of just put in dir of have game.exe 
Sorry I am not good at it

It is will be my honor to have your reply 
Thanks
## Post #5
- Username: JohnWason
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Aug 17, 2016 10:17 pm
- Post datetime: 2016-08-17T17:11:49+00:00
- Post Title: Dynasty warriors 8 PC

AND another thing I should to ask is  the version of your game is Eur Or other  
I main  my vision is Japan an  Chinses Taiwan 
I am not preety sure it can works on my game 
Should I download Which vision
maybe the idk file of is same Eur and Jap 
Wish your reply
