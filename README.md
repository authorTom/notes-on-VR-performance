# Notes on VR Performance
Performance is crucial in VR content creation to prevent user discomfort and motion sickness. However, ensuring smooth operation and reasonable frame rates is often an afterthought. When it comes to VR development, performance should be at the forefront due to the potential for low frame rates, or more accurately frame times, to cause user discomfort. <br />
<br />
Creating performant VR content can be challenging, as PCVR (a high-powered gaming PC) and standalone VR (a low powered headset) require different approaches. In these notes, I focus on optimising for standalone using the Oculus Quest headsets. Different headsets have different requirements, and several factors impact performance, including required minimum frame rates, high resolutions, the need to render each frame twice, power constraints, limited processing power, and the effects of heat and thermal throttling. <br />
<br />
Long build times will hinder productivity. Testing on the standalone headset is essential as mobile hardware has far less power and fewer GPU features than a desktop PC. Although developing for VR introduces unique challenges, many of the tips, tricks, and solutions from the flat game world apply. These notes cover the basics to help get you started. <br />
<br />
# Table of contents

- [When to Optimise?](#when-to-optimise)
- [Frame Rate Vs Frame Time](#frame-rate-vs-frame-time)
- [Profiling](#profiling)
  - [CPU Bound](#cpu-bound)
  - [GPU Bound](#gpu-bound)
- [Tip 1 - Reduce Drawcalls](#tip-1---reduce-drawcalls)
- [Tip 2 - Textures](#tip-2---textures)
- [Tip 3 - Lighting](#tip-3---lighting)
- [Tip 4 - Transparency & Blending](#tip-4---transparency--blending)
- [Tip 5 - Shaders](#tip-5---shaders)
- [Tip 6 - Antialiasing](#tip-6---antialiasing)
- [Tip 7 - Occlusion culling](#tip-7---occlusion-culling)
- [Tip 8 - Fixed Foveated Rendering](#tip-8---fixed-foveated-rendering)
- [Resources](#resources)
- [Issues](#issues)
- [My Other Projects](#my-other-projects)
## When to Optimise?
## Frame Rate Vs Frame Time
* **Frame rate** is the number of frames displayed per second (FPS). It is calculated by dividing the total number of frames displayed by the total amount of time taken to display them. <br />
* **Frame time** is calculated by dividing the total time it takes to render a frame by the number of frames rendered. It is typically measured in milliseconds (ms). <br />
* Let's say a game runs at 60 frames per second (fps), and it takes a total of 16.67 milliseconds to render each frame. This means that the frame time for that game is 16.67 milliseconds / frame. <br />
* Frame time is a better measure of performance than frame rate because it takes into account the consistency of the frame rate. A high frame rate does not necessarily mean that the game will be smooth, if the frame time is inconsistent. For example, a game may have a frame rate of 60fps, but if the frame time varies from 16ms to 33ms, the game will not be smooth. <br />
* Frame time is useful for diagnosing performance issues. If you are experiencing stuttering or other performance problems, you can use frame time to identify the source of the problem. <br />
## Profiling
### CPU Bound
### GPU Bound
## Tip 1 - Reduce Drawcalls
## Tip 2 - Textures
## Tip 3 - Lighting
## Tip 4 - Transparency & Blending
## Tip 5 - Shaders
## Tip 6 - Antialiasing
## Tip 7 - Occlusion culling
## Tip 8 - Fixed Foveated Rendering
## Resources
[➡️ My list of XR performance resources](https://github.com/authorTom/ultimate-XR-dev-guide#performance-and-benchmarking)
## Issues
This project is actively maintained, please raise an issue if you feel the need to. <br />
<br />
**Like what has been done? please give the repository a star ⭐** <br />
## My Other Projects
[➡️ The Ultimate XR Developers Resource Guide](https://github.com/authorTom/ultimate-XR-dev-guide)
