---
# You can also start simply with 'default'
theme: seriph
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: /comet_tail.jpg
# some information about your slides (markdown enabled)
title: DFD 25
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

# Radiation Forces and Torque on Dielectric Janus Particles

<div class="mt-4 text-center leading-relaxed">
  <span class="text-l font-semibold">Mohd Meraj Khan<sup>a</sup></span>,
  <span class="text-l">Sumesh P. Thampi<sup>b</sup></span>
  and
  <span class="text-l">Anubhab Roy<sup>a</sup></span>
</div>


<div class="mt-5 text-3.5 leading-tight text-center">
  <sup class="text-3.5 align-super">a</sup> Department of Applied Mechanics<br>
  <sup class="text-3.5 align-super">b</sup> Department of Chemical Engineering
</div>



<div class="text-l leading-tight text-center mt-5 mb-5">
  78th APS Division of Fluid Dynamics
</div>




<div class="my-10 flex justify-center items-center">
  <img src="/figures/IITM_Logo.png" alt="IIT Madras logo" class="h-24 w-24 opacity-90">
</div>

<div class="mt-4 text-4 text-center ">
  Indian Institute of Technology Madras, Chennai, India
</div>

<!--
<div class="mt-4 text-sm text-center ">
  Fluid Mechanics Division, Department of Applied Mechanics and Biomedical Engineering<br>
  Indian Institute of Technology Madras, Chennai, India — 600036
</div>
-->




<div class="abs-br m-1.5 text-2">
  Background image: astronomy.swin.edu.au
</div>

---
layout: default
---

# Radiation Force and its Applications

<div class="grid grid-cols-2 gap-6 mt-2 items-start">

  <!-- Comet tail -->
  <figure class="flex flex-col items-center">
    <img src="/figures/comet_tail.jpg" class="w-[75%] h-auto rounded shadow" />
    <figcaption class="text-3 mt-3 leading-tight text-center">
      Comet tail (radiation forces in nature)
      <div class="text-2 opacity-70 mt-1">(Source: astronomy.swin.edu.au)</div>
    </figcaption>
  </figure>

  <!-- Optical trapping video -->
  <figure v-click="1" class="flex flex-col items-center">
    <video autoplay loop muted playsinline class="w-[75%] h-auto rounded shadow">
      <source src="/figures/Particl_Trapping_Nobel_2018.mp4" type="video/mp4" />
    </video>
    <figcaption class="text-3 mt-3 leading-tight text-center">
      Optical trapping using radiation forces
      <div class="text-2 opacity-70 mt-1">Ashkin & Dziedzic (1989)</div>
    </figcaption>
  </figure>

</div>


<div class="grid grid-cols-2 gap-6 mt-2 items-start">

  <!-- Particle manipulation video -->
  <figure v-click="2" class="flex flex-col items-center">
    <video autoplay loop muted playsinline class="w-[75%] h-auto rounded shadow">
      <source src="/figures/Particl_Manipulation_Nobel_2018.mp4" type="video/mp4" />
    </video>
    <figcaption class="text-3 mt-3 leading-tight text-center">
      Radiation forces enabling particle manipulation
      <div class="text-2 opacity-70 mt-1">Ashkin & Dziedzic (1989)</div>
    </figcaption>
  </figure>

  <!-- Dust storm -->
<div v-click="3"class="absolute bottom-12 right-12 w-80 text-3.75 leading-relaxed text-left">

  <ul class="list-disc ml--15 space-y-2 text-left">
    <li>Radiation pressure shapes comet tails</li>
    <li>Enables optical trapping & manipulation</li>
    <li>Foundation of optical tweezers</li>
    <li>Drives micro/nano-particle transport & self-assembly</li>
    <li>Applications in targeted drug delivery</li>
  </ul>

</div>



</div>


<div class="abs-br m-2 text-3">
  <SlideCurrentNo />
</div>

---

# Why Janus Particles?

<div class="grid grid-cols-2 gap-16 mt-12 items-center">

  <!-- Homogeneous cylinder -->
  <div class="flex flex-col items-center">
    <figure class="text-center">
      <img src="/figures/homo_cylinder.png" class="w-80 h-auto" />
    </figure>
    <p class="text-xl mt-4 opacity-80">
      Symmetric scattering from a<br>
      homogeneous dielectric cylinder
    </p>
  </div>

  <!-- Janus cylinder -->
  <div class="flex flex-col items-center">
    <figure class="text-center">
      <img src="/figures/janus_cylinder.png" class="w-80 h-auto" />
    </figure>
    <p class="text-xl mt-4 opacity-80">
      Asymmetric scattering due to<br>
      refractive-index contrast (Janus)
    </p>
  </div>

