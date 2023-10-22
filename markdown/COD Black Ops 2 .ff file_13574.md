## Post #1
- Username: A20Group
- Rank: beginner
- Number of posts: 22
- Joined date: Fri Nov 28, 2014 12:36 am
- Post datetime: 2015-11-25T15:09:49+00:00
- Post Title: COD Black Ops 2 .ff file

Hi All
How to decompress and compress .ff file in black ops 2?
Sample file From Localization File in attachment.
Help me.
Thanks
[en_karma.rar](https://xentaxbackup.github.io/file/10071_en_karma.rar)
## Post #2
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2015-11-26T02:53:27+00:00
- Post Title: COD Black Ops 2 .ff file

Heres the gold for you

```
{
  ASSET_TYPE_XMODELPIECES = 0x0,
  ASSET_TYPE_PHYSPRESET = 0x1,
  ASSET_TYPE_PHYSCONSTRAINTS = 0x2,
  ASSET_TYPE_DESTRUCTIBLEDEF = 0x3,
  ASSET_TYPE_XANIMPARTS = 0x4,
  ASSET_TYPE_XMODEL = 0x5,
  ASSET_TYPE_MATERIAL = 0x6,
  ASSET_TYPE_TECHNIQUE_SET = 0x7,
  ASSET_TYPE_IMAGE = 0x8,
  ASSET_TYPE_SOUND = 0x9,
  ASSET_TYPE_SOUND_PATCH = 0xA,
  ASSET_TYPE_CLIPMAP = 0xB,
  ASSET_TYPE_CLIPMAP_PVS = 0xC,
  ASSET_TYPE_COMWORLD = 0xD,
  ASSET_TYPE_GAMEWORLD_SP = 0xE,
  ASSET_TYPE_GAMEWORLD_MP = 0xF,
  ASSET_TYPE_MAP_ENTS = 0x10,
  ASSET_TYPE_GFXWORLD = 0x11,
  ASSET_TYPE_LIGHT_DEF = 0x12,
  ASSET_TYPE_UI_MAP = 0x13,
  ASSET_TYPE_FONT = 0x14,
  ASSET_TYPE_FONTICON = 0x15,
  ASSET_TYPE_MENULIST = 0x16,
  ASSET_TYPE_MENU = 0x17,
  ASSET_TYPE_LOCALIZE_ENTRY = 0x18,
  ASSET_TYPE_WEAPON = 0x19,
  ASSET_TYPE_WEAPONDEF = 0x1A,
  ASSET_TYPE_WEAPON_VARIANT = 0x1B,
  ASSET_TYPE_WEAPON_FULL = 0x1C,
  ASSET_TYPE_ATTACHMENT = 0x1D,
  ASSET_TYPE_ATTACHMENT_UNIQUE = 0x1E,
  ASSET_TYPE_WEAPON_CAMO = 0x1F,
  ASSET_TYPE_SNDDRIVER_GLOBALS = 0x20,
  ASSET_TYPE_FX = 0x21,
  ASSET_TYPE_IMPACT_FX = 0x22,
  ASSET_TYPE_AITYPE = 0x23,
  ASSET_TYPE_MPTYPE = 0x24,
  ASSET_TYPE_MPBODY = 0x25,
  ASSET_TYPE_MPHEAD = 0x26,
  ASSET_TYPE_CHARACTER = 0x27,
  ASSET_TYPE_XMODELALIAS = 0x28,
  ASSET_TYPE_RAWFILE = 0x29,
  ASSET_TYPE_STRINGTABLE = 0x2A,
  ASSET_TYPE_LEADERBOARD = 0x2B,
  ASSET_TYPE_XGLOBALS = 0x2C,
  ASSET_TYPE_DDL = 0x2D,
  ASSET_TYPE_GLASSES = 0x2E,
  ASSET_TYPE_EMBLEMSET = 0x2F,
  ASSET_TYPE_SCRIPTPARSETREE = 0x30,
  ASSET_TYPE_KEYVALUEPAIRS = 0x31,
  ASSET_TYPE_VEHICLEDEF = 0x32,
  ASSET_TYPE_MEMORYBLOCK = 0x33,
  ASSET_TYPE_ADDON_MAP_ENTS = 0x34,
  ASSET_TYPE_TRACER = 0x35,
  ASSET_TYPE_SKINNEDVERTS = 0x36,
  ASSET_TYPE_QDB = 0x37,
  ASSET_TYPE_SLUG = 0x38,
  ASSET_TYPE_FOOTSTEP_TABLE = 0x39,
  ASSET_TYPE_FOOTSTEPFX_TABLE = 0x3A,
  ASSET_TYPE_ZBARRIER = 0x3B,
  ASSET_TYPE_COUNT = 0x3C,
  ASSET_TYPE_STRING = 0x3C,
  ASSET_TYPE_ASSETLIST = 0x3D,
  ASSET_TYPE_REPORT = 0x3E,
  ASSET_TYPE_DEPEND = 0x3F,
  ASSET_TYPE_FULL_COUNT = 0x40,
};

union XAssetHeader
{
  XModelPieces *xmodelPieces;
  PhysPreset *physPreset;
  PhysConstraints *physConstraints;
  DestructibleDef *destructibleDef;
  XAnimParts *parts;
  XModel *model;
  Material *material;
  MaterialPixelShader *pixelShader;
  MaterialVertexShader *vertexShader;
  MaterialTechniqueSet *techniqueSet;
  GfxImage *image;
  SndBank *sound;
  SndPatch *soundPatch;
  clipMap_t *clipMap;
  ComWorld *comWorld;
  GameWorldSp *gameWorldSp;
  GameWorldMp *gameWorldMp;
  MapEnts *mapEnts;
  GfxWorld *gfxWorld;
  GfxLightDef *lightDef;
  Font_s *font;
  FontIcon *fontIcon;
  MenuList *menuList;
  menuDef_t *menu;
  LocalizeEntry *localize;
  WeaponVariantDef *weapon;
  WeaponAttachment *attachment;
  WeaponAttachmentUnique *attachmentUnique;
  WeaponCamo *weaponCamo;
  SndDriverGlobals *sndDriverGlobals;
  FxEffectDef *fx;
  FxImpactTable *impactFx;
  RawFile *rawfile;
  StringTable *stringTable;
  LeaderboardDef *leaderboardDef;
  XGlobals *xGlobals;
  ddlRoot_t *ddlRoot;
  Glasses *glasses;
  TextureList *textureList;
  EmblemSet *emblemSet;
  ScriptParseTree *scriptParseTree;
  KeyValuePairs *keyValuePairs;
  VehicleDef *vehicleDef;
  MemoryBlock *memoryBlock;
  AddonMapEnts *addonMapEnts;
  TracerDef *tracerDef;
  SkinnedVertsDef *skinnedVertsDef;
  Qdb *qdb;
  Slug *slug;
  FootstepTableDef *footstepTableDef;
  FootstepFXTableDef *footstepFXTableDef;
  ZBarrierDef *zbarrierDef;
  void *data;
};


```
## Post #3
- Username: RedEyeX32
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Sep 22, 2014 4:38 am
- Post datetime: 2015-11-26T04:55:53+00:00
- Post Title: COD Black Ops 2 .ff file

> Reply from A20Group
>
> Hi All
How to decompress and compress .ff file in black ops 2?
Sample file From Localization File in attachment.
Help me.
Thanks

They are encrypted with Salsa20 symmetric algorithm and you have to decompress the blocks after decryption.
