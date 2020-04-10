node-red-contrib-image-tools
============================

A <a href="http://nodered.org" target="_new">Node-RED</a> node to perform functions on images and decode barcodes.

IMPORTANT - Breaking changes in V1
---------
Version 1 has breaking change ~ vs ~ V0.x versions.
Existing flows using the "2D Barcode Decode" node will need to be modified. The easy way of fixing this is to delete any "2D Barchode Decode" & deploy, then update the node, then re-add the new "Barcode Decode" nodes.

Alternatively, you can avoid this issue by performing the following steps...

1. Upgrade node-red-contrib-image-tools
1. Stop node-red
1. Make a bakup of your flow.json file
1. Opening your flow.json file in a text editor 
1. Search / replace all instances of `"type":"2D Barcode Decoder"` with `"type":"Barcode Decoder"`
1. Save and close your flow file
1. Start node-red



FEATURES
--------
* image viewer node
  * View images in the node-red editor (for preview / debug purposes)
  * **Full credit** to [rikukissa](https://github.com/rikukissa) and [dceejay](https://github.com/dceejay) for the excellent [node-red-contrib-image-output](https://github.com/rikukissa/node-red-contrib-image-output) on which the "image viewer node" is heavily based. (Copy of MIT license included in src files as requested)
  * Features include ability to display a jimp image, buffer, file name, base64 string, Data URL, Image URL.
  * Works in Internet Explorer (IE11 tested)


* image node
  * Read image from file, http, base64 string or buffer
  * Create blank image by setting Image field to an object `{"w":100,"h":100,"background":0}`
  * Print text to an image
  * Over 40 image function built in with many more possible by using [convolution kernels](https://en.wikipedia.org/wiki/Kernel_(image_processing))
  * Perform 1 or more images processes in each node
    * TIP: you can convert a function to batch JSON my clicking the button adjacent to the function dropdown field
  * All function parameters can be either fixed or passed in by msg/flow/global
  * Can output image data as a buffer or base64 string.
  * All functions and parameters are self doumenting - a tip under each item in the node editor helps the user


* Barcode Decode node
  * Ability to decode 1D, QR and Data Matrix barcodes. See [supported formats](https://www.npmjs.com/package/@zxing/library#supported-formats).


* Other...
  * Built in examples.  
    * **In node-red, look under the hamburger menu >> import >> examples >> image tools**

Screen shots
------------

Get image from internet...<br>
![chrome_2019-06-08_15-50-57](https://user-images.githubusercontent.com/44235289/59148818-421a4c00-8a05-11e9-8dd1-08342298132a.png)

Image processing...<br>
![Image_processing](https://user-images.githubusercontent.com/44235289/59148882-30857400-8a06-11e9-9b7a-227e761bd617.png)

Printing text...<br>
![printing_text](https://user-images.githubusercontent.com/44235289/59148604-fcf51a80-8a02-11e9-9a6b-f1578d6ee391.gif)

Barcode decoding...<br>
![barcode](https://user-images.githubusercontent.com/44235289/79021999-e5cc0f80-7b74-11ea-8cd5-456497313671.gif)


Pre-requesites
--------------

None!


Install
-------

Run the following command in the root directory of your Node-RED install.
(Usually this is `~/.node-red` or `%userprofile%\.node-red`).

Install from GIT

    npm install Steve-Mcl/node-red-contrib-image-tools

Install from NPM 

    npm install node-red-contrib-image-tools 

Alternatively, install from a folder

    npm install c:/tempfolder/node-red-contrib-image-tools

Or simply copy the folder `node-red-contrib-image-tools` into a folder named `nodes` inside your node-red folder then `cd` into `nodes/node-red-contrib-image-tools` and execute `npm install`

NOTES
-----
* Tested on Node V 10 only. YMMV
* Bugs are likely :)

KNOWN ISSUES
------------
Clicking the preview image in IE doesnt dismiss it (works in chrome)

