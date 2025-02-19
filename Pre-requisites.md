---
title: Basic requirements for OpenSPIM image processing
layout: page
description: Basic requirements for OpenSPIM image processing
---
## Hardware requirements

OpenSPIM image processing involves computationally relatively expensive steps particularly due to the size of the imaged dataset. Typical acquisition will consist of multiple views 100-400 MB each. Those large images have to be at least temporarily held in memory, usually in multiple copies and therefore we recommend to **invest in RAM**.

Most of the code involved in SPIMage processing is in Java and is multi-threaded, therefore investing in **multi-core processors** is also advisable.

The output of the SPIMage processing may increase the already substantial total raw data volume and so it is prudent to plan for **ample hard drive** space.

Multi-view deconvolution, 3d rendering and in general visualisation of SPIM data is placing high demands on graphics hardware (GPU). We recommend to invest in [CUDA capable graphics cards](https://www.nvidia.de/object/cuda_home_new.html) such as **NVIDIA
Tesla or Quadro or GeForce**.

Moving SPIM amount of data to and from the computer takes time and every network bottleneck between the end points should be removed starting with **10GigaBit Network Interface**.

The processing described in this tutorial is performed on the following hardware configuration:

`Processor : `**`Two``   ``Intel``   ``Xeon``   ``Processor``
 ``E5-2630`**` (`**`Six``   ``Core,``   ``2.30GHz``
 ``Turbo`**`, 15MB, 7.2 GT/s) `  
`Memory : `**`128GB`**` (16x8GB) 1600MHz DDR3 ECC RDIMM`  
`Hard Drive : `**`4x2TB`**` 3.5inch Serial ATA (7.200 Rpm) Hard Drive`  
`HDD Controller : PERC H310 SATA/SAS Controller for Dell Precision`  
`HDD Configuration : C1 SATA 3.5inch, 1-4 Hard Drives`  
`Graphics : `**`Dual``   ``2``   ``GB``   ``NVIDIA``   ``Quadro``
 ``4000`**` (2cards w/ 2DP & 1DVI-I each) (2DP-DVI & 2DVI-VGA adapter) (MRGA17H)`  
`Network : Intel X520-T2 Dual Port `**`10GbE``   ``Network``
 ``Interface``   ``Card`**

This is clearly a monster and it is not cheap (roughly 5000 Euros). Fortunately OpenSPIM data are not as humongous as SPIM data can be (for example from the commercial [Zeiss Lightsheet Z.1](http://www.zeiss.com/microscopy/en_de/products/imaging-systems/lightsheet-z-1.html), primarily due to limited frame rate achievable by the OpenSPIM. The configuration we recommend for processing OpenSPIM data should have:

`4 processors`  
`48 GB of RAM`  
`2TB of hard drive space`  
`one CUDA capable graphics card`

One can of course get by with an even lesser computer and the Fiji SPIM code offers several work arounds to be able to process on large SPIM data without the higher end hardware. BUT IT WILL TAKE TIME. Investing into a decent computer (Mac or PC) is a good idea.

One way to truly speed up OpenSPIMage processing is to perform it **in parallel on a cluster computer**. Since this is outside the scope to this tutorial we refer users to the [SPIM registration on a cluster](https://fiji.sc/SPIM_Registration_on_cluster) recipes on the Fiji wiki.

## Software requirements

All we need is love, I mean, [Fiji](https://fiji.sc).
