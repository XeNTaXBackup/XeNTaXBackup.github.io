## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-26T02:27:45+00:00
- Post Title: Checksums in archives

Archives usually come with some sort of checksum.
Do they usually pose a big problem when trying to re-pack files? For example if you change a file, you have to re-compute the checksum, etc.
## Post #2
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-03-31T08:58:47+00:00
- Post Title: Checksums in archives

Usually games won't actively check the checksum against that of the data itself, because that poses extra load time overhead. So in those cases you're actually more likely to have success if you intentionally leave the original hash in place. That isn't true for all games though. And often games will enforce the hash only on certain types of data, like scripts or materials, to ensure validity and/or up-to-date status.
