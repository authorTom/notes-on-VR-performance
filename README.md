# Notes on VR Performance
Performance is crucial in VR content creation to prevent user discomfort and motion sickness. However, ensuring smooth operation and reasonable frame rates is often an afterthought. When it comes to VR development, performance should be at the forefront due to the potential for low frame rates, or more accurately frame times, to cause user discomfort. <br />
<br />
Creating performant VR content can be challenging, as PCVR (a high-powered gaming PC) and standalone VR (a low powered headset) require different approaches. In these notes, I focus on optimising for standalone using the Oculus Quest headsets. Different headsets have different requirements, and several factors impact performance, including required minimum frame rates, high resolutions, the need to render each frame twice, power constraints, limited processing power, and the effects of heat and thermal throttling. <br />
<br />
Long build times will hinder productivity. Testing on the standalone headset is essential as mobile hardware has far less power and fewer GPU features than a desktop PC. Although developing for VR introduces unique challenges, many of the tips, tricks, and solutions from the flat game world apply. These notes cover the basics to help get you started. <br />
<br />
# Table of contents

- [When to Optimise?](#when-to-optimise)
- [Frame Rate Vs Frame Time Vs Frame Budget](#frame-rate-vs-frame-time-vs-frame-budget)
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
## Frame Rate Vs Frame Time Vs Frame Budget
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
