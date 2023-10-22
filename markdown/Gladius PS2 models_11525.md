## Post #1
- Username: xexuxjy
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Apr 10, 2014 9:35 pm
- Post datetime: 2014-05-20T13:29:08+00:00
- Post Title: Gladius PS2 models?

I've been trying to unpack some model data for the PS2 version of Gladius. I've identified the model files and managed to identify some common structures and data but have now become a bit stuck. I've got a hundred or more model files, but have picked out the 3 smallest / simplest ones to try and understand the complete format.

I've found file data that seems to contain the number of vertices and number of triangles (based on extracting a few of the models in a ps2 emulator). I think the vertex format is  position,normal,uv  , but am unable to get sensible vertex values out , nor determine if they're using indexed tri's or just duplicating vertices. 

Has anyone come across a similar format before , or offer some hints as to how to interpret the data?

Thanks

Ivy (12 vertices , 8 tri's )
0D000010000000000000000000000000030100010180096DB73F000090000080B73F0000474003800000000090000600000000004740090048C0000090000C0048C0000047400F00B73F0000FE7F158000000000FE7F1B0048C00000FE7F2100028009650000000000080000000000080008000800000010000800100010000000100008001000100380096A00810000810000810000810000810000810000810000810000810000040400011C80036D00080000030012800008000809001800000800100F001E0000C0016D0C801B00000003000000000000000000000000000000000000000000

Tree(12 Vertices ,4 tri's)
0C000010000000000000000000000000030100010180086DA6E84217C27D008095E21A0754FD0380ED1842F852FF06002E1C6805707F0F00DD123B15BCFC12808917D51FDD7C15809AED5AF9FF7F1800ADEE16EB43011E8002800865B10FEC1FD10FF70F4E0000104E00EC0F4E0000004E00EC0FB10FEC0FFB0FF90F0380086FB5BEA594A594B5BEA594B5BEB5BEA594040400011980046DB10FEC0F000009804E00000006000C80B10FEC1F18001B804E0000101200210000C0016D0C801800000004000000000000000000000000000000000000000000

MoveSelectCursor (4v , 2 tri's)
06000010000000000000000000000000030100010180046D01800180FFFF0080FF7F0180FFFF03800180FF7F00000600FF7FFF7F0000090002800465000000000010000000000010001000100380046A00007F00007F00007F00007F0404000100C0016D04800C0000000000000000000000000000000000
## Post #2
- Username: xexuxjy
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Apr 10, 2014 9:35 pm
- Post datetime: 2014-05-22T18:01:07+00:00
- Post Title: Gladius PS2 models?

included the full models for the above samples
[sample-models.zip](https://xentaxbackup.github.io/file/7363_sample-models.zip)
## Post #3
- Username: xexuxjy
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Apr 10, 2014 9:35 pm
- Post datetime: 2014-07-16T15:52:03+00:00
- Post Title: Gladius PS2 models?

Ok, so it's not the original PS2 models I mentioned (yet) . But I have got basic viewing of the GameCube versions of the models working. Code available at :

[http://code.google.com/p/xexuxjy-xna-ga ... lReader.cs](http://code.google.com/p/xexuxjy-xna-games/source/browse/trunk/Gladius/Unpacking/ModelNamer/ModelNamer/GCModelReader.cs)

Still want to understand the PS2 and XBOX formats though 

Just an update to this - i've now got it reading the skinned/skeleton based models as well (they use quite a different format) , still issues with weights and textures on it, but it loads a lot more models now. updates at google code above.
