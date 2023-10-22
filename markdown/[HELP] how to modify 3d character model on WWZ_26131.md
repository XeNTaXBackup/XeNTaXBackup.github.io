## Post #1
- Username: villynx
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Dec 30, 2022 2:37 am
- Post datetime: 2022-12-30T14:58:13+00:00
- Post Title: [HELP] how to modify 3d character model on WWZ?

Hello so I'm trying to modding WWZ, and I'm a newbie at modding game textures. So far I can only change the texture of some characters or even weapons, not make some changes or add something to the 3d model. The structure of the WWZ model as far as I know is, the texture or skin of an object (2d or texture atlas) is stored on 'shared_texture.pak'(for high resolution) and 'shared_texture_base.pak' (for low resolution). Those two files can be opened with WinRAR and the file inside it can be extracted. After the content inside it is extracted, the format or the file extension on 'shared_texture.pak' is '.pct' and '.pct_header'. While on 'shared_texture_base.pak' is only '.pct_base'.  Here is some example of the content from those 2 folders:
[](https://postimg.cc/vDx7KLgp)
(from 'shared_texture.pak')
and
[](https://postimages.org/)
(from 'shared_texture_base.pak')
From those files, I can only edit them (mostly recoloring or adding images or text) on photoshop with help from 'QCPCT' software and convert them from '.pct' to '.tga' and convert them back with 'QCPCT'.

While the 3d model is stored on 'shared_tpl.pak'. The content of 'shared_tpl.pak' is only a 3d model including the mesh and others. The content of 'shared_tpl.pak' is a file that has '.tpl' extension or format. Until now I can only edit or recolor the 2d texture and I can't figure out how to modify the 3d model. For the 3d model so far I only know how to view the inside of tpl file, with 'QCVIewer' from this thread: [viewtopic.php?p=159829&hilit=wwz#p159829](https://forum.xentax.com/viewtopic.php?p=159829&hilit=wwz#p159829)

This is some example of the model using 'QCVIewer' :
(from 'shared_tpl.pak')
[](https://postimg.cc/ppJmcqxV)
The 3D model can be seen, but not with the texture and I can't edit it.

I tried to find a way to edit the 3d models, but it seems I'm stuck with my current information. I already tried 'Noesis' and 'Ninja Ripper 2'. The result from 'Noesis' is that I can't open the tpl files, it gives this error while I'm trying to open '.tpl' file "File could not be previewed."
While the result from 'Ninja Ripper 2' is more worst. When I try to import all the 'mesh_x_x.nr', my 'Blender' software is crashed. I already add on 'add-ons' and already enabled the 'Import-Export: Import Ninja Ripper 2.' I already try to import every 10 'mesh_x_x.nr' but the result is distorted on the blender, I already try to change the 'FOV_Y(degrees)' but didn't change anything. Besides that, it will take a long time too if I try to import it every 10 'mesh_x_x.nr' cause there are 749 files of 'mesh_x_x.nr'.

So to summarize my problem, I have several questions:
1. How to edit the 3D models ('.tpl' format) on Blender?
2. If Blender can't open '.tpl' format, is there any 3D software that can open and modify '.tpl' format?
3. If I can edit the 3D models and I'm done modifying them, how to add or replace them back on 'shared_tpl.pak' ? Because I only know that I can do that for the '.pct' format with 'QCPCT' software.

I can provide more information if needed on the thread comment.
If there are any modders that can help me solve my problem or tell me some steps by discussing it, thank you.
