## Post #1
- Username: Raijinmaru
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Feb 19, 2011 12:37 pm
- Post datetime: 2011-12-17T11:04:29+00:00
- Post Title: Arc Rise Fantasia models: Luminous Arc cameo characters

I'm not asking for the models, I'm just asking in which file they might be located in, because I've extracted the playable characters, enemies characters, monsters and bosses already.  I've ran into a wall trying to find the file that stores their model.  If anyone has any info on the models and what method they used to extract them, please share your wisdom with me please and Thank you.
## Post #2
- Username: reizu
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jun 03, 2010 6:31 am
- Post datetime: 2011-12-22T18:12:51+00:00
- Post Title: Arc Rise Fantasia models: Luminous Arc cameo characters

The models are in btl_enemy.vld file. Darkfox made a list of all the models that it has: [viewtopic.php?p=48887#p48887](http://forum.xentax.com/viewtopic.php?p=48887#p48887)

Here's an example:



This is how I did it:

1.Extracted encrypted BTEM files from btl_enemy
2.Decrypted all the BTEM files using  lz77ex.exe (Slow process)
3.Extracted all RTDP/Vol files from every BTEM
4.Extracted Brres and other files from RTDP/Vol

Alternatively you could try to only extact the BTEM files that have Luminous characters. This should work:

I'm using HxD hex editor

1. Use hex editor and extract 248-250th BTEM files from btl_enemy.vld. These files have the vols that have opt_lum000(Lucia), opt_lum010 (Venessa), opt_lum020 (Saki) brres files.
2. All in all there should be 270 encrypted BTEM files in btl_enemy, so from the end of the file use your hex editors search to find BTEM strings
3. When you find the 20th BTEM go six more bytes backward and copy the offset. This will be the end offset for 250th BTEM file
4. Use search one more time to next BTEM. This time move 5 bytes backwards. Now you have the beginning and ending offsets for 250th BTEM file. 
5.Were already next to the ending offset of the 249th BTEM file, so move one more byte to backward and copy this offset too.
6.Select a block(Ctrl+e) by putting in the offsets for start and beginning.
7.Copy the block to a new file. Check that the very first byte has a hex value of 10 and save it. 
8.Repeat step 4-6 for 248-249 BTEM files

9.Use lz77ex.exe to decrypt the file. 
10.The files still have some useless garbage at the beginning. Do one seach for RTDP string copy the offset, now delete everything before it manually or select a block(ctrl+e) by using 0 as starting offset and the copied offset as ending and hit delete. (Make sure that you didn't delete any letters from RTDP, if you did write them again). Save the file
11. Use the quickbms script
12. You finally have your brres model files & some brcha animation files, Enjoy!

One more thing you should know. Usually the BTEM files have more than one RTDP/Vol file but lz77ex will only extract the first one. If you want all the RTDP files, you need to separate them from the file.
## Post #3
- Username: Raijinmaru
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Feb 19, 2011 12:37 pm
- Post datetime: 2011-12-28T07:02:50+00:00
- Post Title: Arc Rise Fantasia models: Luminous Arc cameo characters

Thankyou Reizu with the guide in extracting the models out of the file.  

I made a quick picture of the three all together in a pose using brresviewer by following the instructions:
