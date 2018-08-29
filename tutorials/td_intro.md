---
layout: subpage
title: "Intro to TouchDesigner"
---

<img 
src="{{site.baseurl}}/assets/touchdesigner.png" 
style="max-width: 600px;" 
/>

## What is TouchDesigner?

TouchDesigner is a node-based programming platform used primarily for visual content generation and delivery. From the [Derivative Website](https://www.derivative.ca/):

> TouchDesigner is a visual development platform that equips you with the tools you need to create stunning realtime projects and rich user experiences. Whether you're creating interactive media systems, architectural projections, live music visuals, or simply rapid-prototyping your latest creative impulse, TouchDesigner is the platform that can do it all.

We're using TouchDesigner in this course because it offers the lowest barrier to entry for getting interactive projects up and running. It comes packaged with pre-built functionality to integrate with commercial lighting systems, create sound, and communicate Arduino microcontrollers.

## First Things to Know

<iframe src="https://player.vimeo.com/video/160552892?color=fffffff&title=0&byline=0&portrait=0" width="600" height="338" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe>

## Operators

Projects in TouchDesigner are called "networks" and consist of several types of functional nodes called [operators](https://docs.derivative.ca/index.php?title=Operator).

Each operator has specific [parameters](https://docs.derivative.ca/Parameter) and [flags](https://docs.derivative.ca/Flag) that control different aspects of that operator's functionality.

Operators either create data (generators) or modify data (filters). We connect operators by drawing lines between the inputs and outputs of different operators. In this way, we are often able to see, in real time, how our data is being changed.

## Data

Data in Touchdesigner can be confusing. Raw data (tables, lists, collections) is usually handled by CHOPs and DATs.

### Data and CHOPs

CHOPs usually boil all forms of data into two dimensions: samples and channels. If you imagine a spreadsheet of data, you could potentially store that data in a CHOP in which each row of the spreadsheet is a _sample_ and each column is a _channel_ or VICE VERSA. This makes more sense when you think of a streaming signal. Take a look at the image below:

<img
src="{{site.baseurl}}/assets/td_data.png"
style="max-width: 600px;"
/>

You can see that we have a `noise` CHOP with its parameters and a `chopto` DAT and its parameters. The `noise` CHOP has three `channels`, each with different shaped signal-like lines. Looking at the parameters window above the CHOP, you'll see we are on the `channel` tab, we have three channels written out `chan1`, `chan2`, `chan3`. We have a start number of 0 and an end number of 1999. Next to the start and end sliders, you'll see a dropdown in which we've selected `I`, which stands for "samples". In this configuration, we have three `channels` and 2000 `samples`. This is our collection of data as stored in a CHOP.

Next to that CHOP is a `chopto` DAT, which takes data from a CHOP and populates an internal data container. In the parameters of that DAT, you'll see we've chosen the `output` to "column per channel". This means that each channel will have it's own column and each sample will occupy a new row.
