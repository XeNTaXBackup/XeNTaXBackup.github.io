## Post #1
- Username: SubZer0
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Dec 23, 2021 3:57 am
- Post datetime: 2023-02-20T14:34:21+00:00
- Post Title: C code in to Quick BMS Script

How can i write this code in to Quick bms code.

Can any one help me on this?

```

int main(int argc, char *argv[]) {
    if (argc < 2) {
        printf("Usage: %s <filename>\n", argv[0]);
        return 1;
    }

    char *filename = argv[1];
    int fd = open(filename, O_RDWR);

    if (fd < 0) {
        printf("Error opening file %s\n", filename);
        return 1;
    }

    unsigned char buf[BUF_SIZE];
    ssize_t bytes_read, bytes_written;
    off_t offset = 0;

    while ((bytes_read = pread(fd, buf, BUF_SIZE, offset)) > 0) {
        for (int i = 0; i < bytes_read; i++) {
            buf[i] ^= 0x90;
        }

        bytes_written = pwrite(fd, buf, bytes_read, offset);
        if (bytes_written != bytes_read) {
            printf("Error writing to file %s\n", filename);
            return 1;
        }

        offset += bytes_read;
    }

    close(fd);
    printf("File %s decrypted successfully\n", filename);

    return 0;
}

```
## Post #2
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2023-02-21T14:56:26+00:00
- Post Title: C code in to Quick BMS Script

It would be something like this:

```
string NAME p "output/%s" NAME

math BUF_SIZE = 1024
get SIZE asize
math SIZE - BUF_SIZE
encryption xor 0x90
log NAME 0 BUF_SIZE
encryption "" ""
append
	log NAME BUF_SIZE SIZE
append
```
## Post #3
- Username: SubZer0
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Dec 23, 2021 3:57 am
- Post datetime: 2023-02-21T20:07:11+00:00
- Post Title: C code in to Quick BMS Script

Thank you for replying "Spiritovod"

I have made few more changes in code also found aft xor decrypted file,
It have zlib compression.

Providing both code for your reference.
Kindly help me to make  quick bms script.

Xor Enc Dec code :

```
#define XOR_KEY 0x90 // Key in hexadecimal format

void xor_encrypt(const char* in_file, const char* out_file) {
    int in_fd = open(in_file, O_RDONLY);
    if (in_fd == -1) {
        perror("open");
        exit(1);
    }

    int out_fd = open(out_file, O_WRONLY | O_CREAT | O_TRUNC, 0666);
    if (out_fd == -1) {
        perror("open");
        close(in_fd);
        exit(1);
    }

    unsigned char buffer[CHUNK_SIZE] = {0};
    
    ssize_t bytes_read = 0;

    while ((bytes_read = read(in_fd, buffer, CHUNK_SIZE)) > 0) {
        for (size_t i = 0; i < bytes_read; i++) {
            buffer[i] ^= XOR_KEY;
        }
        if (write(out_fd, buffer, bytes_read) != bytes_read) {
            perror("write");
            close(in_fd);
            close(out_fd);
            exit(1);
        }
    }

    if (bytes_read == -1) {
        perror("read");
        close(in_fd);
        close(out_fd);
        exit(1);
    }

    close(in_fd);
    close(out_fd);
}

int main(int argc, char* argv[]) {
    if (argc != 3) {
        fprintf(stderr, "Usage: %s infile outfile\n", argv[0]);
        return 1;
    }

    xor_encrypt(argv[1], argv[2]);

    return 0;
}

```


Zlib compression code

```

int main(int argc, char* argv[]) {
  if (argc != 3) {
    std::cout << "Usage: " << argv[0] << " [input file] [output file]" << std::endl;
    return 1;
  }

  // Open input and output files
  std::ifstream input_file(argv[1], std::ios::binary);
  std::ofstream output_file(argv[2], std::ios::binary);

  // Initialize zlib structures
  z_stream strm;
  strm.zalloc = Z_NULL;
  strm.zfree = Z_NULL;
  strm.opaque = Z_NULL;
  deflateInit(&strm, Z_DEFAULT_COMPRESSION);

  // Buffer for the input and compressed data
  char input_data[CHUNK_SIZE];
  char compressed_data[CHUNK_SIZE];

  // Compress the input data chunk by chunk
  do {
    input_file.read(input_data, CHUNK_SIZE);
    int bytes_read = input_file.gcount();
    strm.avail_in = bytes_read;
    strm.next_in = (Bytef *)input_data;
    do {
      strm.avail_out = CHUNK_SIZE;
      strm.next_out = (Bytef *)compressed_data;
      deflate(&strm, Z_NO_FLUSH);
      output_file.write(compressed_data, CHUNK_SIZE - strm.avail_out);
    } while (strm.avail_out == 0);
  } while (input_file);

  // Finish compression
  strm.avail_in = 0;
  do {
    strm.avail_out = CHUNK_SIZE;
    strm.next_out = (Bytef *)compressed_data;
    deflate(&strm, Z_FINISH);
    output_file.write(compressed_data, CHUNK_SIZE - strm.avail_out);
  } while (strm.avail_out == 0);

  // Clean up and return
  deflateEnd(&strm);
  return 0;
}

```


