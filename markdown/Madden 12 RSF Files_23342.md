## Post #1
- Username: deerlybeloved
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Jan 20, 2021 1:08 am
- Post datetime: 2021-01-19T20:25:51+00:00
- Post Title: Madden 12 RSF Files

I've recently been looking through the AST files of Madden 12, I've encountered multiple RSF files. These files contain geometry and material parameters. While I've been successful in extracting the textures, I've been unable to extract any of the geometry. I've attached one of the files in question, I believe this one should contain six submeshes total. If anyone can help or point me in the right direction, I'd really appreciate it!
[MASCOT_BEARS.zip](https://xentaxbackup.github.io/file/19337_MASCOT_BEARS.zip)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-01-20T15:06:28+00:00
- Post Title: Madden 12 RSF Files

Using hex2obj (view link in my sig):
.



MASCOT_BEARS-RSF.png (124.4 KiB) Viewed 113 times

Checked one sub mesh only.

Be aware that you need to switch to HF_ to get proper uvs.
You can combine two obj files to one (File / SaveAs mesh with ShortAll then with HF_all)
by replacing the uvs in the 1st file with those from the 2nd one).

If you don't understand this you might try AMR.
## Post #3
- Username: deerlybeloved
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Jan 20, 2021 1:08 am
- Post datetime: 2021-01-20T17:14:26+00:00
- Post Title: Madden 12 RSF Files

Thanks so much for your help! I've been able to extract 4 of the 6 submeshes from the file. These include Submesh 1 (the Head), 3 (Right Arm), 5 (Legs), and 6 (Feet).
Unfortunately, I've been experiencing trouble trying to extract the 2nd and 4th submesh.



mistake.png (75.77 KiB) Viewed 103 times


I believed the addresses were 0x40D10 for faces and 0xF526 for vertices on the 2nd submesh, while the 4th submesh was 0x4830A for faces and 0x24620 for vertices. However, I'd just end up with a mess of a mesh. (as seen above)
What am I doing wrong here?
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-01-20T18:47:16+00:00
- Post Title: Madden 12 RSF Files

4th submesh is left arm, looks ok to me with your parameters.

For a part of the shirt ("2nd sub mesh") use an FVFsize of 32 .
## Post #5
- Username: deerlybeloved
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Jan 20, 2021 1:08 am
- Post datetime: 2021-01-20T20:07:27+00:00
- Post Title: Madden 12 RSF Files

I'm pleased to report the model is complete!
I am incredibly grateful for your help, thank you so much!



complete.png (76.37 KiB) Viewed 92 times
