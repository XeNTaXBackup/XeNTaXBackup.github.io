## Post #1
- Username: meyz
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Jul 12, 2022 3:55 pm
- Post datetime: 2022-07-12T08:01:55+00:00
- Post Title: Game crash on text change [Unity]

Hello, I have a game that I want to translate. I opened the resource.assets file of the game with UnityEX and found the texts that I needed to translate in a file named "resources_00001.-13", but the game crashes when I make changes. I guess it's because my own translation contains more letters than the original. How can I make the changes I want without crashing the game?
## Post #2
- Username: brtraducoes
- Rank: advanced
- Number of posts: 41
- Joined date: Wed Sep 30, 2015 12:54 am
- Post datetime: 2022-07-12T15:06:42+00:00
- Post Title: Game crash on text change [Unity]

It is extracting or inserted wrong.
## Post #3
- Username: meyz
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Jul 12, 2022 3:55 pm
- Post datetime: 2022-07-12T19:42:02+00:00
- Post Title: Game crash on text change [Unity]

I'm pretty sure it was extracted correctly, and I discovered that the game uses the I2 localization. Could that be why?
## Post #4
- Username: brtraducoes
- Rank: advanced
- Number of posts: 41
- Joined date: Wed Sep 30, 2015 12:54 am
- Post datetime: 2022-07-13T01:36:55+00:00
- Post Title: Game crash on text change [Unity]

It has nothing to do with that.
i2 is a paid plugin for localization in unity games.
You have to extract and insert it correctly.
## Post #5
- Username: meyz
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Jul 12, 2022 3:55 pm
- Post datetime: 2022-07-13T17:30:05+00:00
- Post Title: Game crash on text change [Unity]

Which script would you recommend I use? I was using UnityEx until now.
## Post #6
- Username: brtraducoes
- Rank: advanced
- Number of posts: 41
- Joined date: Wed Sep 30, 2015 12:54 am
- Post datetime: 2022-07-13T18:27:10+00:00
- Post Title: Game crash on text change [Unity]

Each game and way of translating has to be analyzed.
What is the name of the game and what platform Pc, android ?
## Post #7
- Username: meyz
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Jul 12, 2022 3:55 pm
- Post datetime: 2022-07-13T18:51:15+00:00
- Post Title: Game crash on text change [Unity]

Otaku's Adventure
## Post #8
- Username: brtraducoes
- Rank: advanced
- Number of posts: 41
- Joined date: Wed Sep 30, 2015 12:54 am
- Post datetime: 2022-07-13T19:43:18+00:00
- Post Title: Game crash on text change [Unity]

You didn't say if it was for computer.
So I did the analysis for computer.
As I said above you extracted or inserted the wrong texts.
The game start menu and image.
You may have to create special characters.
## Post #9
- Username: meyz
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Jul 12, 2022 3:55 pm
- Post datetime: 2022-07-13T20:27:20+00:00
- Post Title: Game crash on text change [Unity]

Can you tell me how to do it, I've been trying for a long time.
## Post #10
- Username: brtraducoes
- Rank: advanced
- Number of posts: 41
- Joined date: Wed Sep 30, 2015 12:54 am
- Post datetime: 2022-07-14T17:50:01+00:00
- Post Title: Game crash on text change [Unity]

As we discussed over discord, wrong extraction of the files.
It was solved.
## Post #11
- Username: fuvegotado
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Jun 24, 2019 1:30 am
- Post datetime: 2023-02-27T00:19:17+00:00
- Post Title: Game crash on text change [Unity]

Thanks to the hints in this thread I was able to find the (horrible, horrible, horrible) translations in Tales from Candlekeep Tomb of Annihilation.

I used uTinyRipper, dragged the entire game folder in there and extracted all. The result was a 1337(lol)KB large file:

```
TalesCandlekeep\Assets\Resources\I2Languages.prefab
```


Content looks like this:

```
%TAG !u! tag:unity3d.com,2011:
--- !u!1001 &100100000
Prefab:
  serializedVersion: 2
  m_Modification:
    m_TransformParent: {fileID: 0}
    m_Modifications: []
    m_RemovedComponents: []
  m_ParentPrefab: {fileID: 0}
  m_RootGameObject: {fileID: 1035145497450118}
  m_IsPrefabParent: 1
--- !u!1 &1035145497450118
GameObject:
  serializedVersion: 5
  m_Component:
  - component: {fileID: 4909445282943530}
  - component: {fileID: 114256672560461989}
  m_Layer: 0
  m_Name: I2Languages
  m_TagString: Untagged
  m_Icon: {fileID: 0}
  m_NavMeshLayer: 0
  m_StaticEditorFlags: 0
  m_IsActive: 1
--- !u!4 &4909445282943530
Transform:
  m_GameObject: {fileID: 1035145497450118}
  m_LocalRotation: {x: 0, y: 0, z: 0, w: 1}
  m_LocalPosition: {x: 0, y: 0, z: 0}
  m_LocalScale: {x: 1, y: 1, z: 1}
  m_Children: []
  m_Father: {fileID: 0}
  m_RootOrder: 0
  m_LocalEulerAnglesHint: {x: 0, y: 0, z: 0}
--- !u!114 &114256672560461989
MonoBehaviour:
  m_GameObject: {fileID: 1035145497450118}
  m_Enabled: 1
  m_EditorHideFlags: 0
  m_Script: {fileID: 11500000, guid: 2476f3a706edee642a77791b973db19a, type: 3}
  m_Name:
  m_EditorClassIdentifier:
  Google_WebServiceURL: https://script.google.com/macros/s/AKfycbx6rgbybr4eDcp5BjXYkDHhAczeU8pBnMxfsU4QDN6laumqubhH/exec
  Google_SpreadsheetKey: 1gjBzkXy7KYFpf9JAr-K2dcxV4g_9PZUsHnRd-FhNbXo
  Google_SpreadsheetName: 'I2Loc D&D : Tomb of Annihilation Localization'
  Google_LastUpdatedVersion: 1522856111668
  GoogleUpdateFrequency: 1
  GoogleUpdateDelay: 5
  mTerms:
  - Term: MainMenuScreen/MainMenu/Button_Resume_ID
    TermType: 0
    Description:
    Languages:
    - Resume
    - Reprendre
    - Reanudar
    - Continuar
    - Fortsetzen
    - Возобновить
    - 回到游戏
    Languages_Touch:
    - 
    - 
    - 
    - 
    - 
    - 
    - 
    Flags: 00000000000000
  - Term: MainMenuScreen/MainMenu/Button_NewGame_ID
    TermType: 0
    Description:
    Languages:
    - New Game
    - Nouveau jeu
    - Nuevo Juego
    - Novo jogo
    - Neues Spiel
    - Новая игра
    - 新游戏
    Languages_Touch:
    - 
    - 
    - 
    - 
    - 
    - 
    - 
    Flags: 00000000000000
```

etc.

Anybody know a way to convert this to XML/JSON/CSV or similar by any chance?
