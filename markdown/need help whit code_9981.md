## Post #1
- Username: wolfen
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Dec 27, 2011 7:13 am
- Post datetime: 2012-12-28T00:03:51+00:00
- Post Title: need help whit code

Hello I would like to know who is this code

as compiled?
what else do I need?
how to use?

any help is appreciated thanks
here more codes


 Project.rar
(88.04 KiB) Downloaded 27 times



```
  unsigned long version;
  struct MindPower::lwGeomObjInfo::lwGeomObjInfoHeader header;
  // Material Data
  #if (header.mtl_size > 0)
         #if (version == 0)
                unsigned long version; // Set only for this block
         #endif  
         unsigned long mtl_num;
         #if ((version >= 0x1000)||(version == 2))
           struct MindPower::lwMtlTexInfo mtl_seq[mtl_num];
         #else if (version == 1)
           struct MindPower::lwMtlTexInfo_0001 mtl_seq[mtl_num] { // Some special case
                 /* this+0x0 */ float opacity;
                 /* this+0x4 */ unsigned long transp_type;
                 /* this+0x8 */ struct MindPower::lwMaterial mtl;
                 /* this+0x4c */ struct MindPower::lwRenderStateSetTemplate<2,8> rs_set;
                 /* this+0xcc */ struct MindPower::lwTexInfo_0001 tex_seq[4]; // The original stucture tell us, that here is MindPower::lwTexInfo. But reading procedure tell us something else
           }
         #else if (version == 0)
           struct MindPower::lwMtlTexInfo_0000 mtl_seq[mtl_num];
         #endif
  #endif
 
  // Mesh Data
  #if (header.mesh_size > 0)
         #if (version == 0)
                unsigned long version; // Set only for this block
         #endif
         #if (version >= 0x1004)
                struct MindPower::lwMeshInfo::lwMeshInfoHeader mesh_info;
         #else if (version >= 0x1003)
           struct MindPower::lwMeshInfo_0003::lwMeshInfoHeader mesh_info;
         #else if ((version >= 0x1000)||(version == 1))
           struct MindPower::lwMeshInfo_0003::lwMeshInfoHeader mesh_info;
         #else if (version == 0)
           struct MindPower::lwMeshInfo_0000::lwMeshInfoHeader mesh_info;
         #endif
         #if (version >= 0x1004)
                struct MindPower::lwMeshInfo::lwMeshInfoData mesh_data { // This is pseudo structure, none exist in reality.
                  #if (mesh_info.vertex_element_num > 0)
                         struct _D3DVERTEXELEMENT9 vertex_element_seq[mesh_info.vertex_element_num];
                  #endif
                  #if (mesh_info.vertex_num > 0)
                         struct D3DXVECTOR3 vertex_seq[mesh_info.vertex_num];
                  #endif
                  #if (mesh_info.fvf & 0x10)
                         struct D3DXVECTOR3 vertex_seq[mesh_info.vertex_num];
                  #endif
                  #if (mesh_info.fvf & 0x100)
                         struct D3DXVECTOR2 texcoord0_seq[mesh_info.vertex_num];
                  #else if (mesh_info.fvf & 0x200)
                         struct D3DXVECTOR2 texcoord0_seq[mesh_info.vertex_num];
                         struct D3DXVECTOR2 texcoord1_seq[mesh_info.vertex_num];
                  #else if (mesh_info.fvf & 0x300)
                         struct D3DXVECTOR2 texcoord0_seq[mesh_info.vertex_num];
                         struct D3DXVECTOR2 texcoord1_seq[mesh_info.vertex_num];
                         struct D3DXVECTOR2 texcoord2_seq[mesh_info.vertex_num];
                  #else if (mesh_info.fvf & 0x400)
                         struct D3DXVECTOR2 texcoord0_seq[mesh_info.vertex_num];
                         struct D3DXVECTOR2 texcoord1_seq[mesh_info.vertex_num];
                         struct D3DXVECTOR2 texcoord2_seq[mesh_info.vertex_num];
                         struct D3DXVECTOR2 texcoord3_seq[mesh_info.vertex_num];
                  #endif
                  #if (mesh_info.fvf & 0x40)
                         unsigned long vercol_seq[mesh_info.vertex_num];
                  #endif
                  #if (mesh_info.bone_index_num > 0)
                          struct MindPower::lwBlendInfo blend_seq[mesh_info.vertex_num];
                          unsigned long bone_index_seq[mesh_info.bone_index_num];
                  #endif
                  #if (mesh_info.index_num > 0)
                          unsigned long index_seq[mesh_info.index_num];
                  #endif
                  #if (mesh_info.subset_num > 0)
                          struct MindPower::lwSubsetInfo subset_seq[mesh_info.subset_num];
                  #endif
                }
         #else
                struct MindPower::lwMeshInfo::lwMeshInfoData_0000 mesh_data { // This is pseudo structure, none exist in reality.
                  struct MindPower::lwSubsetInfo subset_seq[mesh_info.subset_num];
                  struct D3DXVECTOR3 vertex_seq[mesh_info.vertex_num];
                  #if (mesh_info.fvf & 0x10)
                         struct D3DXVECTOR3 normal_seq[mesh_info.vertex_num];
                  #endif
                  #if (mesh_info.fvf & 0x100)
                         struct D3DXVECTOR2 texcoord0_seq[mesh_info.vertex_num];
                  #else if (mesh_info.fvf & 0x200)
                         struct D3DXVECTOR2 texcoord0_seq[mesh_info.vertex_num];
                         struct D3DXVECTOR2 texcoord1_seq[mesh_info.vertex_num];
                  #else if (mesh_info.fvf & 0x300)
                         struct D3DXVECTOR2 texcoord0_seq[mesh_info.vertex_num];
                         struct D3DXVECTOR2 texcoord1_seq[mesh_info.vertex_num];
                         struct D3DXVECTOR2 texcoord2_seq[mesh_info.vertex_num];
                  #else if (mesh_info.fvf & 0x400)
                         struct D3DXVECTOR2 texcoord0_seq[mesh_info.vertex_num];
                         struct D3DXVECTOR2 texcoord1_seq[mesh_info.vertex_num];
                         struct D3DXVECTOR2 texcoord2_seq[mesh_info.vertex_num];
                         struct D3DXVECTOR2 texcoord3_seq[mesh_info.vertex_num];
                  #endif
                  #if (mesh_info.fvf & 0x40)
                         unsigned long vercol_seq[mesh_info.vertex_num];
                  #endif
                  #if (mesh_info.fvf & 0x1000)
                         struct MindPower::lwBlendInfo blend_seq[mesh_info.vertex_num];
                         unsigned char bone_index_seq[mesh_info.bone_index_num];
                  #endif
                  #if (mesh_info.index_num > 0)
                          unsigned long index_seq[mesh_info.index_num];
                  #endif
                }
         #endif
  #endif
 
  // Helper Data
  #if (header.helper_size > 0)
         #if (version == 0)
                unsigned long version; // Set only for this block
         #endif
         unsigned long type;
         #if (type & 0x1)
                #if (version >= 0x1001)
                   unsigned long dummy_num;
                   struct MindPower::lwHelperDummyInfo dummy_seq[dummy_num];
                #else if (version <= 0x1000)
                   unsigned long dummy_num;
                   struct MindPower::lwHelperDummyInfo_1000 dummy_seq[dummy_num];
        #endif
         #endif
         #if (type & 0x2)
                unsigned long box_num;
                struct MindPower::lwHelperBoxInfo box_seq[box_num];
         #endif
         #if (type & 0x4)
                unsigned long mesh_num;
                struct MindPower::lwHelperMeshInfo bbox_seq[mesh_num] { // This is Changed Struct. Because the reading sequence is different from the actual struct.
                  /* this+0x0 */ unsigned long id;
                  /* this+0x4 */ unsigned long type;
                  /* this+0x8 */ unsigned long sub_type;
                  /* this+0xc */ char name[64];
                  /* this+0x2c */ unsigned long state;
                  /* this+0x30 */ struct D3DXMATRIX mat;
                  /* this+0x70 */ class MindPower::lwBox box;
                  /* this+0x88 */ unsigned long vertex_num;
                  /* this+0x8c */ unsigned long face_num;
                  /* this+0x90 */ struct D3DXVECTOR3 vertex_seq[vertex_num];
                  /* this+0x90+(vertex_num * 0xc) */ struct MindPower::lwHelperMeshFaceInfo face_seq[face_num]; // This one id Delta position.
                }
         #endif
         #if (type & 0x10)
                unsigned long bbox_num;
                struct MindPower::lwBoundingBoxInfo bbox_seq[bbox_num];
         #endif
         #if (type & 0x20)
                unsigned long bsphere_num;
                struct MindPower::lwBoundingSphereInfo bsphere_seq[bsphere_num];
         #endif
  #endif
 
  // Animation Data
  #if (header.anim_size > 0)
         #if (version == 0)
                unsigned long version; // Set only for this block
         #endif
         unsigned long data_bone_size;
         unsigned long data_mat_size;
         #if (version >= 0x1005)
                unsigned long data_mtlopac_size[16];
         #endif
         unsigned long data_texuv_size[4][16];
         unsigned long data_teximg_size[4][16];
         #if (version > 0)
                #if (version == 0)
                   unsigned long old_version;
                #endif
                struct MindPower::lwAnimDataBone::lwBoneInfoHeader anim_bone.header;
                struct MindPower::lwBoneBaseInfo anim_bone._base_seq[anim_bone.header.bone_num];
                struct D3DXMATRIX anim_bone._invmat_seq[anim_bone.header.bone_num];
                struct MindPower::lwBoneDummyInfo anim_bone._dummy_seq[anim_bone.header.dummy_num];
                #if (anim_bone.header.key_type == 1)
                   class MindPower::lwMatrix43 anim_bone.mat43_seq[anim_bone.header.frame_num];
                #else if (anim_bone.header.key_type == 2)
                   struct D3DMATRIX anim_bone.mat44_seq[anim_bone.header.frame_num];
                #else if (anim_bone.header.key_type == 3)
                   #if (version >= 0x1003)
                          struct D3DXVECTOR3 anim_bone.pos_seq[anim_bone.header.frame_num];
                          struct D3DXQUATERNION anim_bone.quat_seq[anim_bone.header.frame_num];
                   #else
                          #for (#i = 0; #i < anim_bone.header.bone_num; #i++)
                                struct D3DXVECTOR3 anim_bone._key_seq[#i].pos_seq[anim_bone._base_seq[i].parent_id == -1 ? anim_bone.header.frame_num : 1];
                                struct D3DXQUATERNION anim_bone._key_seq[#i].quat_seq[anim_bone.header.frame_num];
                          #endfor
                   #endif
                #endif
         #endif
         #if (data_mat_size > 0)
                class MindPower::lwMatrix43 anim_mat[anim_bone.header.frame_num];
         #endif
         #if (version >= 0x1005)
                #for (#i = 0; #i < 16; i++)
                   #if (data_mtlopac_size[#i] == 0)
                          #next
                   #endif
                   struct anim_mtlopac[#i] { // There is no Actual Struct. so I did not named it
                         unsigned long anim_mtlopac[#i].num;
                         struct MindPower::lwKeyFloat anim_mtlopac[#i].seq[anim_mtlopac[#i].num];
                   }
                #endfor
         #endif
         #for (#i = 0; #i < 16; #i++)
                #for (#j = 0; #j < 4; #j++)
                   #if (data_texuv_size[#i][#j] == 0)
                          #next
                   #endif
                   struct anim_tex[#i][#j] { // There is no Actual Struct. so I did not named it
                         unsigned long anim_tex[#i][#j].frame_num;
                         struct D3DXMATRIX anim_tex[#i][#j]._mat_seq[anim_tex[#i][#j].frame_num];
                   }
                #endfor
         #endfor
         #for (#i = 0; #i < 16; #i++)
                #for (#j = 0; #j < 4; #j++)
                   #if (data_teximg_size[#i][#j] == 0)
                          #next
                   #endif
                   #if (version != 0)
                          struct data_teximg_size[#i][#j] {  // There is no Actual Struct. so I did not named it
                                unsigned long data_teximg_size[#i][#j].data_num;
                                struct MindPower::lwTexInfo data_teximg_size[#i][#j].data_seq[data_teximg_size[#i][#j].data_num];
                          }
                   #endif
                #endfor
         #endfor
  #endif
 
}

```
