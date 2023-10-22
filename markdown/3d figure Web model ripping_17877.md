## Post #1
- Username: oamio
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Mar 06, 2011 9:52 pm
- Post datetime: 2018-03-25T13:24:27+00:00
- Post Title: 3d figure Web model ripping

[http://view.realvu3d.com/realvu_v28/FG01.html](http://view.realvu3d.com/realvu_v28/FG01.html)
[http://www.vrism.net/project/banpresto-001/](http://www.vrism.net/project/banpresto-001/)
[http://www.vrism.net/project/captain-america/](http://www.vrism.net/project/captain-america/)

I'm not sure if this is a picture or 3d model
I think ripping is possible if it is 3d
I would like your attention to the ability
All I can do is introduce  the material
## Post #2
- Username: oamio
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Mar 06, 2011 9:52 pm
- Post datetime: 2018-03-25T13:34:28+00:00
- Post Title: 3d figure Web model ripping

Alright, This is texture file
Now, I am sure of that is 3d model
[texture_adroid18.jpg](https://xentaxbackup.github.io/file/14091_texture_adroid18.jpg)
## Post #3
- Username: oamio
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Mar 06, 2011 9:52 pm
- Post datetime: 2018-03-25T13:40:09+00:00
- Post Title: 3d figure Web model ripping

Maybe this is model file
[model_obj.jpg](https://xentaxbackup.github.io/file/14093_model_obj.jpg)
## Post #4
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-03-25T15:23:33+00:00
- Post Title: 3d figure Web model ripping

Easy to extract:



meshUVs.jpg (56.3 KiB) Viewed 134 times
## Post #5
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-03-25T16:30:28+00:00
- Post Title: 3d figure Web model ripping

Yes, easy structure. Everything is in order. Indices at the beginning, after that starts the vertex positions,  followed by uvs. You can even find the index/vertex counts in the json file, if you don't want to look for yourself. Anyway here is the exported model : [http://www.mediafire.com/file/xctkpqcd1 ... FG01_0.obj](http://www.mediafire.com/file/xctkpqcd11zx7jq/FG01_0.obj)

Btw pretty impressive polycount. I wonder if it is the actual model that got printed for the figure.
## Post #6
- Username: oamio
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Mar 06, 2011 9:52 pm
- Post datetime: 2018-03-26T02:17:54+00:00
- Post Title: 3d figure Web model ripping

```
!function(a,b){"use strict";"object"==typeof module&&"object"==typeof module.exports?module.exports=a.document?b(a,!0):function(a){if(!a.document)throw new Error("jQuery requires a window with a document");return b(a)}:b(a)}("undefined"!=typeof window?window:this,function(a,b){"use strict";var c=[],d=a.document,e=Object.getPrototypeOf,f=c.slice,g=c.concat,h=c.push,i=c.indexOf,j={},k=j.toString,l=j.hasOwnProperty,m=l.toString,n=m.call(Object),o={};function p(a,b){b=b||d;var c=b.createElement("script");c.text=a,b.head.appendChild(c).parentNode.removeChild(c)}var q="3.2.1",r=function(a,b){return new r.fn.init(a,b)},s=/^[\s\uFEFF\xA0]+|[\s\uFEFF\xA0]+$/g,t=/^-ms-/,u=/-([a-z])/g,v=function(a,b){return b.toUpperCase()};r.fn=r.prototype={jquery:q,constructor:r,length:0,toArray:function(){return f.call(this)},get:function(a){return null==a?f.call(this):a<0?this[a+this.length]:this[a]},pushStack:function(a){var b=r.merge(this.constructor(),a);return b.prevObject=this,b},each:function(a){return r.each(this,a)},map:function(a){return this.pushStack(r.map(this,function(b,c){return a.call(b,c,b)}))},slice:function(){return this.pushStack(f.apply(this,arguments))},first:function(){return this.eq(0)},last:function(){return this.eq(-1)},eq:function(a){var b=this.length,c=+a+(a<0?b:0);return this.pushStack(c>=0&&c<b?[this[c]]:[])},end:function(){return this.prevObject||this.constructor()},push:h,sort:c.sort,splice:c.splice},r.extend=r.fn.extend=function(){var a,b,c,d,e,f,g=arguments[0]||{},h=1,i=arguments.length,j=!1;for("boolean"==typeof g&&(j=g,g=arguments[h]||{},h++),"object"==typeof g||r.isFunction(g)||(g={}),h===i&&(g=this,h--);h<i;h++)if(null!=(a=arguments[h]))for(b in a)c=g[b],d=a[b],g!==d&&(j&&d&&(r.isPlainObject(d)||(e=Array.isArray(d)))?(e?(e=!1,f=c&&Array.isArray(c)?c:[]):f=c&&r.isPlainObject(c)?c:{},g[b]=r.extend(j,f,d)):void 0!==d&&(g[b]=d));return g},r.extend({expando:"jQuery"+(q+Math.random()).replace(/\D/g,""),isReady:!0,error:function(a){throw new Error(a)},noop:function(){},isFunction:function(a){return"function"===r.type(a)},isWindow:function(a){return null!=a&&a===a.window},isNumeric:function(a){var b=r.type(a);return("number"===b||"string"===b)&&!isNaN(a-parseFloat(a))},isPlainObject:function(a){var b,c;return!(!a||"[object Object]"!==k.call(a))&&(!(b=e(a))||(c=l.call(b,"constructor")&&b.constructor,"function"==typeof c&&m.call(c)===n))},isEmptyObject:function(a){var b;for(b in a)return!1;return!0},type:function(a){return null==a?a+"":"object"==typeof a||"function"==typeof a?j[k.call(a)]||"object":typeof a},globalEval:function(a){p(a)},camelCase:function(a){return a.replace(t,"ms-").replace(u,v)},each:function(a,b){var c,d=0;if(w(a)){for(c=a.length;d<c;d++)if(b.call(a[d],d,a[d])===!1)break}else for(d in a)if(b.call(a[d],d,a[d])===!1)break;return a},trim:function(a){return null==a?"":(a+"").replace(s,"")},makeArray:function(a,b){var c=b||[];return null!=a&&(w(Object(a))?r.merge(c,"string"==typeof a?[a]:a):h.call(c,a)),c},inArray:function(a,b,c){return null==b?-1:i.call(b,a,c)},merge:function(a,b){for(var c=+b.length,d=0,e=a.length;d<c;d++)a[e++]=b[d];return a.length=e,a},grep:function(a,b,c){for(var d,e=[],f=0,g=a.length,h=!c;f<g;f++)d=!b(a[f],f),d!==h&&e.push(a[f]);return e},map:function(a,b,c){var d,e,f=0,h=[];if(w(a))for(d=a.length;f<d;f++)e=b(a[f],f,c),null!=e&&h.push(e);else for(f in a)e=b(a[f],f,c),null!=e&&h.push(e);return g.apply([],h)},guid:1,proxy:function(a,b){var c,d,e;if("string"==typeof b&&(c=a[b],b=a,a=c),r.isFunction(a))return d=f.call(arguments,2),e=function(){return a.apply(b||this,d.concat(f.call(arguments)))},e.guid=a.guid=a.guid||r.guid++,e},now:Date.now,support:o}),"function"==typeof Symbol&&(r.fn[Symbol.iterator]=c[Symbol.iterator]),r.each("Boolean Number String Function Array Date RegExp Object Error Symbol".split(" "),function(a,b){j["[object "+b+"]"]=b.toLowerCase()});function w(a){var b=!!a&&"length"in a&&a.length,c=r.type(a);return"function"!==c&&!r.isWindow(a)&&("array"===c||0===b||"number"==typeof b&&b>0&&b-1 in a)}var x=function(a){var b,c,d,e,f,g,h,i,j,k,l,m,n,o,p,q,r,s,t,u="sizzle"+1*new Date,v=a.document,w=0,x=0,y=ha(),z=ha(),A=ha(),B=function(a,b){return a===b&&(l=!0),0},C={}.hasOwnProperty,D=[],E=D.pop,F=D.push,G=D.push,H=D.slice,I=function(a,b){for(var c=0,d=a.length;c<d;c++)if(a[c]===b)return c;return-{}X.set(a,b,c)}else c=void 0;return c}r.extend({hasData:function(a){return X.hasData(a)||W.hasData(a)},data:function(a,b,c){return X.access(a,b,c)}

```

 Is it part of the model file?
## Post #7
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-03-26T03:00:59+00:00
- Post Title: 3d figure Web model ripping

> Reply from oamio
>
> 
It is part of the file
A real mess. What's the point of this? The model attributes are described in FG01.json, and that would be pretty much enough for building the mesh.
## Post #8
- Username: oamio
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Mar 06, 2011 9:52 pm
- Post datetime: 2018-03-26T04:03:04+00:00
- Post Title: 3d figure Web model ripping

> Reply from Bigchillghost
>
> oamio wrote:
It is part of the file
A real mess. What's the point of this? The model attributes are described in FG01.json, and that would be pretty much enough for building the mesh.

Okay, I'm modified my article 
buytheway I cant find FG01.json in Crome
## Post #9
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-03-26T04:14:17+00:00
- Post Title: 3d figure Web model ripping

> Reply from oamio
>
> buytheway I cant find FG01.json in Crome
It's FG01.json.gz in the cache. You get the json after decompression.