Zlib decompression code

```

int main(int argc, char* argv[]) {
  if (argc != 3) {
    std::cout << "Usage: " << argv[0] << " [input file] [output file]" << std::endl;
    return 1;
  }

  // Open input and output files
  std::ifstream input_file(argv[1], std::ios::binary);
  std::ofstream output_file(argv[2], std::ios::binary);

  // Initialize zlib structures
  z_stream strm;
  strm.zalloc = Z_NULL;
  strm.zfree = Z_NULL;
  strm.opaque = Z_NULL;
  inflateInit(&strm);

  // Buffer for the input and decompressed data
  char input_data[CHUNK_SIZE];
  char decompressed_data[CHUNK_SIZE];

  // Decompress the input data chunk by chunk
  do {
    input_file.read(input_data, CHUNK_SIZE);
    int bytes_read = input_file.gcount();
    strm.avail_in = bytes_read;
    strm.next_in = (Bytef *)input_data;
    do {
      strm.avail_out = CHUNK_SIZE;
      strm.next_out = (Bytef *)decompressed_data;
      inflate(&strm, Z_NO_FLUSH);
      output_file.write(decompressed_data, CHUNK_SIZE - strm.avail_out);
    } while (strm.avail_out == 0);
  } while (input_file);

  // Finish decompression
  strm.avail_in = 0;
  do {
    strm.avail_out = CHUNK_SIZE;
    strm.next_out = (Bytef *)decompressed_data;
    inflate(&strm, Z_FINISH);
    output_file.write(decompressed_data, CHUNK_SIZE - strm.avail_out);
  } while (strm.avail_out == 0);

  // Clean up and return
  inflateEnd(&strm);
  return 0;
}

```
## Post #4
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2023-02-21T21:03:16+00:00
- Post Title: C code in to Quick BMS Script

@SubZer0: It's not clear what you're trying to do with this code. If you want to decompress decrypted chunk with unknown decompressed size and compression is zlib, you can add "comtype unzip_dynamic" at the beginning and replace "log NAME 0 BUF_SIZE" with "clog NAME 0 BUF_SIZE BUF_SIZE". If you want to decompress data after encrypted part in chunks with fixed size, it would look something like this within "append" operator:

```
	math CHUNK_SIZE = 1024
	math OFFSET = BUF_SIZE
	for OFFSET = OFFSET < FSIZE
		xmath LEFT "FZIZE - CHUNK_SIZE"
		if LEFT < CHUNK_SIZE
			CHUNK_SIZE = LEFT
		endif
		clog NAME OFFSET CHUNK_SIZE CHUNK_SIZE
		math OFFSET + CHUNK_SIZE
	next
```

For any further adjustments I'd advice to read [quickbms documentation](https://aluigi.altervista.org/papers/quickbms.txt) and try to make them by yourself.
## Post #5
- Username: SubZer0
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Dec 23, 2021 3:57 am
- Post datetime: 2023-02-22T06:17:05+00:00
- Post Title: C code in to Quick BMS Script

@Spiritovod :
I wanted to decrypt file with Xor , then which output file we received it have Zlib compression. 
So want Quick Bms script to extract chunks(from output file receive after xor function) which are compressed with Zlib. 
Its not "after encrypted part",  it is itself a "fixed size zlib compressed chunks" which are xored with x90.
## Post #6
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2023-02-23T00:06:53+00:00
- Post Title: C code in to Quick BMS Script

@SubZer0: If the whole file is xored, this should work:

```
get NAME filename
string NAME p "output/%s" NAME

math CHUNK_SIZE = 1024
get SIZE asize
encryption xor 0x90
log MEMORY_FILE 0 SIZE
encryption "" ""
log NAME 0 0
append
	math OFFSET = 0
	for OFFSET = OFFSET < SIZE
		xmath LEFT "SIZE - OFFSET"
		if LEFT < CHUNK_SIZE
			CHUNK_SIZE = LEFT
		endif
		clog NAME OFFSET CHUNK_SIZE CHUNK_SIZE MEMORY_FILE
		math OFFSET + CHUNK_SIZE
	next
append
```

But there are other things which are still not clear, so it may fail on some files.
## Post #7
- Username: SubZer0
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Dec 23, 2021 3:57 am
- Post datetime: 2023-02-23T12:58:59+00:00
- Post Title: C code in to Quick BMS Script

This did not create separate extracted chunks like
000000.dat
000001.dat

It gives single file output.
## Post #8
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2023-02-23T13:54:11+00:00
- Post Title: C code in to Quick BMS Script

@SubZer0:

> Reply from Spiritovod ↑Wed Feb 22, 2023 5:03 am at Wed Feb 22, 2023 5:03 am
>
> For any further adjustments I'd advice to read quickbms documentation and try to make them by yourself.
