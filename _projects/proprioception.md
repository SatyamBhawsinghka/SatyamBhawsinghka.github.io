---
layout: page
title: Proprioception using hydraulic knuckles on tendon driven multi link mechanism
description: Hydraulic knuckles used for joint state estimation while acting as variable stiffness joints on a tendon driven multi link mechanism
img: assets/img/mlse/pressure_relaxation.gif
importance: 1
category: Latest
---

In addition to the hydraulic knuckles being used as `variable stiffness joints`, they were also used 
for proprioception i.e. state estimation for joint angles. The intrinsic property of change in internal 
pressure due to the bending on knuckles is exploited to develop a state estimation model using feed forward 
neural network. This eliminates the use of additional positional encoders.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/mlse/est_setup.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="caption">
    Experimental setup for data collection for state estimation. Internal pressure and joint angle data was recorded 
    at each time step as the tendon is actuated with increasing torque. The data is recorded for starting angles of 0-20 deg 
    with interval of 5 deg and starting pressures 0-5 psi with an interval of 1 psi for 5 knuckle samples
</div>


<div class="row justify-content-sm-center">
    <div class="col-sm-5 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/mlse/data.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-7 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/mlse/model.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="row justify-content-sm-center">
    <div class="col-sm-6 mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/mlse/result.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="caption">
    Details of data split for model training (top left), model parameters (top right), results (bottom)
</div>

A multi link tendon driven mechanism with hydraulic knuckles as VSJs was fabricated to generate planar 
trajectories by controlling internal knuckle pressures and tendon tension. The state estimation model was
validated on this multi link mechanism as well. 

<div class="row justify-content-sm-center">
    <div class="col-sm-5 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/mlse/pc1.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-7 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/mlse/pc2.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="row justify-content-sm-center">
    <div class="col-sm-6 mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/mlse/mechanism.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="caption">
    Fabricated pressure control system for controlling 6 independent knuckle pressures (top left and right), ground link for multi link mechanism (bottom)
</div>

The results of multi link mechanism activated with two different set of starting pressure angles are presented.
The trajectory that resembles wrap type grasp has a pressure combination of `1, 1, 5, 5, 5, 5 psi` starting from the most proximal 
joint (considering ground link) to the most distal joint. Similarly, the pressure combination for a 
pinch type grasp trajectory is `5, 5, 5 ,5 ,1 ,1 psi`.


<div class="row justify-content-sm-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/mlse/pinch_ml.gif" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/mlse/wrap_ml.gif" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="row justify-content-sm-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/mlse/pinch_se.gif" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/mlse/wrap_se.gif" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="row justify-content-sm-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/mlse/pinch_res.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/mlse/wrap_res.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Actual trajectories generated: pinch and wrap (top left and right), state estimation result visualization: pinch and wrap (middle left and right),
    quantitative state estimation results: pinch and wrap (bottom left and right)
</div>