</div>



---

# Maxwell–LBM Computational Framework

<div class="grid grid-cols-2 gap-6 mt-4">

  <!-- Left Column -->
<div class="pl-0">

<div class="text-4" >
<p class="text-lg mb-3">Maxwell's equations</p>

$$
\begin{alignedat}{3}
\nabla \cdot \mathbf{D} &= \rho 
&\quad\quad &
\nabla \times \mathbf{E} &= -\frac{\partial \mathbf{B}}{\partial t} \\[1.2em]
\nabla \cdot \mathbf{B} &= 0
&\quad\quad &
\nabla \times \mathbf{H} &= \mathbf{J} + \frac{\partial \mathbf{D}}{\partial t}
\end{alignedat}
$$
</div>

<div v-click='1' class="text-4" >
<p class="mt-4 ">For linear media</p>
$$
\mathbf{D} = \varepsilon \mathbf{E}, \quad \mathbf{B} = \mu \mathbf{H}
$$
</div>

<div v-click='2' class="text-4" >
<p class="mt-4 ">Boundary conditions at the interface of two media</p>
$$
\begin{array}{cc}
\begin{aligned}
\hat{n} \cdot (\mathbf{D}_{2} - \mathbf{D}_{1}) &= \sigma \\[1.2em]
\hat{n} \times (\mathbf{E}_{2} - \mathbf{E}_{1}) &= 0
\end{aligned}
&
\begin{aligned}
\hat{n} \cdot (\mathbf{B}_{2} - \mathbf{B}_{1}) &= 0 \\[1.2em]
\hat{n} \times (\mathbf{H}_{2} - \mathbf{H}_{1}) &= \mathbf{K}
\end{aligned}
\end{array}
$$
</div>
</div>


<div class="pl-0">
  <!-- Right Column -->


<div v-click='3'>
<p class="text-lg mb-3">Lattice Boltzmann method</p>


<div class="relative w-full mt-0">

<div v-click='3' v-click.hide='7' absolute inset-0 >
<div >
<div class="flex justify-between items-center text-3.5 mt-2">
  <div class="text-center mr-15 ml-10">
    Post collision
  </div>
  <div class="text-center ml-15 mr-15">
    Pre collision
  </div>
</div>

<figure v-click='3' class="text-center item-center my-1">
  <img src="/figures/LBM_Kruger.png" alt="Image 1" class="h-auto">
</figure>



<div class="flex justify-between items-center text-2.75 mt--5">
<div v-click='4' class="text-center mx-0">
$$
f_i^* (\mathbf{x}, t) = f_i (\mathbf{x}, t) + \frac{\Delta t}{\tau} \left[f_i^{eq} (\mathbf{x}, t) - f_i (\mathbf{x}, t) \right]
$$
</div>
<div v-click='5' class="text-center mx-5">
$$
f_i (\mathbf{x} + \mathbf{c}_i \Delta t, t + \Delta t) = f_i^* (\mathbf{x}, t)
$$
</div>
</div>



<div v-click='6' class="text-3 text-left mt--2">
$$
{\bf e}_i^{eq} ({\bf r} ,t) = 
    \begin{cases}
      \frac{1}{6}\Big(\mathbf{E} ({\bf r} ,t) -   {\bf c}_i \times \mathbf{H} ({\bf r} ,t) \Big) & \text{if $i \neq 0$}\\
      (\varepsilon_{r} - 1 ) \mathbf{E} ({\bf r} ,t) & \text{if $i = 0$}
    \end{cases},  \\
    {\bf h}_i^{eq} ({\bf r} ,t) = 
    \begin{cases}
      \frac{1}{6}\Big(\mathbf{H} ({\bf r} ,t) +  {\bf c}_i \times \mathbf{E} ({\bf r} ,t) \Big) & \text{if $i \neq 0$}\\
      (\mu_{r} - 1 ) \mathbf{H} ({\bf r} ,t) & \text{if $i = 0$}
    \end{cases},  
$$
</div>



</div>
</div>


