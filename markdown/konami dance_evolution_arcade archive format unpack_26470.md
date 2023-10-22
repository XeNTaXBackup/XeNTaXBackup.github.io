## Post #1
- Username: zhouhang95
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Feb 10, 2023 1:49 am
- Post datetime: 2023-02-14T16:58:08+00:00
- Post Title: konami dance_evolution_arcade archive format unpack

dance dance revolution series

about 2010 game release

first byte is flag
next 6 byte is dds header
next is unkonwn
is compressed texture

[https://drive.google.com/file/d/1RsCREq ... sp=sharing](https://drive.google.com/file/d/1RsCREqHvmST5FFmDfNqcEGhjX9BlZm86/view?usp=sharing)

[https://drive.google.com/file/d/1WpiMTE ... sp=sharing](https://drive.google.com/file/d/1WpiMTE0MheNHaRSezATeNQiPfNZzP4ez/view?usp=sharing)

[https://drive.google.com/file/d/1arimKJ ... sp=sharing](https://drive.google.com/file/d/1arimKJ4TnCpHOXGexLWnfnc3bPfSmlga/view?usp=sharing)
## Post #2
- Username: zhouhang95
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Feb 10, 2023 1:49 am
- Post datetime: 2023-03-06T15:10:06+00:00
- Post Title: konami dance_evolution_arcade archive format unpack

i solve it.

```
    let length = data.len() as u64;
    let mut reader = Cursor::new(data);
    let mut control_code: u16 = 0;
    let mut output: Vec<u8> = Vec::with_capacity(raw_size as _);
    while length - reader.position() > 0 {
        if control_code & 0x100 == 0 {
            control_code = reader.read_u8().unwrap() as u16;
            control_code |= 0xFF00;
        }
        if control_code & 1 != 0 {
            output.push(reader.read_u8().unwrap());
        } else {
            let flag = reader.read_u16::<BE>().unwrap();
            if flag == 0 {
                break;
            }
            let offset = flag >> 4;
            let len = (flag & 0xF) + 3;
            for _ in 0..len {
                let pos = output.len() as i32 - offset as i32;
                if pos < 0 {
                    output.push(0);
                } else {
                    output.push(output[pos as usize]);
                }
            }
        }
        control_code >>= 1;
    }
    assert_eq!(output.len(), raw_size as usize);
    output
}

```
