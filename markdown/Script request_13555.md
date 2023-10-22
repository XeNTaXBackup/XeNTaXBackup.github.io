## Post #1
- Username: Hayden Tenno
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Nov 22, 2015 10:05 am
- Post datetime: 2015-11-22T02:10:12+00:00
- Post Title: Script request

I need a scrip that makes all normals opposite from each other the same.
## Post #2
- Username: Seyren
- Rank: advanced
- Number of posts: 63
- Joined date: Sat Oct 30, 2010 8:39 pm
- Post datetime: 2015-11-30T02:55:03+00:00
- Post Title: Script request

You can do this manually in 3DS Max by selecting the normal modifier on the whole model.

If you want to do this via script, an easy way i can think about right now is just doing this thing via script.

You should before consider seeing how are you placing the vertices of the model to fix the normals, since you are probably putting them wrong if you are asking for this. You should check if the triangles you are calling are being saved Clockwise or counter clock wise. 



This means that they will be seen from a side or another depending on how you placed them in the array.

But if you can't, just look at the MS API.

An example would be:

For adding it to the selected nodes.

```
modpanel.addmodtoselection myNormal

```


Or just directly to a specific node:

```
addModifier <node> <modifier> [before:index] 
```


There are various ways to do this. Then you might want to collapse the stack to apply it to the geometry, you can do this using
the collapseStack <node> line.
