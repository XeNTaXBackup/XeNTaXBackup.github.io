## Post #1
- Username: RayTrace77
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Nov 30, 2014 4:05 am
- Post datetime: 2016-11-20T17:41:58+00:00
- Post Title: Dishonored 2 Audio Data

Hey,

Managed to extract the .resources files using quickbms but the audio related files, the .decl files seem to point to another file which might be in the .sharedrsc file, anyone know how to extract that ?. so you'll have a file like "bsp_ai_dist_smoke_exhale.decl" and it will have in it:

{
edit = {
m_EngineID = {
m_Name = "BSP_AI_Dist_Smoke_Exhale";
m_ID = 4101515222;
}
m_Spatialized = true;
m_MaxDistance = 25;
}
}

Any help is greatly appreciated.
## Post #2
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2016-12-09T21:08:57+00:00
- Post Title: Dishonored 2 Audio Data

Game uses WWise Audio system. so like all games using WWise, the audio data is in the pck directory, in the *.pck files. Search the forum on how to unpack PCK files and convert WWise Audio.
