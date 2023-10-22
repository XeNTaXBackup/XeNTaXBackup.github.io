## Post #1
- Username: zhouhang95
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Feb 10, 2023 1:49 am
- Post datetime: 2023-03-06T17:19:29+00:00
- Post Title: [Solved]konami dance evolution arcade model format with skinning

Snipaste_2023-03-07_01-11-44.png (113.02 KiB) Viewed 151 times



```
    let x = reader.read_f32::<LE>().unwrap();
    let y = reader.read_f32::<LE>().unwrap();
    let z = reader.read_f32::<LE>().unwrap();
    vec3(x, y, z)
}

fn main() {
    let contents_ = std::fs::read("1.pmx").unwrap();
    pmx::Pmx::read(contents_);
    let mut ktmodel = KTModel::default();

    let ktmdl_path = "pl_unaf002.model";
    let b2it_path = ktmdl_path.replace(".model", ".b2it");
    let b2it_content = std::fs::read(b2it_path).unwrap();
    ktmodel.bone_names = parse_b2it(&b2it_content);

    let content = std::fs::read(ktmdl_path).unwrap();
    let mut reader = std::io::Cursor::new(content);
    reader.set_position(0x18);
    let bone_count = reader.read_u32::<LE>().unwrap();
    let bone_ptr = reader.read_u32::<LE>().unwrap();
    eprintln!("0x18: bone count: {}, ptr: {:X}", bone_count, bone_ptr);

    reader.set_position(0x20);
    let bone_mapping_section_count = reader.read_u32::<LE>().unwrap() as usize;
    let mut bone_map_section_to_batch = Vec::new();

    for i in 0..bone_count {
        let cur_bone_ptr = bone_ptr + 16 * 11 * i;
        reader.set_position((16 * 4 + cur_bone_ptr) as _);
        ktmodel.bone_pos.push(read_vec3f(&mut reader));
        reader.set_position((16 * 8 + cur_bone_ptr) as _);
        reader.set_position((16 * 9 + cur_bone_ptr) as _);
        reader.set_position((16 * 10 + 12 + cur_bone_ptr) as _);
        let p = reader.read_i32::<LE>().unwrap();
        ktmodel.bone_parent.push(if p == -1 {
            None
        } else {
            Some(p as usize)
        });
    }
    assert_eq!(ktmodel.bone_names.len(), ktmodel.bone_pos.len());

    reader.set_position(0x28);
    let section_count = reader.read_u32::<LE>().unwrap();
    eprintln!("0x28: section_count: {}", section_count);

    reader.set_position(0x34);
    let section_ptr = reader.read_u32::<LE>().unwrap();
    eprintln!("0x34: section_ptr: {:X}", section_ptr);

    let mut bone_mapping_section = Vec::<BTreeSet<i32>>::new();

    for i in 0..section_count {
        let mut set = BTreeSet::<i32>::new();
        let mut mesh = KTSubMesh::default();
        reader.set_position((i * 64 + section_ptr) as _);

        let vert_offset = reader.read_u32::<LE>().unwrap();
        let vert_count = reader.read_u32::<LE>().unwrap();
        reader.read_u8().unwrap();
        let fvf_size = reader.read_u8().unwrap() as u32;
        assert_eq!(fvf_size, 68);
        reader.seek(SeekFrom::Current(22)).unwrap();

        let face_offset = reader.read_u32::<LE>().unwrap();
        let face_count = reader.read_u32::<LE>().unwrap() / 3;

        for j in 0..vert_count {
            let vert_start = section_ptr + i * 64 + vert_offset + j * fvf_size;
            reader.set_position(vert_start as _);
            let pos = read_vec3f(&mut reader);
            let b_0 = reader.read_u8().unwrap() as i32;
            let b_1 = reader.read_u8().unwrap() as i32;
            let b_2 = reader.read_u8().unwrap() as i32;
            let b_3 = reader.read_u8().unwrap() as i32;
            let bone_index = ivec4(b_0, b_1, b_2, b_3);
            let bw = read_vec3f(&mut reader);
            let bone_weight = vec4(1.0 - bw.x - bw.y - bw.z, bw.x, bw.y, bw.z);
            let norm = read_vec3f(&mut reader);
            let tang = read_vec3f(&mut reader);
            let bitang = read_vec3f(&mut reader);
            let u = half::f16::from_bits(reader.read_u16::<LE>().unwrap()).to_f32();
            let v = half::f16::from_bits(reader.read_u16::<LE>().unwrap()).to_f32();
            let uv = vec2(u, v);
            mesh.verts.push(KTVertex{ pos, bone_index, bone_weight, norm, tang, bitang, uv });
            set.insert(b_0);
            if b_1 != 0 {
                set.insert(b_1);
            }
            if b_2 != 0 {
                set.insert(b_2);
            }
            if b_3 != 0 {
                set.insert(b_3);
            }
        }
        let max_value = *set.iter().max().unwrap();
        if max_value + 1 == set.len() as _ {
            bone_mapping_section.push(BTreeSet::new());
        }
        for v in &set {
            bone_mapping_section.last_mut().unwrap().insert(*v);
        }

        bone_map_section_to_batch.push(bone_mapping_section.len() - 1);


        for j in 0..face_count {
            let face_start = section_ptr + 32 + i * 64 + face_offset + j * 6;
            reader.set_position(face_start as _);
            let _0 = reader.read_u16::<LE>().unwrap() as u32;
            let _1 = reader.read_u16::<LE>().unwrap() as u32;
            let _2 = reader.read_u16::<LE>().unwrap() as u32;
            mesh.face.push([_0, _1, _2]);
        }
        ktmodel.meshs.push(mesh);
    }
    assert_eq!(bone_mapping_section.len(), bone_mapping_section_count);

    reader.set_position(0x24);
    let bone_mapping_table_ptr = reader.read_u32::<LE>().unwrap();
    reader.set_position(bone_mapping_table_ptr as _);
    
    let mut bone_mapping_table: Vec<Vec<i32>> = Vec::new();
    {
        for s in &bone_mapping_section {
            let max_value = *s.iter().max().unwrap() as usize;
            assert_eq!(max_value + 1, s.len());
            let mut subtable = Vec::new();
            for _ in 0..s.len() {
                subtable.push(reader.read_u16::<LE>().unwrap() as i32);
            }
            bone_mapping_table.push(subtable);
        }
    }

    eprintln!("{}", reader.position());

    let mut verts = Vec::new();
    let mut vert_start = 0;
    let mut faces = Vec::new();
    let mut mats = Vec::new();
    for i in 0..ktmodel.meshs.len() {
        let m = &ktmodel.meshs[i];
        let batch = bone_map_section_to_batch[i];
        for v in &m.verts {
            let mut bone_index = IVec4::ZERO;
            for j in 0..4 {
                bone_index[j] = bone_mapping_table[batch][v.bone_index[j] as usize];
            }

            verts.push(pmx::Vertex {
                pos: v.pos,
                nrm: v.norm,
                uv: v.uv,
                weight: pmx::VertexWeight::Four(bone_index, v.bone_weight),
                edge_scale: 1.0,
            });
        }
        for f in &m.face {
            faces.push([
                f[0] + vert_start,
                f[1] + vert_start,
                f[2] + vert_start,
            ]);
        }
        vert_start += m.verts.len() as u32;
        let mut mat = pmx::Mat::default();
        mat.name = i.to_string();
        mat.associated_face_count = m.face.len() as _;
        mats.push(mat);
    }
    let mut bones = Vec::new();
    for i in 0..ktmodel.bone_names.len() {
        let mut b = pmx::Bone::default();
        b.name = ktmodel.bone_names[i].clone();
        b.name_en = ktmodel.bone_names[i].clone();
        b.pos = ktmodel.bone_pos[i];
        b.parent_index = ktmodel.bone_parent[i];
        bones.push(b);
    }
}


#[derive(Default, Clone, Copy)]
struct KTVertex {
    pos: Vec3,
    bone_index: IVec4,
    bone_weight: Vec4,
    norm: Vec3,
    tang: Vec3,
    bitang: Vec3,
    uv: Vec2,
}

#[derive(Default, Clone)]
struct KTSubMesh {
    verts: Vec<KTVertex>,
    face: Vec<[u32; 3]>,
}

#[derive(Default, Clone)]
struct KTModel {
    bone_names: Vec<String>,
    bone_pos: Vec<Vec3>,
    bone_parent: Vec<Option<usize>>,
    meshs: Vec<KTSubMesh>,
}

fn read_string_to_null<T>(reader: &mut T) -> String 
    where T: BufRead {
        let mut buf = Vec::new();
        loop {
            let c = reader.read_u8().unwrap();
            if c == 0 {
                break;
            }
            buf.push(c);
        }
        String::from_utf8(buf).unwrap()
}

fn parse_b2it(data: &Vec<u8>) -> Vec<String> {
    let mut reader = std::io::Cursor::new(data);
    reader.set_position(0x10);
    let count = reader.read_u32::<LE>().unwrap();
    reader.set_position(0x18);
    let offset = reader.read_u32::<LE>().unwrap();
    reader.set_position(0x20);
    let mut str_starts = Vec::new();
    for _ in 0..count {
        str_starts.push(reader.read_u32::<LE>().unwrap());
    }
    let mut bone_names = Vec::new();
    for str_start in &str_starts {
        reader.set_position(*str_start as _);
        bone_names.push(read_string_to_null(&mut reader));
    }
    let mut numbers = Vec::new();
    reader.set_position(offset as _);
    for _ in 0..count {
        numbers.push(reader.read_u32::<LE>().unwrap());
    }
    let mut out = Vec::new();
    out.resize(numbers.len(), String::new());

    for i in 0..count {
        out[numbers[i as usize] as usize] = bone_names[i as usize].clone();
    }
    out
}

```
## Post #2
- Username: zhouhang95
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Feb 10, 2023 1:49 am
- Post datetime: 2023-03-13T20:13:45+00:00
- Post Title: [Solved]konami dance evolution arcade model format with skinning

