## Update 

* March 2016 - Supports 3.6 

* March 1, 2016 - Based on suggestion by @aaronmw in Issue #1, The BG layer will now redraw around the text and not the other way round. 
![sketch dynamic button](https://cloud.githubusercontent.com/assets/5616123/13418613/13e8a00c-df45-11e5-9957-f16ec23b773f.gif)



# Dynamic button plugin for Sketch.app 3.5 onward

Dynamic button plug-in for [Sketch.app](http://bohemiancoding.com/sketch/) allows to create buttons with fixed paddings no matter what text you add. 

## Documentation

1: Remove the old dynamic button plugin if you have one. 

2: Checkout the Demo

[![Demo Video](https://i.imgur.com/KPqbgwJ.png)](https://www.dropbox.com/s/9eqlfsb6jslnonl/Dynamic%20Button%203.5.mov?dl=0)

3: For more info refer to the old [README](https://github.com/ddwht/sketch-dynamic-button/blob/master/README.md) 



## Detailed Update:

I had initially logged the issue [here](https://github.com/ddwht/sketch-dynamic-button/issues/30) but the old repo seems to have been abandoned. Thought I'd take a stab at it. I had no clue whatsoever but soon I managed to atleast run the script via the Custom plugin option in Sketch. I then used console.app in mac to view the log messages. 

[This post](http://hackingui.com/design/how-to-create-a-sketch-plugin/) was of great help to get me started. The [Sketch Plugins Cookbook](https://github.com/turbobabr/Sketch-Plugins-Cookbook) was immensely helpful. The plugin library by Sketch wasn't very helpful honestly. Soon after debugging and logging I isolated the issue to the 'resizeRoot' 

    resizeRoot: Available in Sketch 3.4 and below, 
    removed in Sketch 3.5 (see resizeToFitChildrenWithOption:). Resizes the group to fit around all of its sub-layers.

I then played around with it and go a single button working however for multiple text layers, it was adding the BG layer on top of the text. The old layer was somehow only working for the first layer in the loop. I simply switch the logic to insert the BF layer first and then insert my text later. That seemed to have worked. 

Tested it out manually, working well so far. 






