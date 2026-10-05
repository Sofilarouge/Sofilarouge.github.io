---
name: "Design of a Bionic, Shape-Memory Alloy Fish Tail"
subtitle: "Bachelor's thesis for Mechanical Engineering (B.Sc.) (2019) Universidad de los Andes"
keywords: "keywords: multibody dynamics, mechanical design, experimental characterization, biomimetics, prototype construction"
image_url: /assets/images/fish2.jpg
director: "Prof. Dr. Carlos Francisco Rodriguez Herrera"
summary: "Design, construction and characterization of a modular biomimetic fish tail powered by Shape-Memory Alloy (SMA) actuators. Part of my Bachelor's thesis for Mechanical Engineering (B.Sc.) (2019) Universidad de los Andes."
Emphasis: "Awarded Silver Award for Best Student Paper, Symposium on Multibody Systems and Mechatronics (MuSMe 2020-2021)." 
---
![fish2](/assets/images/Carangiform_locomotion/fish2.jpg)
Directed by Prof. Dr. Carlos Francisco Rodriguez Herrera

Propeller-driven ROVs have been successfully used for open water exploration for decades now. However, there are some concerns about the impact of propeller blades on the most delicate reef ecosystems. There are also some concerns about the electromagnetic and acoustic noise caused by motors, as they particularly impact key species such as sharks. As an alternative, this semester-long project explored the use of shape-memory alloy (SMA) to power a biomimetic fish tail undergoing carangiform (undulatory) locomotion. To that end, a modular double-lever mechanism was designed and characterized experimentally. Its purpose is to create a controlled rotational movement using two SMA wires that contract and relax, just like a pair of muscles would.

For brevity's sake, the following page includes only a brief overview, and the more theoretical aspects have been largely glossed over. Please refer to the [full thesis](https://hdl.handle.net/1992/45039) and [conference paper](https://link.springer.com/chapter/10.1007/978-3-030-60372-4_31) for a proper description of the mathematical model.

<video height="200" autoplay muted loop>
  <source src="/assets/images/Carangiform_locomotion/carangiform_locomotion_cropped.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>

<h2>{{ "SMA Module Design and Characterization" }}</h2>

![Double_lever_mechanism](/assets/images/Carangiform_locomotion/mechanism.tif)

The driving principle of the double lever mechanism added several layers of complexity, the first of which was experimental characterization in lieu of known dynamic behavior. To that end, a testing jig was constructed. On first glance, the wire seemingy exhibits a classical frst-order response to a known current step input.

<video width="640" height="360" autoplay muted loop>
  <source src="/assets/images/Carangiform_locomotion/wire_pulse.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>

However, the biggest issue was the fact that SMA dynamics require solving a series of heat transfer problems: SMA wire relative lenght contraction is correlated to the material temperature itself, not to the input current or voltage. This means that, unless heat can be dissipated as quickly as it is administered, the same actuator has two distinct dynamic behaviors for contraction and relaxation. Through iteration and experimentation, a suitable configuration was found for sustained oscillations at a reasonable frequency.

![1hz_flutter](/assets/images/Carangiform_locomotion/1hz_flutter.tif)

Finally, the experimental results were used in combination with the SMA wire properties to graph the possible movement amplitude and torque limits for modules of different dimensions, which was useful to establish their operational ranges.

![mechanism_graphs](/assets/images/Carangiform_locomotion/mechanism_graphs.PNG)


<h2>{{ "Fish Tail Kinematic and Dynamic Model" }}</h2>

The next step was defining how the fish tail segments would move, i.e. the driving functions for each actuator. The process to achieve this was iterative: first, a swimming configuration and mechanism dimensions were initialized, and the necessary driving torques for it were calculated. The parameters were tweaked until the theoretical amplitudes and torques were consistent with the module operational ranges.

No specialized multibody dynamics simulation software was used, as none was available. Instead, the fish tail was abstracted to a system of nonlinear equations to be solved.

<table style="width:100%">
  <tr>
    <td style="width:30%"><img src="/assets/images/Carangiform_locomotion/element_model.PNG" alt="element_model"></td>
    <td style="width:70%">The flexible tail of a fish was modeled as a series of three rigid, interconnected propulsive elements connected by holonomic rotational joints. The overall swimming motion can be decomposed as three driving functions describing the relative angle between each element and the previous one. For simplicity, we assume all three driving functions to be sinusoidal, each with a characteristic phase and amplitude. </td>
  </tr>
</table>


![fish_model](/assets/images/Carangiform_locomotion/fish_model.PNG)

Lagrangian mechanics and generalized coordinates were used to describe the equations of motion, as well as its kinematic and driving constraints. To solve the system dynamics, the added mass coefficients of the tail were considered, as were the acting unstable hydrodynamic forces. These were modeled using the Kutta Jukowsky theorem (again, plese refer to the full thesis for a proper description). The resulting system of equations were highly nonlinear. Therefore, they were solved numerically by using Newton's method in Matlab. An animation of the final selected configuration can be seen below:

<video width="640" height="360" autoplay muted loop>
  <source src="/assets/images/Carangiform_locomotion/swimming_sim.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>

<h2>{{ "Electromechanical Prototype Construction" }}</h2>

Once a suitable configuration was found, a tail was constructed using mostly laser-cut aluminium and 3D printed profiles. SMA wires were attached connected to the central wiring using screw terminals. Here it is shown from above (a) and below (b).

![fish_tail](/assets/images/Carangiform_locomotion/tail_foto.tif)

Meanwhile, the fish body housed the power circuit necessary for their activation. To eliminate the complexities associated with batteries, the driving current was provided externally. A simplified schematic can be seen below:

The circuit board consisted mainly of transistors that acted as valves to power the mechanism according to the signal voltage provided by an Arduino Nano. A voltage follower was added to further insulate the Arduino from the driving current. Additionally, other safety features included indicator LEDS and and a dead man's switch to avoid accidental activation. To eliminate the complexities associated with batteries, the driving current was provided externally.

Of course, the prototype was tested for complete waterproofness underwater before any further testing was done.

Some pictures of the construction process can be seen below:

![fish2](/assets/images/fish3.jpeg)
![fish2](/assets/images/fish4.jpg)


<h2>{{ "Testing and Conclusions" }}</h2>

Preliminary testing was simple: dunk the fish in water and see what happens when it's activated. Buoyancy was corrected using a pouch of coins. Due to the thermal suceptibility of the driving mechanism, it was perhaps not suprising to notice that room temperature water proved to be too effective at heat dispersion, and thus the movement was noticeably sluggish, even if some forward motion was achieved.

<video width="640" height="360" autoplay muted loop>
  <source src="/assets/images/Carangiform_locomotion/swimming.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>

Even if the mechanism does not move exacly as intended, some important conclusions can be drawn. While it is perfectly possible to make a biomimetic fish using SMA wire actuators, it would be difficult to argue in favor of its suitability for underwater exploration due to its energetical inefficiency.


