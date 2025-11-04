---
# You can also start simply with 'default'
theme: seriph
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: /sundog.jpg
# some information about your slides (markdown enabled)
title: Seminar II
info: |
  ## Slidev Starter Template
  Presentation slides for developers.

  Learn more at [Sli.dev](https://sli.dev)
# apply unocss classes to the current slide
class: text-center
# https://sli.dev/features/drawing
drawings:
  persist: false
# slide transition: https://sli.dev/guide/animations.html#slide-transitions
transition: slide-left
# enable MDC Syntax: https://sli.dev/features/mdc
mdc: false
pointer: true

slideNumber: true
---

## Radiation Forces and Torque on Dielectric Janus Particles

<div class="mt-4 text-center leading-relaxed">
  <span class="text-xl font-semibold">Mohd Meraj Khan<sup class="text-sm align-super">a</sup></span>,
  <span class="text-xl">Sumesh P. Thampi<sup class="text-sm align-super">b</sup></span>,
  and
  <span class="text-2xl">Anubhab Roy<sup class="text-sm align-super">a</sup></span>
</div>

<div class="mt-5 text-sm leading-tight text-center">
  <sup class="text-sm align-super">a</sup> Department of Applied Mechanics, IIT Madras<br>
  <sup class="text-sm align-super">b</sup> Department of Chemical Engineering, IIT Madras
</div>

<div class="mt-10 flex justify-center items-center">
  <img src="/figures/IITM_Logo.png" alt="IIT Madras logo" class="h-24 w-24 opacity-90">
</div>

<div class="mt-8 text-sm text-center text-gray-600">
  Fluid Mechanics Division, Department of Applied Mechanics and Biomedical Engineering<br>
  Indian Institute of Technology Madras, Chennai, India — 600036
</div>

<div class="abs-br m-2 text-xs text-gray-400 italic">
  Background image: pixabay.com
</div>


<div class="abs-br m-1.5 text-2">
  Background image: https://pixabay.com
</div>

---

## Radiation Force

<v-drag  pos="852,15,94,_">
<figure class="text-center">
  <img src="/figures/rad_force/paramecium.png" alt="Image 2" class="w-full h-auto">
</figure>
</v-drag>

<div class="relative w-full mt-0">

<div class="absolute grid grid-cols-2 gap-15 place-items-center mt-15 ">
  <figure  class="text-center">
    <video autoplay loop muted class="w-full h-auto">
      <source src="/figures/rad_force/Particl_Trapping_Nobel_2018.mp4" type="video/mp4">
      Your browser does not support the video tag.
    </video>
    <figcaption class="text-3 mt-2">
      Trapping of the fat particle of a Paramecium
      <div class="text-2"> A Ashkin and J M Dziedzic (1989)</div>
    </figcaption>
  </figure>
  
  <figure v-click="1" class="text-center">
    <video autoplay loop muted class="w-full h-auto">
      <source src="/figures/rad_force/Particl_Manipulation_Nobel_2018.mp4" type="video/mp4">
      Your browser does not support the video tag.
    </video>
    <figcaption class="text-3 mt-2">
      Manipulation of a diatom
      <div class="text-2"> A Ashkin and J M Dziedzic (1989)</div>
    </figcaption>
  </figure>
</div>

</div>

<div class="abs-br m-2 text-3">
  <SlideCurrentNo />
</div>
---
layout: two-cols
layoutClass: gap-16
---

## Governing Equations

<div h-3 />

<div v-click>
Maxwell's equations in matter
$$
\begin{aligned}
\nabla \cdot \vec{D} &= \rho \\[1.0em]
\nabla \cdot \vec{B} &= 0 \\[1.0em]
\nabla \times \vec{E} &= -\frac{\partial\vec{B}}{\partial t} \\[1.0em]
\nabla \times \vec{H} &= \vec{J} + \frac{\partial\vec{D}}{\partial t}
\end{aligned}
$$
</div>

<div h-5 />

<div v-click>
For linear media
$$
\vec{E} = \frac{\vec{D}}{\varepsilon}  \hspace{10pt} \textcolor{gray}{and} \hspace{10pt} \vec{H} = \frac{\vec{B}}{\mu} 
$$

</div>

::right::

<div v-click class="mt-10">
Boundary conditions at the interface of two media
$$
\begin{aligned}
\hat{n} \cdot ( \vec{D}_{2} - \vec{D}_{1} ) &= \sigma \\[1.0em]
\hat{n} \times ( \vec{E}_{2} - \vec{E}_{1} ) &= 0 \\[1.0em]
\hat{n} \cdot \left( \vec{B}_2 -  \vec{B}_1 \right) &= 0 \\[1.0em]
\hat{n} \times ( \vec{H_2} - \vec{H_1}) &= \vec{K} \\[1.0em]
\end{aligned}
$$

</div>


<div v-click class="mt-0">
Radiation force and torque
</div>


<v-drag pos="533,389,355,_">
<div v-click class="text-3 text-left">
$$
\langle \mathbb{T} \rangle = \frac{1}{2} \Re \left[ \varepsilon_0  {\bf E}  {\bf E}^* + \mu_0 {\bf H}  {\bf H}^*- \frac{1}{2}  \left( \varepsilon_0 |{\bf E}|^2 + \mu_0 |{\bf H}|^2 \right) \mathbb{I} \right]
$$
</div>
</v-drag>

<v-drag pos="527,457,184,_">
<div v-click class="text-3 text-left">
$$
\langle {\bf F} \rangle = \oint \langle \mathbb{T} \rangle \cdot  {\bf \hat{n}} dl
$$
</div>
</v-drag>


<v-drag pos="725,461,184,_">
<div v-click class="text-3 text-left">
$$
\langle {\bf M} \rangle = \oint {\bf r} \times ( \langle \mathbb{T} \rangle \cdot  {\bf \hat{n}} ) dl
$$
</div>
</v-drag>





<div class="abs-br m-2 text-3">
  <SlideCurrentNo />
</div>

---

## Blank slide

---


## Solution Methods

<table class="w-full border-collapse border text-center text-3.5 mt-5">
  <thead>
    <tr class="bg-gray-100">
      <th class="border px-3 py-2 text-center font-bold">Method Category</th>
      <th class="border px-3 py-2 text-center font-bold">Method</th>
      <th class="border px-3 py-2 text-center font-bold">Domain</th>
      <th class="border px-3 py-2 text-center font-bold">Applicable Shapes</th>
      <th class="border px-3 py-2 text-center font-bold">Challenges</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td class="border px-3 py-2" rowspan="2">Series expansion of basis function</td>
      <td class="border px-3 py-2">Mie</td>
      <td class="border px-3 py-2">Frequency domain</td>
      <td class="border px-3 py-2">Sphere, circular cylinder</td>
      <td class="border px-3 py-2"></td>
    </tr>
    <tr>
      <td class="border px-3 py-2">T-matrix</td>
      <td class="border px-3 py-2">''</td>
      <td class="border px-3 py-2">Shapes with symmetries</td>
      <td class="border px-3 py-2"></td>
    </tr>
    <tr>
      <td class="border px-3 py-2" rowspan="2">Solves IE at grids</td>
      <td class="border px-3 py-2">DDA</td>
      <td class="border px-3 py-2">''</td>
      <td class="border px-3 py-2">Arbitrary shape</td>
      <td class="border px-3 py-2">Size parameter 10 <div class="text-2" style="color: red"> Kahnert (2016) </div> </td>
    </tr>
    <tr>
      <td class="border px-3 py-2">MoM</td>
      <td class="border px-3 py-2">''</td>
      <td class="border px-3 py-2">''</td>
      <td class="border px-3 py-2">Low accuracy <div class="text-2" style="color: red"> Mishchenko (2014) </div> </td>
    </tr>
    <tr>
      <td class="border px-3 py-2" rowspan="2">Solves PDE at grids</td>
      <td class="border px-3 py-2">FEM</td>
      <td class="border px-3 py-2">''</td>
      <td class="border px-3 py-2">''</td>
      <td class="border px-3 py-2">Size parameter 10 <div class="text-2" style="color: red"> Mishchenko et. al (2000)  </div> </td>
    </tr>
    <tr>
      <td class="border px-3 py-2">FDTD</td>
      <td class="border px-3 py-2">Time domain</td>
      <td class="border px-3 py-2">''</td>
      <td class="border px-3 py-2">Size parameter 20 <div class="text-2" style="color: red"> Kahnert (2016)  </div> </td>
    </tr>
    <tr>
      <td class="border px-3 py-2" colspan="1">Solves particle populations at grids</td>
      <td class="border px-3 py-2"><span v-mark.circle.red="1">Lattice Boltzmann method</span></td>
      <td class="border px-3 py-2">''</td>
      <td class="border px-3 py-2">''</td>
    </tr>
  </tbody>
</table>

<v-drag pos="765,36,155,_">
<div class="text-3 ">
$$
\text{Size parameter}  = 2 \pi \frac{a}{\lambda}
$$
</div>
</v-drag>

<div class="abs-br m-2 text-3">
  <SlideCurrentNo />
</div>


---
layout: two-cols-header
layoutClass: gap-10
---

## Lattice Boltzmann Method

::left::

<div class="mt-0">
  <img src="/figures/LBM_scale.png" alt="Image 1" class="h-auto">
</div>

::right::

<div v-click="1" class="mt-0 text-3">
Distribution function (Particle population)
$$
f (\vec{x}, \vec{c}, t)
$$
</div>

<div v-click="2" class="mt-0 text-3">
Lattice Boltzmann equation
$$
\begin{aligned}
f_i (\vec{x} + \vec{c}_i \Delta t, t + \Delta t) &= f_i (\vec{x}, t) + \Omega_i (\vec{x}, t) \\[1.0em]
\end{aligned}
$$
</div>

<div v-click="4" class="mt-0 text-3">
$$
\begin{aligned}
\Omega_i (\vec{x}, t) &= - \frac{f_i (\vec{x}, t) - f_i^{eq} (\vec{x}, t)}{\tau} \Delta t \\[1.0em]
\end{aligned}
$$
</div>

<div v-click="5" class="mt-0 text-3">
$$
\begin{aligned}
f_i (\vec{x} + \vec{c}_i \Delta t, t + \Delta t) &= \left( 1 - \frac{\Delta t}{\tau} \right) f_i (\vec{x}, t) + \frac{\Delta t}{\tau} f_i^{eq} (\vec{x}, t)  \\[1.0em]
\end{aligned}
$$
</div>

<div v-click="6" class="mt-0 text-3">
Macroscopic quantity
$$
\Sigma_{i} f_i (\vec{x}, t)
$$
</div>

<v-drag v-click="3" pos="824,165,117,_">
  <div text-center text-3 border border-main rounded>
    Collision operator
  </div>
</v-drag>

<v-drag-arrow v-click="3" pos="854,189,-34,31" op70 />

<v-drag v-click="4"  pos="647,337,164,_">
  <div v-click.hide="5" text-center text-3 border border-main rounded>
    BGK collision operator
  </div>
</v-drag>

<div class="abs-bl m-2 text-2">
  Timm Kruger (2017)
</div>

<div class="abs-br m-2 text-3">
  <SlideCurrentNo />
</div>

---
layout: two-cols-header
---

## Plane Wave Scattering from Metallo-dielectric Janus cylinder



::left::

<figure class="text-center item-center my-5">
  <img src="/figures/Janus/JanusHalf_schematic.png" alt="Image 1" class="w-3/4 h-auto">
</figure>

::right::





<v-drag pos="527,121,55,_">
<div v-click="1"  class="text-3 text-left">
$$
\varepsilon_{r_1} = 1
$$
</div>
</v-drag>

<v-drag pos="430,150,241,_">
<div v-click="1" class="mt-3">
  <figure class="text-center">
    <img src="/figures/Janus/RCS_1.svg" alt="Image 1" class="w-auto h-auto">
  </figure>
</div>
</v-drag>

<v-drag pos="813,126,55,_">
<div v-click="1"  class="text-3 text-left">
$$
\varepsilon_{r_1} = 2
$$
</div>
</v-drag>

<v-drag pos="719,148,225,_">
<div v-click="1" class="mt-3">
  <figure class="text-center">
    <img src="/figures/Janus/RCS_2.svg" alt="Image 1" class="w-auto h-auto">
  </figure>
</div>
</v-drag>

<v-drag pos="796,365,55,_">
<div v-click="1"  class="text-3 text-left">
$$
\varepsilon_{r_1} = 5
$$
</div>
</v-drag>


<v-drag pos="575,319,224,_">
<div v-click="1" class="mt-3">
  <figure class="text-center">
    <img src="/figures/Janus/RCS_5.svg" alt="Image 1" class="w-auto h-auto">
  </figure>
</div>
</v-drag>

<v-drag v-click="1" pos="451,498,168,_">
  <div text-center text-3 border border-main rounded>
    Hurd and Sachdeva (1975)
  </div>
</v-drag>


<v-drag pos="825,74,128,_">
<div class="text-3 text-left">
$$
\begin{aligned}
\sigma = \lim_{r \to \infty} 2 \pi r \frac{|\vec{E}^S|^2}{|\vec{E}^I|^2}
\end{aligned}
$$
</div>
</v-drag>


<div class="abs-br m-2 text-3">
  <SlideCurrentNo />
</div>

---

## Radiation Forces and Torques on a Metallo-dielectric Janus Cylinder


<div v-click="1" class="grid grid-cols-3 gap-25 mt-2">
  <figure class="text-center">
    <img src="/figures/Fx_LBM_Hurd.svg" alt="Image 1" class="w-full h-auto">
  </figure>
  
  <figure class="text-center">
    <img src="/figures/Fy_LBM_Hurd.svg" alt="Image 2" class="w-full h-auto">
  </figure>
  
  <figure class="text-center">
    <img src="/figures/Tz_LBM_Hurd.svg" alt="Image 3" class="w-full h-auto">
  </figure>
</div>

<div v-click="2" class="grid grid-cols-3 gap-25 mt-2">
  <figure class="text-center">
    <img src="/figures/Fx_Hurd_Per_Err.svg" alt="Image 1" class="w-full h-auto">
  </figure>
  
  <figure class="text-center">
    <img src="/figures/Fy_Hurd_Per_Err.svg" alt="Image 2" class="w-full h-auto">
  </figure>
  
  <figure class="text-center">
    <img src="/figures/Tz_Hurd_Per_Err.svg" alt="Image 3" class="w-full h-auto">
  </figure>
</div>

<v-drag pos="870,9,94,_">
<figure class="text-center">
  <img src="/figures/Janus_PEC.png" alt="Image 2" class="w-full h-auto">
</figure>
</v-drag>

<div class="abs-br m-2 text-3">
  <SlideCurrentNo />
</div>

---

## Radiation Forces and Torques on a Dielectric Janus Cylinder


<!-- Row 1 -->
<div v-click="1" class="grid grid-cols-3 gap-25 mt-2">
  <figure class="text-center">
    <img src="/figures/Fx_Janus_er_1.svg" alt="Fx er1" class="w-full h-auto" />
  </figure>
  <figure class="text-center">
    <img src="/figures/Fx_Janus_er_2.svg" alt="Fx er2" class="w-full h-auto" />
  </figure>
  <figure class="text-center">
    <img src="/figures/Fx_Janus_er_5.svg" alt="Fx er5" class="w-full h-auto" />
  </figure>
</div>

<!-- Row 2 -->
<div v-click="2" class="grid grid-cols-3 gap-25 mt-4">
  <figure class="text-center">
    <img src="/figures/Fy_Janus_er_1.svg" alt="Fy er1" class="w-full h-auto" />
  </figure>
  <figure class="text-center">
    <img src="/figures/Fy_Janus_er_2.svg" alt="Fy er2" class="w-full h-auto" />
  </figure>
  <figure class="text-center">
    <img src="/figures/Fy_Janus_er_5.svg" alt="Fy er5" class="w-full h-auto" />
  </figure>
</div>

<!-- Row 3 (overlay row, shown on click 3) -->
<div
  v-click="3"
  class="absolute inset-0 flex justify-center items-center pointer-events-none"
>
  <div
    class="grid grid-cols-3 gap-10 p-1 bg-white/70 backdrop-blur-md rounded-xl shadow-2xl ring-1 ring-black/10"
    style="transform: translateY(-10%);"
  >
    <figure class="text-center">
      <img src="/figures/Tz_Janus_er_1.svg" alt="Fz er1" class="w-48 h-auto drop-shadow-lg" />
    </figure>
    <figure class="text-center">
      <img src="/figures/Tz_Janus_er_2.svg" alt="Fz er2" class="w-48 h-auto drop-shadow-lg" />
    </figure>
    <figure class="text-center">
      <img src="/figures/Tz_Janus_er_5.svg" alt="Fz er5" class="w-48 h-auto drop-shadow-lg" />
    </figure>
  </div>
</div>


<v-drag pos="880,-3,94,_" class="presentation:!border-none presentation:!outline-none">
  <figure class="text-center">
    <img src="/figures/Janus_dielectric.png" class="w-full h-auto" />
  </figure>
</v-drag>



<div class="abs-br m-2 text-3">
  <SlideCurrentNo />
</div>

---

## Trajectories of Janus cylinder

<!-- <div v-click="1" class="text-center mt-5">
Scattering of electromagnetic waves in nature
</div> -->

<div v-click="1" class="grid grid-cols-3 gap-15 mt-10">
  <figure class="text-center">
    <img src="/figures/MDJC_Trajectory_er_1.svg" alt="Image 1" class="w-full h-auto">
  </figure>
  
  <figure class="text-center">
    <img src="/figures/MDJC_Trajectory_er_3.svg" alt="Image 2" class="w-full h-auto">
  </figure>
  
  <figure class="text-center">
    <img src="/figures/MDJC_Trajectory_er_5.svg" alt="Image 3" class="w-full h-auto">
  </figure>
</div>

<div v-click="2" class="grid grid-cols-3 gap-15 mt-15">
  <figure class="text-center">
    <img src="/figures/DJC_Trajectory_er_1_er2byer1_2.svg" alt="Image 1" class="w-full h-auto">
  </figure>
  
  <figure class="text-center">
    <img src="/figures/DJC_Trajectory_er_1_er2byer1_3.svg" alt="Image 2" class="w-full h-auto">
  </figure>
  
  <figure class="text-center">
    <img src="/figures/DJC_Trajectory_er_1_er2byer1_5.svg" alt="Image 3" class="w-full h-auto">
  </figure>
</div>

<div class="abs-br m-2 text-3">
  <SlideCurrentNo />
</div>

---

## Trajectories of Janus cylinder

<div v-click="1" class="grid grid-cols-3 gap-15 mt-10">
  <figure class="text-center">
    <img src="/figures/DJC_Trajectory_er_2_er2byer1_2.svg" alt="Image 1" class="w-full h-auto">
  </figure>
  
  <figure class="text-center">
    <img src="/figures/DJC_Trajectory_er_2_er2byer1_3.svg" alt="Image 2" class="w-full h-auto">
  </figure>
  
  <figure class="text-center">
    <img src="/figures/DJC_Trajectory_er_2_er2byer1_5.svg" alt="Image 3" class="w-full h-auto">
  </figure>
</div>

<div v-click="2" class="grid grid-cols-3 gap-15 mt-15">
  <figure class="text-center">
    <img src="/figures/DJC_Trajectory_er_5_er2byer1_2.svg" alt="Image 1" class="w-full h-auto">
  </figure>
  
  <figure class="text-center">
    <img src="/figures/DJC_Trajectory_er_5_er2byer1_3.svg" alt="Image 2" class="w-full h-auto">
  </figure>
  
  <figure class="text-center">
    <img src="/figures/DJC_Trajectory_er_5_er2byer1_5.svg" alt="Image 3" class="w-full h-auto">
  </figure>
</div>

<div class="abs-br m-2 text-3">
  <SlideCurrentNo />
</div>

---




## Trajectories of Janus cylinder

<div class="grid grid-cols-2 gap-4 mt-6">
  <video src="/figures/Janus_Trajectories_MDJC_er1_1.mp4" autoplay loop muted playsinline controls class="w-full h-auto rounded-lg shadow"></video>
  <video src="/figures/Janus_Trajectories_DJC_er1_1_er2byer1_3.mp4" autoplay loop muted playsinline controls class="w-full h-auto rounded-lg shadow"></video>
  <video src="/figures/Janus_Trajectories_DJC_er1_2_er2byer1_3.mp4" autoplay loop muted playsinline controls class="w-full h-auto rounded-lg shadow"></video>
  <video src="/figures/Janus_Trajectories_DJC_er1_5_er2byer1_3.mp4" autoplay loop muted playsinline controls class="w-full h-auto rounded-lg shadow"></video>
</div>

---
layout: center
class: text-center
---

## Thank you!