and dance motion (.anm) file

quaternion
3FFF7FFEFFFF
1/15/15/15/2
0/x/y/z/flag
(0, 0, 0, 1)

```
    let mut num: u64 = 0;
    for i in (0..6).rev() {
        num = num << 8;
        num += data[i] as u64;
    }
    num = num >> 2;
    let x = ((num & 0x7FFF) as f32 - 16383.5) / 23169.767578125;
    num = num >> 15;
    let y = ((num & 0x7FFF) as f32 - 16383.5) / 23169.767578125;
    num = num >> 15;
    let z = ((num & 0x7FFF) as f32 - 16383.5) / 23169.767578125;
    let w = (1.0 - (x * x + y * y + z * z)).sqrt();
    [x, y, z, w]
}

```


``````````````
Yout must to know about quaternion
I find a lot of game programmer don't konw it:

(x, y, z) = normal(rot_axis) * sin(rot_angle_in_radians / 2)
w = cos(rot_angle_in_radians / 2) 
```````````````
## Post #3
- Username: ziliangya
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Jan 29, 2023 11:21 pm
- Post datetime: 2023-09-25T13:19:46+00:00
- Post Title: [Solved]konami dance evolution arcade model format with skinning

Hello, I am not very familiar with the code. Can you generate an application to execute the corresponding file? Thank you very much
## Post #4
- Username: garamika
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue May 09, 2017 4:29 pm
- Post datetime: 2023-10-04T12:29:02+00:00
- Post Title: [Solved]konami dance evolution arcade model format with skinning

Looks like a code in Rust language but cannot run the script
