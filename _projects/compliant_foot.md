---
name: "Compliant Prosthetic Foot"
subtitle: "Semester project for the class Neuroprosthetics (2022) TUM"
keywords: "keywords: multibody dynamics, topological optimization, mechanical design, compliant mechanism, 3D printing, user-centered design"
image_url: /assets/images/foot2.jpg
director: "Prof. Dr. Cristina Piazza"
co-authors: "Nithin Balan"
summary: "Design of a low-cost compliant foot prosthetic designed for traversing irregular terrain. Semester project for the class Neuroprosthetics (2022) TUM."
tags: [ multibody dynamics, topological optimization, mechanical design, compliant mechanism, 3D printing, user-centered design ]
---
![fish2](/assets/images/foot2.jpg)

Directed by Prof. Dr. Cristina Piazza

Co-Authors: Balan, Nithin


This semester-long project involved the design and first iteration of a foot prosthesis prototype. The motivation behind this design stems from the consecuences of the armed conflict in Colombia, after which a considerable amount of people, mostly inhabitants from remote rural communities, lost their lives or limbs to anti-personnel mines. The design of this soft foot adresses the unique necessities of people who earn ther livelyhood by cultivating crops on the hillsides with steep, irregular terrain. The full report can be downloaded <a href="/assets/documents/Final_Report__Design_of_a_Soft_Foot_for_Lower_limb_Prostheses.pdf">here </a>.

Rather than expensive and delicate electronics, this design relies on mechanical simplicity. The design requirements that needed to be met were:
 <ul>
    <li> <p>{{ "Dorsiflexion, plantar flexion, and toe joint movement within the naturally occurring ranges of a normal human gait cycle." }}</p> </li>
    <li> <p>{{ "Controlled heel inversion-eversion: similar stiffness values and limited range of motion to avoid buckling." }}</p> </li>
    <li> <p>{{ "Shock absorption during heel-strike impact." }}</p> </li>
    <li> <p>{{ "Sole deforms locally to conform to small terrain irregularities (i.e. pebbles)." }}</p> </li>
    <li> <p>{{ "Similar shape and density to a human foot with a shoe." }}</p> </li>
</ul>

<h2>{{ "Biomechanical Model (Phases of Walking Gait)" }}</h2>
<p>{{ " The normative human gait consistes of three distinct stages:" }}</p>

 <ul>
    <li> <p>{{ "Foot-strike: The heel receives and dampens the dynamic impact of the body weight (reaction force equivalent to 120% of the body weight applied on the heel alone)." }}</p> </li>
    <li> <p>{{ "Dual-flexion: the foot is completely on the ground (distributed force equivalent to 80% of the body weight)." }}</p> </li>
    <li> <p>{{ "Toe-off: the load is applied at the toes, which accumulate tension to provide a propulsive effect (reaction force equivalent to the body weight applied only on the toe section)." }}</p> </li>
</ul>

<!-- ![Gait Cycle](/assets/images/compliant_foot/gait_cycle.png) -->

<figure>
  <img src="/assets/images/compliant_foot/gait_cycle.png" alt="Gait_Cycle" style="width:80%">
  <figcaption>Ankle moment vs. relative angle curve for a representative subject walking at 1.75 m/s. image taken from Kamran Shamaei, Gregory S Sawicki, and Aaron M Dollar. “Estimation of quasi-stiffness
and propulsive work of the human ankle in the stance phase of walking”. In: PloS one
8.3 (2013), e59935.</figcaption>
</figure>

<p>{{ " During unimpeded, normal gait, the heel joint changes stiffness dynamically, becoming its stiffest during dual-flexion and much less so during toe-off. Of course, this change cannot be replicated with a passive deivice... or can it?" }}</p>



<h2>{{ "Soft Foot with Selective Flexibility" }}</h2>
<p>{{ "We used the pseudo-rigid model (PRM) approximation as a starting point. In this case, the flexible foot was modelled as a multibody mechanism in which the thinner sections act as pivot joints with torsional springs wth a characteristic stiffness. This stiffness depends on the section geometry and the Young's modulus of the selected material. The rough section profiles were selected based on this principle. One notable aspect of the design is that joints 2 and 3 (as seen in the sketch) are springs in a serial configuration. During dual-flexion, the toe joint movement is constrained by the floor. However, as soon as the foot starts to lift off during toe-off, this constraint is removed and allows both heel and toe joint to act as a single equivalent (softer) spring. Thus, a change in overall stiffness can be achieved." }}</p>

<p>{{ "Two design iterations were made. A first design was made in CAD using Solid Works, after which it was exported to Ansys to simulate its dynamic behavior under different conditions. Additionally, we implemented topological optimization to reduce structurally redundant material. The second, revised version included improved aesthetics, as well as improved stability on inversion-eversion by adding a thicker cross section (added stiffness) and ensure motion limits." }}</p>