<div v-click="7" absolute inset-0  >
<figure class="text-center item-center">
  <video autoplay loop muted class="w-11/12 h-auto">
    <source src="/figures/lattice_boltzmann.mp4" type="video/mp4">
    Your browser does not support the video tag.
  </video>
</figure>
</div>

</div>


</div>



<div class="flex justify-between items-center text-3.5 mt-2 abs-br mr-5 ">
  <div v-click='3' class="m-2 text-2">
    Timm Kruger (2017)
  </div>
  <div v-click='6' class="m-2 text-2">
    Hauser and Verhey (2017)
  </div>
</div>




</div>





<div class="abs-br m-2 text-3">
  <SlideCurrentNo />
</div>

</div>

---
layout: two-cols-header
---

# Validation: PEC–Dielectric Benchmark

Scattering width validation

::left::

<figure class="text-center item-center my-5">
  <img src="/figures/Janus_Half_schematic.svg" alt="Image 1" class="w-3/4 h-auto">
</figure>

::right::



<v-drag pos="439,110,471,_">
<div v-click="1" class="mt-3 text-3.5">
$$
E_z^I (r, \phi) = \sum_{m = 0}^{\infty} \alpha_m (-j)^m J_m (k_0 r) \cos{ { m ( \phi - \phi_0) } }
$$
</div>
</v-drag>



<v-drag pos="446,238,500,_">
<div v-click="1" class="mt-3 text-3.5">
$$
E_z^S (r, \phi) = \sum_{m = 0}^{\infty} \left[ B_m \cos{(m \phi)} + D_m \sin{(m \phi)} \right] H_m^{(1)} (k_0 r)
$$
</div>
</v-drag>


<v-drag pos="567,177,219,_">
<div v-click="1"  class="text-3 text-left">
$$
\alpha_m =
\begin{cases}
1, & \text{if } m = 0, \\
2, & \text{otherwise.}
\end{cases}
$$
</div>
</v-drag>

<v-drag pos="504,390,55,_">
<div v-click="2"  class="text-3 text-left">
$$
\varepsilon_{r_1} = 5
$$
</div>
</v-drag>



<v-drag pos="603,346,237,_">
<div v-click="2" class="mt-3">
  <figure class="text-center">
    <img src="/figures/RCS_5.svg" alt="Image 1" class="w-auto h-auto">
  </figure>
</div>
</v-drag>

<v-drag v-click="1" pos="791,90,168,_">
  <div text-center text-3 border border-main rounded>
    Hurd and Sachdeva (1975)
  </div>
</v-drag>


<v-drag pos="665,494,157,_">
<div v-click="2"  class="text-3 text-left">
$$
\theta = \text{scattering angle}
$$
</div>
</v-drag>


<v-drag pos="470,475,157,_">
<div v-click="2"  class="text-3 text-left">
$$
\sigma = \lim_{r \to \infty} 2 \pi r \frac{|\mathbf{E}^S|^2}{|\mathbf{E}^I|^2}
$$
</div>
</v-drag>


<div class="abs-br m-2 text-3">
  <SlideCurrentNo />
</div>

---

# Validation: PEC–Dielectric Benchmark

Radiation force and torque validation



<div class="grid grid-cols-3 gap-0 mt-5 ml-15">
  <figure class="text-center">
    <img src="/figures/Fx_LBM_Hurd.svg" alt="Image 1" class="w-7/8 h-auto">
  </figure>
  
  <figure class="text-center">
    <img src="/figures/Fy_LBM_Hurd.svg" alt="Image 2" class="w-7/8 h-auto">
  </figure>
  
  <figure class="text-center">
    <img src="/figures/Tz_LBM_Hurd.svg" alt="Image 3" class="w-7/8 h-auto">
  </figure>
</div>



<div v-click="1" class="text-center text-4 mb-0 mt-0">
  Percentage error
</div>

<div v-click="1" class="grid grid-cols-3 gap-0 mt-0 ml-15">
  <figure class="text-center">
    <img src="/figures/Fx_Hurd_Per_Err.svg" alt="Image 1" class="w-7/8 h-auto">
  </figure>
  
  <figure class="text-center">
    <img src="/figures/Fy_Hurd_Per_Err.svg" alt="Image 2" class="w-7/8 h-auto">
  </figure>
  
  <figure class="text-center">
    <img src="/figures/Tz_Hurd_Per_Err.svg" alt="Image 3" class="w-7/8 h-auto">
  </figure>
  
