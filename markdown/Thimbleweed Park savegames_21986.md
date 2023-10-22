## Post #1
- Username: scemino
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Apr 09, 2020 8:19 pm
- Post datetime: 2020-04-09T12:30:37+00:00
- Post Title: Thimbleweed Park savegames

Is there someone can help me do reverse engineering on the savegames of Thimbleweed Park?
Here is some information about it: [https://blog.thimbleweedpark.com/savegame](https://blog.thimbleweedpark.com/savegame)

I'm the author of engge [https://github.com/scemino/engge](https://github.com/scemino/engge), this is an open source game engine which is able run Thimbleweed Park, an awesome adventure game by Ron Gilbert.
Now the big limitations are the savegames.
It would be very nice to be able to load and save the original savegames. With your help, maybe it's possible.
Thank you
## Post #2
- Username: scemino
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Apr 09, 2020 8:19 pm
- Post datetime: 2020-04-11T12:12:03+00:00
- Post Title: Thimbleweed Park savegames

Good news: I have made some progress, I bypassed the function which encrypts the data and I get the same structure as in a ggpack file (the one starting with the signature 0x04030201
Here is an example of 1 savegame converted to json, I had to remove some parts due to the size of the content

```
  "actors": {
  "bankmanager": {
      "_costume": "BankMgrAnimation",
      "_dir": 2,
      "_lockFacing": 0,
      "_pos": "{541,61}",
      "_roomKey": "Bank",
      "defaultVerb": 3,
      "detective": 0,
      "dialog": null,
      "enterWalk": 10,
      "flags": 3158024,
      "gender": 3145728,
      "last_selected": 0,
      "name": "@30103",
      "rambleTID": 0,
      "sawRaysBadge": 0,
      "sawReyesBadge": 0,
      "selectable": 0
    },
    // other actors,
  },
  "callbacks": {
    "callbacks": [],
    "nextGuid": 8000000
  },
  "currentRoom": "Bridge",
  "dialog": {},
  "easy_mode": 1,
  "gameGUID": "",
  "gameScene":
  "actorsSelectable": 0,
    "actorsTempUnselectable": 0,
    "forceTalkieText": 0,
    "selectableActors": [
      {
        "_actorKey": "ray",
        "selectable": 0
      },
      // etc.
      ]
  },
  "gameTime": 1003.47,
  "globals": {
  {
    "abducted_agent": null,
    "abducted_agent_seen": 0,
    "act1": 1,
    "act2": 0,
    "act2_delores_intro": 0,
    "act2_franklin_intro": 0,
    "act2_ransome_intro": 0,
    "act3": 0,
    "act4": 0,
    "act4_ransome_done": 0,
    "act4_ray_done": 0,
    "act4_reyes_done": 0,
    "activeRatHole": {
      "_objectKey": "bigtopHole4"
    },
    "actorGreetingTID": 10000375,
    "agent_kidnapped": 0,
    "agent_needs_dime": 0,
    // etc.
    },
  "inputState": 101,
  "inventory": {
    "slots":
    [
      {
        "objects": [
          "raysBadge",
          "raysNotebook",
          "cellPhone"
        ],
        "scroll": 0
      },
      // etc.
      ]
  },
  "objects":
  "aStreetArcadeDoorWF": {
      "flags": 1073742912,
      "name": "@29000"
    },
    // etc.
    },
  "rooms": {
    "AStreet": {
      "background": "AStreet",
      "speck_of_dust": 1,
      "speck_of_dust_collected": 0
    },
    // etc.
    },
  "savebuild": 958,
  "savetime": 1586606075,
  "selectedActor": "boris",
  "version": 2
}

```
