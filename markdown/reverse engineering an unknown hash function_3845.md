## Post #1
- Username: jfwfreo
- Rank: veteran
- Number of posts: 124
- Joined date: Sat Nov 15, 2008 8:31 am
- Post datetime: 2009-11-07T13:08:00+00:00
- Post Title: reverse engineering an unknown hash function

The game I am working with (red alert iPhone) stores file names in the VFS as hashes. I am trying to reverse engineer the hash algorithim but I dont understand enough about ARM assembly to do so. Anyone got any tips on reverse engineering this hash (or figuring out the ARM assembly?)
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-11-07T13:20:44+00:00
- Post Title: reverse engineering an unknown hash function

That's not going to be easy, as the ARM compilers/emulators for your PC out there are frankly lacking substance to be helpful. I've been trying to do this with a Nintendo DS game, to no avail.
## Post #3
- Username: jfwfreo
- Rank: veteran
- Number of posts: 124
- Joined date: Sat Nov 15, 2008 8:31 am
- Post datetime: 2009-11-07T13:29:36+00:00
- Post Title: reverse engineering an unknown hash function

If it helps, I actually found the hash function itself in the mach-0 binary thanks to the symbol table.
