## Post #1
- Username: UberBlack
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Oct 23, 2009 3:54 am
- Post datetime: 2011-02-01T16:46:29+00:00
- Post Title: Crysis 2

In testing the new CGF format. It is very different from Crysis. Below I have included a link to the demo files that have been zipped fro someone who would like to look at this format. Crysis2 I am sure it has amazing models and it would be a worth while format to support, as I am sure many more games will be released with CryEngine3.

*Note: It truly is unfortunate that we don't have a means of importing Crysis into 3DSMAX with weighting and bones yet. Maybe we can change that with Crysis2.

[http://uberblack3d.com/articles/crysis-2/](http://uberblack3d.com/articles/crysis-2/)
## Post #2
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2011-02-16T13:32:55+00:00
- Post Title: Crysis 2

Format doesn't seem to have changed much.  Header added a data size value making them 0x14 bytes now instead of 0x10 bytes.  Some data chunks also no longer duplicate the chunk header information in the actual chunk data.  There also seems to be a flag to indicate when data is big endian, instead of little endian (chunk header information is always little endian it seems).

Other than that everything seems to still match up.  i now have more information on the Compiled chunk data, so meshes that use that instead of the other Bone related chunks can hopefully be weighted now, will have to see.

Once i get materials loading and test the other findings, should be good to go.

Any other cgf file from earlier crytech engine games could be helpful.  Don't have any currently that are not based on the Compiled chunks added by Crysis and above.

Will have to see how things go.
