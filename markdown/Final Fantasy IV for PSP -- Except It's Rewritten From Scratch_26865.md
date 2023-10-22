## Post #1
- Username: travistrue
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Mar 23, 2020 6:14 am
- Post datetime: 2023-06-15T18:33:00+00:00
- Post Title: Final Fantasy IV for PSP -- Except It's Rewritten From Scratch

I've been wanting to make my own top-level, random-battle RPG for years now, but I didn't have the necessary assets. I was inspired by FF4 because its game loop seemed simple, yet fun. I've also wanted to learn more about how people figure out already-compiled games, and make mods for them. Then, I realized that maybe I could achieve a bit of both those goals by combining them together. Maybe I could figure out how to scrape assets from a version of FF4, and then write my own game "engine" logic around it. I could also learn Rust while I'm at it because it's been an interesting language that I've wanted to get more experience with.

Then, the pandemic came back in 2020, and I suddenly had the free time to work on this project. I started it with a friend, and we worked on it throughout April, 2020. It was a lot of fun, and I learned quite a bit about Rust and FF4. We both dropped off of that project a few weeks into it when work started to pick up for us, but I've recently started back up. I don't get to stretch my software engineering skills at my current job like I used at my previous job, so I needed a creative outlet.

I've been writing an unarchiver for the PSP version of FF4, so that I can write my own clone of the game using its assets. The unarchiver's going pretty well so far, and the tool can do the following:
- Extracts the necessary files from the ISO (mainly PAC0.BIN, PAC1.BIN, and the EBOOT.PBP executable)
- Extracts all of the files from PAC1.BIN (they're mostly .lzs files)
- Decompress/extract all files from each .lzs files encountered (there are 3 files that throw an error, but not a bad bug)
- Decompresses all .TM2 texture files

The "game" portion of the project doesn't do much yet... It just loads up a .cn2 map file, and the associated TM2 image files for it. I've got both layers of the maps rendering, and the animated tiles work too. My friend also wrote a decoder for .AT3 files in Rust, so the game logic can easily load and play those audio files.

I initially wrote a little graphics wrapper on top of OpenGL to render the graphics when I started this project 3 years ago. The project started up and rendered just fine on an old Linux installation that I had back in 2020, but it doesn't work correctly on my current installation. In fact, my drivers are old, and not very well supported on my old PC computer (I'm still rocking on a GTX 770 from 10 years ago lol). I also have Windows 10 on my PC, but I don't like developing with PowerShell, and trying to use WSL with graphics apps can be painful to set up and maintain.

This leaves me with macOS... I work off of a MacBook Pro as my primary computer, and it's easy to maintain. I don't have to worry about graphics drivers falling out-of-date, running out of partition space, etc. The only problem is that Apple deprecated OpenGL a few years ago, and I wasn't able to get my project's OpenGL context to find the proper GL driver functions.

All of the compatibility issues between the current hardware that I had available to me vs software support and maintenance almost turned me off of this project. I thought about learning one of the newer graphics APIs as it was something else that I was excited to jump into, but that could easily end up being a rabbit hole where I spend months learning the graphics APIs instead of making a game. Plus, there's quite a bit of platform division between DX12, Vulkan, and Metal DX12 is Windows-proprietary, Metal is Apple-proprietary, and Vulkan doesn't have a lot of direct support outside of Linux, which I wanted to avoid until I have newer hardware. Vulkan's the most portable (and the API that I was the most interested in learning), but it's emulated with limited support on macOS, so ehh...

Then, I started to see the support for WebGPU. WebGPU's still in its infancy, and I don't think it's even got a release out yet, but I did find a set of tutorials that taught me quite a bit about how WebGPU works. I ended up picking up WebGPU, and it's been great so far. I'm glad to see that my OpenGL knowledge transferred over nicely too, so it was easier to grasp a lot of those concepts.

Here's a high-level development roadmap of what I'd like to accomplish during this project:
- Fully support TM2 files within the context of FF4 (there are still bugs in my image loader)
- Load the various definitions from the ISO assets:
  - Character stats/level up table
  - Items and equipment stats/modifiers
  - Monster definitions
  - Battle arrangement definitions
  - Shop definitions
  - Dialog
  - Cut-scene information
  - Write a PMF decoder in Rust so I can play those videos
- Write an "installer" pipeline that'll take those extracted assets, and transform them into cleaner, portable, and easier-to-manage assets like PNGs for images and JSON (or Rust's own "RON" format) for definitions files
- Documentation
  - Write up docs on the various file formats contained in the ISO
  - Write up docs for the formats of the transformed files used by the game for modding purposes
- Gameplay logic
- STRETCH GOAL: Write an archiver that'll allow users to change those pipeline-generated files, and then re-pack them into a new ISO similar to what the [FF6Tools](https://github.com/everything8215/ff6tools) allows you to do with the NES/SNES/GBA versions of FF1-FF6.
- OTHER POSSIBLE STRETCH GOAL: Get the Rust project to compile for the PSP. The audio and FMVs are already in the PSP's proprietary format, and I plan on writing a PMF library in Rust, so it's portable. The graphics engine is spaghetti code, but I have ideas on how to clean that up better. I might opt to use an ECS engine like Bevy for game logic too. Anyway, once the game's done, I might be able to get the Rust project to compile on PSP hardware without too issue.

tl;dr: I'm currently working on writing my own open source port of the PSP version of FF4 written in Rust. You just provide an ISO to the CLI tool, and it'll extract everything. It also uses WebGPU for a renderer, so it might not be too much effort to support WASM for browser support either.

For those who are interested, here's the [link](http://github.com/travistrue2008/rs-ff4) to my GitHub project.
