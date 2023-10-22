## Post #1
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2018-08-28T18:14:07+00:00
- Post Title: combine and export into fbx with Noesis

I need to combine all models in folder and export result as single FBX
found this script: [https://github.com/RoadTrain/noesis-plu ... elmerge.py](https://github.com/RoadTrain/noesis-plugins-official/blob/master/Rich/tool_modelmerge.py)
does anyone know what to change/add to that script to combine and export models to single FBX with just this line of code(?):

```
"C:\Program Files (x86)\noesis\Noesis.exe" ?runtool "&Model merger" <file>
```
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-08-28T21:12:32+00:00
- Post Title: combine and export into fbx with Noesis

> Reply from Tosyk
>
>  with just this line of code(?):
Code: Select all"C:\Program Files (x86)\noesis\Noesis.exe" ?runtool "&Model merger" <file>where do you have that line from?

I assume the tool has evolved to tool_batchload_context.py. 
Try out Batch process in Noesis, menu Tools.
## Post #3
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2018-08-29T07:39:45+00:00
- Post Title: combine and export into fbx with Noesis

> Reply from shakotay2
>
> Tosyk wrote: with just this line of code(?):
Code: Select all"C:\Program Files (x86)\noesis\Noesis.exe" ?runtool "&Model merger" <file>where do you have that line from?I made it based on the help doc from noesis folder

> Reply from shakotay2
>
> I assume the tool has evolved to tool_batchload_context.py. 
Try out Batch process in Noesis, menu Tools.also I should have mentioned that I wanna skip noesis ui and do the combine/convert with a single drag&drop on the CMD batch script.

btw: original 'tool_modelmerge.py' do what I need with just a single action - by choosing tool option from RMB popup and combine all models in a folder though I want to have an addition to this tool to export result as FBX
## Post #4
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2018-08-30T07:43:54+00:00
- Post Title: combine and export into fbx with Noesis

The combined model can be exported if you chose "export from preview". How and if you can do this with a cmd solution, no idea.
## Post #5
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2018-08-30T14:05:51+00:00
- Post Title: combine and export into fbx with Noesis

> Reply from o0Crofty0o
>
> The combined model can be exported if you chose "export from preview". How and if you can do this with a cmd solution, no idea.can be done with modified tool_modelmerge.py script by the line I wrote in first message. the only question is "who can modified it?"
