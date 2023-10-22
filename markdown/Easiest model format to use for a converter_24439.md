## Post #1
- Username: jfwfreo
- Rank: veteran
- Number of posts: 124
- Joined date: Sat Nov 15, 2008 8:31 am
- Post datetime: 2021-09-01T04:27:00+00:00
- Post Title: Easiest model format to use for a converter?

I have a custom 2D format that contains textured triangles (so basically its got x,y coordinates, RGBA color and optionally u,v texture coordinates and a reference to a texture name) and I want to write a converter into another more standard 3D format.

Can anyone suggest a format that is simple to work with and write files out in (just need to write out, not parse or read in) and that is easy to view or display?
## Post #2
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2021-09-01T10:48:55+00:00
- Post Title: Easiest model format to use for a converter?

I prefer the obj format for a lot of things.
Text based and easy to work with.

One project I did was to take a terrain height file used in Silent Hunter 5 and convert it to an obj file for easy editing.
Then We convert it back to the SH5 terrain height format.

I wrote 2 scripts for SweetScape 010 that does the conversions.