</div>

<v-drag pos="-23,233,163,_">
<figure class="text-center">
  <img src="/figures/Janus_schematic_PEC.svg" alt="Image 2" class="w-full h-auto">
</figure>
</v-drag>



<v-drag pos="755,43,195,_">
<div class="text-3 text-left">
$$
F_0 = \frac{\pi}{2 c} I a \quad M_0 = 2 F_0 a
$$
</div>
</v-drag>





<v-drag pos="221,97,53,_">
<div class="text-3 text-left">
$$
\langle \vec{F}_x \rangle
$$
</div>
</v-drag>

<v-drag pos="487,94,53,_">
<div class="text-3 text-left">
$$
\langle \vec{F}_y \rangle
$$
</div>
</v-drag>

<v-drag pos="762,95,53,_">
<div class="text-3 text-left">
$$
\langle \vec{M}_z \rangle
$$
</div>
</v-drag>



<div class="abs-br m-2 text-3">
  <SlideCurrentNo />
</div>

---

# Radiation Force Landscapes

<div class="grid grid-cols-3 gap-2 mt-8 ml-10">
  <figure class="text-center">
    <img src="/figures/Fx_Janus_er_1.svg" alt="Image 1" class="w-7/8 h-auto">
  </figure>
  
  <figure class="text-center">
    <img src="/figures/Fy_Janus_er_1.svg" alt="Image 2" class="w-7/8 h-auto">
  </figure>
  
  <figure class="text-center">
    <img src="/figures/Tz_Janus_er_1.svg" alt="Image 3" class="w-7/8 h-auto">
  </figure>
</div>

<div v-click="1" class="grid grid-cols-3 gap-2 mt-5 ml-10">
  <figure class="text-center">
    <img src="/figures/Fx_Janus_er_2.svg" alt="Image 1" class="w-7/8 h-auto">
  </figure>
  
  <figure class="text-center">
    <img src="/figures/Fy_Janus_er_2.svg" alt="Image 2" class="w-7/8 h-auto">
  </figure>
  
  <figure class="text-center">
    <img src="/figures/Tz_Janus_er_2.svg" alt="Image 3" class="w-7/8 h-auto">
  </figure>
</div>



<div
  v-click="2"
  class="absolute inset-0 flex justify-center items-center pointer-events-none"
>
  <div
    class="grid grid-cols-3 gap-10 p-1 bg-white/30 backdrop-blur-md rounded-xl shadow-2xl ring-1 ring-black/10"
    style="transform: translateX(2%);"
  >
    <figure class="text-center">
      <img src="/figures/Fx_Janus_er_5.svg" alt="Fz er1" class="w-52 h-auto drop-shadow-lg" />
    </figure>
    <figure class="text-center">
      <img src="/figures/Fy_Janus_er_5.svg" alt="Fz er2" class="w-52 h-auto drop-shadow-lg" />
    </figure>
    <figure class="text-center">
      <img src="/figures/Tz_Janus_er_5.svg" alt="Fz er5" class="w-52 h-auto drop-shadow-lg" />
    </figure>
  </div>
</div>


<v-drag pos="745,19,195,_">
<div class="text-3 text-left">
$$
F_0 = \frac{\pi}{2 c} I a \quad M_0 = 2 F_0 a
$$
</div>
</v-drag>



<v-drag pos="200,72,53,_">
<div class="text-3 text-left">
$$
\langle \vec{F}_x \rangle
$$
</div>
</v-drag>

<v-drag pos="479,73,53,_">
<div class="text-3 text-left">
$$
\langle \vec{F}_y \rangle
$$
</div>
</v-drag>

<v-drag pos="760,71,53,_">
<div class="text-3 text-left">
$$
\langle \vec{M}_z \rangle
$$
</div>
</v-drag>

<v-drag pos="21,143,60,_">
<div class="text-3 text-left">
$$
\varepsilon_{r_1} = 1
$$
</div>
</v-drag>

<v-drag pos="22,378,53,_">
<div v-click="1"  class="text-3 text-left">
$$
\varepsilon_{r_1} = 2
$$
</div>
</v-drag>



<v-drag pos="906,238,53,_">
<div v-click="2"  class="text-3 text-left">
$$
\varepsilon_{r_1} = 5
$$
</div>
</v-drag>



