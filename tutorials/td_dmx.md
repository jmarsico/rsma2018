---
layout: subpage
title: "TouchDesigner, Pixelmapping + DMX"
---

<img 
src="{{site.baseurl}}/assets/td_pixlite_diagram.png" 
style="max-width: 600px;" 
/>

> Download the [td_pixelmapper.toe](xxxx) file from the [TouchDesigner Examples](https://drive.google.com/drive/folders/144ml7hfzFDR0Y7ZKa4WMo_aPQbVOkqTP?usp=sharing) folder on Google Drive. 

> Download and install the PixLite Assistant Software for [macOS](https://itunes.apple.com/us/app/advatek-assistant/id990140692?ls=1&mt=12) or [Windows](https://www.advateklights.com/download/928/)


## What is DMX?

DMX is a protocol standard for communicating with and controlling "addressable" lights. This is the standard communication protocol for theatrical lighting, stage lighting and most architectural lighting. 

> From Wikipedia: DMX512 (Digital Multiplex) is a standard for digital communication networks that are commonly used to control stage lighting and effects. It was originally intended as a standardized method for controlling light dimmers, which, prior to DMX512, had employed various incompatible proprietary protocols. It soon became the primary method for linking controllers (such as a lighting console) to dimmers and special effects devices such as fog machines and intelligent lights. DMX has also expanded to uses in non-theatrical interior and architectural lighting, at scales ranging from strings of Christmas lights to electronic billboards. DMX can now be used to control almost anything, reflecting its popularity in theaters and venues.


<img 
src="https://upload.wikimedia.org/wikipedia/commons/thumb/6/62/SimpleDmxUniverse.gif/1200px-SimpleDmxUniverse.gif" 
style="max-width: 600px;" 
/>


#### Some Facts:

- DMX can control up to 512 `channels`. 
- Each channel has 256 steps of resolution (0-255). 
- Each group of 512 channels is called a `universe`
- DMX is a "bus" protocol, which means that with every frame, a DMX `controller` communicates all of its channel information. 
- Each `slave device` is has a `start address`, and only listens to the parts of the DMX packet that pertain to its address.
- Standard DMX is traditionally transmitted with 3-pin or 5-pin XLR-style cables and connectors.

<img 
src="https://upload.wikimedia.org/wikipedia/commons/thumb/1/1c/XLR5_pinouts.svg/600px-XLR5_pinouts.svg.png" 
style="max-width: 200px;" 
/>


### What is sACN E1.31?
DMX can be sent over a network as well. There are two ways of doing this. [Art-Net](https://en.wikipedia.org/wiki/Art-Net) is the older and less robust protocol. [E1.31 Streaming ACN (sACN)](https://opendmx.net/index.php/E1.31) is newer, easier to use and more robust. We will be using sACN to communicate between TouchDesigner and our PixLite controllers.


## What are Addressable LEDs
It is important to know that most "addressable LEDs" do NOT use the DMX protocol. Most "addressable LEDs" require some piece of hardware to sit between them and a DMX controller. In our case, we will be sending DMX over sACN to our PixLite controllers. The PixLite controllers will then translate our DMX signal into another protocol that the LEDs can understand.

### LED Addressing
The LED strands that we are using are addressed sequentially, starting from the "pixel" that is nearest to the PixLite controller. 