<table style="width:100%">
  <tr>
    <td style="width:40%"><img src="/assets/images/compliant_foot/PRM.JPG" alt="sketch"></td>
    <td style="width:60%"><p>{{ "We used the pseudo-rigid model (PRM) approximation as a starting point. In this case, the flexible foot was modelled as a multibody mechanism in which the thinner sections act as pivot joints with torsional springs wth a characteristic stiffness. This stiffness depends on the section geometry and the Young's modulus of the selected material. The rough section profiles were selected based on this principle. One notable aspect of the design is that joints 2 and 3 (as seen in the sketch) are springs in a serial configuration. During dual-flexion, the toe joint movement is constrained by the floor. However, as soon as the foot starts to lift off during toe-off, this constraint is removed and allows both heel and toe joint to act as a single equivalent (softer) spring. Thus, a change in overall stiffness can be achieved." }}</p></td>
  </tr>
</table>

<p>{{ "Two design iterations were made. A first design was made in CAD using Solid Works, after which it was exported to Ansys to simulate its dynamic behavior under different conditions. Additionally, we implemented topological optimization to reduce structurally redundant material. The second, revised version included improved aesthetics, as well as improved stability on inversion-eversion by adding a thicker cross section (added stiffness) and ensure motion limits." }}</p>

<h2>{{ "Quantitative results: Mechanical Properties according to Simulations" }}</h2>
<h3>{{ "Gait Cycle" }}</h3>

Some of the results can be seen below. For reference: BW refers to a unit of force equivalent to one body weight under standard gravity.
<figure>
  <img src="/assets/images/compliant_foot/Gait-simul.JPG" alt="Gait_Cycle" style="width:80%">
  <figcaption>Visual comparison of the simulated foot deformations during different stages of the gait cycle.</figcaption>
</figure>

<h3>{{ "Eversion - Inversion" }}</h3>

<p>{{ "Movement amplitude: -10.50° (Eversion) 11.35° (Inversion)" }}</p>
<p>{{ "Stiffness: 3.44 Nm/degree" }}</p>

<table style="width:100%">
  <tr>
    <td style="width:50%"><img src="/assets/images/compliant_foot/sim_ev_1.PNG" alt="angular displacement"></td>
    <td style="width:50%"><img src="/assets/images/compliant_foot/sim_ev_2.PNG" alt="stiffness"></td>
  </tr>
</table>

<video height="250" autoplay muted loop>
  <source src="/assets/images/compliant_foot/Dorsilexion-Plantarflexion-Color.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>

<video height="250" autoplay muted loop src="/assets/images/compliant_foot/Dorsilexion-Plantarflexion-Color.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>
<p>{{ "meep?" }}</p>

<video height="250" autoplay muted loop>
  <source src="/assets/images/Carangiform_locomotion/carangiform_locomotion_cropped.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>

<!--
<h3>{{ "Dorsiflexion - Plantar flexion" }}</h3>

<table style="width:100%">
  <tr>
    <td style="width:30%">
    <p>{{ "Movement amplitude: 5.44° (dorsiflexion) -5.95° (plantar flexion)" }}</p>
    <p>{{ "Stiffness: 16.29 Nm/degree" }}</p></td>
    <td style="width:35%"><img src="/assets/images/compliant_foot/sim_dp_1.PNG" alt="angular displacement"></td>
    <td style="width:35%"><img src="/assets/images/compliant_foot/sim_dp_2.PNG" alt="stiffness"></td>
  </tr>
</table>

<video height="250" autoplay muted loop>
  <source src="/assets/images/compliant_foot/Dorsilexion-Plantarflexion-Color.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>

<h3>{{ "Toe Joint" }}</h3>

<table style="width:100%">
  <tr>
    <td style="width:50%">
    <p>{{ "Movement amplitude: 20.4°" }}</p>
    <p>{{ "Stiffness: 6.44 Nm/degree" }}</p></td>
    <td style="width:50%"><img src="/assets/images/compliant_foot/sim_toe_1.PNG" alt="angular displacement"></td>
  </tr>
  <tr>
    <td style="width:50%"><p>{{ "foot video here" }}</p></td>
    <td style="width:50%"><img src="/assets/images/compliant_foot/sim_toe_2.PNG" alt="stiffness"></td>
  </tr>
</table>

<h3>{{ "Combined Toe and Heel" }}</h3>

<table style="width:100%">
  <tr>
    <td style="width:50%">
    <p>{{ "Movement amplitude: 11.89° (heel) 34.31° (Toes)" }}</p>
    <p>{{ "Stiffness: 8.83 Nm/degree" }}</p></td>
    <td style="width:50%"><img src="/assets/images/compliant_foot/sim_comb_1.PNG" alt="angular displacement"></td>
  </tr>
  <tr>
    <td style="width:50%"><video height="250" autoplay muted loop>
  <source src="/assets/images/compliant_foot/Toe-Off.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video></td>
    <td style="width:50%"><img src="/assets/images/compliant_foot/sim_comb_2.PNG" alt="stiffness"></td>
  </tr>
</table>
-->

<h3>{{ "Simulation Results" }}</h3>


<p>{{ "" }}</p>

<h2>{{ "Qualitative Results: Visual Similarities in Proof of Concept" }}</h2>
<p>{{ " A life-size prototype was printed on TPU Ninja-flex and mounted on a frame. Using our own body weight as reference, we did a visual comparison of the foot deformations when stepping on a small plastic cap. Although no objective measure was used and more accurate testing equipment was unavailable for the project, the experimental results are visually similar to the simulated deformations. " }}</p>

![fish2](/assets/images/compliant_foot/step_cap.JPG)

