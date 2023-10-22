## Post #1
- Username: djmauro
- Rank: beginner
- Number of posts: 36
- Joined date: Tue Sep 16, 2008 9:49 pm
- Post datetime: 2012-05-31T21:42:12+00:00
- Post Title: Shader editing/shader format

well... magic word RF Online - a hard to dev game. But not the shaders - they´r not really encrypted.
.pso.vso and .vsh - looks like standard dx shaders.
eg. BlurBlit.pso 
D3DX8 Shader Assembler Version 0.91

but unfortunately these are already compiled shaders. Anyone ever  touched them or ca at least give hints as of how to find ut what registers etc it uses.. like p0,p1 or v1 etc - or perhaps some other one - im not asking for as of what those registers are actually assigned to in source.

basically the assembled  shader into a more readable format. So i can continue and use it as a base to find more info from the source.

Can provide this tho : 

```
; ------------------------------------------------- -----------------------------
; C0-c3-matrix a
; C4-c7 Matrix
; C8 fog
; C9 x = rocking numbers, y = alpha
; C12-vertex shader settings for different situations.
;
; Vertex components
; V0 = Position
; ------------------------------------------------- -----------------------------

; ------------------------------------------------- -----------------------------
; Vertex transformation
; ------------------------------------------------- -----------------------------

; Transform to view space (world matrix is ​​identity)
m4x4 r9, v0, c0

; Shaking part.
mul r10.x, v0.y, c9.x
add r9.x, r9.x, r10.x

; Transform to projection space
m4x4 r10, r9, c4

; Store output position
mov oPos, r10
mov oD0, v3; put the color values​​.
mov oD0.w, c9.y ;/ / alpha adjustment

; ------------------------------------------------- -----------------------------
; Texture coordinates
; ------------------------------------------------- -----------------------------

; Copy tex coords
mov oT0.xy, v4



; ------------------------------------------------- -----------------------------
; Fog calculation
; ------------------------------------------------- -----------------------------
; Compute fog factor f = (fog_end - dist) * (1 / (fog_end-fog_start))
add r0.x,-r9.z, c8.y
mul r0.x, r0.x, c8.z
max r0.x, r0.x, c9.z; clamp fog to> 0.0
min oFog.x, r0.x, c9.w; clamp fog to <1.0

; mov oFog.x, c10.x
```


thats a Grass1.vsh 
basically only readable shader.

and:

```
{   
    D3DVSD_STREAM( 0 ),   
    D3DVSD_REG( 0, D3DVSDT_FLOAT3 ), // Position of first mesh   
    D3DVSD_REG( 3, D3DVSDT_D3DCOLOR ), // DWORD color   
    D3DVSD_REG( 4, D3DVSDT_FLOAT2 ), // Tex coords   
    D3DVSD_END()   
};   
DWORD stDetailTexVertexShader;   
DWORD stDetailTexVertexDecl[] =   
{   
    D3DVSD_STREAM( 0 ),   
    D3DVSD_REG( 0, D3DVSDT_FLOAT3 ), // Position of first mesh   
    D3DVSD_REG( 3, D3DVSDT_FLOAT3 ), // Normal   
    D3DVSD_REG( 6, D3DVSDT_D3DCOLOR ), // DWORD color   
    D3DVSD_REG( 7, D3DVSDT_FLOAT2 ), // Tex coords   
    D3DVSD_REG( 9, D3DVSDT_FLOAT2 ), // Tex coords 2   
    D3DVSD_END()   
}; 
```
