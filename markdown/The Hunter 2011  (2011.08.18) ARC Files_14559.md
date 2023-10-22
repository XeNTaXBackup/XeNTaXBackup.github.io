## Post #1
- Username: venoom92
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Jun 23, 2016 9:01 pm
- Post datetime: 2016-06-24T11:46:42+00:00
- Post Title: The Hunter 2011  (2011.08.18) ARC Files

please help my unpak all files from archives...

# The Hunter (tested with 2009072101)
# script for QuickBMS [http://quickbms.aluigi.org](http://quickbms.aluigi.org)

get EXTENSION extension
if EXTENSION != TAB
    open FDDE TAB 1
endif
open FDDE ARC 1

get CHUNKSZ long
get FILES asize
math FILES /= 12
for i = 0 < FILES
    get CRC long
    get OFFSET long
    get SIZE long

    log "" OFFSET SIZE 1
next i

- this script from aluigi unpack only "unknown" files noi includes folders and files in folders... please help me..  

this script inpack pkt 1 on screenshot  and not unpack pkt 2 on screenshot..  sorry for bad english.
[Screenshot_1.jpg](https://xentaxbackup.github.io/file/11105_Screenshot_1.jpg)
## Post #2
- Username: venoom92
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Jun 23, 2016 9:01 pm
- Post datetime: 2016-06-26T11:37:10+00:00
- Post Title: The Hunter 2011  (2011.08.18) ARC Files

please help mi for unpack bin files from *.arc
## Post #3
- Username: venoom92
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Jun 23, 2016 9:01 pm
- Post datetime: 2016-06-28T09:00:15+00:00
- Post Title: The Hunter 2011  (2011.08.18) ARC Files

pls
## Post #4
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2016-06-28T19:36:14+00:00
- Post Title: The Hunter 2011  (2011.08.18) ARC Files

Example file.
## Post #5
- Username: venoom92
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Jun 23, 2016 9:01 pm
- Post datetime: 2016-06-28T20:12:19+00:00
- Post Title: The Hunter 2011  (2011.08.18) ARC Files

[https://drive.google.com/open?id=0Bzzni ... HFzVXYyZ3M](https://drive.google.com/open?id=0Bzzniy3aYThma0o1eHFzVXYyZ3M)
## Post #6
- Username: venoom92
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Jun 23, 2016 9:01 pm
- Post datetime: 2016-06-30T08:03:04+00:00
- Post Title: The Hunter 2011  (2011.08.18) ARC Files

any ideas?
## Post #7
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2016-06-30T18:27:07+00:00
- Post Title: The Hunter 2011  (2011.08.18) ARC Files

The script cannot handle this. The TAB file does not contain any filenames. Nor does the ARC, although it may be the first XML like part: 

```
	<object name="project_info">
		<value name="project_file_version" type="int">1000</value>
		<value name="project_type" type="string">Avalanche Engine Project</value>
		<value name="project_name" type="string">The Hunter</value>
		<value name="project_file_guid" type="string">{0B7F26DD-5124-4CCA-B6D7-7FA50E488B1F}</value>
		<value name="project_location_export" type="int">0</value>
	</object>
	<object name="paths">
		<value name="editor_directory" type="string">intermediate\</value>
		<value name="run_in_directory" type="string">editor\</value>
		<value name="ai_directory" type="string">AI\</value>
		<value name="model_directory" type="string">Models\</value>
		<value name="texture_directory" type="string">Textures\</value>
		<value name="character_directory" type="string">Models\Characters</value>
		<value name="animation_directory" type="string">Animations\</value>
		<value name="sequence_directory" type="string">Sequences\</value>
		<value name="particle_system_directory" type="string">ParticleSystems\</value>
		<value name="vegetation_directory" type="string">Models\Vegetation\</value>
		<value name="road_directory" type="string">Roads\</value>
		<value name="system_directory" type="string">Editor\System\</value>
		<value name="settings_directory" type="string">Settings\</value>
		<value name="location_directory" type="string">Locations\</value>
		<value name="entity_directory" type="string">Editor\Entities\</value>
		<value name="temp_directory" type="string">Temp\</value>
		<value name="compiler_directory" type="string">bin\compilers\</value>
		<value name="rule_directory" type="string">Rules\</value>
		<value name="mission_directory" type="string">Missions\</value>
	</object>
	<object name="systems">
		<object name="win32">
			<value name="name" type="string">win32</value>
			<object name="{AFA5230-5235GE-53241-6345}">
				<value name="name" type="string">CDynamicShadowManager</value>
				<value name="enabled" type="int">0</value>
				<value name="creation_index" type="int">9</value>
				<object name="params">
				</object>
			</object>
			<value name="enabled" type="int">0</value>
			<object name="{WEE5244-5235GE-53241-6345}">
				<value name="name" type="string">CConstraintFactory</value>
				<value name="enabled" type="int">1</value>
				<value name="creation_index" type="int">10</value>
				<object name="params">
				</object>
			</object>
			<object name="{WEE5230-5235GE-53843-6345}">
				<value name="name" type="string">CContextActionFactory</value>
				<value name="enabled" type="int">1</value>
				<value name="creation_index" type="int">11</value>
				<object name="params">
				</object>
			</object>
			<object name="{WEE5230-5235GE-53241-2356}">
				<value name="name" type="string">CGuiSystem</value>
				<value name="enabled" type="int">1</value>
				<value name="creation_index" type="int">6</value>
				<object name="params">
				</object>
			</object>
			<object name="{WEE5230-5235GE-53241-1186}">
				<value name="name" type="string">CConsole</value>
				<value name="enabled" type="int">1</value>
				<value name="creation_index" type="int">12</value>
				<object name="params">
					<value name="font_path" type="string">Font\Terminal_9</value>
				</object>
			</object>
			<object name="{WEE5230-5235GE-53241-5355}">
				<value name="name" type="string">CDebugMenu</value>
				<value name="enabled" type="int">1</value>
				<value name="creation_index" type="int">13</value>
				<object name="params">
				</object>
			</object>
			<object name="{WAS5230-5235GE-53241-6345}">
				<value name="name" type="string">CCameraManager</value>
				<value name="enabled" type="int">1</value>
				<value name="creation_index" type="int">1</value>
				<object name="params">
				</object>
			</object>
			<object name="{MUL5230-5235GE-53241-6345}">
				<value name="name" type="string">CCameraControlManager</value>
				<value name="enabled" type="int">1</value>
				<value name="creation_index" type="int">14</value>
				<object name="params">
					<value name="settings" type="string">settings\cameras.bin</value>
				</object>
			</object>
			<object name="{WEE5230-5235GE-85631-6345}">
				<value name="name" type="string">CSteeringManager</value>
				<value name="enabled" type="int">1</value>
				<value name="creation_index" type="int">15</value>
				<object name="params">
				</object>
			</object>
			<object name="{WEE5230-5235GE-86452-6345}">
				<value name="name" type="string">CGraphicsEngine</value>
				<value name="enabled" type="int">1</value>
				<value name="creation_index" type="int">2</value>
				<object name="params">
					<object name="ShadowManager">
						<value name="tex_side" type="int">1024</value>
					</object>
				</object>
			</object>
			<object name="{WEE5230-5235GE-90832-6345}">
				<value name="name" type="string">CTextureManager</value>
				<value name="enabled" type="int">1</value>
				<value name="creation_index" type="int">3</value>
				<object name="params">
				</object>
			</object>
			<object name="{WEE5230-5235GE-75322-6345}">
				<value name="name" type="string">CRenderBlockFactory</value>
				<value name="enabled" type="int">1</value>
				<value name="creation_index" type="int">4</value>
				<object name="params">
				</object>
			</object>
			<object name="{WEE5230-5235GE-16789-6345}">
				<value name="name" type="string">CLightManager</value>
				<value name="enabled" type="int">1</value>
				<value name="creation_index" type="int">8</value>
				<object name="params">
				</object>
			</object>
			<object name="{WEE5230-5235GE-90551-6345}">
				<value name="name" type="string">CClientWindow</value>
				<value name="enabled" type="int">1</value>
				<value name="creation_index" type="int">0</value>
				<object name="params">
				</object>
			</object>
			<object name="{WEE5230-5235GE-62889-6345}">
				<value name="name" type="string">CStorageDeviceManager</value>
				<value name="enabled" type="int">1</value>
				<value name="creation_index" type="int">16</value>
				<object name="params">
				</object>
			</object>
			<object name="{WEE5230-5235GE-09878-6345}">
				<value name="name" type="string">CClock</value>
				<value name="enabled" type="int">1</value>
				<value name="creation_index" type="int">17</value>
				<object name="params">
				</object>
			</object>
			<object name="{WEE5230-5235GE-00076-6345}">
				<value name="name" type="string">CRenderEngine</value>
				<value name="enabled" type="int">1</value>
				<value name="creation_index" type="int">5</value>
				<object name="params">
				</object>
			</object>
			<object name="{WEE5230-5235GE-00441-6345}">
				<value name="name" type="string">CPhysicsSystem</value>
				<value name="enabled" type="int">1</value>
				<value name="creation_index" type="int">18</value>
				<object name="params">
					<value name="max_terrain_height" type="float">1785</value>
					<value name="world_sea_level" type="float">200</value>
					<value name="settings_file" type="string">Settings\PhysicsSettings.bin</value>
				</object>
			</object>
			<object name="{WEE5230-5235GE-0034-6345}">
				<value name="name" type="string">CWorldTime</value>
				<value name="enabled" type="int">1</value>
				<value name="creation_index" type="int">19</value>
				<object name="params">
				</object>
			</object>
			<object name="{WEE5230-5235GE-32555-6345}">
				<value name="name" type="string">CStreamPatchManager</value>
				<value name="enabled" type="int">1</value>
				<value name="creation_index" type="int">20</value>
				<object name="params">
					<value name="terrain_file_pc" type="string">Terrain\Terrain_PC.dat</value>
					<value name="terrain_file_xbox" type="string">Terrain\Terrain_XBOX.dat</value>
					<value name="terrain_file_xbox360" type="string">Terrain\Terrain_XBOX360.dat</value>
					<value name="terrain_file_ps3" type="string">Terrain\Terrain_PS3.dat</value>
					<value name="terrain_file_editor" type="string">Terrain\Terrain_Editor.dat</value>
				</object>
			</object>
			<object name="{WEE5230-5235GE-87624-6345}">
				<value name="name" type="string">CLandscapeManager</value>
				<value name="enabled" type="int">1</value>
				<value name="creation_index" type="int">23</value>
				<object name="params">
					<value name="_class" type="string">CLandscapeManagerProperties</value>
					<value name="global_terrain_data_editor" type="string">Terrain\GlobalTerrainData_Editor.dat</value>
					<value name="global_texture_pc" type="string">Terrain\GlobalTexture.dxt</value>
					<value name="global_water_texture_pc" type="string">Terrain\GlobalWaterTexture.pc</value>
					<value name="global_heights_pc" type="string">Terrain\GlobalHeights.raw</value>
					<value name="global_terrain_data_pc" type="string">Terrain\GlobalTerrainData_PC.dat</value>
					<value name="terrain_mop_pc" type="string">Terrain\Terrain.mop</value>
					<value name="global_terrain_data_xbox360" type="string">Terrain\GlobalTerrainData_Xbox360.dat</value>
					<value name="global_texture_xbox360" type="string">Terrain\GlobalTexture.dxt</value>
					<value name="global_water_texture_xbox360" type="string">Terrain\GlobalWaterTexture.pc</value>
					<value name="global_heights_xbox360" type="string">Terrain\GlobalHeights.raw</value>
					<value name="terrain_mop_xbox360" type="string">Terrain\Terrain.mop</value>
					<value name="global_texture_ps3" type="string">Terrain\GlobalTexture_PS3.dxt</value>
					<value name="global_water_texture_ps3" type="string">Terrain\GlobalWaterTexture_PS3.dds</value>
					<value name="global_heights_ps3" type="string">Terrain\GlobalHeights_PS3.raw</value>
					<value name="terrain_mop_ps3" type="string">Terrain\Terrain_PS3.mop</value>
					<value name="global_terrain_data_ps3" type="string">Terrain\GlobalTerrainData_PS3.dat</value>
					<value name="terrain_settings" type="string">Settings\terrain.bin</value>
					<value name="landscape_effects_settings" type="string">Settings\landscape_effects.bin</value>
					<value name="global_terrain_data_xbox" type="string">Terrain\GlobalTerrainData_Editor.dat</value>
					<value name="global_texture_xbox" type="string">Terrain\GlobalTexture.dxt</value>
					<value name="global_water_texture_xbox" type="string">Terrain\GlobalWaterTexture.pc</value>
					<value name="global_heights_xbox" type="string">Terrain\GlobalHeights.raw</value>
					<value name="terrain_mop_xbox" type="string">Terrain\Terrain.mop</value>
				</object>
			</object>
			<object name="{WEE5230-5235GE-24678-6345}">
				<value name="name" type="string">CModelInstanceManager</value>
				<value name="enabled" type="int">1</value>
				<value name="creation_index" type="int">21</value>
				<object name="params">
				</object>
			</object>
			<object name="{WEE5230-5235GE-89985-6345}">
				<value name="name" type="string">CModelManager</value>
				<value name="enabled" type="int">1</value>
				<value name="creation_index" type="int">22</value>
				<object name="params">
				</object>
			</object>
			<object name="{WEE5230-5235GE-12467-6345}">
				<value name="name" type="string">CSpawnSystem</value>
				<value name="enabled" type="int">1</value>
				<value name="creation_index" type="int">24</value>
				<object name="params">
					<value name="settings_file" type="string">settings\SpawnSettings.bin</value>
				</object>
			</object>
			<object name="{WEE5230-5235GE-08644-6345}">
				<value name="name" type="string">CGameWorld</value>
				<value name="enabled" type="int">1</value>
				<value name="creation_index" type="int">25</value>
				<object name="params">
					<value name="_class" type="string">CGameWorldProperties</value>
					<value name="global_locations_file" type="string">global\global.bin</value>
					<value name="world_file" type="string">locations\world.bin</value>
					<value name="game_material_file" type="string">settings\game_materials.bin</value>
				</object>
			</object>
			<object name="{WEE5230-5235GE-15799-6345}">
				<value name="name" type="string">CLocator</value>
				<value name="enabled" type="int">1</value>
				<value name="creation_index" type="int">26</value>
				<object name="params">
					<value name="settings_file" type="string">settings\locator.bin</value>
				</object>
			</object>
			<object name="{WEE5230-2785GE-53241-6345}">
				<value name="name" type="string">CWeaponManager</value>
				<value name="enabled" type="int">1</value>
				<value name="creation_index" type="int">28</value>
				<object name="params">
					<value name="weapon_file" type="string">settings\weapons.bin</value>
				</object>
			</object>
			<object name="{WEE5230-G2E785-25341-6435}">
				<value name="name" type="string">CItemManager</value>
				<value name="enabled" type="int">1</value>
				<value name="creation_index" type="int">28</value>
				<object name="params">
					<value name="items_file" type="string">settings\hunter_items.bin</value>
				</object>
			</object>
			<object name="{WEE5230-5235GE-53241-8043}">
				<value name="name" type="string">CCharacterManager</value>
				<value name="enabled" type="int">1</value>
				<value name="creation_index" type="int">29</value>
				<object name="params">
					<value name="player_definition_file" type="string">settings\player.bin</value>
					<value name="base_state_machine" type="string">animations\statemachine\hunter_base.afsm</value>
					<value name="upperbody_state_machine" type="string">animations\statemachine\hunter_upper_bode.afsm</value>
					<value name="left_arm_state_machine" type="string">animations\statemachine\hunter_left_arm.afsm</value>
					<value name="right_arm_state_machine" type="string">animations\statemachine\hunter_right_arm.afsm</value>
					<value name="ragdoll_description_file" type="string">animations\ragdoll\ragdoll_params.bin</value>
				</object>
			</object>
			<object name="{WEE5230-7235GE-53241-6345}">
				<value name="name" type="string">CPaletteManager</value>
				<value name="enabled" type="int">1</value>
				<value name="creation_index" type="int">30</value>
				<object name="params">
				</object>
			</object>
			<object name="{WEG5230-5235GE-53241-6345}">
				<value name="name" type="string">CParticleManager</value>
				<value name="enabled" type="int">1</value>
				<value name="creation_index" type="int">31</value>
				<object name="params">
				</object>
			</object>
			<object name="{WEG5230-5235GE-57371-6345}">
				<value name="name" type="string">IAnimationManager</value>
				<value name="enabled" type="int">1</value>
				<value name="creation_index" type="int">32</value>
				<object name="params">
				</object>
			</object>
			<object name="{WEG5230-5235GE-57631-6345}">
				<value name="name" type="string">CAnimatedSkeletonManager</value>
				<value name="enabled" type="int">1</value>
				<value name="creation_index" type="int">33</value>
				<object name="params">
				</object>
			</object>
			<object name="{WEG5230-5235GE-53241-7231}">
				<value name="name" type="string">CAnimationSetManager</value>
				<value name="enabled" type="int">1</value>
				<value name="creation_index" type="int">34</value>
				<object name="params">
				</object>
			</object>
			<object name="{WEG5230-5235GE-53241-1784}">
				<value name="name" type="string">CAnimationInstanceManager</value>
				<value name="enabled" type="int">1</value>
				<value name="creation_index" type="int">35</value>
				<object name="params">
				</object>
			</object>
			<object name="{WEG5230-5235GE-83422-6345}">
				<value name="name" type="string">CAmmunitionManager</value>
				<value name="enabled" type="int">1</value>
				<value name="creation_index" type="int">39</value>
				<object name="params">
				</object>
			</object>
			<object name="{WEG5230-5235GE-86444-6345}">
				<value name="name" type="string">CExportedEntityManager</value>
				<value name="enabled" type="int">1</value>
				<value name="creation_index" type="int">40</value>
				<object name="params">
				</object>
			</object>
			<object name="{WBB5230-5235GE-53241-6345}">
				<value name="name" type="string">CTargetSystem</value>
				<value name="enabled" type="int">1</value>
				<value name="creation_index" type="int">41</value>
				<object name="params">
				</object>
			</object>
			<object name="{WBB5230-5235GE-27787-6345}">
				<value name="name" type="string">CFpsCounter</value>
				<value name="enabled" type="int">1</value>
				<value name="creation_index" type="int">43</value>
				<object name="params">
				</object>
			</object>
			<object name="{WBB5230-5235GE-83333-6345}">
				<value name="name" type="string">CStatisticsManager</value>
				<value name="enabled" type="int">1</value>
				<value name="creation_index" type="int">45</value>
				<object name="params">
				</object>
			</object>
			<object name="{WBB5230-5235GE-45126-6345}">
				<value name="name" type="string">CSoundSystem</value>
				<value name="enabled" type="int">1</value>
				<value name="creation_index" type="int">27</value>
				<object name="params">
					<value name="core_initfile" type="string">sound/settings_core.bin</value>
					<value name="smod_initfile" type="string">sound/settings_smod.bin</value>
				</object>
			</object>
			<object name="{WBB5230-5235GE-00089-6345}">
				<value name="name" type="string">CRoadManager</value>
				<value name="enabled" type="int">1</value>
				<value name="creation_index" type="int">46</value>
				<object name="params">
					<object name="road_mesh_params">
						<value name="swap_endian" type="int">0</value>
						<value name="road_file" type="string">Settings/roads.bin</value>
						<value name="decoration_file" type="string">Settings/road_decorations.bin</value>
					</object>
				</object>
			</object>
			<object name="{WBB5230-5235AS-64868-6345}">
				<value name="name" type="string">CDebugBookmark</value>
				<value name="enabled" type="int">1</value>
				<value name="creation_index" type="int">47</value>
				<object name="params">
				</object>
			</object>
			<object name="{WBB5230-5235AS-44442-6345}">
				<value name="name" type="string">CMotionBlur</value>
				<value name="enabled" type="int">1</value>
				<value name="creation_index" type="int">49</value>
				<object name="params">
				</object>
			</object>
			<object name="{WBB5230-5235AS-99999-6345}">
				<value name="name" type="string">CSafeAreaBorder</value>
				<value name="enabled" type="int">1</value>
				<value name="creation_index" type="int">50</value>
				<object name="params">
				</object>
			</object>
			<object name="{BEF45BDA-7485-4d1d-A579-EFE57FB0A17A}">
				<value name="name" type="string">CPDManager</value>
				<value name="enabled" type="int">1</value>
				<value name="creation_index" type="int">52</value>
				<object name="params">
				</object>
			</object>
			<object name="{47B75135-7039-47C8-B267-6F4D72119CAC}">
				<value name="name" type="string">CDirect3D</value>
				<value name="enabled" type="int">1</value>
				<value name="creation_index" type="int">44</value>
				<object name="params">
				</object>
			</object>
			<object name="{F94FFC58-F7F2-4D4E-9C8D-E947B92F280E}">
				<value name="name" type="string">CInputDeviceManager</value>
				<value name="enabled" type="int">1</value>
				<value name="creation_index" type="int">51</value>
				<object name="params">
				</object>
			</object>
			<object name="{E8B4B188-3BD4-45F0-9F2E-FE1C49D78673}">
				<value name="name" type="string">CAVGui</value>
				<value name="enabled" type="int">1</value>
				<value name="creation_index" type="int">54</value>
				<object name="params">
					<value name="input_file" type="string">Gui\gui_input.bin</value>
				</object>
			</object>
			<object name="{0A40A74B-B53C-49D4-B98C-4E6284FD6BD4}">
				<value name="name" type="string">CAISystem</value>
				<value name="enabled" type="int">1</value>
				<value name="creation_index" type="int">55</value>
				<object name="params">
					<value name="_class" type="string">CAISystemProperties</value>
					<value name="RoadNetworkFile" type="string">default.rg</value>
				</object>
			</object>
			<object name="{5FF9AAF6-9B39-4FDA-9D96-86AE788966CC}">
				<value name="name" type="string">CEffectSystem</value>
				<value name="enabled" type="int">1</value>
				<value name="creation_index" type="int">58</value>
				<object name="params">
					<value name="settings_file" type="string">effects/effectsettings.bin</value>
					<value name="_class" type="string">CEffectSystemProperties</value>
				</object>
			</object>
			<object name="{E84EC604-3EB3-41F4-BA29-E574086129A9}">
				<value name="name" type="string">CAnarkGui</value>
				<value name="enabled" type="int">1</value>
				<value name="creation_index" type="int">53</value>
				<object name="params">
					<value name="input_file" type="string">Gui\gui_input.xml</value>
					<value name="pda_database_file" type="string">Gui\pda_database.xml</value>
				</object>
			</object>
			<object name="{5C2A3C8F-8164-45EE-A501-C612D6D65950}">
				<value name="name" type="string">CRuleSystem</value>
				<value name="enabled" type="int">1</value>
				<value name="creation_index" type="int">59</value>
				<object name="params">
				</object>
			</object>
			<object name="{DDED16A1-2374-4E28-BA98-EE7366E877CB}">
				<value name="name" type="string">CSettingsManager</value>
				<value name="enabled" type="int">1</value>
				<value name="creation_index" type="int">63</value>
				<object name="params">
				</object>
			</object>
			<object name="{FF8237A3-ACD3-438A-9086-BC6AE0487E90}">
				<value name="name" type="string">CFactionHandler</value>
				<value name="enabled" type="int">1</value>
				<value name="creation_index" type="int">64</value>
				<object name="params">
					<value name="faction_relations" type="string">settings/factions.bin</value>
				</object>
			</object>
			<object name="{5E08C7ED-AFF6-4E51-A48E-EDD59A4EACCF}">
				<value name="name" type="string">CStartupProgress</value>
				<value name="enabled" type="int">1</value>
				<value name="creation_index" type="int">7</value>
				<object name="params">
					<value name="_class" type="string">CStartupProgressProperties</value>
					<value name="texture_bar" type="string">gui/startup_bar.dds</value>
					<value name="textures_used" type="int">3</value>
					<value name="texture_1" type="string">gui/frontend_publisher_splash_screen.dds</value>
					<value name="percentage_1" type="float">0.3000000119</value>
					<value name="texture_2" type="string">gui/frontend_developer_splash_screen.dds</value>
					<value name="percentage_2" type="float">0.6999999881</value>
					<value name="texture_3" type="string">gui/frontend_title_splash_screen.dds</value>
					<value name="percentage_3" type="float">1</value>
					<value name="texture_4" type="string"></value>
					<value name="percentage_4" type="float">0</value>
					<value name="texture_5" type="string"></value>
					<value name="percentage_5" type="float">0</value>
				</object>
			</object>
			<object name="{8A4AFF50-0545-476F-A990-362E5BE2B63C}">
				<value name="name" type="string">CSaveManager</value>
				<value name="enabled" type="int">1</value>
				<value name="creation_index" type="int">67</value>
				<object name="params">
				</object>
			</object>
			<object name="{0034622A-3FBC-4565-9431-AD6AEEA40103}">
				<value name="name" type="string">CAreaSetsManager</value>
				<value name="enabled" type="int">1</value>
				<value name="creation_index" type="int">56</value>
				<object name="params">
					<value name="area_sets_file_name" type="string">AreaSets.bin</value>
				</object>
			</object>
			<object name="{0034622A-3FBC-4565-9431-AD6AEEA40104}">
				<value name="name" type="string">CEmoteClient</value>
				<value name="enabled" type="int">1</value>
				<value name="creation_index" type="int">58</value>
				<object name="params">
				</object>
			</object>
			<object name="{EAC5763-B4E643-64574-3298}">
				<value name="name" type="string">CScenarioManager</value>
				<value name="enabled" type="int">1</value>
				<value name="creation_index" type="int">70</value>
				<object name="params">
				</object>
			</object>
			<object name="{WBB5230-5235AS-72323-6347}">
				<value name="name" type="string">CCloudShadowManager</value>
				<value name="enabled" type="int">1</value>
				<value name="creation_index" type="int">71</value>
				<object name="params">
					<value name="cloudshadow_settings" type="string">Settings\cloudshadows.bin</value>
				</object>
			</object>
			<object name="{BAF9347-2348-CEA0175-9842}">
				<value name="name" type="string">CCreatureManager</value>
				<value name="enabled" type="int">1</value>
				<value name="creation_index" type="int">72</value>
				<object name="params">
					<value name="settings_file" type="string">settings\creatures.bin</value>
				</object>
			</object>
			<object name="{B75CC583-33CB-4E7D-A2EF-36D27DF63471}">
				<value name="name" type="string">CAnimalPopulationManager</value>
				<value name="enabled" type="int">1</value>
				<value name="creation_index" type="int">73</value>
				<object name="params">
					<value name="settings_file" type="string">settings\AnimalPopulation.bin</value>
				</object>
			</object>
		</object>
	</object>
</object>

```
## Post #8
- Username: venoom92
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Jun 23, 2016 9:01 pm
- Post datetime: 2016-07-03T06:48:20+00:00
- Post Title: The Hunter 2011  (2011.08.18) ARC Files

So I don't understand what to do
## Post #9
- Username: venoom92
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Jun 23, 2016 9:01 pm
- Post datetime: 2016-07-07T07:48:41+00:00
- Post Title: The Hunter 2011  (2011.08.18) ARC Files

The TAB file has the names of the folders because the GIBBED AVANLANCHE VIEWER reads it... please help
## Post #10
- Username: venoom92
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Jun 23, 2016 9:01 pm
- Post datetime: 2016-07-12T19:03:39+00:00
- Post Title: The Hunter 2011  (2011.08.18) ARC Files

hello
