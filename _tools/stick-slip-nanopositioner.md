---
title: "Stick-slip Nanopositioner"
category: electrophysiology
order: 1
summary: "Piezo stick-slip nanopositioner with effectively unlimited travel."
gallery: false
images:
  - /assets/img/electrophysiology/nanopositioner-1.jpg
  - /assets/img/electrophysiology/nanopositioner-2.jpg
  - /assets/img/electrophysiology/nanopositioner-3.jpg
build_status: coming_soon
---

A stick-slip nanopositioner for electrode placement in fly and moth
preparations.

## Links

*(Papers and websites for this tool)*

- [Reference paper](https://doi.org/10.1016/j.ohx.2022.e00317)
- [Nanopositioners playlist](https://www.youtube.com/playlist?list=PLu3g1bSKNvea5Te0lFSqtd8AIK4uVeLH7)

## Overview

{% include fig.html img="electrophysiology/nanopositioner-1.jpg" side="right" caption="Add a caption" %}

The Hwu stick-slip nanopositioner was originally designed for applications in Atomic Force Microscopy. Its slender footprint and long travel range make it a candidate for micropositioning in electrophysiology.  
While our implementation is open loop, there are also closed loop implementations in Hwu's work. The electronics in the original paper are deliberately chosen for their exceptionally low cost, and more modern chips and boards can be substituted in future builds.  
We believe that the main benefit of this design is the small footprint, which may allow for multiple positioners holding electrodes, to be stacked in parallel.
Multi axis designs may also be implemented

## Design & build

{% include fig.html img="electrophysiology/nanopositioner-2.jpg" side="left" caption="Add a caption" %}

The design is based on the principle of static and sliding friction. It uses a piezo stack between a cube-magnet and a linear slide carriage. When a low force piezo pushes the carriage of a linear slide, the magnet holds its place, due to static friction. When the pushing force of the piezo stack overcomes this static friction, then both the magnet and carriage can slide. By shaping the force asymmetrically, high resolution positioning can be achieved.  
For movement control, a sawtooth wave drives a piezo stack, and the shape and direction of the sawtooth determines the travel speed and direction. 

<!-- {% include fig.html img="electrophysiology/nanopositioner-3.jpg" caption="Add a caption" %} -->

## Stick-slip nanopositioner

- Based on En Te Hwu's design
- Piezo stack + magnet driven with a sawtooth wave from an audio amplifier
- Effectively "unlimited" travel range
- Step size: 30 nm – 2400 nm
- **Cost: ~$35 per axis**
