## Post #1
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-08-19T06:27:57+00:00
- Post Title: AMR - Mesh Format Research Helper

1) Introduction

Advanced Mesh Reaper, or AMR for short, is a tool I created when playing around with MFC.

It's aimed to be a quick approach to obtain a couple of meshes with all basic attributes including positions, normal vectors, texture coordinates, and if necessary, to transform them to the target coordinate system without the assistance of extra programing or other 3D applications.

Though it can be used for format researching purpose, it's not served to be a beginner's tool. So there're not any step-by-step tutorials on specific formats.

2) Change Log

```
				Fixed a digest message displaying error resulted from v1.6.0;
				Fixed some abnormal behaviors of right-clicking on the spin controls;
				Right-click on the Del button of the Paramters to clear the entire list;
				Right-click on the Del button of the UV Settings to clear all UV slots;
				Right-click on the Del button of the Material Groups to clear the entire list.
2020.07.12 - v1.6.1		Fixed a radio button grouping issue exposed by the last update.
2020.07.11 - v1.6.0		Replaced indices distance control with more universal per-index Excess Bytes;
				Added Int21 & UInt21 datatypes for positions;
				Added Word & UInt10 datatypes for normals;
				Changes of plf format definition;
				Right-click on the vertex address spin controls to reset the values to 0;
				Right-click on the vertex stride spin controls to set to the minimum strides;
				Looking for the source data file(s) in the same directory as the plf file
				if relative path is used;
				Display position divisor factor in the digest message if short/word is used;
				Reset Pannel operation does not affect Preview options now;
				Other UI adjustments and small fixes.
2020.06.23 - v1.5.2		Fixed false alarm when directly preview using loaded param with mat groups;
				Fixed false alarms when EOF comes right after coresponding geometry data;
				Added support for passing a file to open through command line.
2020.04.18 - v1.5.1		Emergent fixes of a few newly introduced bugs.
2020.04.13 - v1.5.0		Added a "Zero Calibration" check box;
				Added support for material groups;
				Added access to the check buttons when open/save a parameter file
				in the Options menu, for OS before Vista;
				Changes on the UI and the plf file definition due to the introduced new features.
2020.03.17 - v1.4.3		Fixed stripped indices decoding orientation order;
				Placing the mesh to the viewport center during preview;
				Fixed transformation failure after previewing from list;
				Added bounding and pivot info for position digest;
				Fixed false alarm when relative address being 0.
2019.12.08 - v1.4.2		Added an option for enable/disable file verification when open a PLF;
				Changes on paramter list file definition;
				Fixed Data Interpretation display issues;
				Fixed Texcoords UI issue when loading params.
2019.12.02 - v1.4.0		Added implicit triangle/triangle strip indices generation;
				Address and Count fields support values with digital segmentation,
				like "12 ABCD" for Address, and 1,234" or "1, 234" for Count;
				Fixed BBox checkbox disabled when AllSame type is checked.
2019.11.07 - v1.3.2		Added a new data type Int10 for normal encoding;
				Fixed preview status not flushed under certain circumstances;
				Fixed open file failed when a param file has been created/opened.
2019.10.30 - v1.3.1		Fixed a parameter validation issue;
				Fixed a display issue of negative relative offsets.
2019.10.27 - v1.3.0		Added UINT8 datatype support for face indices;
				Distance control applied also to tristrips;
				Fixed naming issue during export;
				Minor bug fixes.
2019.09.12 - v1.2.0		A few small modifications;
				Fixed some UI issues.
2019.08.24 - v1.1.0		Added option for previewing all meshes in param list;
				Added support for relative source path when saving param list file;
				Fixed a couple of issues.
2019.08.19 - v1.0.1		Initial release.

```

3) User Interface
[](https://ibb.co/N1G73qZ)

Refer to the [AMR Specification](https://mega.nz/file/jIVmFABQ#pSjxIQqnB0NGmhvu0cGB5ku94qogMUgaknu4-L5eYM0) for a detailed explanation.

4) Main Features
The Multi Sources mode allows you to specify individual data files as inputs. This can be very convenient when you have raw data dumped from discrete compressed blocks.
Independent routines of handling different mesh elements, which ensures a simple, clean and user friendly interface.
Complete modules for managing the parameter list to make your work easier and faster.
Ability to handle cases where extra data is inserted in polygon indices. This is useful for files containing combined UV or normal indices.
Support of parsing position bounding box to restore the mesh to its in-game scaling.
Multiple UV channels support. By exporting to FBX format, the tool allows to export each mesh with up to 4 individual UV channels.
Flip UV option. It allows to vertically flip the UV so as to map with the textures.
Supports for normal vectors of various encodings.
Transformation options of the model including axis inversion and mesh rotations.
Assignment of material groups to polygons.
Implicit triangle/triangle strip indices generation.
Visulizes meshes, UVs and vertex normals vectors.
5) Examples Using the Tool

[](https://ibb.co/6sfpLDf)

[](https://ibb.co/cgJ3H46)
[](https://ibb.co/C9zgF9B)
[](https://ibb.co/gTTP3fF)
[](https://ibb.co/gdmHrkt)
[](https://ibb.co/JyYb06z)

6) Notes

AMR is using an external mesh viewer called ViewScene to preview the model with different attributes.
It's based on the ViewScene sample program of Autodesk FBX SDK, version 2019.2. I made some modifications myself to meet with different demands of this project. The main modifications include:
- Added codes for displaying vertex normal vectors;
- Added codes for displaying as point cloud;
- Added codes for displaying shaded wireframe;
- Changed some of the keyboard accelerators, and added a few more to interact with the scene more easily;

Still, the modified ViewScene executable along with its required libaries technically are not a part of AMR. So they do not come with this release. You should obtain these components from the link provided below and place them into the location of the AMR executable.

[ViewScene Executable](https://mega.nz/#!zYt3xCQC!dXZPIWn9r3FEuqL26ITxOEpg_fJTGcTemni2mbEG9WE) (date 2019/10/27)

7) Download
[Advanced Mesh Reaper.7z](https://xentaxbackup.github.io/file/18552_Advanced Mesh Reaper.7z)
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-08-23T16:55:41+00:00
- Post Title: AMR - Mesh Format Research Helper

Detailed Explanation on the AMR User Interface
(obsolete content removed)
## Post #3
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-12-08T06:59:37+00:00
- Post Title: AMR - Mesh Format Research Helper

Version 1.4.2 updated.
## Post #4
- Username: damndoe
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Dec 13, 2019 9:14 am
- Post datetime: 2019-12-13T08:08:15+00:00
- Post Title: AMR - Mesh Format Research Helper

Amazing tool, can you send me a DM please? I need help with just a few small things you posted and dont want to make a big topic
## Post #5
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-04-18T12:13:04+00:00
- Post Title: AMR - Mesh Format Research Helper

Updated v1.5.1: emergent fixes of a few newly introduced bugs.

Anyone using v1.5.0 should update to this version immediately.
## Post #6
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-08-02T08:34:51+00:00
- Post Title: AMR - Mesh Format Research Helper

Updated v1.6.2.
