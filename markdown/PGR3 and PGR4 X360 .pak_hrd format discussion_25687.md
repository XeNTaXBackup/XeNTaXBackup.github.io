## Post #1
- Username: UB833
- Rank: advanced
- Number of posts: 79
- Joined date: Tue Jan 04, 2022 4:55 pm
- Post datetime: 2022-08-10T13:59:53+00:00
- Post Title: PGR3 and PGR4 X360 .pak_hrd format discussion

Ik that no one in this community has researched about PGR3 and PGR4 X360 file formats but this topic needed to be revived for extracting .pak_hrd archive. I've used QuickBMS or Offzip for extracting the archive but after the extraction, it came with .dat file whether I could identify that it is a "model" or "texture" files. Mostly these two games runs on Bizzare Creation so this needs a full research about the files specifically.

Sample file (.pak_hrd): [https://mega.nz/file/4KwiGDqD#0pyDuAiaX ... 7Zy1ozK9Mg](https://mega.nz/file/4KwiGDqD#0pyDuAiaXsVQW1QBivgCEtny3O2FUUDoV7Zy1ozK9Mg)

After extracting .pak_hrd files using offzip (.dat): [https://mega.nz/file/RLJ1CZyD#iDkKyh4W7 ... GRIIeTE1I4](https://mega.nz/file/RLJ1CZyD#iDkKyh4W7p0I51bdkKC2krjF6CWpwkWTgGRIIeTE1I4)

If the .dat files are observed, anyone I mean ANYONE, would create a Noesis plugin or Blender Plugin for importing the model and extracting the textures at correct UV mapping and better normals.

Thx in advance.
## Post #2
- Username: Machinedramon
- Rank: advanced
- Number of posts: 77
- Joined date: Tue Apr 09, 2019 1:13 am
- Post datetime: 2022-08-10T22:54:01+00:00
- Post Title: PGR3 and PGR4 X360 .pak_hrd format discussion

If you had check a little better the forums you would see that there is in fact people who have researched both games, or rather all the project gotham racing games, that there is no public models does not mean that it has not been tried before.

As mentioned in the other thread about PGR3/PGR4, if you intend to extract the files properly, first of all the main problem lies with the compression, using offzip will not get you files you would be able to work with, faces and mesh data is split in different files which makes it partly hard to work with the data, that and also there is extensive information like illuminance color for vertexes and other stuff to take into account. Also the textures use swizzle, there is an easy way of bypassing that using some noesis script but needs to be adapted cause it is not as simple...(also regarding the compression, headers are not, only the contents, most information regarding sizes and offsets be in headers)

Only because of those troubles is enough to discourage most of hobby rippers, so yeah if you really think anyone can go code a noesis script, suit yourself, if it isn't that hard you should be able to pull it off, the information is there.


Pro tip, somebody said in the other thread you can rip using ninja ripper and xenia, you got way better chances doing that if you are in a hurry to rip models honestly...

Cheers
## Post #3
- Username: UB833
- Rank: advanced
- Number of posts: 79
- Joined date: Tue Jan 04, 2022 4:55 pm
- Post datetime: 2022-08-11T09:45:42+00:00
- Post Title: PGR3 and PGR4 X360 .pak_hrd format discussion

> Reply from Machinedramon ↑Thu Aug 11, 2022 6:54 am at Thu Aug 11, 2022 6:54 am
>
> 
Pro tip, somebody said in the other thread you can rip using ninja ripper and xenia, you got way better chances doing that if you are in a hurry to rip models honestly...

Cheers

I have Xenia and two games, but the problem is that latest Ninja ripper requires Patreon donation and I do not have real money to purchase Ninja ripper to do it's job so it's impossible to use Ninja ripper without patreon subscription. thx for the tip but I may not do that since I'm a cheap person. But thx for the reply
