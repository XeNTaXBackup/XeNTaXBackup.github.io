## Post #1
- Username: iambosh
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Oct 04, 2014 12:22 pm
- Post datetime: 2016-10-06T19:21:57+00:00
- Post Title: Mafia 3 - .SDS

seems to be using the same filetype.
## Post #2
- Username: Espio
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Jan 08, 2007 7:47 am
- Post datetime: 2016-10-07T01:24:53+00:00
- Post Title: Mafia 3 - .SDS

Sample file
[http://www24.zippyshare.com/v/NpZjwaKD/file.html](http://www24.zippyshare.com/v/NpZjwaKD/file.html)

SDS extractors for Mafia 2 don't work. File contains ZLIB, but most probably is just slightly different from older format.
## Post #3
- Username: tice17
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Dec 04, 2015 1:20 am
- Post datetime: 2016-10-07T07:17:36+00:00
- Post Title: Mafia 3 - .SDS

Any news on this? We're thinking to translate this game to our language but we couldn't start to the project because lack of tools
## Post #4
- Username: Timbab
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jun 15, 2012 10:05 pm
- Post datetime: 2016-10-07T18:55:32+00:00
- Post Title: Mafia 3 - .SDS

At a quick glance, they look extremely similar, it's version 13 (Mafia 2) vs 14 (Mafia 3). I don't have much/any knowledge of Mafia 2 modding or its files, but if you compare tables.sds of both games, the header seems to be of the same length and structure for the most part. 

Shouldn't be too hard. With one of the old Mafia 2 SDS tools I got a hash error when hex editing the version of an .SDS, but I have no idea how flexible that tool was written.

Would take a shot at it myself, but don't think I have the time.
## Post #5
- Username: Skrillex
- Rank: advanced
- Number of posts: 66
- Joined date: Sat Aug 23, 2014 1:11 am
- Post datetime: 2016-10-08T13:10:19+00:00
- Post Title: Mafia 3 - .SDS

UP
## Post #6
- Username: CarLuver69
- Rank: advanced
- Number of posts: 50
- Joined date: Fri Mar 09, 2012 1:17 am
- Post datetime: 2016-10-08T23:01:50+00:00
- Post Title: Mafia 3 - .SDS

Posting my research here in case anyone can put it to good use. I'll probably make my own tools eventually, but I don't have an ETA on that 

Thanks to aluigi for his [Mafia .SDS (PS3)](http://aluigi.altervista.org/bms/mafia_sds_ps3.bms) script, it helped point me in the right direction.

NOTE: I'm probably wrong on a lot of this, so please feel free to make corrections. I'm most likely off on the chunkCount being used to determine how many SDSChunkData's there are.

```
    int magic; // 0x534453 ('SDS\0')
    
    int version; // 0x14 (v20 / v1.4?)
    
    enum SDSType : int {
        PC = 0x4350,
        
        /* These are ASSUMED, I only have the PC version */
        PS4 = 0x345350,
        XB1 = 0x314258,
    } type;
    
    int unk_0C; // 0x5DE53FDE
    
    int dataInfoOffset;
    int dataOffset;
    
    int unk_18; // always zero?
    int unk_1C; // offset / size of something?
    int unk_20; // always zero?
    int unk_24; // offset / size of something?
    int unk_28; // always zero?
    int unk_2C; // 1
    int unk_30; // always zero?
    int unk_34; // always zero?
    int unk_38; // always zero?
    int unk_3C; // always zero?
    
    int chunkCount; // how many data chunks? (educated guess)
    int reserved; // checksum, hash, or key of some sort?
    
    /* @ dataInfoOffset */
    struct SDSDataInfo {
        int count; // how many data types there are
        
        struct SDSDataType {
            int typeIndex; // local index to reference this type
            
            int strLen;
            char typeName[strLen]; // no null-terminator
            
            int reserved; // possibly a guard? (always zero?)
        } dataTypes[count];
    
    } dataInfo;
    
    /* @ dataOffset */
    struct SDSData {
        int magic; // 0x6C7A4555 ('UEzl')
        
        int unk_04; // 0x10000? (never seems to change)
        char unk_05; // 4?
        
        struct SDSChunkData {
            int dataSize; // size of SDSChunkData
            char dataType; // reference to SDSDataInfo.dataType
            
            struct SDSChunkData {
                int memorySize; // size in memory? (e.g. uncompressed size)
                
                int bufferOffset; // offset to start of data
                
                int memorySize_2; // SDSData.unk_04 again?
                
                short unk_0A; // number of something? (this format is confusing)
                short unk_0C; // 0x80F?
                
                short bufferSize; // this might be an int, but unlikely
                /*
                    <<< Data padding >>>
                */
                /* @ bufferOffset */
                char buffer[bufferSize];
            } data;
        } chunks[chunkCount];
    };
};
```
## Post #7
- Username: Skrillex
- Rank: advanced
- Number of posts: 66
- Joined date: Sat Aug 23, 2014 1:11 am
- Post datetime: 2016-10-08T23:59:02+00:00
- Post Title: Mafia 3 - .SDS

> Reply from CarLuver69
>
> Posting my research here in case anyone can put it to good use. I'll probably make my own tools eventually, but I don't have an ETA on that 

Thanks to aluigi for his Mafia .SDS (PS3) script, it helped point me in the right direction.

NOTE: I'm probably wrong on a lot of this, so please feel free to make corrections. I'm most likely off on the chunkCount being used to determine how many SDSChunkData's there are.

QuickBMS have letter limit sir, is there any solution except BMS script?
## Post #8
- Username: CarLuver69
- Rank: advanced
- Number of posts: 50
- Joined date: Fri Mar 09, 2012 1:17 am
- Post datetime: 2016-10-09T02:21:11+00:00
- Post Title: Mafia 3 - .SDS

> Reply from Skrillex
>
> QuickBMS have letter limit sir, is there any solution except BMS script?

Not at the moment sir, someone will need to make an SDS extractor. There are tools for Mafia II but they would need to be updated.

If I ever make my own tools, I'll post a link in this thread. But don't hold your breath for anything soon.
## Post #9
- Username: grimmp
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Oct 08, 2016 9:03 pm
- Post datetime: 2016-10-09T07:47:36+00:00
- Post Title: Mafia 3 - .SDS

Anyone knows in game texts or subtitles are encrypted or plain?
## Post #10
- Username: GRiNDERKILLER
- Rank: veteran
- Number of posts: 92
- Joined date: Thu Jul 12, 2012 7:24 pm
- Post datetime: 2016-10-09T09:57:18+00:00
- Post Title: Mafia 3 - .SDS

Not encrypted. They are in readable form but with Binary tables. Fonts are GFX scaleform. Other words SWF.
EDiT: Correction, subtitles are encrypted, but stringtable doesn't.

Sounds can be extracted with Ravioli. It's a pck file with Wwise format.
## Post #11
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2016-10-09T13:56:34+00:00
- Post Title: Mafia 3 - .SDS

somethink's about audio
## Post #12
- Username: BitEmE
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jun 23, 2014 5:06 pm
- Post datetime: 2016-10-11T19:38:43+00:00
- Post Title: Mafia 3 - .SDS

Hey guys,

I've started to try porting Ricks Mafia 2 SDS Extractor tool to Mafia 3 (based on CarLuver69s source)
Its open source and can be found here: [https://github.com/MartinJK/Mafia3SDSExplorer](https://github.com/MartinJK/Mafia3SDSExplorer)



When trying out a testfile, this was my result (It shows not available because I'm not able to extract the names of the resources at the moment)


Looking deeper into it, I've tried to find the TEA stuff of Mafia 2 in Mafia 3, it seems that there's no more TEA encryption at all, also XML content in SSD files is gone (was plaintext in mafia 2's ssds)


At the moment I'm dealing with an issue that the extractor crashes because of invalid memory stream / reading position.
Also the content seems to be encrypted, I've tried to open an encrypted DDS file -> exception.

Hope it helps someone here
## Post #13
- Username: ner0
- Rank: advanced
- Number of posts: 50
- Joined date: Sun Aug 28, 2011 11:47 pm
- Post datetime: 2016-10-11T19:44:56+00:00
- Post Title: Mafia 3 - .SDS

Aluigi seems to have made some tweaks to his quickbms script for PC version, not sure if it helps in any way: [http://aluigi.altervista.org/bms/mafia_sds_ps3.bms](http://aluigi.altervista.org/bms/mafia_sds_ps3.bms)

Your project looks awesome though, let's hope you make progress soon
## Post #14
- Username: Skrillex
- Rank: advanced
- Number of posts: 66
- Joined date: Sat Aug 23, 2014 1:11 am
- Post datetime: 2016-10-11T21:27:02+00:00
- Post Title: Mafia 3 - .SDS

> Reply from BitEmE
>
> Hey guys,

I've started to try porting Ricks Mafia 2 SDS Extractor tool to Mafia 3 (based on CarLuver69s source)
Its open source and can be found here: https://github.com/MartinJK/Mafia3SDSExplorer

When trying out a testfile, this was my result (It shows not available because I'm not able to extract the names of the resources at the moment)


Looking deeper into it, I've tried to find the TEA stuff of Mafia 2 in Mafia 3, it seems that there's no more TEA encryption at all, also XML content in SSD files is gone (was plaintext in mafia 2's ssds)

At the moment I'm dealing with an issue that the extractor crashes because of invalid memory stream / reading position.
Also the content seems to be encrypted, I've tried to open an encrypted DDS file -> exception.

Hope it helps someone here

I hope you make it my friend. I'm counting on you.
## Post #15
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2016-10-12T00:07:41+00:00
- Post Title: Mafia 3 - .SDS

> Reply from BitEmE
>
> 
Also the content seems to be encrypted, I've tried to open an encrypted DDS file -> exception.
They not encrypted, chunks are compressed with Zlib. About XML toc > not exist anymore. Content filenames hashed (fnv64a).

```
{
   uint64 dwHash = 0xCBF29CE484222325;
   for(int i = 0; i < dwLength; i++)
   {
      dwHash *= 0x00000100000001B3;
      dwHash ^= m_String[i];
   }
  return dwHash;
}
```


Some names

```
/maps/engine/debug_font.dds
/maps/engine/env_brdf_lut_blinn.dds
/maps/engine/normalfix.dds
/maps/engine/pseudoshadow.dds
/maps/engine/sincos.dds
/maps/engine/smaa/area_tex_dx10.dds
/maps/engine/smaa/search_tex.dds
/maps/engine/water_normal_variance.dds
/scripts/common/base/butil.lua
/scripts/common/base/code_extensions.lua
/scripts/common/base/debug_utils.lua
/scripts/common/base/game_structure_console.lua
/scripts/common/base/gutil.lua
/scripts/common/base/script.lua
/scripts/common/base/script_classes.lua
/scripts/common/base/threads.lua
/scripts/common/base/various_utils.lua
/scripts/common/cityapscripts/animationlists.lua
/scripts/common/commands_library/common/common_init.lua
/scripts/common/commands_library/common/human/common_human.lua
/scripts/common/commands_library/common/human/common_human_events.lua
/scripts/common/commands_library/common/human/common_human_obsolete.lua
/scripts/common/commands_library/common/props.lua
/scripts/common/commands_library/common/vehicle/common_vehicle.lua
/scripts/common/commands_library/common/vehicle/common_vehicle_events.lua
/scripts/common/commands_library/common/vehicle/common_vehicle_obsolete.lua
/scripts/common/commands_library/entity/ab_detector.lua
/scripts/common/commands_library/entity/actor_detector.lua
/scripts/common/commands_library/entity/boat.lua
/scripts/common/commands_library/entity/camera.lua
/scripts/common/commands_library/entity/car/car.lua
/scripts/common/commands_library/entity/car/car_obsolete.lua
/scripts/common/commands_library/entity/crash_object.lua
/scripts/common/commands_library/entity/cutscene.lua
/scripts/common/commands_library/entity/distance_detector.lua
/scripts/common/commands_library/entity/door.lua
/scripts/common/commands_library/entity/fire_target.lua
/scripts/common/commands_library/entity/human/human.lua
/scripts/common/commands_library/entity/human/human_obsolete.lua
/scripts/common/commands_library/entity/interact_detector.lua
/scripts/common/commands_library/entity/light.lua
/scripts/common/commands_library/entity/particle.lua
/scripts/common/commands_library/entity/player.lua
/scripts/common/commands_library/entity/sensor.lua
/scripts/common/commands_library/entity/trigger_volume.lua
/scripts/common/commands_library/nodes_moved_to_code.lua
/scripts/common/commands_library/system/audio/game_audio.lua
/scripts/common/commands_library/system/audio/game_audio_deprecated.lua
/scripts/common/commands_library/system/audio/viscript_wwise_events.lua
/scripts/common/commands_library/system/audio/viscript_wwise_states.lua
/scripts/common/commands_library/system/game/capture.lua
/scripts/common/commands_library/system/game/collectibles.lua
/scripts/common/commands_library/system/game/coverage.lua
/scripts/common/commands_library/system/game/datastore.lua
/scripts/common/commands_library/system/game/delivery.lua
/scripts/common/commands_library/system/game/fleet.lua
/scripts/common/commands_library/system/game/fsm.lua
/scripts/common/commands_library/system/game/game.lua
/scripts/common/commands_library/system/game/garage.lua
/scripts/common/commands_library/system/game/hideout.lua
/scripts/common/commands_library/system/game/hud.lua
/scripts/common/commands_library/system/game/hud/hud_game_structure.lua
/scripts/common/commands_library/system/game/hud/objective_missions.lua
/scripts/common/commands_library/system/game/hud/objective_rackets.lua
/scripts/common/commands_library/system/game/hud/objective_spokes.lua
/scripts/common/commands_library/system/game/interactions.lua
/scripts/common/commands_library/system/game/persistent_location.lua
/scripts/common/commands_library/system/game/pipcamera.lua
/scripts/common/commands_library/system/game/police.lua
/scripts/common/commands_library/system/game/savesystem.lua
/scripts/common/commands_library/system/game/services.lua
/scripts/common/commands_library/system/game/shop.lua
/scripts/common/commands_library/system/game/sound.lua
/scripts/common/commands_library/system/game/stat_tracker.lua
/scripts/common/commands_library/system/game/streammap.lua
/scripts/common/commands_library/system/game/tailing.lua
/scripts/common/commands_library/system/game/traffic.lua
/scripts/common/commands_library/system/game/weather.lua
/scripts/common/commands_library/system/game/wiretapping.lua
/scripts/common/commands_library/system/game_director/activity.lua
/scripts/common/commands_library/system/game_director/business.lua
/scripts/common/commands_library/system/game_director/crime_family.lua
/scripts/common/commands_library/system/game_director/custom_state.lua
/scripts/common/commands_library/system/game_director/dialog.lua
/scripts/common/commands_library/system/game_director/economy.lua
/scripts/common/commands_library/system/game_director/kickback.lua
/scripts/common/commands_library/system/game_director/objective.lua
/scripts/common/commands_library/system/game_director/old.lua
/scripts/common/commands_library/system/game_director/other.lua
/scripts/common/commands_library/system/game_director/persistent_characters.lua
/scripts/common/commands_library/system/game_director/quest.lua
/scripts/common/commands_library/system/system.lua
/scripts/common/commands_library/system/test_nodes/bodyshop.lua
/scripts/common/commands_library/system/test_nodes/game_structure.lua
/scripts/common/commands_library/system/test_nodes/patrols_and_stalking.lua
/scripts/common/commands_library/system/test_nodes/testscenes.lua
/scripts/common/commands_library/system/test_nodes/user_bar.lua
/scripts/common/helpers/camera_helper.lua
/scripts/common/helpers/class.lua
/scripts/common/helpers/data/data_input_presets.lua
/scripts/common/helpers/data/data_journal.lua
/scripts/common/helpers/data/data_objectives.lua
/scripts/common/helpers/data/data_owas.lua
/scripts/common/helpers/data/data_traffic.lua
/scripts/common/helpers/data/data_tutorials.lua
/scripts/common/helpers/data/data_vo_selection.lua
/scripts/common/helpers/data/data_wiretapping.lua
/scripts/common/helpers/delivery_mission_defaults.lua
/scripts/common/helpers/delivery_objective_tables.lua
/scripts/common/helpers/difficulty_helper.lua
/scripts/common/helpers/dlc-services.lua
/scripts/common/helpers/entity_helper.lua
/scripts/common/helpers/event_helper.lua
/scripts/common/helpers/hud/skill_challenge_settings.lua
/scripts/common/helpers/hud/spoke_owa_icon_settings.lua
/scripts/common/helpers/mobile_store_inventory.lua
/scripts/common/helpers/persistent_locations/persistent_location_districts.lua
/scripts/common/helpers/persistent_locations/persistent_location_list.lua
/scripts/common/helpers/persistent_locations/persistent_location_teplates.lua
/scripts/common/helpers/services_definitions.lua
/scripts/common/helpers/tgrunwald/containers.lua
/scripts/common/helpers/tgrunwald/death_pool.lua
/scripts/common/helpers/tgrunwald/home_enter.lua
/scripts/common/helpers/tgrunwald/quest_helper.lua
/scripts/common/helpers/timer.lua
/scripts/common/helpers/viscript_helper.lua
/scripts/common/poi/poi.lua
/scripts/common/sandbox/gangsters_anger_manager.lua
/scripts/common/searchactionpoints/example.lua
/scripts/entities/interactions/interaction_placeholder_hold.vi
/scripts/entities/interactions/int_barrel_tossing_slave_hold.vi
/scripts/entities/interactions/int_construction_site_execution_boss_hold.vi
/scripts/entities/interactions/int_construction_site_execution_gunman_hold.vi
/scripts/entities/interactions/int_construction_site_execution_victim_hold.vi
/scripts/entities/interactions/int_father_james_serving_soup_civ_hold.vi
/scripts/entities/interactions/int_french_ward_brothel_fem_standing_rail_hold.vi
/scripts/entities/interactions/int_heist_giorgi_turn_in_shotgun_hold.vi
/scripts/entities/interactions/int_junky_hallucinogens_hold.vi
/scripts/entities/interactions/int_junky_kicked_hold.vi
/scripts/entities/interactions/int_junky_twitchy_hold.vi
/scripts/entities/interactions/int_kill_olivia_game_room_guard_l_hold.vi
/scripts/entities/interactions/int_kill_the_judge_dealer_1_hold.vi
/scripts/entities/interactions/int_kill_the_judge_dealer_2_hold.vi
/scripts/entities/interactions/int_kill_tommy_trainer_tending_hero_trainer_hold.vi
/scripts/entities/interactions/int_mugging_civilian_hold.vi
/scripts/entities/interactions/int_patrol_delay_eat_snack_hold.vi
/scripts/entities/interactions/int_plow_house_pull_guy_in_room_fem_hold.vi
/scripts/entities/interactions/int_plow_house_pull_guy_in_room_male_hold.vi
/scripts/entities/interactions/int_police_harass_hobo_hold.vi
/scripts/entities/interactions/int_police_obstruct_shop_hold.vi
/scripts/entities/interactions/int_prostitution_solicit_attempt_hold.vi
/scripts/entities/interactions/int_raking_working_hold.vi
/scripts/entities/interactions/int_standing_idle_hold.vi
/scripts/entities/interactions/int_standing_read_newspaper_hold.vi
/scripts/entities/interactions/int_voter_registration_police_disrupt_civ1_hold.vi
/scripts/entities/interactions/int_voter_registration_police_disrupt_civ2_hold.vi
/scripts/entities/interactions/int_west_marais_brothel_fem_standing_hold.vi
/scripts/entities/interactions/int_west_marais_brothel_pimp_standing_hold.vi
/scripts/entities/interactions/sc_protest_listener_hold.vi
/scripts/missions/bc_city/rare_cars.lua
/scripts/missions/statistic_tracking/statistic_tracking.lua
```


For DDS you need skip additional header with 0x2F bytes after decompress. You can do it here in TextureViewer:

```
		{
			MemoryStream memory = new MemoryStream();
			memory.Write(this.Resource.Data, 0, this.Resource.Data.Length);
			memory.Position = 0L;
			DDSFile expr_32 = new DDSFile();
			expr_32.Deserialize(memory);
			Image image = expr_32.Image(true, true, true, this.toggleAlphaButton.Checked);
			if (this.toolStripButton1.Checked)
			{
				this.previewPictureBox.Dock = DockStyle.Fill;
				this.previewPictureBox.Image = image;
				this.previewPictureBox.SizeMode = PictureBoxSizeMode.Zoom;
				return;
			}
			this.previewPictureBox.Dock = DockStyle.None;
			this.previewPictureBox.Image = image;
			this.previewPictureBox.Width = image.Width;
			this.previewPictureBox.Height = image.Height;
			this.previewPictureBox.SizeMode = PictureBoxSizeMode.Normal;
		}
```


Try set to 0x2F for code (memory.Position = 0L;) and this will be enought i guess
## Post #16
- Username: iambosh
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Oct 04, 2014 12:22 pm
- Post datetime: 2016-10-12T02:12:06+00:00
- Post Title: Re: Mafia 3 - .SDS

> Reply from CarLuver69
>
> Posting my research here in case anyone can put it to good use. I'll probably make my own tools eventually, but I don't have an ETA on that 

Thanks to aluigi for his Mafia .SDS (PS3) script, it helped point me in the right direction.

NOTE: I'm probably wrong on a lot of this, so please feel free to make corrections. I'm most likely off on the chunkCount being used to determine how many SDSChunkData's there are.
Code: Select allstruct SDSFile {
    int magic; // 0x534453 ('SDS\0')
    
    int version; // 0x14 (v20 / v1.4?)
    
    enum SDSType : int {
        PC = 0x4350,
        
        /* These are ASSUMED, I only have the PC version */
        PS4 = 0x345350,
        XB1 = 0x314258,
    } type;
    
    int unk_0C; // 0x5DE53FDE
    
    int dataInfoOffset;
    int dataOffset;
    
    int unk_18; // always zero?
    int unk_1C; // offset / size of something?
    int unk_20; // always zero?
    int unk_24; // offset / size of something?
    int unk_28; // always zero?
    int unk_2C; // 1
    int unk_30; // always zero?
    int unk_34; // always zero?
    int unk_38; // always zero?
    int unk_3C; // always zero?
    
    int chunkCount; // how many data chunks? (educated guess)
    int reserved; // checksum, hash, or key of some sort?
    
    /* @ dataInfoOffset */
    struct SDSDataInfo {
        int count; // how many data types there are
        
        struct SDSDataType {
            int typeIndex; // local index to reference this type
            
            int strLen;
            char typeName[strLen]; // no null-terminator
            
            int reserved; // possibly a guard? (always zero?)
        } dataTypes[count];
    
    } dataInfo;
    
    /* @ dataOffset */
    struct SDSData {
        int magic; // 0x6C7A4555 ('UEzl')
        
        int unk_04; // 0x10000? (never seems to change)
        char unk_05; // 4?
        
        struct SDSChunkData {
            int dataSize; // size of SDSChunkData
            char dataType; // reference to SDSDataInfo.dataType
            
            struct SDSChunkData {
                int memorySize; // size in memory? (e.g. uncompressed size)
                
                int bufferOffset; // offset to start of data
                
                int memorySize_2; // SDSData.unk_04 again?
                
                short unk_0A; // number of something? (this format is confusing)
                short unk_0C; // 0x80F?
                
                short bufferSize; // this might be an int, but unlikely
                /*
                    <<< Data padding >>>
                */
                /* @ bufferOffset */
                char buffer[bufferSize];
            } data;
        } chunks[chunkCount];
    };
};

hey man do you have a compiled version? it wont compile for me for some reason in visual studio
## Post #17
- Username: BitEmE
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jun 23, 2014 5:06 pm
- Post datetime: 2016-10-12T22:15:17+00:00
- Post Title: Re: Mafia 3 - .SDS

> Reply from Ekey
>
> BitEmE wrote:
Also the content seems to be encrypted, I've tried to open an encrypted DDS file -> exception.
They not encrypted, chunks are compressed with Zlib. About XML toc > not exist anymore. Content filenames hashed (fnv64a).
Code: Select alluint64 m3_gethash(unsigned char *m_String, int dwLength)
{
   uint64 dwHash = 0xCBF29CE484222325;
   for(int i = 0; i < dwLength; i++)
   {
      dwHash *= 0x00000100000001B3;
      dwHash ^= m_String[i];
   }
  return dwHash;
}

Some names
Code: Select all/gui/pop/garage.dds

For DDS you need skip additional header with 0x2F bytes after decompress. You can do it here in TextureViewer:
Code: Select all		private void UpdatePreview()
		{
			...
		}

Try set to 0x2F for code (memory.Position = 0L;) and this will be enought i guess

Ok the thing with zlib, I get it. 
But i have the following problem at the moment:

My .SDS File has 9 chunks, the alignment is 0x10000 (65335)
The first file has a size of 699239 bytes (682kb)


Of course I can't read the file, because there are too less chunks (at least I'm getting exceptions thrown in my face)
9 Chunks a. 65335 bytes alignment = 588015 bytes

So I will always fail to read that file.

Am I doing something with zlib wrong?
I think the TypeID and Version are correct? Maybe the file sizes too?

I am confused right now. Would be great if someone could tell me what I'm doing wrong or at least giving me a clue 
Thanks!
## Post #18
- Username: chipsman
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Dec 20, 2010 5:15 am
- Post datetime: 2016-10-13T13:34:55+00:00
- Post Title: Re: Mafia 3 - .SDS

> Reply from BitEmE
>
> ...

Zlib decompression is exactly the same as was in the M2

About files.. It looks like now the file header has bigger size than was before (36 bytes instead of 30, I have such assumption because there was extra 11 bytes between file header and DDS file magic in M2, if we follow the same logic - the header size has increased by 6 bytes) 

here is my 010 Editor Templates for sds files and decompressed memory blocks [https://github.com/Chipsman/mafia3-010ETemplates](https://github.com/Chipsman/mafia3-010ETemplates)
may be it will help you somehow

p.s.: anybody knows where radio music is located? here Mafia III\sds_retail\audio or here Mafia III\edit\audio\packages ?
## Post #19
- Username: GRiNDERKILLER
- Rank: veteran
- Number of posts: 92
- Joined date: Thu Jul 12, 2012 7:24 pm
- Post datetime: 2016-10-13T16:03:29+00:00
- Post Title: Re: Mafia 3 - .SDS

\edit\audio\packages\radio_global.pck
## Post #20
- Username: BitEmE
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jun 23, 2014 5:06 pm
- Post datetime: 2016-10-13T22:36:52+00:00
- Post Title: Re: Mafia 3 - .SDS

Alright, thanks to your help guys, really apprechiate it!

I'm now able to extract/show DDS files. Unfortunately DDs file in Mafia 3 can have the compression types ATI and DXT10, I'm not quite sure how to fix those decompressions with the texture viewer, but that's just a minor problem. (Also extracting is kind of a problem as there are +4 bytes infront of the magic DDs identifier of the file, so external DDs viewer will fail to load the image)


Also I've modified the XML reading and get now 'readable' XML content. Again, unfortunately, the format has changed in Mafia 3. The Problem right now is that I'm not able to say that the next node in memory is an attribute of a node, is a value, a child, or another node.
For example, with this file it's working because the values are only numeric (I'm using a hack at the moment to detect values inside nodes -> TryDouble)


With this file, it's not working because there are node attributes (see xsi:type is a node instead of attribute)


The structure is weird because it looks like this:

node type = 4
6 bytes = 0
String (length is not written in memory, you have to check for null terminator)
String Terminator
node type = 4
6 bytes = 0
String (length is not written in memory, you have to check for null terminator)
... and so on and so on..

So basically there's always a 4 between all nodes (maybe seperator? idk)
I don't know how I should figure out what's a child node, what's an attribute etc..

Again, here's the source (Just based of Rick's Mafia 2 tool) [https://github.com/MartinJK/Mafia3SDSExplorer](https://github.com/MartinJK/Mafia3SDSExplorer) (in case someone of you wants to try it out etc.)

Thanks for you help guys, really apprechiate it. I'm used to reverse engineer and mod games, this is the first time I'm trying to 'reverse' the files format and create a tool for it
## Post #21
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2016-10-14T00:33:07+00:00
- Post Title: Re: Mafia 3 - .SDS

Some new names 

```
/gui/pop/womaniser_voodoo_dancer.dds
/gui/pop/alternative_shop.dds
/gui/pop/classy_shop.dds
/gui/pop/cloth_shop.dds
/gui/pop/fashion_shop.dds
/gui/pop/gun_shop.dds
/gui/pop/item_shop.dds
/gui/pop/shades_shop.dds
/gui/bc_map_pcp_lab_a.gfx
/gui/config/maps/bc_map_pcp_lab_a
/gui/hideout_district_assignment.swf
/gui/images/icons/button_a.dds
/gui/images/icons/button_b.dds
/gui/images/icons/button_x.dds
/gui/images/icons/other_icons0031.dds
/gui/images/icons/other_icons0037.dds
/gui/images/icons/other_icons0099.dds
/gui/images/icons/other_icons0101.dds
/gui/images/icons/other_icons0103.dds
/gui/images/icons/other_icons0105.dds
/gui/images/icons/other_icons0106.dds
/gui/interact_collectable.swf
/gui/interact_object.swf
/gui/interact_weapon_pickup.swf
/gui/in_world_menu.swf
/gui/pop/garage.dds
/gui/pop/home.dds
/gui/scripted_test.swf

/xbin/cities.xlaybin
/xbin/plotlines.xlaybin
/xbin/missions.xlaybin
/xbin/quests.xlaybin
/xbin/game_events.xlaybin
/xbin/persistent_characters.xlaybin
/xbin/businesses.xlaybin
/xbin/speeches.xlaybin
/xbin/shops.xlaybin
/xbin/cities_game_group.xbin
/xbin/plotlines_group.xbin
/xbin/missions_group.xbin
/xbin/quests_group.xbin
/xbin/game_events_group.xbin
/xbin/persistent_characters_group.xbin
/xbin/businesses_group.xbin
/xbin/streammap_gameinit_group.xbin
/xbin/speeches_game_group.xbin
/xbin/generic_speech_mp.xlaybin
/xbin/generic_speech_mp_group.xbin
/xbin/generic_speech_situations_group.xbin
/xbin/generic_speech_variations_group.xbin
/xbin/shops_group.xbin
/xbin/game_main.xlaybin
/xbin/game_main_group.xbin
/xbin/expressiondata.xlaybin
/xbin/game_expressions_group.xbin
/xbin/charactertable.xlaybin
/xbin/charactertable_cinematics_group.xbin

/sds/maps/mapa_bourbon2.sds
/sds/maps/mapa_testscene.sds

/root/Situations
/root/Variations
/root/CharacterTableMP
/root/StreamMapTableMP
/root/GameEventsTableMP
/root/QuestsTableMP
/root/MissionsTable
/root/SpeechesTableMP
/root/PlotlinesTableMP
/root/BusinessesTableMP
/root/PersistentCharactersTableMP

/fsm/persistent_characters/alvarez_active
/fsm/persistent_characters/alvarez_inactive
/fsm/persistent_characters/biaggio_active
/fsm/persistent_characters/biaggio_inactive
/fsm/persistent_characters/cesar_active
/fsm/persistent_characters/cesar_inactive
/fsm/persistent_characters/clayton_active
/fsm/persistent_characters/clayton_inactive
/fsm/persistent_characters/creed_active
/fsm/persistent_characters/creed_inactive
/fsm/persistent_characters/danny_quest_active
/fsm/persistent_characters/danny_quest_inactive
/fsm/persistent_characters/doctor_active
/fsm/persistent_characters/doctor_inactive
/fsm/persistent_characters/donovan_active
/fsm/persistent_characters/donovan_inactive
/fsm/persistent_characters/mack_quest_active
/fsm/persistent_characters/mack_quest_inactive
/fsm/persistent_characters/marcano_active
/fsm/persistent_characters/marcano_inactive
/fsm/persistent_characters/maria_active
/fsm/persistent_characters/maria_inactive
/fsm/persistent_characters/martinez_active
/fsm/persistent_characters/martinez_inactive
/fsm/persistent_characters/professor_active
/fsm/persistent_characters/professor_inactive
/fsm/persistent_characters/sixto_active
/fsm/persistent_characters/sixto_inactive

/scripts/gamelogic/bc_openworld
/scripts/gamelogic/fpm/fpm_plotline
/scripts/gamelogic/milestones/milestone27/drug_farm_main
/scripts/gamelogic/milestones/milestone27/gameplay_bricks/shooting_from_boat
/scripts/gamelogic/milestones/milestone27/gameplay_bricks/shooting_from_car
/scripts/gamelogic/milestones/milestone28/steal_rum
/scripts/gamelogic/plotline_act2
/scripts/gamelogic/testscenes/bourbon_test_mission/bourbon_test_mission
/scripts/gamelogic/testscenes/districts/west_marais_district_structure_quest
/scripts/gamelogic/testscenes/districts/wharf_district_structure_quest
/scripts/gamelogic/testscenes/game_structure_init
/scripts/gamelogic/testscenes/game_structure_quest
/scripts/gamelogic/testscenes/open_world/main
/scripts/gamelogic/testscenes/racing_focustest/main
/scripts/gamelogic/testscenes/test_bartek/simple
/scripts/gamelogic/testscenes/test_racing_pod/main
```
## Post #22
- Username: Skrillex
- Rank: advanced
- Number of posts: 66
- Joined date: Sat Aug 23, 2014 1:11 am
- Post datetime: 2016-10-14T01:28:10+00:00
- Post Title: Re: Mafia 3 - .SDS

> Reply from BitEmE
>
> Alright, thanks to your help guys, really apprechiate it!

Thanks for you help guys, really apprechiate it. I'm used to reverse engineer and mod games, this is the first time I'm trying to 'reverse' the files format and create a tool for it

We owe you bro, thanks. Can you share compiled version of this script? And i want a question, this tool does it work to subtitles.sds files, can you extract and repack clearly?
## Post #23
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2016-10-14T19:52:47+00:00
- Post Title: Re: Mafia 3 - .SDS

Info for PCKG archives

```
{
   uint32_t   dwID; // Always PCKG (0x50434B47)
   uint32_t   dwVersion; // 1
   uint32_t   dwTotalFiles;
   uint32_t   dwFlag; // 0xFFFFFFFF
};

struct PCKGEntry
{
   uint64_t   dwHash; // Hash of filename?
   uint32_t   dwOffset;
   uint32_t   dwSize;
   uint32_t   dwZSize;
};
```
## Post #24
- Username: Godxon1
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Jun 06, 2015 2:35 am
- Post datetime: 2016-10-15T16:41:08+00:00
- Post Title: Re: Mafia 3 - .SDS

> Reply from BitEmE
>
> Alright, thanks to your help guys, really apprechiate it!

I'm now able to extract/show DDS files. Unfortunately DDs file in Mafia 3 can have the compression types ATI and DXT10, I'm not quite sure how to fix those decompressions with the texture viewer, but that's just a minor problem. (Also extracting is kind of a problem as there are +4 bytes infront of the magic DDs identifier of the file, so external DDs viewer will fail to load the image)


Also I've modified the XML reading and get now 'readable' XML content. Again, unfortunately, the format has changed in Mafia 3. The Problem right now is that I'm not able to say that the next node in memory is an attribute of a node, is a value, a child, or another node.
For example, with this file it's working because the values are only numeric (I'm using a hack at the moment to detect values inside nodes -> TryDouble)


With this file, it's not working because there are node attributes (see xsi:type is a node instead of attribute)


The structure is weird because it looks like this:

node type = 4
6 bytes = 0
String (length is not written in memory, you have to check for null terminator)
String Terminator
node type = 4
6 bytes = 0
String (length is not written in memory, you have to check for null terminator)
... and so on and so on..

So basically there's always a 4 between all nodes (maybe seperator? idk)
I don't know how I should figure out what's a child node, what's an attribute etc..

Again, here's the source (Just based of Rick's Mafia 2 tool) https://github.com/MartinJK/Mafia3SDSExplorer (in case someone of you wants to try it out etc.)

Thanks for you help guys, really apprechiate it. I'm used to reverse engineer and mod games, this is the first time I'm trying to 'reverse' the files format and create a tool for it
Can you please post here builded version of your tool? Thx
## Post #25
- Username: chipsman
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Dec 20, 2010 5:15 am
- Post datetime: 2016-10-16T08:17:31+00:00
- Post Title: Re: Mafia 3 - .SDS

Audio packages format info (AKPK)

```
{
    char    dwMagic[4];   // AKPK (0x4B504B41h)
    DWORD   dwHeaderSize; // +0x4
    DWORD   _f8;
    DWORD   _fC;
    DWORD   _f10;
    DWORD   _f14;
    DWORD   _f18;
    DWORD   _f1C;
    DWORD   _f20;
    DWORD   _f24;
    DWORD   _f28;
    DWORD   _f2C;
    DWORD   _f30;
    DWORD   dwFileCount;    //+0x34
};

struct FileEntry
{
    DWORD   dwHash;     // +0x0
    DWORD   _f4;        // always 16,  block size ? or aligment ?
    DWORD   dwSize;     // +0x8
    DWORD   dwOffsetInBlocks; //+0xC // block size == 16
    DWORD   _f10;       // always 0, // or dwOffsetInBlocks is QWORD
};

```


Audio is stored in .wav container but the format/codec inside is unknown

here is 010 template [https://github.com/Chipsman/mafia3-010E ... /m3-pck.bt](https://github.com/Chipsman/mafia3-010ETemplates/blob/master/m3-pck.bt)
## Post #26
- Username: iambosh
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Oct 04, 2014 12:22 pm
- Post datetime: 2016-10-22T21:44:48+00:00
- Post Title: Re: Mafia 3 - .SDS

any progress on decrypting the dat files?
## Post #27
- Username: Skrillex
- Rank: advanced
- Number of posts: 66
- Joined date: Sat Aug 23, 2014 1:11 am
- Post datetime: 2016-10-27T16:55:30+00:00
- Post Title: Re: Mafia 3 - .SDS

> Reply from Skrillex
>
> BitEmE wrote:Alright, thanks to your help guys, really apprechiate it!

Thanks for you help guys, really apprechiate it. I'm used to reverse engineer and mod games, this is the first time I'm trying to 'reverse' the files format and create a tool for it 

We owe you bro, thanks. Can you share compiled version of this script? And i want a question, this tool does it work to subtitles.sds files, can you extract and repack clearly?
## Post #28
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2016-10-31T20:28:39+00:00
- Post Title: Re: Mafia 3 - .SDS

I just wanted to add my support for anyone thinking of putting tools together for this game! Love it! Great character models, and vehicles, too! Would love to be able to get in and take a proper look at some of them...!
## Post #29
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-11-19T13:19:02+00:00
- Post Title: Re: Mafia 3 - .SDS

> Reply from iambosh
>
> any progress on decrypting the dat files?

they are not encrypted
## Post #30
- Username: iambosh
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Oct 04, 2014 12:22 pm
- Post datetime: 2016-11-20T04:49:31+00:00
- Post Title: Re: Mafia 3 - .SDS

> Reply from daemon1
>
> iambosh wrote:any progress on decrypting the dat files?

they are not encrypted

yeah when decrypted with the tool the results from the sds are dat files with random names and they are encrypted. so no actual assets
## Post #31
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-11-20T08:50:07+00:00
- Post Title: Re: Mafia 3 - .SDS

> Reply from iambosh
>
> yeah when decrypted with the tool the results from the sds are dat files with random names and they are encrypted. so no actual assets

What? I repeat, they are NOT ENCRYPTED!

here: Lincolns' body and his head. All parts separated. And some car.
## Post #32
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-11-20T17:30:35+00:00
- Post Title: Re: Mafia 3 - .SDS

Now skeletons are working too...
## Post #33
- Username: TheMask85
- Rank: veteran
- Number of posts: 80
- Joined date: Sun May 19, 2013 7:55 am
- Post datetime: 2016-11-20T19:41:26+00:00
- Post Title: Re: Mafia 3 - .SDS

looks like you even got the vertex normals working, right?
## Post #34
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-11-20T20:22:04+00:00
- Post Title: Re: Mafia 3 - .SDS

> Reply from chipsman
>
> Audio is stored in .wav container but the format/codec inside is unknown

Are you serious? This is wwise ogg, the format used in so many games, you can't even count them.
## Post #35
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-11-20T20:23:09+00:00
- Post Title: Re: Mafia 3 - .SDS

> Reply from TheMask85
>
> looks like you even got the vertex normals working, right?
not yet. but they look the same as in mafia2
## Post #36
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-11-24T19:37:54+00:00
- Post Title: Re: Mafia 3 - .SDS

Don't know why, but all bodies in game are naked, and all dress parts are stored separately.
## Post #37
- Username: JimmyJ
- Rank: beginner
- Number of posts: 32
- Joined date: Wed Dec 21, 2011 8:54 am
- Post datetime: 2016-11-24T22:37:18+00:00
- Post Title: Re: Mafia 3 - .SDS

> Reply from daemon1
>
> Don't know why, but all bodies in game are naked, and all dress parts are stored separately.
how you extract models?
## Post #38
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-11-25T15:42:44+00:00
- Post Title: Re: Mafia 3 - .SDS

> Reply from JimmyJ
>
> how you extract models?

Some user here said that files are encrypted. To prove that its wrong, I quickly made a tool to extract models.
## Post #39
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2016-11-25T17:35:01+00:00
- Post Title: Re: Mafia 3 - .SDS

> Reply from daemon1
>
> JimmyJ wrote:how you extract models?

Some user here said that files are encrypted. To prove that its wrong, I quickly made a tool to extract models.

Nice. I hope you share that soon. Preferably with source code.
## Post #40
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-11-25T18:13:33+00:00
- Post Title: Re: Mafia 3 - .SDS

> Reply from volfin
>
> Nice. I hope you share that soon. Preferably with source code.

Why do you need source? If you want to proceed with this game, please go ahead, I'll provide you with all info. While I have a lot of other games to do.
## Post #41
- Username: TheMask85
- Rank: veteran
- Number of posts: 80
- Joined date: Sun May 19, 2013 7:55 am
- Post datetime: 2016-11-25T19:16:26+00:00
- Post Title: Re: Mafia 3 - .SDS

for some people (including me) who can't code, it's basically about having these models in a common, readable 3d format such as fbx, mesh.ascii, smd etc.
i mean the sheer variety of different people and clothing + these old school cars are like every modders dream.
long story short, i'd love to see a release of an unpacker and tool/script for 3DSmax, Noesis, Blender or such.
really digging what you're doing here!
## Post #42
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-11-25T20:01:44+00:00
- Post Title: Re: Mafia 3 - .SDS

ok i'm now working on more models to be supported. Statics, like weapons, have no bones.
## Post #43
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2016-11-26T02:20:57+00:00
- Post Title: Re: Mafia 3 - .SDS

> Reply from daemon1
>
> volfin wrote:Nice. I hope you share that soon. Preferably with source code.

Why do you need source? If you want to proceed with this game, please go ahead, I'll provide you with all info. While I have a lot of other games to do.

That's fine, I can usually just read the source to understand the structure, but if you want to provide the structure, that works too.
## Post #44
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-11-26T12:41:08+00:00
- Post Title: Re: Mafia 3 - .SDS

the tool will be posted there: [viewtopic.php?f=16&t=15543](http://forum.xentax.com/viewtopic.php?f=16&t=15543)
## Post #45
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2017-02-26T14:06:46+00:00
- Post Title: Re: Mafia 3 - .SDS

Hello,

Some files can't be extracted with [luigi's script](http://aluigi.altervista.org/bms/mafia_sds_ps3.bms).

Here's are the files:
[http://www.mediafire.com/file/l9grvqjsj ... ackable.7z](http://www.mediafire.com/file/l9grvqjsjse0g9r/m3_cars_not_unpackable.7z)
[http://www.mediafire.com/file/93i8m1p7g ... ackable.7z](http://www.mediafire.com/file/93i8m1p7gpp97zh/m3_auto_unique_not_unpackable.7z)
[http://www.mediafire.com/file/bvea585cy ... ackable.7z](http://www.mediafire.com/file/bvea585cy180b7v/m3_auto_not_unpackable.7z)
## Post #46
- Username: RolandHUE
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Feb 25, 2017 5:14 am
- Post datetime: 2017-02-28T16:07:38+00:00
- Post Title: Re: Mafia 3 - .SDS

How can i extract car models? I'm looking to extract the Eckhart Champion. But i dont undestand how this software works. Could someone provide me the car model and its textures?
## Post #47
- Username: ramyzahran
- Rank: n00b
- Number of posts: 19
- Joined date: Tue May 23, 2017 7:41 am
- Post datetime: 2018-11-12T17:43:15+00:00
- Post Title: Re: Mafia 3 - .SDS

Up
## Post #48
- Username: ner0
- Rank: advanced
- Number of posts: 50
- Joined date: Sun Aug 28, 2011 11:47 pm
- Post datetime: 2018-11-12T23:24:29+00:00
- Post Title: Re: Mafia 3 - .SDS

> Reply from daemon1
>
> the tool will be posted there: viewtopic.php?f=16&t=15543
Also, maybe this is useful for the intended purpose: [https://mafiamods.com/mods/mafia-iii-resource-explorer/](https://mafiamods.com/mods/mafia-iii-resource-explorer/)
## Post #49
- Username: MichaelBFS
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Jan 04, 2021 10:18 pm
- Post datetime: 2023-08-12T20:01:40+00:00
- Post Title: Re: Mafia 3 - .SDS

Hi,
Any progress on decrypting the dat (subtitles) files?
## Post #50
- Username: memz
- Rank: beginner
- Number of posts: 23
- Joined date: Fri Dec 16, 2022 8:00 pm
- Post datetime: 2023-08-12T22:38:34+00:00
- Post Title: Re: Mafia 3 - .SDS

> Reply from MichaelBFS ↑Sun Aug 13, 2023 4:01 am at Sun Aug 13, 2023 4:01 am
>
> 
Hi,
Any progress on decrypting the dat (subtitles) files?

Try this: [https://github.com/Greavesy1899/MafiaToolkit/releases](https://github.com/Greavesy1899/MafiaToolkit/releases)
