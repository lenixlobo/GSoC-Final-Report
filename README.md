Final Report for Project FURY (GSoC 2020)

<center><a href="https://summerofcode.withgoogle.com/projects/#6653942668197888"><img src="https://developers.google.com/open-source/gsoc/resources/downloads/GSoC-logo-horizontal.svg" alt="gsoc" height="50"/></a></center>

<center>
<a href="https://summerofcode.withgoogle.com/projects/#6653942668197888"><img src="https://www.python.org/static/community_logos/python-logo.png" height="45"/></a>
<a href="https://fury.gl/latest/community.html"><img src="https://python-gsoc.org/logos/FURY.png" alt="fury" height="45"/></a>
</center>

# Google Summer of Code Final Report
* **Student:** Lenix Lobo
* **Mentors:** David Reagan, skoudoro, Javier Guaje
* **Organisation:** Python Software Foundation
* **Sub-Organisation:** FURY
* **Project:** [FURY - Improve Shader Framework](https://github.com/fury-gl/fury/wiki/Google-Summer-of-Code-2020)

## Introduction

The current shader framework for FURY is based on VTK and lacks documentation to get started which can be overwhelming for new users . The objective of this project is to enable users to be easily able to understand and use the shader framework to render stunning visual representations of data. The project involves programming vertex and fragment shaders to generate effects for more immersive visualization.

## Proposed Objectives
* Adding SDF actor to the API

 This actor uses raymarching to model actors using SDF. The method provides several actors including `ellipsoid`, `sphere` and `torus`.
* Shader demos

 Use the FURY shader system to create and visualize different shading algorithms. Implementations include `SphereMap`, `Toon`, `Gooch` and `Vertex Noise`

## Unsubmitted Functionalities
# Spherical Harmonics using Shaders.

The spherical harmonics algorithm is used to generate spherical surfaces using biases and coefficients computed . The general approach to achieve this is computationally expensive. The idea proposed was to leverage the GPU hardware using shaders to provide a faster more efficient alternative to the current implementations. The second month of the coding period was devoted to the same task but unfortunately, the observed performance was quite unsatisfactory than the expected performance. Moreover the output shape of the geometry was distorted. It was then decided to continue the work after the GSoC period and prioritize the task at hand.

The Work in Progress can be accessed here. https://github.com/lenixlobo/fury/tree/Spherical-Harmonics

# Dynamic Texture using Geometry Shader

Geometry Shaders provide a lot of flexibility to users to create custom geometry behaviors such as instancing. The idea was to create a dynamic Fur/Hair effect on top of a FURY actor. Unfortunately due to missing documentation on VTK geometry shaders and lack of resources, the project was not completed during the GSoC period. However, I will continue to try to solve the issue.

The source code for the current progress can be accessed here. https://github.com/lenixlobo/fury/tree/Dynamic-Texture


## Objectives Completed
* ### SDF based Actor

  The objective here was to provide an alternative approach to users to use SDF modeled actors in the scene. This actor is modeled using the raymarching algorithm which provides much better performance than conventional polygon-based actors. Currently, the shapes supported include ellipsoid, sphere and torus

  *Pull Requests:*
  * **SDF Actor method:** https://github.com/fury-gl/fury/pull/250
  * **SDF Actor Tutorial:** https://github.com/fury-gl/fury/pull/267

* ### Multiple SDF Actor

  The objective was to create a method through which multiple SDF primitives are rendered within a single cube. This task helped us explore the limitations of the shader system and also benchmarking the performance.

  *Pull Requests:*
  * **MultiSDF Shader:** https://github.com/fury-gl/fury/blob/master/docs/experimental/viz_multisdf.py

* ### Shader Demos

  The task here was to create a pull request showcasing the capabilities of the FURY shader system and to also provide examples or new users to get started with integrating custom shaders into the scenes.

  *Pull Requests:*
  * **Shader Demos:** https://github.com/fury-gl/fury/pull/296



## Other Objectives
* ### Tutorials

 Create Tutorials for new users to get familiar with the Shader System
 
 *Pull Requests*
 * **Shader UI Tutorial:**
 https://github.com/fury-gl/fury/pull/296
 
 * **SDF Actor Tutorial:**
 https://github.com/fury-gl/fury/pull/267

* ### GSoC weekly Blogs

  Weekly blogs were added for FURY's Website.

  *Pull Requests:*
  * **First & Second Evaluation:** 
  
  https://github.com/fury-gl/fury/pull/250
  https://github.com/fury-gl/fury/pull/267
  * **Third Evaluation:** 
  
  https://github.com/fury-gl/fury/pull/296


## Timeline
| Date                 | Description  | Blog Link          |
|----------------------|--------------|--------------------|
|Week 1<br>(30-05-2020)| Welcome to my GSoC Blog!!|[Weekly Check-in #1](https://blogs.python-gsoc.org/en/lenixlobos-blog/gsoc-blog-week-1/) |
|Week 2<br>(07-06-2020)| Geometry Shaders!|[Weekly Check-in #2](https://blogs.python-gsoc.org/en/lenixlobos-blog/weekly-check-in-week-2/)|
|Week 3<br>(14-06-2020)| Ray Marching!|[Weekly Check-in #3](https://blogs.python-gsoc.org/en/lenixlobos-blog/weekly-check-in-week-3/)|
|Week 4<br>(21-06-2020)| Raymarching continued!|[Weekly Check-in #4](https://blogs.python-gsoc.org/en/lenixlobos-blog/weekly-check-in-week-4/)|
|Week 5<br>(28-06-2020)| Spherical harmonics!|[Weekly Check-in #5](https://blogs.python-gsoc.org/en/lenixlobos-blog/weekly-check-in-week-5/)|
|Week 6<br>(05-07-2020)| Spherical harmonics, Continued!|[Weekly Check-in #6](https://blogs.python-gsoc.org/en/lenixlobos-blog/weekly-check-in-week-6/)|
|Week 7<br>(12-07-2020)| Multiple SDF primitives!|[Weekly Check-in #7](https://blogs.python-gsoc.org/en/lenixlobos-blog/weekly-check-in-week-7/)|
|Week 8<br>(19-07-2020)| Improvements in SDF primitives.|[Weekly Check-in #8](https://blogs.python-gsoc.org/en/lenixlobos-blog/weekly-check-in-week-8/)|
|Week 9<br>(26-07-2020)| Merging SDF Actor and Benchmarks!|[Weekly Check-in #9](https://blogs.python-gsoc.org/en/lenixlobos-blog/weekly-check-in-week-9/)|
|Week 10<br>(02-08-2020)| More shaders.|[Weekly Check-in #10](https://blogs.python-gsoc.org/en/lenixlobos-blog/weekly-check-in-week-10/)|
|Week 11<br>(09-08-2020)| Even More shaders.|[Weekly Check-in #11](https://blogs.python-gsoc.org/en/lenixlobos-blog/weekly-check-in-week-11/)|
|Week 12<br>(16-08-2020)|Picking Outline.|[Weekly Check-in #12](https://blogs.python-gsoc.org/en/lenixlobos-blog/weekly-check-in-week-12/)|
|Week 13<br>(23-08-2020)|Final Week.|[Weekly Check-in #13](https://blogs.python-gsoc.org/en/lenixlobos-blog/weekly-check-in-week-13/)|

Detailed weekly tasks and work done can be found [here](https://blogs.python-gsoc.org/en/lenixlobos-blog/).
