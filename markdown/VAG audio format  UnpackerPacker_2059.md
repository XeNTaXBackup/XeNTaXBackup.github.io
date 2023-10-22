## Post #1
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-08-26T13:43:01+00:00
- Post Title: VAG audio format  Unpacker/Packer

I found this sources how to pack/unpack a VAG audio format, maybe helps 

The unpacker:

```

    VAG-Depack, hacked by bITmASTER@bigfoot.com
    V0.1
*/




#ifdef _mam
extern "C"
{
#endif /* _mam */

#include <stdio.h>
#include <string.h>

double f[5][2] = { { 0.0, 0.0 },
                    {  60.0 / 64.0,  0.0 },
                    {  115.0 / 64.0, -52.0 / 64.0 },
                    {  98.0 / 64.0, -55.0 / 64.0 },
                    {  122.0 / 64.0, -60.0 / 64.0 } };

double samples[28];

int main( int argc, char *argv[] )
{
    FILE *vag, *pcm;
    char fname[128];
    char *p;
    int predict_nr, shift_factor, flags;
    int i;
    int d, s;
    static double s_1 = 0.0;
    static double s_2 = 0.0;
        
    if ( argc != 2 ) {
        printf( "usage: depack *.vag\n" );
        return( -1 );
    }
    
    vag = fopen( argv[1], "rb" );
    fseek( vag, 64, SEEK_SET );

    strcpy( fname, argv[1] );
    p = strrchr( fname, '.' );
    p++;
    strcpy( p, "PCM" );
    pcm = fopen( fname, "wb" );
    if ( vag == NULL ) {
        printf( "canï½´t write output file\n" );
        return( -8 );
    }




    while( 1 ) {
        predict_nr = fgetc( vag );
        shift_factor = predict_nr & 0xf;
        predict_nr >>= 4;
        flags = fgetc( vag );                          // flags
        if ( flags == 7 )
            break;              
        for ( i = 0; i < 28; i += 2 ) {
            d = fgetc( vag );
            s = ( d & 0xf ) << 12;
            if ( s & 0x8000 )
                s |= 0xffff0000;
            samples[i] = (double) ( s >> shift_factor  );
            s = ( d & 0xf0 ) << 8;
            if ( s & 0x8000 )
                s |= 0xffff0000;
            samples[i+1] = (double) ( s >> shift_factor  );
        }
    
        for ( i = 0; i < 28; i++ ) {
            samples[i] = samples[i] + s_1 * f[predict_nr][0] + s_2 * f[predict_nr][1];
            s_2 = s_1;
            s_1 = samples[i];
            d = (int) ( samples[i] + 0.5 );
            fputc( d & 0xff, pcm );
            fputc( d >> 8, pcm );
        }
    }
    
    fclose( pcm );
    fclose( vag );
    return( 0 );
}

```


The Packer:

```

    PSX VAG-Packer, hacked by bITmASTER@bigfoot.com
    v0.1                              
*/



#include <stdio.h>
#include <string.h>
#include <ctype.h>
#include <math.h>
#include <conio.h>

#define BUFFER_SIZE 128*28

short wave[BUFFER_SIZE];

void find_predict( short *samples, double *d_samples, int *predict_nr, int *shift_factor );
void pack( double *d_samples, short *four_bit, int predict_nr, int shift_factor );
void fputi( int d, FILE *fp );

int main( int argc, char *argv[] )
{
    FILE *fp, *vag;
    char fname[128];
    char *p;
    short *ptr;
    double d_samples[28];
    short four_bit[28];
    int predict_nr;
    int shift_factor;
    int flags;
    int size;
    int i, j, k;    
    unsigned char d;
    char s[4];
    int chunk_data;
    short e;
    int sample_freq, sample_len;
    
    if ( argc != 2 ) {
        printf( "usage: vag-pack *.wav\n" );
        return( -1 );
    }
            
    fp = fopen( argv[1], "rb" );
    if ( fp == NULL ) {
        printf( "canï½´t open %s\n", argv[1] );
        return( -2 );
    }

    fread( s, 1, 4, fp );
    if ( strncmp( s, "RIFF", 4 ) ) {
        printf( "not a wav-file\n" );
        return( -3 );
    }

    fseek( fp, 8, SEEK_SET );
    fread( s, 1, 4, fp );
    if ( strncmp( s, "WAVE", 4 ) ) {
        printf( "not a wav-file\n" );
        return( -3 );
    }

    fseek( fp, 8 + 4, SEEK_SET );
    fread( s, 1, 4, fp );
    if ( strncmp( s, "fmt", 3 ) ) {
        printf( "not a wav-file\n" );
        return( -3 );
    }
    
    fread( &chunk_data, 4, 1, fp ); 
    chunk_data += ftell( fp );
    
    fread( &e, 2, 1, fp );
    if ( e != 1 ) {
        printf( "no PCM\n" );
        return( -4 );
    }  

    fread( &e, 2, 1, fp );
    if ( e != 1 ) {
        printf( "must be MONO\n" );
        return( -5 );
    }

    fread( &sample_freq, 4, 1, fp );
    fseek( fp, 4 + 2, SEEK_CUR );

    fread( &e, 2, 1, fp );
    if ( e != 16 ) {
        printf( "only 16 bit samples\n" );
        return( -6 );
    }      
        
    fseek( fp, chunk_data, SEEK_SET );
    
    fread( s, 1, 4, fp );
    if ( strncmp( s, "data", 4 ) ) {
        printf( "no data chunk \n" );
        return( -7 );
    }

    fread( &sample_len, 4, 1, fp );
    sample_len /= 2;

    strcpy( fname, argv[1] );
    p = strrchr( fname, '.' );
    p++;
    strcpy( p, "VAG" );
    vag = fopen( fname, "wb" );
    if ( vag == NULL ) {
        printf( "canï½´t write output file\n" );
        return( -8 );
    }

    fprintf( vag, "VAGp" );            // ID
    fputi( 0x20, vag );                // Version
    fputi( 0x00, vag );                // Reserved
    size = sample_len / 28;
    if( sample_len % 28 )
        size++;
    fputi( 16 * ( size + 2 ), vag );    // Data size
    fputi( sample_freq, vag );          // Sampling frequency
    
    for ( i = 0; i < 12; i++ )          // Reserved
        fputc( 0, vag );

    p -= 2;
    i = 0;
    while( isalnum( *p ) ) {
        i++;
        p--;
    }
    p++;
    for ( j = 0; j < i; j++ )          // Name
        fputc( *p++, vag );
    for( j = 0; j < 16-i; j++ )
        fputc( 0, vag );
        
    for( i = 0; i < 16; i++ )
        fputc( 0, vag );                // ???

    flags = 0;  
    while( sample_len > 0 ) {
        size = ( sample_len >= BUFFER_SIZE ) ? BUFFER_SIZE : sample_len; 
        fread( wave, sizeof( short ), size, fp );
        i = size / 28;
        if ( size % 28 ) {
            for ( j = size % 28; j < 28; j++ )
                wave[28*i+j] = 0;
            i++;
        }
        
        for ( j = 0; j < i; j++ ) {                                    // pack 28 samples
            ptr = wave + j * 28;
            find_predict( ptr, d_samples, &predict_nr, &shift_factor );
            pack( d_samples, four_bit, predict_nr, shift_factor );
            d = ( predict_nr << 4 ) | shift_factor;
            fputc( d, vag );
            fputc( flags, vag );
            for ( k = 0; k < 28; k += 2 ) {
                d = ( ( four_bit[k+1] >> 8 ) & 0xf0 ) | ( ( four_bit[k] >> 12 ) & 0xf );
                fputc( d, vag );
            }
            sample_len -= 28;
            if ( sample_len < 28 )
                flags = 1;
        }
    }
    
    fputc( ( predict_nr << 4 ) | shift_factor, vag );
    fputc( 7, vag );            // end flag
    for ( i = 0; i < 14; i++ )
        fputc( 0, vag );

    
    fclose( fp );
    fclose( vag );  
//    getch(); 
    return( 0 );
}


static double f[5][2] = { { 0.0, 0.0 },
                            {  -60.0 / 64.0, 0.0 },
                            { -115.0 / 64.0, 52.0 / 64.0 },
                            {  -98.0 / 64.0, 55.0 / 64.0 },
                            { -122.0 / 64.0, 60.0 / 64.0 } };
                  


void find_predict( short *samples, double *d_samples, int *predict_nr, int *shift_factor )
{
    int i, j;
    double buffer[28][5];
    double min = 1e10;
    double max[5];
    double ds;
    int min2;
    int shift_mask;
    static double _s_1 = 0.0;                            // s[t-1]
    static double _s_2 = 0.0;                            // s[t-2]
    double s_0, s_1, s_2;

    for ( i = 0; i < 5; i++ ) {
        max[i] = 0.0;
        s_1 = _s_1;
        s_2 = _s_2;
        for ( j = 0; j < 28; j ++ ) {
            s_0 = (double) samples[j];                      // s[t-0]
            if ( s_0 > 30719.0 )
                s_0 = 30719.0;
            if ( s_0 < - 30720.0 )
                s_0 = -30720.0;
            ds = s_0 + s_1 * f[i][0] + s_2 * f[i][1];
            buffer[j][i] = ds;
            if ( fabs( ds ) > max[i] )
                max[i] = fabs( ds );
//                printf( "%+5.2f\n", s2 );
                s_2 = s_1;                                  // new s[t-2]
                s_1 = s_0;                                  // new s[t-1]
        }
        
        if ( max[i] < min ) {
            min = max[i];
            *predict_nr = i;
        }
        if ( min <= 7 ) {
            *predict_nr = 0;
            break;
        }
        
    }

// store s[t-2] and s[t-1] in a static variable
// these than used in the next function call

    _s_1 = s_1;
    _s_2 = s_2;
    
    for ( i = 0; i < 28; i++ )
        d_samples[i] = buffer[i][*predict_nr];

//  if ( min > 32767.0 )
//      min = 32767.0;
        
    min2 = ( int ) min;
    shift_mask = 0x4000;
    *shift_factor = 0;
    
    while( *shift_factor < 12 ) {
        if ( shift_mask  & ( min2 + ( shift_mask >> 3 ) ) )
            break;
        (*shift_factor)++;
        shift_mask = shift_mask >> 1;
    }
      
}

void pack( double *d_samples, short *four_bit, int predict_nr, int shift_factor )
{
    double ds;
    int di;
    double s_0;
    static double s_1 = 0.0;
    static double s_2 = 0.0;
    int i;

    for ( i = 0; i < 28; i++ ) {
        s_0 = d_samples[i] + s_1 * f[predict_nr][0] + s_2 * f[predict_nr][1];
        ds = s_0 * (double) ( 1 << shift_factor );

        di = ( (int) ds + 0x800 ) & 0xfffff000;

        if ( di > 32767 )
            di = 32767;
        if ( di < -32768 )
            di = -32768;
            
        four_bit[i] = (short) di;

        di = di >> shift_factor;
        s_2 = s_1;
        s_1 = (double) di - s_0;

    }
}

void fputi( int d, FILE *fp )
{
    fputc( d >> 24, fp );
    fputc( d >> 16, fp );  
    fputc( d >> 8,  fp );
    fputc( d,      fp );
}

```



