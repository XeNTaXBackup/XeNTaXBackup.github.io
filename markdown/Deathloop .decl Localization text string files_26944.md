## Post #1
- Username: fuvegotado
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Jun 24, 2019 1:30 am
- Post datetime: 2023-07-05T17:26:59+00:00
- Post Title: Deathloop .decl Localization text string files

Deathloop uses the VOID engine, just like the Dishonored series. The data files are different though. I'm trying to extract the translations.

With deathloop.bms and master_resources.index the process appears to be similar ( [viewtopic.php?p=181858](https://forum.xentax.com/viewtopic.php?p=181858) )

The folder structure seems much much more complex:

output\generated\decls\localized contains:

```
brazilian/
english/
french/
german/
italian/
japanese/
korean/
mexican/
polish/
russian/
simplified_chinese/
spanish/
traditional_chinese/
```


arabic for example contains:

```
\---speech
    \---speech_barks
        +---combat
        |       bk_ally_death.decl
        |       bk_attack.decl
        |       bk_attack_grenade.decl
        |       bk_attack_invisible.decl
        |       bk_attack_jul.decl
        |       bk_chase.decl
        |       bk_chase_jul.decl
        |       bk_colt_react_alarm.decl
        |       bk_colt_rewind.decl
        |       bk_enter_combat_alarm.decl
        |       bk_enter_combat_buddy.decl
        |       bk_enter_combat_grenade.decl
        |       bk_enter_combat_nail.decl
        |       bk_flank.decl
        |       bk_hostile_turret.decl
        |       bk_isl_jul_kill_target.decl
        |       bk_isl_run_to_player.decl
        |       bk_jul_kill_colt.decl
        |       bk_move_cover.decl
        |       bk_player_hit_by_rock.decl
        |       bk_player_weaponjam.decl
        |       bk_reload_buddy.decl
        |       bk_reload_last_man.decl
        |       bk_respawn_first.decl
        |       bk_respawn_second.decl
        |       bk_roger.decl
        |       bk_see_player_no_ammo.decl
        |       bk_taunt.decl
        |       bk_taunt_last_man.decl
        |       bk_taunt_unreachable.decl
        |       bk_touch_react.decl
        |       bk_use_radio.decl
        |       bk_vanish.decl
        |       bk_vanish_jul.decl
        |       
        +---detection
        |       bk_busted.decl
        |       bk_busted_invisible.decl
        |       
        +---general
        |       bk_alarm_react.decl
        |       bk_effort_death_bullet.decl
        |       bk_effort_death_burst.decl
        |       bk_effort_death_explode.decl
        |       bk_effort_death_gas.decl
        |       bk_effort_death_silent.decl
        |       bk_effort_death_water.decl
        |       bk_effort_hit_bullet.decl
        |       bk_effort_hit_electric.decl
        |       bk_effort_hit_explode.decl
        |       bk_effort_hit_gas.decl
        |       bk_effort_hit_kick.decl
        |       bk_effort_hit_light.decl
        |       bk_effort_loco_land.decl
        |       bk_effort_loco_long_fall.decl
        |       bk_effort_loco_mantle.decl
        |       bk_jul_interaction.decl
        |       bk_jul_tag_gen.decl
        |       bk_jumpscare.decl
        |       bk_masquerade_react.decl
        |       bk_multiplayer_outofammo.decl
        |       bk_player_ammo.decl
        |       bk_player_assassination.decl
        |       bk_player_health.decl
        |       bk_surprised.decl
        |       bk_unsure.decl
        |       
        +---patrol
        |       bk_alarm_over.decl
        |       bk_ambient_noise_react.decl
        |       bk_broken_glass_react.decl
        |       bk_broken_obj_react.decl
        |       bk_check_this_out.decl
        |       bk_check_this_out_wary.decl
        |       bk_colt_locked_door.decl
        |       bk_corpse_sideline_react.decl
        |       bk_danger_react.decl
        |       bk_distraction_react.decl
        |       bk_footsteps_react.decl
        |       bk_glimpse_react.decl
        |       bk_idle.decl
        |       bk_idle_alterted.decl
        |       bk_impact_react.decl
        |       bk_isl_idle_radio.decl
        |       bk_isl_idle_radio_fup.decl
        |       bk_missing_batt_react.decl
        |       bk_missing_deploy_react.decl
        |       bk_new_deploy_react.decl
        |       bk_open_door_react.decl
        |       bk_reac_jul.decl
        |       bk_reac_jul_interrogation.decl
        |       bk_reac_jul_relief.decl
        |       bk_reac_jul_threat.decl
        |       bk_reac_jul_wtf.decl
        |       bk_search_giveup.decl
        |       bk_sec_target_react.decl
        |       bk_see_unusual_react.decl
        |       bk_tamper_react.decl
        |       bk_visual_react.decl
        |       
        +---radio
        |       bk_use_radio_2d.decl
        |       
        +---search
        |       bk_chase_giveup.decl
        |       bk_look_around.decl
        |       bk_search_buddy.decl
        |       bk_search_buddy_fup.decl
        |       bk_search_corpse.decl
        |       bk_search_lost_player.decl
        |       bk_search_missing_buddy.decl
        |       bk_search_noise.decl
        |       bk_search_saw_player.decl
        |       bk_search_tether.decl
        |       bk_stop_search.decl
        |       bk_stop_search_buddy.decl
        |       bk_stop_search_corpse.decl
        |       bk_stop_search_lost_player.decl
        |       
        \---streetspeakers
            +---antenna
            |   +---v1
            |   |       spk_wu_advert_v1.decl
            |   |       spk_wu_reward_01.decl
            |   |       spk_wu_reward_01_fail.decl
            |   |       spk_wu_reward_02.decl
            |   |       spk_wu_reward_03.decl
            |   |       spk_wu_reward_04.decl
            |   |       
            |   \---v2
            |           spk_egor_prop.decl
            |           
            +---common
            |   +---common
            |   |       spk_2bit_fiz_pop.decl
            |   |       spk_boomboomroom_advert_2.decl
            |   |       spk_gift_poster_aleksis.decl
            |   |       spk_gift_poster_charlie.decl
            |   |       spk_gift_poster_colt.decl
            |   |       spk_gift_poster_egor.decl
            |   |       spk_gift_poster_fia.decl
            |   |       spk_gift_poster_frank.decl
            |   |       spk_gift_poster_harriet.decl
            |   |       spk_gift_poster_julianna.decl
            |   |       spk_gift_poster_wenjie.decl
            |   |       spk_hunter_arrival_01.decl
            |   |       spk_hunter_arrival_02.decl
            |   |       spk_hunter_arrival_03.decl
            |   |       spk_hunter_arrival_04.decl
            |   |       spk_hunter_arrival_05.decl
            |   |       spk_jul_to_isl_at_01.decl
            |   |       spk_jul_to_isl_at_02.decl
            |   |       spk_jul_to_isl_at_03.decl
            |   |       spk_jul_to_isl_at_04.decl
            |   |       spk_jul_to_isl_at_05.decl
            |   |       spk_jul_to_isl_at_06.decl
            |   |       spk_jul_to_isl_at_07.decl
            |   |       spk_jul_to_isl_at_08.decl
            |   |       spk_jul_to_isl_at_09.decl
            |   |       spk_jul_to_isl_at_10.decl
            |   |       spk_jul_to_isl_nt_01.decl
            |   |       spk_jul_to_isl_nt_02.decl
            |   |       spk_jul_to_isl_nt_03.decl
            |   |       spk_jul_to_isl_nt_04.decl
            |   |       spk_jul_to_isl_nt_05.decl
            |   |       spk_jul_to_isl_nt_06.decl
            |   |       spk_jul_to_isl_nt_07.decl
            |   |       spk_jul_to_isl_nt_08.decl
            |   |       spk_jul_to_isl_nt_09.decl
            |   |       spk_rules_advert.decl
            |   |       
            |   +---v1
            |   |       spk_official_welcome.decl
            |   |       
            |   +---v2
            |   |       spk_firework_cancel.decl
            |   |       spk_firework_destroyed.decl
            |   |       
            |   \---v4
            |           spk_frank_fireworks.decl
            |           spk_frank_fireworks_eulogy.decl
            |           
            +---island
            |   +---common
            |   |       spk_diving_pit_advert.decl
            |   |       
            |   +---v1
            |   |       spk_macket_advert_antenna.decl
            |   |       spk_macket_advert_island.decl
            |   |       spk_macket_advert_upper.decl
            |   |       spk_macket_advert_wharf.decl
            |   |       spk_spy01_departed.decl
            |   |       
            |   \---v2
            |           spk_delivery_truck_01.decl
            |           spk_delivery_truck_02.decl
            |           spk_delivery_truck_03.decl
            |           spk_delivery_truck_04.decl
            |           spk_delivery_truck_05.decl
            |           
            +---tuto
            |   \---v1
            |           spk_colt_advance_jul.decl
            |           spk_ext_bay_julianna.decl
            |           spk_ext_bay_julianna_b.decl
            |           spk_frank_cast.decl
            |           spk_jul_gt6.decl
            |           
            +---upper_city
            |   +---common
            |   |       spk_bakery_shop_advert.decl
            |   |       spk_candyshop_advert.decl
            |   |       spk_firework_shop_advert_2.decl
            |   |       spk_isl_concert_advert.decl
            |   |       spk_jumping_death_advert.decl
            |   |       
            |   +---v1
            |   |       spk_charlie_minicom_alert.decl
            |   |       spk_trading_house_advert.decl
            |   |       spk_uc_trading_announce.decl
            |   |       
            |   +---v3
            |   |       spk_isl_moxie_ad.decl
            |   |       spk_isl_moxie_global_fail.decl
            |   |       spk_isl_moxie_intro_02.decl
            |   |       
            |   \---v4
            |           spk_aeon_workshop_burned.decl
            |           
            \---wharf
                \---common
                        spk_automaton_advert.decl
                        spk_gift_hunt_advert.decl
                        spk_glimpse_infinity_advert.decl
                        spk_madame_k_advert.decl
                        spk_maskmaker_shop_advert.decl
                        spk_treasure_ice_advert.decl
                        
speechscene
\---speech
    \---scene
        +---antenna
        |   +---common
        |   |       colt_egor_control_board_invisible.decl
        |   |       colt_egor_deactivate.decl
        |   |       colt_leave_note_hunt.decl
        |   |       jul_egor_control_board_invisible.decl
        |   |       
        |   \---v2
        |           wenjie_gt3_colt_friends.decl
        |           
        +---common
        |       colt_3_password.decl
        |       colt_curious.decl
        |       colt_frustrated.decl
        |       colt_gt_exit_door.decl
        |       colt_kills_p4_target.decl
        |       colt_lila.decl
        |       colt_loop_break.decl
        |       colt_mini_fireworks.decl
        |       colt_mini_hunt.decl
        |       colt_react_fms.decl
        |       colt_react_horizon.decl
        |       colt_schedule_reac.decl
        |       colt_visitor_object1.decl
        |       colt_visitor_object2.decl
        |       
        +---ending
        |       brief_jul_surrender.decl
        |       
        +---radiocalls
        |   +---brief
        |   |       convo_brief_aleksis.decl
        |   |       convo_brief_charlie.decl
        |   |       convo_brief_egor.decl
        |   |       convo_brief_fia.decl
        |   |       convo_brief_frank.decl
        |   |       convo_brief_gt_ant.decl
        |   |       convo_brief_gt_isl.decl
        |   |       convo_brief_gt_uc.decl
        |   |       convo_brief_harriet.decl
        |   |       convo_brief_wenjie.decl
        |   |       
        |   +---chater_l
        |   |       convo_chatter_bucket_12.decl
        |   |       convo_chatter_bucket_13.decl
        |   |       convo_chatter_bucket_14.decl
        |   |       convo_chatter_bucket_15.decl
        |   |       convo_chatter_bucket_16.decl
        |   |       convo_chatter_bucket_17.decl
        |   |       convo_chatter_bucket_18.decl
        |   |       convo_chatter_bucket_19.decl
        |   |       convo_end_chatter_bucket.decl
        |   |       
        |   +---chatter
        |   |       convo_chatter_bucket_01.decl
        |   |       convo_chatter_bucket_02.decl
        |   |       convo_chatter_bucket_03.decl
        |   |       convo_chatter_bucket_04.decl
        |   |       convo_chatter_bucket_05.decl
        |   |       convo_chatter_bucket_06.decl
        |   |       convo_chatter_bucket_07.decl
        |   |       convo_chatter_bucket_08.decl
        |   |       convo_chatter_bucket_09.decl
        |   |       convo_chatter_bucket_10.decl
        |   |       convo_chatter_bucket_11.decl
        |   |       
        |   +---choke
        |   |       convo_choke_1930.decl
        |   |       convo_choke_aeon.decl
        |   |       convo_choke_aeon_2.decl
        |   |       convo_choke_colt_history.decl
        |   |       convo_choke_father.decl
        |   |       convo_choke_gl_discovery.decl
        |   |       convo_choke_gl_late.decl
        |   |       convo_choke_slabs.decl
        |   |       
        |   +---day_one
        |   |       convo_d1_antenna.decl
        |   |       convo_d1_upper.decl
        |   |       convo_d1_wharf.decl
        |   |       
        |   +---death
        |   |       convo_3p_deaths_by_target.decl
        |   |       convo_death_generic_1.decl
        |   |       convo_first_death_by_jul.decl
        |   |       convo_first_jul_kill.decl
        |   |       convo_second_jul_kill.decl
        |   |       
        |   +---end
        |   |       convo_end_chicken_01.decl
        |   |       convo_end_chicken_02.decl
        |   |       convo_end_dumb.decl
        |   |       convo_end_half_dumb.decl
        |   |       convo_end_ruthless.decl
        |   |       
        |   +---golden_l
        |   |       convo_gl_antenna.decl
        |   |       convo_gl_island.decl
        |   |       convo_gl_island_fail.decl
        |   |       convo_gl_upper.decl
        |   |       convo_gl_upper_fail.decl
        |   |       convo_gl_wharf.decl
        |   |       
        |   +---gt
        |   |       convo_gt2_upper.decl
        |   |       convo_gt3_ant.decl
        |   |       convo_gt4_isl.decl
        |   |       convo_gt5_uc.decl
        |   |       convo_gt_post_infusion.decl
        |   |       
        |   +---kill_tar
        |   |       convo_killed_aleksis.decl
        |   |       convo_killed_charlie.decl
        |   |       convo_killed_egor.decl
        |   |       convo_killed_fia.decl
        |   |       convo_killed_fia_and_charlie.decl
        |   |       convo_killed_frank.decl
        |   |       convo_killed_harriet.decl
        |   |       convo_killed_wenjie.decl
        |   |       
        |   +---misc
        |   |       convo_carriers_tears.decl
        |   |       convo_colt_motivation.decl
        |   |       convo_daughter_02.decl
        |   |       convo_daughter_1.decl
        |   |       convo_first_non_target_mission.decl
        |   |       convo_frank_music.decl
        |   |       convo_killed_target_3p_times.decl
        |   |       convo_left_target_mission.decl
        |   |       convo_pick_rexly_finish.decl
        |   |       convo_serial_killer.decl
        |   |       convo_take_power_finish.decl
        |   |       convo_thehunt_complete.decl
        |   |       convo_ubiquity_start.decl
        |   |       
        |   \---tutorial
        |       \---v1
        |               rad_door_lock.decl
        |               rad_gt6_jul_lose.decl
        |               rad_gt6_jul_win.decl
        |               rad_jul_colt_double.decl
        |               rad_jul_colt_idle.decl
        |               rad_jul_colt_idle_alt.decl
        |               rad_jul_house_entryway.decl
        |               rad_jul_library.decl
        |               rad_jul_private.decl
        |               rad_loop2_pickup_hack.decl
        |               rad_post_trap.decl
        |               
        +---tapes
        |       tape_30s_govt_pressure.decl
        |       tape_30s_schedule.decl
        |       tape_amador_masks.decl
        |       tape_captain_nuke.decl
        |       tape_charlie_2bit_speech.decl
        |       tape_charlie_surgery_motives.decl
        |       tape_colt_join_aeon.decl
        |       tape_dossier_aleksis.decl
        |       tape_dossier_aleksis_2.decl
        |       tape_dossier_charlie.decl
        |       tape_dossier_charlie_2.decl
        |       tape_dossier_colt.decl
        |       tape_dossier_egor.decl
        |       tape_dossier_egor_2.decl
        |       tape_dossier_fia.decl
        |       tape_dossier_fia_2.decl
        |       tape_dossier_frank.decl
        |       tape_dossier_frank_2.decl
        |       tape_dossier_harriet.decl
        |       tape_dossier_harriet_2.decl
        |       tape_dossier_wenjie.decl
        |       tape_dossier_wenjie_2.decl
        |       tape_egor_discovery.decl
        |       tape_egor_plan.decl
        |       tape_eternalist_recruitment.decl
        |       tape_fia_imagelocations.decl
        |       tape_fia_visions_v1.decl
        |       tape_fia_visions_v2.decl
        |       tape_fia_visions_v3.decl
        |       tape_fia_visions_v4.decl
        |       tape_fia_visions_v5.decl
        |       tape_frank_and_harriet.decl
        |       tape_frank_doctor.decl
        |       tape_frank_recording_01.decl
        |       tape_frank_recording_02.decl
        |       tape_frank_recording_03.decl
        |       tape_frank_weapons.decl
        |       tape_from_amador_to_harriet.decl
        |       tape_from_harriet_to_amador.decl
        |       tape_hacker_relays.decl
        |       tape_horizon_logistics.decl
        |       tape_isl_drinkinggame.decl
        |       tape_madame_k_rehearsal.decl
        |       tape_rak_launch.decl
        |       tape_scientist_experiment.decl
        |       tape_scientist_instructions.decl
        |       tape_sky_anomaly.decl
        |       tape_spy01_departed_island.decl
        |       tape_spy02_departed_upper.decl
        |       tape_spy03_departed_wharf.decl
        |       tape_uc2_fia_flattery.decl
        |       tape_uc2_frank_flattery.decl
        |       tape_uc2_julianna_flattery.decl
        |       tape_uc2_wenjie_flattery.decl
        |       tape_wenjie_le_records.decl
        |       tape_wenjie_only_one_night.decl
        |       tape_wenjie_sterilization.decl
        |       tape_wenjie_why_visionaries.decl
        |       tape_whf_rakpassword.decl
        |       
        +---tutorial
        |   \---v1
        |           colt_after_kills.decl
        |           colt_asks_fm.decl
        |           colt_first_kill.decl
        |           colt_frank_radio_l2.decl
        |           colt_get_off_the_beach.decl
        |           colt_gt6_board_reac.decl
        |           colt_gt6_pickup_slab.decl
        |           colt_gt6_reac_bunker.decl
        |           colt_gt6_segue_gt7.decl
        |           colt_gt6_spk_jul_mock.decl
        |           colt_gt6_wakeup.decl
        |           colt_infusion_nickname_1.decl
        |           colt_infusion_nickname_2.decl
        |           colt_infusion_nickname_3.decl
        |           colt_infusion_wakeup.decl
        |           colt_infusion_wakeup_2.decl
        |           colt_kick_barrier.decl
        |           colt_meet_his_double.decl
        |           colt_need_ammo.decl
        |           colt_pickup.decl
        |           colt_pickup_hacktool_loop2.decl
        |           colt_pickup_postcard.decl
        |           colt_pickup_slab.decl
        |           colt_pick_grenade.decl
        |           colt_radio_loop.decl
        |           colt_reac_colt_hut.decl
        |           colt_reac_ext_bay_jul_spk.decl
        |           colt_reac_ext_beach_fm_01.decl
        |           colt_reac_int_tun_fm_01.decl
        |           colt_reac_int_tun_fm_02.decl
        |           colt_reac_int_tun_fm_03.decl
        |           colt_reac_loop2_time_master_fm_01.decl
        |           colt_repeating_wakeup.decl
        |           colt_to_outside.decl
        |           colt_tries_to_enter_code.decl
        |           colt_wakeups.decl
        |           colt_water_damage.decl
        |           intro_after_first_floating.decl
        |           intro_after_first_floating_var.decl
        |           intro_after_second_wakeup.decl
        |           intro_first_wakeup.decl
        |           intro_second_wakeup.decl
        |           intro_second_wakeup_var.decl
        |           jul_gt6_colt_pre_rad.decl
        |           jul_trap_colt_scene.decl
        |           oh_isl_combat_1.decl
        |           oh_isl_combat_2.decl
        |           oh_isl_combat_3.decl
        |           pre_intro.decl
        |           
        +---upper_city
        |   +---common
        |   |       colt_pick_up_note_hunt.decl
        |   |       colt_rocketcar_badpass.decl
        |   |       colt_rocketcar_initial.decl
        |   |       colt_rocketcar_password.decl
        |   |       colt_rocketcar_react.decl
        |   |       colt_rocketcar_refuse.decl
        |   |       colt_rocketcar_unknown.decl
        |   |       colt_rocket_fm_reac.decl
        |   |       colt_rocket_fm_reac_no_vce.decl
        |   |       colt_rocket_thought.decl
        |   |       colt_tumbler_code.decl
        |   |       jul_rocketcar_unknown.decl
        |   |       vce_rocket_car.decl
        |   |       
        |   +---v1
        |   |       colt_finds_lpp.decl
        |   |       colt_gt2_complex.decl
        |   |       colt_gt2_directions.decl
        |   |       colt_gt2_meet_visionaries.decl
        |   |       colt_gt2_nail_gun.decl
        |   |       colt_gt2_picture.decl
        |   |       colt_gt2_problemsolver.decl
        |   |       colt_gt2_safe.decl
        |   |       colt_gt2_segue_gt3.decl
        |   |       colt_gt2_uptight.decl
        |   |       colt_gt2_who_frank.decl
        |   |       colt_gt7_picture_reac.decl
        |   |       colt_gt7_reac_lpp.decl
        |   |       colt_otto_machine.decl
        |   |       colt_powerbox_destroy.decl
        |   |       colt_powerbox_destroy_last.decl
        |   |       colt_wenjie_lab.decl
        |   |       isl_jump_encouraging.decl
        |   |       isl_jump_jumping.decl
        |   |       isl_jump_pacing.decl
        |   |       oh_isl_breakwall.decl
        |   |       oh_isl_moxieplayers_post_hack.decl
        |   |       oh_isl_moxieplayers_pre_hack.decl
        |   |       oh_isl_prep_chara.decl
        |   |       oh_isl_trading_security.decl
        |   |       vce_juliannas_office.decl
        |   |       
        |   +---v2
        |   |       colt_workshop_burnt.decl
        |   |       oh_isl_saferoom_talks.decl
        |   |       
        |   \---v4
        |           colt_rocketcar_entry.decl
        |           isl_anon_positive.decl
        |           
        \---wharf
            \---common
                    colt_rocketcar_pass_self_new.decl
```


A 4.5MB zip of all files: [https://mega.nz/file/aeYHmAKK#RCPq1ImgW ... L9GCeBG-l0](https://mega.nz/file/aeYHmAKK#RCPq1ImgWUwQIbzC4fIJPTlTmUW35H74BL9GCeBG-l0)

For example bk_attack_grenade.decl from localized\english\speechbarks\speech\speech_barks\combat looks like this:


According to a Doom wiki (and this thread: [viewtopic.php?p=181858](https://forum.xentax.com/viewtopic.php?p=181858) ), these are text files [https://wiki.eternalmods.com/books/2-ho ... extensions](https://wiki.eternalmods.com/books/2-how-to-create-mods/page/file-extensions) but it would be great if somebody could take a look and help figuring out how to handle all those special characters and how to extract only the interesting parts.
