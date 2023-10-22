## Post #1
- Username: Dandapani
- Rank: advanced
- Number of posts: 55
- Joined date: Tue Jul 03, 2007 12:11 am
- Post datetime: 2007-07-11T19:22:32+00:00
- Post Title: Shrek the Third - .RES files

Need a way to unpack these archives. I need to extract the audio and game sounds.  Attached is a snippet of the "streams.res" file.

Thanks in advance for your help.
[streams.res.zip](https://xentaxbackup.github.io/file/1258_streams.res.zip)
## Post #2
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2007-07-12T22:07:56+00:00
- Post Title: Shrek the Third - .RES files

I only know the sound's are raw pcm
## Post #3
- Username: Dandapani
- Rank: advanced
- Number of posts: 55
- Joined date: Tue Jul 03, 2007 12:11 am
- Post datetime: 2007-07-13T11:41:35+00:00
- Post Title: Shrek the Third - .RES files

> Reply from Savage
>
> I only know the sound's are raw pcm

filedmp'ing the res file it seems the names are in one hash dictionary and the offsets/lengths are in another dictionary.  Quite the puzzle.  Not as neat and tidy as the zsm/zss archives.

Raw PCM doesn't have a start and stop signature so hard to pick out the data in the raw RES file?
## Post #4
- Username: Dandapani
- Rank: advanced
- Number of posts: 55
- Joined date: Tue Jul 03, 2007 12:11 am
- Post datetime: 2007-07-19T15:29:04+00:00
- Post Title: Shrek the Third - .RES files

Hello?  Any new insights?  This .RES format is used for most of the game content including music, dialog, system sounds, etc. Would be nice to crack it...

ETA: here is a dump of the meaningful strings from the "streams.res" file...

music/castle_attack_1
music/castle_attack_2
music/commentary_10_ita
music/commentary_1_ita
music/commentary_3_ita
music/commentary_4_ita
music/commentary_5_ita
music/commentary_6_ita
music/commentary_7_ita
music/commentary_8_ita
music/commentary_9_ita
music/eq_castle_2
music/frontend_credits
music/frontend_multiplayer
music/hook03_pianointerlude1
music/hook06_pianointerlude2
music/lotl_cut_1
music/lotl_cut_2
music/mp_lose_stinger
music/mp_win_stinger
music/puss_theme_1
music/qc_danger1_loop
music/qc_danger2_loop
music/qc_danger3_loop
music/qc_humor1
music/qc_humor2
music/qc_humor3
music/quest_complete
music/s3_academy_witchboss
music/s3_academygrounds1
music/s3_academygrounds2
music/s3_audiocomm_lvl_13_final
music/s3_audiocomm_lvl_13_final_fre
music/s3_audiocomm_lvl_14_final
music/s3_audiocomm_lvl_14_final_fre
music/s3_audiocomm_lvl_15_final
music/s3_audiocomm_lvl_15_final_fre
music/s3_audiocomm_lvl_16_final
music/s3_audiocomm_lvl_16_final_fre
music/s3_audiocomm_lvl_1_final
music/s3_audiocomm_lvl_1_final_fre
music/s3_audiocomm_lvl_5_final
music/s3_audiocomm_lvl_5_final_fre
music/s3_audiocomm_lvl_6_final
music/s3_audiocomm_lvl_6_final_fre
music/s3_audiocomm_lvl_9_final
music/s3_audiocomm_lvl_9_final_fre
music/s3_audiocomm_pinn_final
music/s3_audiocomm_pinn_final_fre
music/s3_charmingboss
music/s3_cyclopsboss
music/s3_fiona_action
music/s3_fiona_catacombs1
music/s3_fiona_catacombs2
music/s3_frontend
music/s3_giantknightboss
music/s3_highhighfight
music/s3_icedragonboss
music/s3_jocksfight
music/s3_levelcomplete_stinger
music/s3_piratecaptain
music/s3_prisonaction
music/s3_rundown_farfaraway
music/sb_floating_theme
music/shrek3_babiescinema
music/shrek3_babiesingame
music/shrek3_charmingbossbattle
music/shrek3_congratsscreenfanfare
music/shrek3_congratsscreenloop
music/shrek3_detentionhighdanger
music/shrek3_docks1
music/shrek3_docks2
music/shrek3_evilqueen_asshrek
music/shrek3_evilqueencastle_puss
music/shrek3_farfar_pussship
music/shrek3_fionagoodbyecinema
music/shrek3_frontscreentuning
music/shrek3_giftshopv2
music/shrek3_highhighmtcave
music/shrek3_highhighmtoutside1
music/shrek3_highhighmtoutside2
music/shrek3_icelake2_artie
music/shrek3_icelake_shrek
music/shrek3_icelakeelevator
music/shrek3_lancelotcastleattack
music/shrek3_merlinshills
music/shrek3_merlinshills2
music/shrek3_prisonattackcinema
music/shrek3_prisonattackoutro
music/shrek3_prisoncastleattack
music/shrek3_prisoncell1
music/shrek3_prisoncell2
music/shrek3_prisoncellpuzzle
music/shrek3_ruins1
music/shrek3_shipasshrek
music/shrek3_sleepingbeautykissattack1
music/shrek3_sleepingbeautykissattack2
music/shrek3_strombolipuzzle
music/shrek3_stromboliworkshop
music/shrek3_tutorial
music/shrek3_worcestershirechase
music/shrek3_worcestroad1donkey
music/shrek3_worcestruins_interior
music/silence
music/witch_spell


Intriguing, isn't it
## Post #5
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2014-09-01T08:01:49+00:00
- Post Title: Shrek the Third - .RES files

[out]
## Post #6
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2014-09-02T09:02:38+00:00
- Post Title: Shrek the Third - .RES files

[out]
## Post #7
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2014-09-02T23:18:21+00:00
- Post Title: Shrek the Third - .RES files

[out]
## Post #8
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2014-09-03T14:45:49+00:00
- Post Title: Shrek the Third - .RES files

[out]
