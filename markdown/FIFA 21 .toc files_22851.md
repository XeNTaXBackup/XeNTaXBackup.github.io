## Post #1
- Username: fifamodgen
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Oct 18, 2020 2:50 am
- Post datetime: 2020-10-17T20:00:57+00:00
- Post Title: FIFA 21 .toc files

Looking for any ideas what the mystery block is in the FIFA 21 .toc files. Hoping it's a string table.

In the attached .toc files, skip to offset 588 to read the (big endian) 4-byte offset to the mystery block. For globals.toc, that offset is 3892. Add 556 to the offset to account for the XOR key and signature block at the start of the file. So, the mystery block starts at offset 3892 + 556 = 4448.

Skip to offset 604 to read a (big endian) 4-byte value which, multiplied by 4, gives the length of the block in bytes. So the length of the mystery block is 126 * 4 = 504 bytes.

Offset 8 to 263 is apparently a 256 byte XOR key, but I don't know if it's being used here. Usually the entire file is XOR'ed with it, if anything.
[globals.zip](https://xentaxbackup.github.io/file/18849_globals.zip)
## Post #2
- Username: fifamodgen
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Oct 18, 2020 2:50 am
- Post datetime: 2020-10-17T20:04:47+00:00
- Post Title: FIFA 21 .toc files

There are a lot of repetitions or very similar values that repeat, which suggest it's not encrypted or compressed. What I'm really hoping to find is the string table containing names of the bundles, which all previous Frostbite games have had in the .toc file - FIFA 21 seems to be the first without them being clearly readable.



globals block.png (39 KiB) Viewed 56 times



Looking at the globals.toc from FIFA 20, it would be quite expected that there are values that are repeated, as the first part of the name often matches. The bundle names from FIFA 20 are:

```
anthems/anthems_02.sbr
content/worlds/lighting/visenviros/bundles/base_night_bp
content/worlds/lighting/visenviros/bundles/base_sunny_bp
crowdloops/ambience_drum.sbr
crowdloops/ambience_gen.sbr
crowdloops/ambience_neth.sbr
crowdloops/beds_common.sbr
crowdloops/beds_common_male.sbr
crowdloops/beds_large_generic.sbr
crowdloops/beds_large_germany.sbr
crowdloops/beds_large_latin_and_spain.sbr
crowdreactions/goals_large.sbr
crowdreactions/heckles_gen.sbr
crowdreactions/heckles_uk.sbr
crowdreactions/reactions_all_sizes_common.sbr
crowdreactions/reactions_all_sizes_common_male.sbr
crowdreactions/reactions_all_sizes_generic.sbr
crowdreactions/reactions_all_sizes_generic_male.sbr
crowdreactions/reactions_all_sizes_uk.sbr
crowdreactions/reactions_futsal_latin_and_spain.sbr
crowdreactions/reactions_futsal_north_america.sbr
crowdreactions/reactions_large_common.sbr
crowdreactions/reactions_large_common_male.sbr
crowdreactions/reactions_large_generic.sbr
crowdreactions/reactions_large_generic_male.sbr
crowdreactions/reactions_large_germany.sbr
crowdreactions/reactions_large_latin_and_spain.sbr
crowdreactions/reactions_large_uk.sbr
default_settings
eatrax/eatrax_01.sbr
eatrax/highlights_music_01.sbr
eatrax/intromusic_01.sbr
fifa/fifa_gameconfig
fifa/movies/moviesinstall_sba
sfx/arena.sbr
sfx/arena_na.sbr
sfx/be_sfx.sbr
sfx/bootflow.sbr
sfx/playerwalla_male.sbr
sfx/propsfx.sbr
shouts/shouts_large.sbr
shouts/ucc_nonlocalized.sbr
sound/chants/chants_demo_sba
sound/speech/announcer/announcer_00_eng1/announcer_eng1_announcer_launch_brt
sound/speech/announcer/announcer_00_eng2/announcer_eng2_announcer_launch_brt
sound/speech/announcer/announcer_00_eng3/announcer_eng3_announcer_launch_brt
sound/speech/announcer/announcer_sb
sound/speech/commentary/commentary_sb
sound/speech/commentary/eng_us/eng_us_loccom_brt
sound/speech/commentary/eng_us_2/eng_us_2_loccom_brt
sound/speech/loccommentary/ara_sa/ara_sa_loccom_brt
sound/speech/loccommentary/dut_nl/dut_nl_loccom_brt
sound/speech/loccommentary/fre_fr/fre_fr_loccom_brt
sound/speech/loccommentary/ger_de/ger_de_loccom_brt
sound/speech/loccommentary/ita_it/ita_it_loccom_brt
sound/speech/loccommentary/jpn_jp/jpn_jp_loccom_brt
sound/speech/loccommentary/pol_pl/pol_pl_loccom_brt
sound/speech/loccommentary/por_br/por_br_loccom_brt
sound/speech/loccommentary/rus_ru/rus_ru_loccom_brt
sound/speech/loccommentary/spa_es/spa_es_loccom_brt
sound/speech/loccommentary/spa_mx/spa_mx_loccom_brt
sound/ssf/pa/database/ssfpadatabasegroup_ssfpa_brt
sound/ssf/pa/ssfpa_sb
sound/ssf/pa/wavecollections/all_all_ssfpa_brt
sound/ssf/pa/wavecollections/bra_all_ssfpa_brt
sound/ssf/pa/wavecollections/bra_pro_ssfpa_brt
sound/ssf/pa/wavecollections/bra_street_ssfpa_brt
sound/ssf/pa/wavecollections/dut_all_ssfpa_brt
sound/ssf/pa/wavecollections/dut_pro_ssfpa_brt
sound/ssf/pa/wavecollections/dut_street_ssfpa_brt
sound/ssf/pa/wavecollections/eng1_all_ssfpa_brt
sound/ssf/pa/wavecollections/eng1_pro_ssfpa_brt
sound/ssf/pa/wavecollections/eng1_street_ssfpa_brt
sound/ssf/pa/wavecollections/eng3_all_ssfpa_brt
sound/ssf/pa/wavecollections/eng3_pro_ssfpa_brt
sound/ssf/pa/wavecollections/eng3_street_ssfpa_brt
sound/ssf/playercalls/database/ssfplayercalldatabasegroup_ssf_pc_brt
sound/ssf/playercalls/ssfplayercall_full_sb
sound/ssf/playercalls/ssfplayercall_sb
sound/ssf/playercalls/wavecollections/ssf_player_calls_demo_ssf_pc_brt
ssf/environment_11v11arena.sbr
ssf/environment_language_dutch.sbr
ssf/ssf_crowdbank_pickup.sbr
ssf/ssf_stadium_1010_amsterdam.sbr
systems/frostbitestartupdata
ui/fifaloadingscreen_sb
uisfx/ui_sfx_arena.sbr
uisfx/ui_sfx_core_menu.sbr
webbrowser/webbrowserresourcebundle
```
