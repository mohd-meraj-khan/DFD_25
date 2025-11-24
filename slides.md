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
  <span class="text-l font-semibold">Mohd. Meraj Khan<sup>a</sup></span>,
  <span class="text-l">Sumesh P. Thampi<sup>b</sup></span>
  and
  <span class="text-l">Anubhab Roy<sup>a</sup></span>
</div>


<div class="mt-5 text-3.5 leading-tight text-center">
  <sup class="text-3.5 align-super">a</sup> Department of Applied Mechanics<br>
  <sup class="text-3.5 align-super">b</sup> Department of Chemical Engineering
</div>



<div class="mt-4 text-4 text-center ">
  Indian Institute of Technology Madras, Chennai, India
</div>








<div class="my-10 flex justify-center items-center">
  <img src="/figures/IITM_Logo.png" alt="IIT Madras logo" class="h-24 w-24 opacity-90">
</div>




<div class="text-l leading-tight text-center mt-5 mb-5">
  78th APS Division of Fluid Dynamics
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
      <div class="text-2.5 opacity-70 mt-1">(Source: astronomy.swin.edu.au)</div>
    </figcaption>
  </figure>

  <!-- Optical trapping video -->
  <figure v-click="1" class="flex flex-col items-center">
    <video autoplay loop muted playsinline class="w-[75%] h-auto rounded shadow">
      <source src="/figures/Particl_Trapping_Nobel_2018.mp4" type="video/mp4" />
    </video>
    <figcaption class="text-3 mt-3 leading-tight text-center">
      Optical trapping using radiation forces
      <div class="text-2.5 opacity-70 mt-1">Ashkin & Dziedzic (1989)</div>
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
      <div class="text-2.5 opacity-70 mt-1">Ashkin & Dziedzic (1989)</div>
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



<div v-click="1" class="mt-4 p-3 text-sm bg-gray-100 border-l-4  rounded">
   The asymmetry of the particle breaks reflectional symmetry, resulting in radiation-induced lift and torque.
</div>



<div class="abs-br m-2 text-3">
  <SlideCurrentNo />
</div>

---

# Macroscopic Maxwell Equations and LBM Framework

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
f_i^* (\mathbf{r}, t) = f_i (\mathbf{r}, t) + \frac{\Delta t}{\tau} \left[f_i^{eq} (\mathbf{r}, t) - f_i (\mathbf{r}, t) \right]
$$
</div>
<div v-click='5' class="text-center mx-5">
$$
f_i (\mathbf{r} + \mathbf{c}_i \Delta t, t + \Delta t) = f_i^* (\mathbf{r}, t)
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
  <div v-click='3' class="m-2 text-2.5">
    Timm Kruger (2017)
  </div>
  <div v-click='6' class="m-2 text-2.5">
    Hauser and Verhey (2017)
  </div>
  <div v-click='6' class="m-2 text-2.5">
    Khan et al. (2024)
  </div>
</div>



<div class="flex justify-between items-center text-3.5 mt-2 abs-bl mr-5 ">
  <div class="m-2 text-2.5">
    Griffiths (2013)
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

# Conducting–Dielectric Janus Cylinder



::left::

<figure class="text-center item-center my-5">
  <img src="/figures/Janus_Half_schematic.svg" alt="Image 1" class="w-3/4 h-auto">
</figure>

::right::




<div v-click="1" class="mt-3 text-3.5">
$$
E_z^I (r, \phi) = \sum_{m = 0}^{\infty} \alpha_m (-j)^m J_m (k_0 r) \cos{ { m ( \phi - \phi_0) } }
$$
</div>


<div v-click="1"  class="text-3 text-left">
$$
\alpha_m =
\begin{cases}
1, & \text{if } m = 0, \\
2, & \text{otherwise.}
\end{cases}
$$
</div>


<div v-click="1" class="mt-3 text-3.5">
$$
E_z^S (r, \phi) = \sum_{m = 0}^{\infty} \left[ B_m \cos{(m \phi)} + D_m \sin{(m \phi)} \right] H_m^{(1)} (k_0 r)
$$
</div>



<div v-click="2" class="mt-15 text-3.5">
$$
\int_0^{\pi} E_z^{\text{tot}} (\phi') K (\phi, \phi') d \phi' = F (\phi)
$$
</div>


<div class="flex justify-between items-center text-3.5 mt-2 abs-br mr-5 ">
  <div class="m-2 text-2.5">
    Hurd and Sachdeva (1975)
  </div>
</div>




<!--
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
-->


<div class="abs-br m-2 text-3">
  <SlideCurrentNo />
</div>

---

# Radiation Force Landscapes


<div class="text-center text-3.5 mb-0 mt-0">
  Conducting–Dielectric Janus Cylinder
</div>


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



<div v-click="1" class="text-center text-3.5 mb-0 mt-0">
  Dielectric–Dielectric Janus Cylinder
</div>

<div v-click="1" class="grid grid-cols-3 gap-0 mt-0 ml-15">
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




<v-drag pos="-23,136,148,_">
<figure class="text-center">
  <img src="/figures/Janus_schematic_PEC.svg" alt="Image 2" class="w-full h-auto">
</figure>
</v-drag>

<v-drag v-click="1" pos="-24,325,148,_">
<figure class="text-center">
  <img src="/figures/Janus_schematic.svg" alt="Image 2" class="w-full h-auto">
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



<v-drag v-click="1" pos="23,445,53,_">
<div class="text-3 text-left">
$$
\varepsilon_{r_1} = 1
$$
</div>
</v-drag>



<div class="abs-br m-2 text-3">
  <SlideCurrentNo />
</div>

---

# Radiation Force Landscapes

