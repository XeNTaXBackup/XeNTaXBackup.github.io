## Post #1
- Username: martanius
- Rank: advanced
- Number of posts: 42
- Joined date: Thu Aug 10, 2017 7:47 am
- Post datetime: 2021-12-18T04:48:45+00:00
- Post Title: Can't find text in files of a unity game

Hello. I'd like to translate a game called She Will Punish Them.

I used UnityEx to find a .txt localization file with a lot of texts. But it seems the game does not use all of them and is loading them from a different files. And some texts are not even in the localizaton file at all.

I encountered such text in game already, but I was able to find it in a monobehavior file and once I changed it and import back in the game, it worked.

But this text is something else:

[](https://ibb.co/VMbdf6q)

I'd like to translate "Slaver" but it is not in the text localization file at all. So what I tried:

I used TotalCommander method to find the string in game files and it found it inside these:
[](https://ibb.co/K96Dxwd)

I used UnityEx to find text Slaver and it was found in these files:
Level1
-UISlaver.gobj
-Slaver.gobj
-Btn Close (3)_00001.Button
-Tittle(2)_00006.Text

The only file with exact match of text I'm looking for was the last one. It's a monobehaviour file and it contains this line:
<m_Text type="string" value="Slaver"/>
So I changed it but to no avail. The game still shows the original text.
Level10
-UISlaver.gobj
-Btn Close (3)_00004.Button
-Tittle(2)_00002.Text

Again, the only file with exact match of text I'm looking for was the last one. It's a monobehaviour file and it contains this line:
<m_Text type="string" value="Slaver"/>
So I changed it but to no avail. The game still shows the original text.
It was almost the exact same file as before. Only some variables were changed.
Level15
-UISlaver.gobj
-Btn Close (3)_00004.Button
-Tittle(2).Text

Again, the only file with exact match of text I'm looking for was the last one. It's a monobehaviour file and it contains this line:
<m_Text type="string" value="Slaver"/>
So I changed it but to no avail. The game still shows the original text.
It was almost the exact same file as before. Only some variables were changed.
globalgamemanagers.assets
-Slaver.script
-UISlaver.script

These are just scripts. I found a tool and extracted the scripts itself from them and this is how they look like:

Slaver.cs

```
using UnityEngine;


public class Slaver : MonoBehaviour
{ 
public Transform[] possibleSlaves;

public CommonArray slaves;

public int refreshTimer;

public int lastPlayerLevel;

private void Start()
{ 
base.InvokeRepeating("CS", 1f, 1f);
this.Refresh();
}

private void CS()
{ 
this.refreshTimer++;
if (this.refreshTimer > 500)
{ 
this.Refresh();
}
}

public void InitiateInteract()
{ 
Global.code.uiSlaver.Open(this);
}

public void QuitInteract()
{ 
Global.code.uiSlaver.Close();
}

public void Refresh()
{ 
this.slaves.ClearItems();
if (this.slaves.items.Count < 10)
{ 
Transform[] array = this.possibleSlaves;
for (int i = 0; i < array.Length; i++)
{ 
Transform transform = array[i];
for (int j = 0; j < 4; j++)
{ 
if (UnityEngine.Random.Range(0, 100) < 50 && transform)
{ 
this.slaves.AddItem(transform);
}
}
}
}
array
i
transform
j
}
}

```

UISlaver.cs

```
using UnityEngine;


public class UISlaver : MonoBehaviour
{ 
public Transform iconPrefab;

public Transform iconGroup;

public AudioClip sndHire;

public Slaver curSlaver;

public void Open(Slaver slaver)
{ 
this.curSlaver = slaver;
base.gameObject.SetActive(true);
for (int i = 0; i < this.iconGroup.childCount; i++)
{ 
if (this.iconGroup.GetChild(i))
{ 
UnityEngine.Object.Destroy(this.iconGroup.GetChild(i).gameObject);
}
}
foreach (Transform current in slaver.slaves.items)
{ 
if (current)
{ 
Transform expr_80 = UnityEngine.Object.Instantiate<Transform>(this.iconPrefab);
expr_80.SetParent(this.iconGroup);
expr_80.localScale = Vector3.one;
expr_80.GetComponent<SlaveIcon>().Initiate(current.GetComponent<Monster>());
}
}
i
enumerator
current
expr_80
}

public void Close()
{ 
base.gameObject.SetActive(false);
}
}

```


I don't think the game is loading the text from these scripts.

And of course there could be more of texts like this in the game.

Do you have any idea where the game could be loading the text from?
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-12-18T14:36:49+00:00
- Post Title: Can't find text in files of a unity game

From what you are saying I can assume that you have checked all files except "Assembly-Csharp.dll".
Try to open this file in hex editor (like Hex Workshop) and seach for occurences of "Slaver" word.
Then change one letter in this word like "Slaver" --> "Zlaver" in hex editor and see if it will change in game.

If it won't work for "Assembly-Csharp.dll", try to do this for every file that was found by total commander.
## Post #3
- Username: martanius
- Rank: advanced
- Number of posts: 42
- Joined date: Thu Aug 10, 2017 7:47 am
- Post datetime: 2021-12-18T17:26:03+00:00
- Post Title: Can't find text in files of a unity game

Thank you. It worked with Level1.

There were 2 occasions of th "Slaver" text. One for the monohebavior and one for a filename.
There is a file in Level1 archive called Slaver.gobj and using Hexeditor I could change that filename and it changed in the game.

Of course I can't exceed string length. Is there a way to change a filename inside unity archive? Apart form hexeditor.
## Post #4
- Username: martanius
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-12-19T01:09:06+00:00
- Post Title: Can't find text in files of a unity game

> Is there a way to change a filename inside unity archive? Apart form hexeditor.

You could try to use combination of UnityEx [https://forum.zoneofgames.ru/topic/36240-unityex/](https://forum.zoneofgames.ru/topic/36240-unityex/)
and UnityText [https://forum.zoneofgames.ru/topic/47582-unitytext/](https://forum.zoneofgames.ru/topic/47582-unitytext/)

But maybe there are some better tools, I'm not sure.
## Post #5
- Username: martanius
- Rank: advanced
- Number of posts: 42
- Joined date: Thu Aug 10, 2017 7:47 am
- Post datetime: 2021-12-19T09:43:52+00:00
- Post Title: Can't find text in files of a unity game

UnityText worked fine. I was able to change the text 

Thank you.
