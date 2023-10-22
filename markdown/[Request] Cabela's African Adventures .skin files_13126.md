## Post #1
- Username: ATinyMotorboat
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jul 29, 2015 3:19 pm
- Post datetime: 2015-07-29T08:01:16+00:00
- Post Title: [Request] Cabela's African Adventures .skin files

I've tried as much as I could to figure out the format, but unfortunately I've had no luck.

Here is all the information I have gathered:
• Format appears to be similar to previous Cabela's games(Or at least it's PS2 counter-parts). [Ref](http://ps23dformat.wikispaces.com/file/view/trophybucksanimalSKINuvTO3ds.bms)
• Mesh is stored in the .skin for some reason, although it would make more sense to store it in the .model file.
• The "RSDBlendedDX9" mesh format(I think it is the format mode?) is also used in Facerig, compiled by the Phidias model tool(Only a CLI version is available).
• Although probably not important, these .skin files are created by Fun Labs, and I have unofficially nicknamed them "Fun labs skin file(s)".

I have included what I had so far on trying to read them, before going to a corner and crying.
It's written in javascript and processed through nodejs.
Specifically, the script was written to read the skin files for the animals located at Mod/CAS/PC/DATA/OBJECTS/ANIMALS/*/*.skin

The [arc unpacker](http://aluigi.altervista.org/papers/bms/cabela.bms) on the QuickBMS site works fine so they haven't changed the .arc format.

Truth be told, I want to be able to import/export animals so I can add manimals. I do not know why, but I had a sudden urge to mod the game to have them.
[Sample file](https://mega.co.nz/#!2kgDRKzT!ltC448eL6lseAJyAZ4Yb0GTjGgTir_Ftt_iMwME6Gko)

I couldn't attach the script because "txt" and "js" are not allowed as formats, and I couldn't figure out how to collapse the code view, sorry if it is too big.

```
Buffer.prototype.readString8 = function(offset){ //Prototypes shouldn't be extended, but I don't care since this is just a single script.
    return this.toString("ascii",offset+1,offset+this.readUInt8(offset)+1);
}

function main(){
    var file=process.argv[2];
    if(typeof file=="undefined")
        return console.log("Cannot read file \"undefined\".");
    else
        console.log("Opening "+file+"...");
    var result={};
    fs.readFile(file, function(err, data){
        if(err)throw err;
        var index=0;
        if(data.readUInt32BE(index)==0x46425346){
            if(data.readUInt32BE(index+=6)!=0x0)//This should ALWAYS be 4 nulls
                return;
            //Find the compiler string
            var tmp="";index+=4;
            while(data.readUInt8(index)!=0x0)
                tmp+=String.fromCharCode(data.readUInt8(index++));
            console.log("Compiler: "+(result.compiler=tmp));index+=4;
            
            //Find the model name
            tmp="";
            console.log("Model: "+(result.model=data.readString8(index)));
            
            /*From here on out, we skip until we find the first ModelLOD*/
            while(data.toString("ascii",index,(index++)+8)!="ModelLOD"){}//Dirty hack
            index+=27;//Above + weight + unknown
            
            //What shader are we using?
            console.log("Shader: "+(result.shader=data.readString8(index)));
            
            //How many bones?
            index+=result.shader.length+9;//Above + unknown
            result.bonecount=data.readUInt32LE(index); index+=4;
            result.bonenames=[];
            for(var i=0;i<result.bonecount;i++){
                var tmp=data.readString8(index);
                result.bonenames.push(tmp);
                index+=tmp.length+1;
            }
            result.bones=[];
            for(var i=0;i<result.bonenames.length;i++){
                result.bones[result.bonenames[i]]=[
                    [
                        data.readFloatLE(index),
                        data.readFloatLE(index+=4),
                        data.readFloatLE(index+=4)
                    ],
                    [
                        data.readFloatLE(index+=4),
                        data.readFloatLE(index+=4),
                        data.readFloatLE(index+=4)
                    ]
                ]
            }
            index+=1;
            console.log(index);
            while(data.readUInt32LE(index++)!=result.bonecount){}//Dirty hack
            console.log(data.readUInt32LE(index-1)+" "+result.bonecount+" "+index);
        }else console.log("Not a Fun Labs .skin file!");
    });
}
main();
```
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-07-29T09:48:31+00:00
- Post Title: [Request] Cabela's African Adventures .skin files

> Reply from ATinyMotorboat
>
> • Format appears to be similar to previous Cabela's games(Or at least it's PS2 counter-parts). RefThis is one of those annoying bms scripts containing hundreds of puts/sets. Really hate this.  
(to be clear: bms scripts normally are great)

Anyway - I used hex2obj (view link in my sig) to get the mesh:



Aardwolf_skin.JPG (41.5 KiB) Viewed 95 times
## Post #3
- Username: ATinyMotorboat
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jul 29, 2015 3:19 pm
- Post datetime: 2015-07-29T10:14:39+00:00
- Post Title: [Request] Cabela's African Adventures .skin files

> Reply from shakotay2
>
> ATinyMotorboat wrote:• Format appears to be similar to previous Cabela's games(Or at least it's PS2 counter-parts). RefThis is one of those annoying bms scripts containing hundreds of puts/sets. Really hate this.  
(to be clear: bms scripts normally are great)

Anyway - I used hex2obj (view link in my sig) to get the mesh:
Aardwolf_skin.JPG
Holy crap, that tool is outstandingly amazing! 
Many thanks for that!