<v-drag pos="-21,225,139,_">
<figure class="text-center">
  <img src="/figures/Janus_schematic.svg" alt="Image 2" class="w-full h-auto">
</figure>
</v-drag>



<div class="abs-br m-2 text-3">
  <SlideCurrentNo />
</div>

---

# Resonant Field Localization

<div class="grid grid-cols-[35%_65%] gap-8 items-center justify-center mt-8">

  
<div class="flex flex-col items-center text-center space-y-30 text-xl leading-relaxed">

<div class="text-center text-xl">

All parameters fixed, except the  
orientation angle $\phi_0$

</div>

<div v-click="1" class="text-center text-xl mt-10">

All parameters fixed, except the  
dielectric contrast ratio $\varepsilon_{r_2}/\varepsilon_{r_1}$

</div>

</div>






<div class="flex flex-col h-full mt--15">

  <div class="grid grid-cols-2 grid-rows-2 gap-2 place-items-center">
    <img src="/figures/EzScat_er1_5_er2er1_4_phi_1.svg" class="w-full h-auto rounded-lg" />
    <img src="/figures/EzScat_er1_5_er2er1_4_phi_66.svg" class="w-full h-auto rounded-lg" />
    <img v-click="1" src="/figures/EzScat_er1_5_er2er1_3.60_phi_90.svg" class="w-full h-auto rounded-lg" />
    <img v-click="1" src="/figures/EzScat_er1_5_er2er1_3.66_phi_90.svg" class="w-full h-auto rounded-lg" />
  </div>

</div>




</div>

  


<div class="abs-br m-2 text-3">
  <SlideCurrentNo />
</div>


---

# Particle Trajectories in Viscous Flow

Dynamic model

<div class="grid grid-cols-[35%_65%] gap-4 items-center justify-center mt-0">

  <!-- Left column: Video -->


  <!-- Right column: Equations -->
<div class="flex flex-col items-center text-center space-y-6">

<p class="text-lg mb-2">Instantaneous Force and Torque Balances</p>

<div  class="text-4">
$$
\mathbf{F}^{H} + \mathbf{F}^{EM} = 0, \quad \mathbf{M}^{H} + \mathbf{M}^{EM} = 0
$$

</div>





<p v-click="1" class="text-lg mt-4">Hydrodynamic Resistances</p>

<div v-click="1" class="text-4">
$$
\mathbf{F}^{H} =
-\frac{4\pi \eta L}{\log(L/a)} \, \mathbf{U}
$$

</div>

<div v-click="1" class="text-4">
$$
\mathbf{M}^{H} =
-4\pi \eta a^{2} \mathbf{\Omega}
$$

</div>

</div>



<div v-click="2" class="flex flex-col  h-full">

<div v-click="1" class="text-4">
$$
\tilde{t}_f = 10,000 \quad \quad\tilde{t} = t/T_0 \quad \quad   T_0 = \frac{2 c }{\pi} \frac{\eta}{I}
$$
</div>

  <figure class="mr--15 text-center border-black rounded-lg p-2 mt-auto">
    <video autoplay loop muted playsinline class="w-full h-auto">
      <source src="/figures/Janus_Trajectories_fixed_er.mp4" type="video/mp4">
      Your browser does not support the video tag.
    </video>
  </figure>
</div>



</div>



<v-drag pos="749,26,70,_">
<div  class="text-3 text-left">
$$
\varepsilon_{r_1} = 1
$$
</div>
</v-drag>


<v-drag pos="809,-5,181,_">
<figure class="text-center">
  <img src="/figures/Janus_schematic_PEC.svg" alt="Image 2" class="w-full h-auto">
</figure>
</v-drag>




<div class="abs-br m-2 text-3">
  <SlideCurrentNo />
</div>

---

# Particle Trajectories in Viscous Flow

Trajectories


<div  class="grid grid-cols-3 gap-2 mt-5 ml-15">
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



<v-drag pos="246,283,70,_">
<div class="text-3 text-left">
$$
\varepsilon_{r_1} = 1
$$
</div>
</v-drag>

<v-drag pos="517,283,70,_">
<div class="text-3 text-left">
$$
\varepsilon_{r_1} = 2
$$
</div>
</v-drag>

<v-drag pos="794,286,70,_">
<div class="text-3 text-left">
$$
\varepsilon_{r_1} = 5
$$
</div>
</v-drag>





