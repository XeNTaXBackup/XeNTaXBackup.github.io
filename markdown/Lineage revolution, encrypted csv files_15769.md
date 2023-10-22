## Post #1
- Username: dev9ru
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jan 21, 2017 8:26 pm
- Post datetime: 2017-01-21T17:44:48+00:00
- Post Title: Lineage revolution, encrypted csv files

in attachment, almost files are encrypted.
[http://www.mediafire.com/file/6qvzvver7pf6ed6/Data.zip](http://www.mediafire.com/file/6qvzvver7pf6ed6/Data.zip)

and a few files are not. only 4 files has UTF-8 BOM.
- PeriodAchievement.csv
- ItemUnseal.csv
- DungeonSubSection.csv
- UsablePensionTypeAchievement.csv

I want to see contents of all the files.

Could you help me??
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2017-01-22T14:34:23+00:00
- Post Title: Lineage revolution, encrypted csv files

Was this game written in unreal engine 4 (for android)?

edit
have a look at libUE4.so - it does all the reading:

> Failed to read csv. [FilePath: VisualEffect.csv]
>
> %s, Failed to deserialize csv. [FilePath: VisualEffect.csv]
>
> %s, Failed to load csv. [FilePath: VisualEffect.csv]
>
> Scale
>
> Offset_X
>
> Offset_Y
>
> Offset_Z

these are the 4 CSV headers expected for VisualEffect.csv

```
int64 s, e;
string header;
char c;

TFindResults r = FindAll( "Failed to load csv. [FilePath:" );
for( i = 0; i < r.count; i++ )
{
  s = r.start[i]+r.size[i]+1;
  e = FindFirst("]",true,false,false,0.0,1,s);

  Printf("\n%s\n", ReadString(s, e-s));

  e += 2;

  while(1)
  {
    header = "";
    l = ReadStringLength(e);

    for( k = 0; k < l -1; ++k )
    {
      c = ReadByte(e+k);
      if( !((c >= 'a' && c <= 'z') ||
            (c >= 'A' && c <= 'Z') ) )
      {
        //Printf("Rejected %02x\n", c);
        header = "";
        break;
      }

      header += c;
    }
    if( header == "" ) break;
    Printf("  %s\n", header);
    e += l;
  } 
}

```


> Achievement.csv
>
>   Id
>
>   RequiredId
>
>   Type
>
>   GroupType
>
>   Name
>
>   Desc
>
>   TaskType
>
>   CompleteNotifyType
>
>   TaskCount
>
>   RewardPoint
>
>   RewardGem
>
>   RewardAdena
>
>   RewardItemInfoId
>
>   RewardCount
>
>   RewardCountDesc
>
>   RewardIcon
>
>   AchievementIcon
>
> 
>
> AchievementLevel.csv
>
>   AchievementLevel
>
>   PointToNextLv
>
>   LevelIcon
>
>   UsingAlphaTexture
>
>   AdditionalAtkPhy
>
>   AdditionalAtkMag
>
>   AdditionalDefPhy
>
>   AdditionalDefMag
>
>   AdditionalHp
>
>   AdditionalMp
>
>   AdditionalPenetration
>
> 
>
> AchievementLevelReward.csv
>
>   GroupId
>
>   RewardType
>
>   AchievementLevelRewardInfo
>
> 
>
> ActorStat.csv
>
>   Description
>
> 
>
> AdenaDungeonClearRank.csv
>
>   ClearRank
>
>   Hprate
>
>   AdenaDungeonClearRankInfo
>
> 
>
> AdenaDungeonClearReward.csv
>
>   Difficulty
>
>   Reward
>
>   DamageReward
>
>   AdenaDungeonClearRewardInfo
>
> 
>
> AdenaDungeonComboReward.csv
>
>   ComboCount
>
>   ComboReward
>
>   AdenaDungeonComboRewardInfo
>
> 
>
> Adventure.csv
>
>   Order
>
>   Title
>
>   ShortcutContent
>
> 
>
> AttendanceDaily.csv
>
>   PlayTime
>
> 
>
> AttendancePeriod.csv
>
>   Image
>
> 
>
> AttendanceWeekly.csv
>
>   Group
>
>   Day
>
> 
>
> AuctionGroup.csv
>
> 
>
> AuctionSubGroup.csv
>
>   UnusedGrade
>
> 
>
> AutoMove.csv
>
>   NpcInfoId
>
>   WorldInfoId
>
>   PosX
>
>   PosY
>
> 
>
> BroadCasting.csv
>
>   Priority
>
> 
>
> BuffEffect.csv
>
>   EffectType
>
>   EffectParam
>
> 
>
> Buff.csv
>
>   BuffType
>
>   ClientType
>
>   Param
>
>   EffectTypeName
>
>   StackCount
>
>   Duration
>
>   Period
>
>   VisualEffectId
>
>   IconTexture
>
>   CameraShake
>
>   CameraShakeIntensity
>
>   Sound
>
> 
>
> Bufft.csv
>
> 
>
> Castle.csv
>
>   BackgroundImage
>
>   Tax
>
>   GlobalBuffInfoId
>
>   LocalBuffInfoId
>
> 
>
> CastleSiegeBuffRule.csv
>
>   Index
>
>   Rule
>
>   Score
>
> 
>
> CastleSiegeFestivalLottery.csv
>
>   GradeId
>
>   BasicRewardAdena
>
>   GradeTexture
>
> 
>
> CastleUpgrade.csv
>
>   UpgradeType
>
>   Lv
>
>   EffectValue
>
> 
>
> Class.csv
>
>   Grade
>
>   StartClass
>
>   RaceType
>
>   TransferRewardGroupId
>
>   RequiredClassInfoId
>
>   RequiredClassLv
>
>   BasicAttackSkillInfoId
>
>   Resource
>
>   StatusBarIconTexture
>
>   UsableWeapon
>
>   UsableArmor
>
> 
>
> ClassTransferQuest.csv
>
>   TaskContentType
>
>   NpcAutoMoveID
>
>   DelayTime
>
>   DialogNpcPortrait
>
>   DialogNpcName
>
>   Dialog
>
> 
>
> ClassTransferReward.csv
>
>   GroupID
>
> 
>
> ClientString.csv
>
>   Key
>
>   Value
>
>   WarningSoundPlay
>
> 
>
> Color.csv
>
>   ColorType
>
>   MatchColor
>
>   Color
>
> 
>
> Combo.csv
>
>   ComboBuffID
>
> 
>
> Const.csv
>
> 
>
> ContentsLock.csv
>
>   Keyword
>
>   ConditionType
>
>   ConditionValue
>
>   ConditionSubValue
>
>   ShowInProgressBar
>
>   SortNum
>
>   ContentsDesc
>
>   ContentIcon
>
>   BadgeType
>
> 
>
> DailyActivityGroup.csv
>
>   Icon
>
> 
>
> DailyActivity.csv
>
>   TaskCondition
>
>   RewardActivityPoint
>
>   RewardGroupId
>
> 
>
> DailyActivityPointReward.csv
>
>   RequiredPoint
>
>   DailyActivityPointRewardInfo
>
> 
>
> DailyActivityReward.csv
>
> 
>
> DailyActivityRewardPeriod.csv
>
>   DailyActivityRewardPeriodInfo
>
> 
>
> DefaultSkill.csv
>
>   SkillId
>
> 
>
> DialogGuide.csv
>
> 
>
> Dialog.csv
>
>   PortraitTexture
>
>   Message
>
>   Delay
>
>   GuideOnly
>
> 
>
> DungeonDialog.csv
>
>   DungeonId
>
>   DungeonDialogType
>
> 
>
> Dungeon.csv
>
>   ContentShow
>
>   RecommendedAttack
>
>   RecommendedDefense
>
>   RecommendedPower
>
>   IntParam
>
>   RecommendedPC
>
>   EnterLevelRestriction
>
>   WorldId
>
>   RepresentRewardId
>
>   RepresentRewardName
>
>   RepresentRewardDescription
>
>   RepresentRewardIconPath
>
>   AddSubLevel
>
>   ResetGemType
>
>   ResetGemCount
>
>   SubLevelForLight
>
>   BGM
>
> 
>
> DungeonMenu.csv
>
>   DungeonMenuType
>
>   DungeonType
>
>   ContentsLockKeyword
>
> 
>
> DungeonQuest.csv
>
>   RewardExp
>
>   RewardItemGroup
>
> 
>
> DungeonSection.csv
>
>   SubId
>
>   StartPointX
>
>   StartPointY
>
>   SectionInfoParam
>
>   SectionPositionParam
>
> 
>
> EffectType.csv
>
>   ActorStatType
>
>   IsPercentage
>
>   Revision
>
> 
>
> ElixirEffect.csv
>
>   ElixirType
>
>   Level
>
> 
>
> Emoticon.csv
>
>   EmoticonTabType
>
>   ShortcutKey
>
>   EmoticonPath
>
> 
>
> EnchantScrollDungeonClearRank.csv
>
>   NpcHpRate
>
> 
>
> EnchantScrollDungeonClearReward.csv
>
> 
>
> EquipDungeonClearRank.csv
>
>   EquipDungeonClearRankInfo
>
> 
>
> EquipDungeonClearReward.csv
>
>   EquipDungeonClearRewardInfo
>
> 
>
> EquipDungeonNpcScore.csv
>
>   NpcInfoID
>
> 
>
> Event.csv
>
>   EventType
>
>   UsePopup
>
> 
>
> ExpDungeonClearRank.csv
>
>   KillCount
>
>   RankExpRate
>
> 
>
> ExpDungeonReward.csv
>
>   ExpEazy
>
>   ExpNormal
>
>   ExpHard
>
>   ExpHell
>
> 
>
> Exp.csv
>
>   ExpToNextLv
>
>   StandardCombatPower
>
> 
>
> ExpPurchase.csv
>
>   Exp
>
> 
>
> Fortress.csv
>
>   TerritoryId
>
>   FortressSiegeWorldInfoId
>
> 
>
> FortressSiegeBuffRule.csv
>
>   FortressSiegeBuffRuleInfo
>
> 
>
> Gadget.csv
>
>   TeamId
>
>   UseType
>
>   ManualControl
>
>   ControlTime
>
>   ControlText
>
>   MultiControl
>
>   HitCancel
>
>   ForbidUserCancel
>
>   Radius
>
>   BPName
>
>   Visible
>
>   InitialSpawning
>
>   Repeatable
>
>   LifeTime
>
>   ControlCoolingTime
>
>   MaxCount
>
>   BasePosX
>
>   BasePosY
>
>   BasePosZ
>
>   RotateP
>
>   RotateY
>
>   RotateR
>
>   SpawnRadius
>
> 
>
> GroundObjectEffect.csv
>
>   GroundObjectId
>
> 
>
> GroundObject.csv
>
> 
>
> GuideQuest.csv
>
>   Rank
>
> 
>
> GuildAchievement.csv
>
>   RewardBloodCrystal
>
> 
>
> GuildAttendanceReward.csv
>
>   AttendUserCount
>
>   RewardGuildCoin
>
> 
>
> GuildBuffCost.csv
>
>   SkillInfoId
>
>   SkillLevel
>
>   Cost
>
> 
>
> GuildBuff.csv
>
>   RequiredGuildLevel
>
>   Tier
>
> 
>
> GuildEmblem.csv
>
>   EmblemName
>
>   EmblemType
>
>   ImageTexture
>
>   HasType
>
>   SmallImageTexture
>
> 
>
> GuildLevelUp.csv
>
>   MaximumGuildMemberCount
>
>   GuildWarehouseCount
>
>   NextLevelNeedExp
>
>   AssignableAssistantMaster
>
>   AssignableKnightsLeader
>
>   AssignableRoyalGuardLeader
>
>   PresentCount
>
> 
>
> GuildMarket.csv
>
>   ItemName
>
>   MarketId
>
>   HighendEffect
>
>   TableInfoldList
>
>   ItemType
>
>   ItemId
>
>   UnBindType
>
>   CostType
>
>   CostPropertyType
>
>   ProductValue
>
>   GradeLimit
>
>   PurchaseLimit
>
>   PurchaseLimitValue
>
> 
>
> GuildMemberGrade.csv
>
>   Advertisement
>
>   JoinRequestAcceptance
>
>   MemberGradeChange
>
>   Expulsion
>
>   Invitation
>
>   UseAdditionalBuff
>
>   FortressWarRegistration
>
>   CastleWarRegistration
>
>   Grant
>
>   SkillUpgrade
>
>   Alliance
>
>   IconPath
>
> 
>
> GuildRecord.csv
>
>   GuildRecordType
>
>   GuildRecordString
>
> 
>
> HelpUrl.csv
>
>   Url
>
>   NaverUrl
>
>   LocType
>
> 
>
> InstantComplete.csv
>
>   RewardRatio
>
>   CostAdena
>
>   AdenaRewardGroupId
>
>   CostDiamond
>
>   DiamondRewardGroupId
>
>   ContentsType
>
>   UseLevelReward
>
> 
>
> InstantCompleteLevelReward.csv
>
> 
>
> InstantCompleteReward.csv
>
>   ConditionParam
>
>   InstantCompleteRewardInfo
>
> 
>
> ItemAbilityEffect.csv
>
>   EffectParamMin
>
>   EffectParamMax
>
>   EffectParamGrowth
>
>   EffectSkillInfoId
>
> 
>
> ItemAbility.csv
>
>   ConditionNpcGradeList
>
>   EffectGroupId
>
> 
>
> ItemAssets.csv
>
>   InfoId
>
> 
>
> ItemBox.csv
>
>   BoxType
>
>   BoxItemInfoId
>
> 
>
> ItemCraft.csv
>
>   SideType
>
>   ItemInfoId
>
>   ItemCount
>
>   CostValue
>
> 
>
> ItemDecomposition.csv
>
>   ItemGrade
>
>   EquipmentType
>
> 
>
> ItemDrop.csv
>
>   MinItemCount
>
>   MaxItemCount
>
> 
>
> ItemEnchant.csv
>
>   WeaponType
>
>   EnchantEfficiency
>
>   SuccessRate
>
>   SuccessRateBless
>
>   FailurePenalty
>
>   RequiredAdena
>
>   RequiredProtectionJewel
>
>   RequiredEnchantScroll
>
> 
>
> ItemGrade.csv
>
>   MaxLevel
>
>   MaxEnchantLevel
>
>   LimitBreakBonusLevel
>
>   LimitBreakAdenaCost
>
>   MaxLimitBreakCount
>
>   LimitBreakRate
>
>   OptionCount
>
>   OptionChangeCashCost
>
>   SocketCount
>
>   CompositionAdenaCost
>
>   UpgradeMaterialCount
>
>   UpgradeAdenaCost
>
>   AbilityUpgradeRate
>
>   SocketExtractionAdenaCost
>
>   RequiredSoulshotCount
>
>   GachaCardTexture
>
> 
>
> Item.csv
>
>   DisplayLevel
>
> 
>
> ItemLack.csv
>
>   Moveable
>
>   MoveContentType
>
>   Text
>
> 
>
> ItemLackResult.csv
>
>   ResultCode
>
> 
>
> ItemLevelUp.csv
>
>   TotalExpForNextLevel
>
>   EffectIncreaseRate
>
> 
>
> ItemOption.csv
>
>   OptionGroup
>
> 
>
> ItemPromotion.csv
>
>   RequiredMaterialCount
>
> 
>
> ItemUnseal.csv
>
>   SealedCount
>
>   RequiredCrystalCount
>
> 
>
> LevelGap.csv
>
>   LvGap
>
> 
>
> LevelUpGift.csv
>
> 
>
> LightningEffect.csv
>
>   LightningEffectResource
>
>   FireSocket
>
>   OffsetX
>
>   OffsetY
>
>   OffsetZ
>
> 
>
> Loading.csv
>
>   TipType
>
>   TipText
>
>   Texture
>
> 
>
> MarketAchievement.csv
>
> 
>
> MarketLeaderboard.csv
>
>   LeaderboardId
>
> 
>
> Matinee.csv
>
>   AdditionalCutSceneName
>
>   KeepHeadMesh
>
> 
>
> MissionDaily.csv
>
>   MissionGrade
>
>   AutoCompleteTime
>
>   PassCost
>
>   MissionIcon
>
> 
>
> MissionDailyReward.csv
>
> 
>
> MissionReward.csv
>
>   MissionType
>
>   RequireCompleteCount
>
> 
>
> MissionWeekly.csv
>
> 
>
> MissionWeeklyReward.csv
>
> 
>
> MonsterBookGroup.csv
>
>   RewardQuantity
>
>   RewardIndex
>
>   PromotePoint
>
> 
>
> MonsterBook.csv
>
>   BookLevel
>
>   MonsterId
>
>   CardBorder
>
>   CardImage
>
>   MonsterCoreItemId
>
>   RequiredQuantity
>
>   StatusIcon
>
>   HuntType
>
>   HuntingSpotId
>
>   NameDirection
>
> 
>
> MonsterGrade.csv
>
>   MonsterGrade
>
>   NameColor
>
>   BackgroundTexture
>
> 
>
> Monster.csv
>
>   MonsterType
>
> 
>
> NotifyCodeString.csv
>
> 
>
> Npc.csv
>
>   NameEN
>
>   ScaleFactor
>
>   VisibleLevel
>
>   BasicAttackSkillInfoIdList
>
>   CreateSkillInfoId
>
>   IgnoreHitAnim
>
>   Aggressive
>
>   Movable
>
>   Rotatable
>
>   IsMonster
>
>   SpawnAnim
>
>   SpawnVFX
>
> 
>
> NpcResourceString.csv
>
>   String
>
> 
>
> NpcSpawn.csv
>
>   NPCTalk
>
>   IsStatic
>
>   Despawn
>
>   PosZ
>
>   MapMark
>
> 
>
> NpcTalk.csv
>
> 
>
> NpcVoice.csv
>
>   Voice
>
> 
>
> Option.csv
>
>   StringKey
>
>   DefaultValueForAOS
>
>   DefaultValueForIOS
>
>   UserData
>
>   StartValue
>
> 
>
> PartyFilter.csv
>
>   PartyTagType
>
>   Purpose
>
>   Adventure
>
>   EnterRestrictionId
>
> 
>
> PatchImage.csv
>
> 
>
> PayShop.csv
>
>   TabType
>
> 
>
> PensionTypeAchievement.csv
>
>   ShopId
>
>   PensionTypeAchievementInfo
>
> 
>
> PensionTypeReward.csv
>
>   ProductType
>
> 
>
> PkArea.csv
>
>   PlaceName
>
> 
>
> PkStatus.csv
>
>   ActiveIconPath
>
>   DeactiveIconPath
>
> 
>
> ProjectileEffect.csv
>
>   ProjectileId
>
> 
>
> Projectile.csv
>
>   MoveType
>
>   MoveSpeed
>
>   Count
>
>   HitCount
>
>   ExplosionCollisionUnitType
>
>   ExplosionCollisionUnitParam
>
>   SocketName
>
> 
>
> PromoteGrade.csv
>
>   ActivateRate
>
>   DecoTexture
>
>   DecoColor
>
> 
>
> Promote.csv
>
>   TemplateName
>
>   TemplateDesc
>
>   GradeGroupId
>
>   CategoryType
>
> 
>
> PvpHonorRank.csv
>
>   RankUpPoint
>
>   RankIcon
>
> 
>
> PvpHonorRankStat.csv
>
>   StatType
>
>   StatValue
>
> 
>
> PvpReward.csv
>
>   RequiredValue
>
> 
>
> QuestActChapter.csv
>
>   ActChapterId
>
>   QuestId
>
> 
>
> QuestActChapterReward.csv
>
>   ActNo
>
>   ChapterNo
>
>   ActImg
>
>   ActName
>
>   ChapterName
>
> 
>
> QuestActProgressReward.csv
>
>   RewardParam
>
> 
>
> Quest.csv
>
>   PreQuestId
>
>   TaskId
>
>   SpotInfoId
>
>   TargetSpotInfoId
>
>   RequirePlayerLevel
>
>   TaskName
>
>   DialogOnly
>
>   MiniDialogId
>
>   StartNpcSpawnInfoId
>
>   StartNpcSpotInfoId
>
>   QuestNpcPortrait
>
>   QuestNpcName
>
>   QuestNpcDialog
>
>   FinishNpcSpawnInfoId
>
>   FinishNpcSpotInfoId
>
> 
>
> QuestNpcSound.csv
>
>   SoundName
>
> 
>
> Race.csv
>
>   PortraitBackgroundTexture
>
>   CharacterSelectTexture
>
>   StatGraphTexture
>
> 
>
> Ranking.csv
>
>   SubType
>
>   Sort
>
>   Unit
>
> 
>
> RefinementDungeonClearRank.csv
>
>   RefinementDungeonClearRankInfo
>
> 
>
> RefinementDungeonClearReward.csv
>
> 
>
> RestReward.csv
>
>   ProductName
>
>   PercentQuantity
>
>   ProductId
>
>   ProductCount
>
>   CostTypeForAdditionalPurchase
>
>   CostForAdditionalPurchase
>
>   MulForAdditionalPurchase
>
> 
>
> ResultCodeString.csv
>
> 
>
> RuneEffect.csv
>
> 
>
> Rune.csv
>
>   RunePage
>
>   RuneNumber
>
>   RuneLevel
>
>   CostRunePiece
>
>   StampProbability
>
>   RunePosX
>
>   RunePosY
>
>   TexturePath
>
>   TextureFramePath
>
>   RuneType
>
> 
>
> RunePageOpen.csv
>
>   RequiredPcLv
>
> 
>
> SetItem.csv
>
>   ItemList
>
> 
>
> ShopInApp.csv
>
>   MarketType
>
>   CurrencyType
>
>   DisplayCost
>
> 
>
> ShopItem.csv
>
>   LimitMinLevel
>
>   LimitMaxLevel
>
>   Display
>
>   DisplayTypeValue
>
>   LimitPeriodStart
>
>   LimitPeriodEnd
>
>   FlatRatePeriod
>
> 
>
> ShopItemProduct.csv
>
>   ProductItemType
>
> 
>
> ShopReward.csv
>
>   RewardGroupInfoId
>
> 
>
> ShopTab.csv
>
>   ShopType
>
> 
>
> SiegeBuff.csv
>
>   ScoreBuffID
>
>   BuffInfo
>
>   GradeIcon
>
>   GradeName
>
> 
>
> SkillAcquire.csv
>
>   PcLvIntervalToNextLv
>
>   SkillTier
>
> 
>
> SkillAction.csv
>
>   Operation
>
>   Parameter
>
>   StartAttack
>
>   FireOnFinish
>
> 
>
> SkillEffect.csv
>
> 
>
> Skill.csv
>
>   Tire
>
>   LevelMatchGroupId
>
>   MaxCastDistance
>
>   PrevSkillId
>
>   FireCount
>
>   LightningEffectInfoId
>
>   MpMin
>
>   MpMax
>
>   MpGrowth
>
>   CastingTime
>
>   CoolTimeMin
>
>   TargetType
>
>   MaxTargetCount
>
>   OffsetDistance
>
>   EffectFireConditionType
>
>   EffectFireConditionParam
>
>   SkillDamageRatio
>
>   Animation
>
>   WeaponDependent
>
>   CameraShakeObject
>
>   EffectDescription
>
>   HitFX
>
>   HitSocket
>
>   DirAlign
>
>   DirAlignRange
>
>   AddForceOnKill
>
>   BasicAttack
>
>   DetailType
>
>   ShowSkillArea
>
>   DashStart
>
>   SkillDialogue
>
> 
>
> SkillLevelMatch.csv
>
>   DisplaySKillLevel
>
>   RealSkillLevel
>
> 
>
> SkillUpgradeCost.csv
>
> 
>
> SlanderMessage.csv
>
>   Word
>
> 
>
> SlanderName.csv
>
> 
>
> SmartPopupDetail.csv
>
>   PopupType
>
>   RepeatType
>
>   DailyType
>
>   UIKeyword
>
>   Probability
>
>   AchievementId
>
>   ShopItemId
>
> 
>
> SmartPopup.csv
>
>   BGTexture
>
>   BGTextureSmall
>
>   ContentType
>
>   Promote
>
> 
>
> SocialAction.csv
>
>   id
>
>   AnimationPath
>
>   HumanDialog
>
>   ElfDialog
>
>   DarkElfDialog
>
>   DwarfDialog
>
> 
>
> SoulCrystalEquip.csv
>
>   EquipType
>
> 
>
> SoulCrystalType.csv
>
>   SocketIconPath
>
> 
>
> StatusRise.csv
>
> 
>
> SummonGemGroup.csv
>
>   RecommendLv
>
>   RecommendPower
>
>   RecommendPeople
>
> 
>
> SynchroEnchant.csv
>
>   EnchantLevel
>
>   ItemOptionInfoGroupId
>
> 
>
> Territory.csv
>
>   NameTagPosX
>
>   NameTagPosY
>
>   NameTagDirection
>
>   CastleTexture
>
>   HelpKeyWord
>
> 
>
> ThemeBGM.csv
>
>   ThemeBGM
>
> 
>
> Title.csv
>
>   TitleName
>
>   TitleNameColor
>
>   GainDetialCondition
>
>   TitleBackgroundPath
>
> 
>
> Tutorial.csv
>
>   WorldMove
>
>   ActivateType
>
>   ActivateValue
>
>   BpName
>
>   ControlPath
>
>   QuestPanelControlBlock
>
>   ItemRecommendPopup
>
> 
>
> TutorialStep.csv
>
>   TutorialId
>
>   Step
>
>   ProcessRequest
>
>   SystemMessagePosition
>
>   NpcPortrait
>
>   NpcName
>
>   DialogMessage
>
>   UIType
>
>   SkillActivateType
>
>   TaskTargetPosX
>
>   TaskTargetPosY
>
>   WidgetName
>
>   ControlName
>
>   ControlIndexType
>
>   ControlIndex
>
>   MoviePath
>
>   SkipFadeOutKeep
>
> 
>
> UsablePensionTypeAchievement.csv
>
> 
>
> UseableAchievementTask.csv
>
>   UseableAchievementTaskInfo
>
> 
>
> VisualEffect.csv
>
>   Scale
>
> 
>
> World.csv
>
>   Hide
>
>   MapData
>
>   QuestMapTexturePath
>
>   WorldMapCategory
>
>   RecommendedMinLv
>
>   RecommendedMaxLv
>
>   MaxChannel
>
>   ClearRewardType
>
>   ClearRewardCount
>
>   ClearRewardTargetInfoId
>
>   NpcSpawnGroupId
>
>   Minimap
>
>   MinimapTextureCountX
>
>   MinimapTextureCountY
>
>   MinimapZoomScale
>
>   MapSizeX
>
>   MapSizeY
>
>   MapCenterX
>
>   MapCenterY
>
>   WorldMapCoordX
>
>   WorldMapCoordY
>
>   DimTexture
>
>   DimPosX
>
>   DimPosY
>
>   DimSizeX
>
>   DimSizeY
>
>   PlayerAllyTeamId
>
>   IsPlayerBlock
>
> 
>
> WorldSpot.csv
>
>   ActorWorldId
>
>   ActorPosX
>
>   ActorPosY
>
>   SpotName
>
>   SpotTexture
>
>   SpotTitle
>
>   UseTeleportScroll
>
>   lineageII
>
>   SLoadingScreen
## Post #3
- Username: dev9ru
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jan 21, 2017 8:26 pm
- Post datetime: 2017-01-24T02:23:01+00:00
- Post Title: Lineage revolution, encrypted csv files

Wow! are you a genius? Thanks a lot!
