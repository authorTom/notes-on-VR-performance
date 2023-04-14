# Notes on VR Performance
Performance is crucial in VR content creation to prevent user discomfort and motion sickness. However, ensuring smooth operation and reasonable frame rates is often an afterthought. When it comes to VR development, performance should be at the forefront due to the potential for low frame rates, or more accurately frame times, to cause user discomfort. <br />
<br />
Creating performant VR content can be challenging, as PCVR (high-powered gaming PC) and standalone VR (low powered headset) require different approaches. In these notes, I focus on optimising for standalone using the Oculus Quest headsets. Different headsets have different requirements, and several factors impact performance, including required minimum frame rates, high resolutions, the need to render each frame twice, power constraints, limited processing power, and the effects of heat and thermal throttling. <br />
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
* Optimise from the beginning!
* Be performance conscious during development - think about scene complexity, do I need to add this in? is it worth the performance hit?
* A good time to optimise is when you are not hitting the desired frame rate.
* Some features look amazing, but are they worth it?
* VR is very performance limited  
## Frame Rate Vs Frame Time
* **Frame rate** is the number of frames displayed per second (FPS). It is calculated by dividing the total number of frames displayed by the total amount of time taken to display them. <br />
* **Frame time** is calculated by dividing the total time it takes to render a frame by the number of frames rendered. It is typically measured in milliseconds (ms). <br />
* Let's say a game runs at 60 frames per second (fps), taking 16.67 milliseconds to render each frame.  The frame time is 16.67 milliseconds per frame. This is also known as the frame budget. Here we have a frame budget of 16.67 ms for both the CPU and GPU. It's super easy to spend your frame budget on a standalone headset (start thinking of other variables like thermal throttling). <br />
   <br />
   | Frame Rate (FPS) | Frame Time (ms) |
   |------------------|-----------------|
   |30|33.3|
   |60|16.67|
   |90|8.3|
* Frame time is a better measure of performance than frame rate because it takes into account the consistency of the frame rate. A high frame rate does not necessarily mean that the game will be smooth, if the frame time is inconsistent. For example, a game may have a frame rate of 60fps, but if the frame time varies from 16ms to 33ms, the game will not be smooth. <br />
* Frame time is useful for diagnosing performance issues. If you are experiencing stuttering or other performance problems, you can use frame time to identify the source of the problem. <br />
* Headsets have different required frame rates. When the frame rates drop, it's likely to cause disorientation and nausea for the user. Maintaining a minimum frame rate (reducing frame times) can be particularly challenging on a standalone headset. <br />
  <br />
  | Headset | Frame Rate |
  |---------|--------------------------------|
  |HTC Vive|90|
  |Quest 1 |72|
  |Quest 2 |120|
  |Quest Pro|90|
  |Valve Index|upto 144|
## Profiling
* Profiling tools can help identify where a game or application is experiencing slow performance by highlighting the frame times that are taking longer to render. There are a variety of profiling solutions available to choose from. Personally, as someone who develops using Unreal Engine (UE) with a Quest headset, I prefer to use RenderDoc and UE's built-in performance suite, Unreal Insights. <br />
* Profiling performance reveals many reasons for increased frame times, which can be classified into two categories: CPU-bound or GPU-bound. <br />
   ### Profiling Tools (lots of options - but can be dependent on headset and graphic chipset)
   [🆓⚒️ Oculus Debug Tool](https://developer.oculus.com/documentation/native/pc/dg-debug-tool/?locale=en_GB) <br />
   [🆓⚒️ RenderDoc](https://renderdoc.org/) <br />
   [🆓⚒️ OVR Metrics Tools](https://developer.oculus.com/downloads/package/ovr-metrics-tool/) <br />
   [🆓⚒️ Android GPU Inspector (AGI) - for Android based HMDs](https://developer.android.com/agi) <br />
   [🆓⚒️ ARM: Streamline Performance Analyzer](https://developer.arm.com/Tools%20and%20Software/Streamline%20Performance%20Analyzer) <br />
   [🆓⚒️ SteamVR Frame Timing](https://developer.valvesoftware.com/wiki/SteamVR/Frame_Timing) <br />
   [🆓⚒️ NVIDIA Visual Profiler](https://developer.nvidia.com/nvidia-visual-profiler) <br />
   [🆓⚒️ NVIDIA Nsight Graphics](https://developer.nvidia.com/nsight-graphics) <br />
   [🆓⚒️ NVIDIA VR Capture & Replay - Early Access](https://developer.nvidia.com/vcr-early-access) <br />
   [🆓⚒️ NVIDIA Performance Analysis Tools](https://developer.nvidia.com/performance-analysis-tools) <br />
   [🆓⚒️ AMD Radeon GPU Profiler](https://gpuopen.com/rgp/) <br />
   [🆓⚒️ Intel® Graphics Performance Analyzers:](https://www.intel.com/content/www/us/en/developer/tools/graphics-performance-analyzers/overview.html) <br />
   [🆓⚒️ Intel® VTune™ Profiler](https://www.intel.com/content/www/us/en/developer/tools/oneapi/vtune-profiler.html#gs.qs0mup) <br />
   [🆓⚒️ PVRTune](https://developer.imaginationtech.com/pvrtune/) <br />
   [⚒️ Superluminal](https://superluminal.eu/) <br />

⭐ [See my resourses on performance](https://github.com/authorTom/ultimate-XR-dev-guide/blob/main/README.md#performance-and-benchmarking)
<br />
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