<div v-click="1" class="grid grid-cols-3 gap-2 mt-10 ml-15">
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



<v-drag pos="707,54,233,_">
<div v-click="1"  class="text-3 text-left">
$$
\tilde{t}_f = 10,000 \quad \quad \tilde{x} = x/a \quad \tilde{y} = y/a
$$
</div>
</v-drag>



<v-drag pos="205,489,145,_">
<div v-click="1"  class="text-3 text-left">
$$
\varepsilon_{r_1} = 2, \varepsilon_{r_2} / \varepsilon_{r_1} = 2
$$
</div>
</v-drag>

<v-drag pos="489,486,128,_">
<div v-click="1"  class="text-3 text-left">
$$
\varepsilon_{r_1} = 2, \varepsilon_{r_2} / \varepsilon_{r_1} = 3
$$
</div>
</v-drag>

<v-drag pos="768,487,129,_">
<div v-click="1"  class="text-3 text-left">
$$
\varepsilon_{r_1} = 2, \varepsilon_{r_2} / \varepsilon_{r_1} = 5
$$
</div>
</v-drag>


<v-drag pos="-22,127,141,_">
<figure class="text-center">
  <img src="/figures/Janus_schematic_PEC.svg" alt="Image 2" class="w-full h-auto">
</figure>
</v-drag>

<v-drag v-click="1" pos="-20,345,139,_">
<figure class="text-center">
  <img src="/figures/Janus_schematic.svg" alt="Image 2" class="w-full h-auto">
</figure>
</v-drag>



<div class="abs-br m-2 text-3">
  <SlideCurrentNo />
</div>

---

# Thank You



<div class="flex flex-col items-center mt-6">

  <!-- Replace this with your QR code -->
  <img src="/figures/QR_github.png" class="w-4/9 h-auto mb-0 rounded shadow-lg"/>

  <p class="text-sm opacity-80 text-center">
    Scan for code and paper
  </p>

</div>


---

## Analytical expression for a PEC-dielectric Janus cylinder

Radiation drag

<div class="text-3 text-left mt-15">
$$
\begin{aligned}
        \tilde{F_x} &= \cos{\phi_0} \left[ \{ \Re (C_1 C_0^* ) - \Re (S_1 S_0^* ) + \Re ( C_1' C_0'^* ) - \Re ( S_1' S_0'^* ) \} + \sum_{n = 0}^{\infty} \{ \Re( C_{n} C_{n+1}^* ) + \Re ( S_{n} S_{n+1}^* )  + \Re (C_{n}' C_{n+1}'^* ) + \Re (S_{n}' S_{n+1}'^*) \} \right] \\
        &\quad + \sin{\phi_0} \left[ \{ \Re (C_1 S_0^* ) + \Re ( C_0 S_1^* ) + \Re ( C_1' S_0'^* ) + \Re ( S_1' C_0'^* )  \} + \sum_{n = 0}^{\infty} \{ \Re ( S_{n+1} C_n^* ) -  \Re (S_{n} C_{n+1}^* ) + \Re (C_{n}' S_{n+1}'^*) - \Re ( S_{n}' C_{n+1}'^* ) \} \right] \\
        &\quad - \frac{1}{(k_0 a)^2} \left[ \cos{\phi_0} \sum_{n = 0}^{\infty} n(n+1) \{ \Re (C_{n} C_{n+1}^* ) + \Re ( S_{n} S_{n+1}^* ) \}  
                - \sin{\phi_0}  \sum_{n = 0}^{\infty} n(n+1) \{ \Re (C_{n+1} S_{n}^* ) - \Re ( C_{n} S_{n+1}^* ) \} \right] \\
        &\quad + \sin{\phi_0} \frac{1}{k_0 a} \Re \left[ \{ C_0' S_1^* + S_0' C_1^* \} + \sum_{n = 1}^{\infty} n \{ (C_{n-1}' + C_{n+1}' ) S_n^* - ( S_{n-1}' + S_{n+1}' ) C_n^* \}  \right] \\
        &\quad - \cos{\phi_0} \frac{1}{k_0 a} \Re \left[ \{ S_0' S_1^* - C_0' C_1^* \} - \sum_{n = 1}^{\infty} n \{ ( C_{n-1}' - C_{n+1}' ) C_n^* + ( S_{n-1}' - S_{n+1}' ) S_n^* \}  \right] 

    \end{aligned}
$$

</div>


---