Dielectric–Dielectric Janus Cylinder

<div class="grid grid-cols-3 gap-2 mt-8 ml-10">
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

<div v-click="1" class="grid grid-cols-3 gap-2 mt-5 ml-10">
  <figure class="text-center">
    <img src="/figures/Fx_Janus_er_5.svg" alt="Image 1" class="w-7/8 h-auto">
  </figure>
  
  <figure class="text-center">
    <img src="/figures/Fy_Janus_er_5.svg" alt="Image 2" class="w-7/8 h-auto">
  </figure>
  
  <figure class="text-center">
    <img src="/figures/Tz_Janus_er_5.svg" alt="Image 3" class="w-7/8 h-auto">
  </figure>
</div>


<!--

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

-->


<v-drag pos="745,19,195,_">
<div class="text-3 text-left">
$$
F_0 = \frac{\pi}{2 c} I a \quad M_0 = 2 F_0 a
$$
</div>
</v-drag>



<v-drag pos="200,101,53,_">
<div class="text-3 text-left">
$$
\langle \vec{F}_x \rangle
$$
</div>
</v-drag>

<v-drag pos="481,105,53,_">
<div class="text-3 text-left">
$$
\langle \vec{F}_y \rangle
$$
</div>
</v-drag>

<v-drag pos="767,104,53,_">
<div class="text-3 text-left">
$$
\langle \vec{M}_z \rangle
$$
</div>
</v-drag>

<v-drag pos="17,177,60,_">
<div class="text-3 text-left">
$$
\varepsilon_{r_1} = 2
$$
</div>
</v-drag>

<v-drag pos="22,378,53,_">
<div v-click="1"  class="text-3 text-left">
$$
\varepsilon_{r_1} = 5
$$
</div>
</v-drag>


<!--
<v-drag pos="906,238,53,_">
<div v-click="2"  class="text-3 text-left">
$$
\varepsilon_{r_1} = 5
$$
</div>
</v-drag>
-->



<v-drag pos="-21,252,139,_">
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





<v-drag pos="541,450,40,_">
<div v-click="2"  class="text-3 text-left">
$$
14
$$
</div>
</v-drag>


<v-drag pos="834,212,40,_">
<div v-click="2"  class="text-3 text-left">
$$
40
$$
</div>
</v-drag>


<v-drag pos="542,212,40,_">
<div v-click="2"  class="text-3 text-left">
$$
14
$$
</div>
</v-drag>


<v-drag pos="832,448,40,_">
<div v-click="2"  class="text-3 text-left">
$$
32
$$
</div>
</v-drag>



  


<div class="abs-br m-2 text-3">
  <SlideCurrentNo />
</div>

---

# Particle Trajectories in Viscous Flow

Dynamic model

<div class="grid grid-cols-[35%_65%] gap-4 items-center justify-center mt-0">

  
  
<div class="flex flex-col items-center text-center space-y-6">

<p class="text-lg mb-2">Instantaneous Force and Torque Balances</p>

<div  class="text-4">
$$
\mathbf{F}^{H} + \mathbf{F}^{EM} = 0, \quad \mathbf{M}^{H} + \mathbf{M}^{EM} = 0
$$

</div>





<p v-click="1" class="text-lg mt-4">Hydrodynamic Force and Torque</p>

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

<div class="text-3.5">
$$
U_0 = \frac{\pi}{2c \eta}Ia \quad \quad \Omega_0 = \frac{\pi}{2c \eta}I \quad \quad   T_0 = \frac{2 c }{\pi} \frac{\eta}{I}
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



<v-drag v-click="1" pos="749,26,70,_">
<div  class="text-3 text-left">
$$
\varepsilon_{r_1} = 1
$$
</div>
</v-drag>


<v-drag v-click="1" pos="825,-8,165,_">
<figure class="text-center">
  <img src="/figures/Janus_schematic_PEC.svg" alt="Image 2" class="w-full h-auto">
</figure>
</v-drag>


<v-drag v-click="2" pos="668,196,91,_">
<div  class="text-3 text-left">
$$
\tilde{t}_f = 10,000 
$$
</div>
</v-drag>




<div v-click="1" class="flex justify-between items-center text-3.5 mt-2 abs-bl mr-5 ">
  <div class="m-2 text-2.5">
    Batchelor (1970)
  </div>
</div>





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
<div class="text-3 text-left">
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

# Thank You!

<div class="grid grid-cols-2 gap-12 items-center mt-10">

  <!-- LEFT: Advisor photos (small) -->
<div class="flex flex-row justify-center space-x-12">


<figure class="text-center">
  <img src="/figures/Anubhab.jpg" class="w-auto h-32 shadow-md" />
  <figcaption class="text-sm mt-2 opacity-80">
    Prof. Anubhab Roy
  </figcaption>
</figure>

<figure class="text-center">
  <img src="/figures/sumesh.jpeg" class="w-auto h-32 shadow-md" />
  <figcaption class="text-sm mt-2 opacity-80">
    Prof. Sumesh P. Thampi
  </figcaption>
</figure>



</div>

  <!-- RIGHT: Big QR Code -->
  <div class="flex flex-col items-center">
    <img src="/figures/QR_github.png" class="w-7/8 h-auto shadow-xl" />
    <p class="text-base opacity-80 text-center mt-4">
      Scan for code and preprint
    </p>
  </div>

</div>





<div class="flex justify-between items-center text-3.5 mt-2 abs-br mr-5 ">
  <div class="m-2 text-2.5">
    Khan et al. (2024)
  </div>
  <div class="m-2 text-2.5">
    Khan et al. (2025)
  </div>
  <div class="m-2 text-2.5">
    Khan et al. (2025)
  </div>
</div>