Well i compiled with Gcc the packer and unpacker and works greats!!

PS: The decoder creates a RAW audio file, maybe somebody can modify the source to create a riff wave, anyway you can encode it with --raw of any audio compressor 
[vags.zip](https://xentaxbackup.github.io/file/827_vags.zip)
## Post #2
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-08-26T13:48:40+00:00
- Post Title: VAG audio format  Unpacker/Packer

Now gimme a source in VB to!
## Post #3
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-08-26T14:35:38+00:00
- Post Title: VAG audio format  Unpacker/Packer

Have a look here:
[http://www.daniweb.com/techtalkforums/thread52807.html](http://www.daniweb.com/techtalkforums/thread52807.html)
## Post #4
- Username: mambox
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Wed Mar 24, 2004 9:06 pm
- Post datetime: 2006-08-27T15:43:02+00:00
- Post Title: VAG audio format  Unpacker/Packer

thanks to share the compiled with us
## Post #5
- Username: pezhvak
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jun 19, 2011 3:01 pm
- Post datetime: 2011-06-19T11:28:45+00:00
- Post Title: VAG audio format  Unpacker/Packer

Thank you, the encoder works great, but about decoder.. i tried to decode a VAG file, but process won't finish, it makes a PCM file and keeps writing data in it..
## Post #6
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2016-10-12T18:29:13+00:00
- Post Title: VAG audio format  Unpacker/Packer

10 years later: Thanks for the code! 
I added a wave header but I think that different games use different formats. Maybe we should pass numChannels, sampleRate, bitsPerSample as arguments?
The unpacker didn't terminate when I fed it with my files so I also added an extra EOF check. I noticed that (flags == 7) was never true, but flags == 1 was, so I also added this check.

```

    VAG-Depack, hacked by bITmASTER@bigfoot.com
    V0.1
    
    Changes:
    12Oct2016, herbert3000, WAVE header added
*/

#ifdef _mam
extern "C"
{
#endif /* _mam */

#include <stdio.h>
#include <string.h>

double f[5][2] = { { 0.0, 0.0 },
                    {  60.0 / 64.0,  0.0 },
                    {  115.0 / 64.0, -52.0 / 64.0 },
                    {  98.0 / 64.0, -55.0 / 64.0 },
                    {  122.0 / 64.0, -60.0 / 64.0 } };

double samples[28];

struct {
   char  chunkId[4];
   int   chunkSize;
   char  format[4];
   char  subchunk1Id[4];
   int   subchunk1Size;
   short audioFormat;
   short numChannels;
   int   sampleRate;
   int   byteRate;
   short blockAlign;
   short bitsPerSample;
   char  subchunk2Id[4];
   int   subchunk2Size;
} waveHeader;

int main( int argc, char *argv[] )
{
    FILE *vag, *pcm, *wav;
    char fname[128];
    char *p;
    int predict_nr, shift_factor, flags;
    int i;
    int d, s;
    static double s_1 = 0.0;
    static double s_2 = 0.0;
    
    if ( argc != 2 ) {
        printf( "Usage: %s *.vag\n", argv[0] );
        return( -1 );
    }
   
    vag = fopen( argv[1], "rb" );
    if ( vag == NULL ) {
        printf( "cannot open input file\n" );
        return( -8 );
    }
    
    fseek( vag, 64, SEEK_SET );
    
    strcpy( fname, argv[1] );
    p = strrchr( fname, '.' );
    p++;
    strcpy( p, "PCM" );
    pcm = fopen( fname, "wb" );
    if ( pcm == NULL ) {
        printf( "cannot open output file\n" );
        return( -8 );
    }
    
    while( 1 ) {
        predict_nr = fgetc( vag );
        shift_factor = predict_nr & 0xf;
        predict_nr >>= 4;
        if ((flags = fgetc( vag )) == EOF) {
            break;
        }
        if ( flags == 7 )
            break;             
        for ( i = 0; i < 28; i += 2 ) {
            d = fgetc( vag );
            s = ( d & 0xf ) << 12;
            if ( s & 0x8000 )
                s |= 0xffff0000;
            samples[i] = (double) ( s >> shift_factor  );
            s = ( d & 0xf0 ) << 8;
            if ( s & 0x8000 )
                s |= 0xffff0000;
            samples[i+1] = (double) ( s >> shift_factor  );
        }
        
        for ( i = 0; i < 28; i++ ) {
            samples[i] = samples[i] + s_1 * f[predict_nr][0] + s_2 * f[predict_nr][1];
            s_2 = s_1;
            s_1 = samples[i];
            d = (int) ( samples[i] + 0.5 );
            fputc( d & 0xff, pcm );
            fputc( d >> 8, pcm );
        }
        if ( flags == 1 )
            break;
    }
    
    fclose( pcm );
    fclose( vag );
    
    // create WAV file
    
    pcm = fopen( fname, "rb" );
    if ( pcm == NULL ) {
        printf( "cannot open PCM file\n" );
        return( -8 );
    }
    
    strcpy( fname, argv[1] );
    p = strrchr( fname, '.' );
    p++;
    strcpy( p, "WAV" );
    wav = fopen( fname, "wb" );
    if ( wav == NULL ) {
        printf( "cannot open WAV file\n" );
        return( -8 );
    }
    
    fseek( pcm, 0, SEEK_END );
    int filesize = ftell( pcm );
    fseek( pcm, 0, SEEK_SET );
    
    // set WAVE header
    
    strcpy( waveHeader.chunkId, "RIFF" );
    strcpy( waveHeader.format, "WAVE" );
    strcpy( waveHeader.subchunk1Id, "fmt " );
    strcpy( waveHeader.subchunk2Id, "data" );
    
    waveHeader.audioFormat = 1; // PCM
    waveHeader.numChannels = 1; // mono = 1, stereo = 2
    waveHeader.sampleRate = 44100;
    waveHeader.bitsPerSample = 16;
    waveHeader.byteRate = waveHeader.sampleRate * waveHeader.numChannels * waveHeader.bitsPerSample / 8;
    waveHeader.blockAlign = waveHeader.numChannels * waveHeader.bitsPerSample / 8;
    waveHeader.subchunk1Size = 16;
    waveHeader.subchunk2Size = filesize;
    waveHeader.chunkSize = filesize + 36;
    
    
    // write WAVE header
    
    fwrite( &waveHeader, sizeof(waveHeader), 1, wav );
    
    // copy PCM file to WAV file
    
    char buffer[1024];
    size_t n;
    
    n = fread( buffer, 1, sizeof buffer, pcm );
    fwrite( buffer, 1, n, wav );
    
    while ( n == sizeof buffer ) {
        n = fread( buffer, 1, sizeof buffer, pcm );
        fwrite( buffer, 1, n, wav );
    }
    
    fclose( wav );
    fclose( pcm );
    
    return( 0 );
}
```