## Analytical expression for a PEC-dielectric Janus cylinder

Radiation lift

<div class="text-3 text-left mt-15">

$$
\begin{aligned}
        \tilde{F_y} &= - \sin{\phi_0}  \left[ \{ \Re (C_1 C_0^* ) - \Re (S_1 S_0^* ) + \Re ( C_1' C_0'^* ) - \Re ( S_1' S_0'^* ) \} + \sum_{n = 0}^{\infty} \{ \Re( C_{n} C_{n+1}^* ) + \Re ( S_{n} S_{n+1}^* )  + \Re (C_{n}' C_{n+1}'^* ) + \Re (S_{n}' S_{n+1}'^*) \} \right] \\
        &\quad + \cos{\phi_0}  \left[ \Re (C_1 S_0^* ) + \Re ( C_0 S_1^* ) + \Re ( C_1' S_0'^* ) + \Re ( S_1' C_0'^* ) +  \sum_{n = 0}^{\infty} \{ \Re ( S_{n+1} C_n^* ) -  \Re (S_{n} C_{n+1}^* ) + \Re (C_{n}' S_{n+1}'^*) - \Re ( S_{n}' C_{n+1}'^* ) \}  \right]  \\
        &\quad + \frac{1}{(k_0 a)^2} \left[\sin{\phi_0} \sum_{n = 0}^{\infty} n(n+1) \{ \Re (C_{n} C_{n+1}^* ) + \Re ( S_{n} S_{n+1}^* ) \}  
        +  \cos{\phi_0} \sum_{n = 0}^{\infty} n(n+1) \{ \Re (C_{n+1} S_{n}^* ) - \Re ( C_{n} S_{n+1}^* ) \} \right] \\
        &\quad + \cos{\phi_0} \frac{1}{k_0 a} \Re \left[ \{ C_0' S_1^* + S_0' C_1^* \} + \sum_{n = 1}^{\infty} n \{ (C_{n-1}' + C_{n+1}' ) S_n^* - ( S_{n-1}' + S_{n+1}' ) C_n^* \}  \right] \\
        &\quad + \sin{\phi_0}  \frac{1}{k_0 a} \Re \left[ \{ S_0' S_1^* - C_0' C_1^* \} - \sum_{n = 1}^{\infty} n \{ ( C_{n-1}' - C_{n+1}' ) C_n^* + ( S_{n-1}' - S_{n+1}' ) S_n^* \}  \right]

    \end{aligned}
$$


</div>


---

## Analytical expression for a PEC-dielectric Janus cylinder

Radiation torque

<div class="text-3 text-left mt-5">

$$
\begin{aligned}
        \tilde{M_z} &= \frac{1}{k_0 a} \sum_{n = 1}^{\infty} n \Re \left[ S_n' C_n^* - C_n' S_n^* \right]
    \end{aligned}
$$


$$
\begin{gather*}
        C_m = \left[ \alpha_m (-j)^m J_m (k_0 a) \cos{(m \phi_0)} + B_m H_m^{(1)} (k_0 a) \right], \\
        S_m = \left[ \alpha_m (-j)^m J_m (k_0 a) \sin{(m \phi_0)} + D_m H_m^{(1)} (k_0 a) \right], \\
        C_m' = \left[ \alpha_m (-j)^m J_m' (k_0 a) \cos{(m \phi_0)} + B_m H_m^{(1)'} (k_0 a) \right], \\
        S_m' = \left[ \alpha_m (-j)^m J_m' (k_0 a) \sin{(m \phi_0)} + D_m H_m^{(1)'} (k_0 a) \right].
    \end{gather*}
$$


$$
\begin{aligned}
    B_m = \frac{\alpha_m}{2 \pi H_m^{(1)} (k_0 a) } \int_0^{\pi} E_z^{\text{tot}} (\phi) \cos(m \phi) \, d\phi  - \frac{\alpha_m (-j)^m J_m (k_0 a) \cos(m \phi_0)}{H_m^{(1)} (k_0 a)}, \\
    D_m = \frac{1}{\pi H_m^{(1)} (k_0 a) } \int_0^{\pi} E_z^{\text{tot}} (\phi) \sin(m \phi) \, d\phi  - \frac{2 (-j)^m J_m (k_0 a) \sin(m \phi_0)}{H_m^{(1)} (k_0 a)}. 
\end{aligned}
$$

</div>
