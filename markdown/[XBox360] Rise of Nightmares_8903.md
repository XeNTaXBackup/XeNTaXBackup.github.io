## Post #1
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-05-07T16:20:27+00:00
- Post Title: [XBox360] Rise of Nightmares

Actually had most of this done a long time ago but had to rewrite it thanks to Onechanbara Z: Kagura lol. Currently supports only character models and weapons. Models have weights but no bones yet (I am rewriting my skeleton code at the moment to support multiple skeleton systems). Bones are easy and will come in an update in a few days. Texturing is automatic, but as always, use Photoshop actions to batch convert textures from DDS to TGA for it to work (since LW doesn't support DDS). Will also do level geometry in a bit too. Character models aren't that impressive, but the zombie models are pretty cool if you like that kind of stuff lol.

Use Luigi's CPK BMS script to extract data.
Then place ripper.exe in game root directory and run.



Want a puppy dog lol?

[ripper.7z](https://xentaxbackup.github.io/file/5405_ripper.7z)
## Post #2
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-05-07T16:27:25+00:00
- Post Title: [XBox360] Rise of Nightmares

BTW, I'm still trying to get the vertex normals out of this game, but they are encoded funny. This is a sample of the leftover unknown vertex data. 8 bytes total. I thought it might be a half-float quaternion which could be converted to a rotation matrix where you can extract normals, bitangents, etc. But no. Those FE's and 00's at the end of each DWORD are pretty consistent. Anyone see a normal-mapping encode like this before? FE is also close to 1.0, so maybe single byte quaternions, but that was a no too. Debug textfiles are generated that print out full hex dumps of the vertex data are generated for those who want to take a look!

```
42eb9cfe-eeb69d00
38e78ffe-e8c49300
47e64efe-efbb7c00
59f155fe-f8a67900
6bc215fe-fc967600
38e158fe-e4cb8400
50cd27fe-f3b16e00
69c014fe-fc8c6d00
67c719fe-fa9c7600
6f8601fe-fd886f00
7dad09fe-fd707700


```
