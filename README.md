# Dynamic button plugin for Sketch.app 3.5

Dynamic button plug-in for [Sketch.app](http://bohemiancoding.com/sketch/) allows to create buttons with fixed paddings no matter what text you add. 

## Update 
Version 1: Added support for 3.5 


## Documentation

1: Remove the old dynamic button plugin. Click on [Plugins>Manage Plugins..](https://i.imgur.com/iCCyNDv.png)

2: Checkout the Demo

[![Demo Video](https://i.imgur.com/KPqbgwJ.png)](https://www.dropbox.com/s/9eqlfsb6jslnonl/Dynamic%20Button%203.5.mov?dl=0)


3: For more info refer to the old [README](https://github.com/ddwht/sketch-dynamic-button/blob/master/README.md) 


## Detailed Update:

I was the one to initially log the issue [here](https://github.com/ddwht/sketch-dynamic-button/issues/30) but for I think this repo has been abandoned. So I took it upon myself to have a quick check. I had no clue whatsoever but soon I managed to atleast run the script via the Custom plugin option in Sketch. I then used console.app in mac to view the log messages. 

[This post](http://hackingui.com/design/how-to-create-a-sketch-plugin/) was of great help to get me started. The [Sketch Plugins Cookbook](https://github.com/turbobabr/Sketch-Plugins-Cookbook) was immensely helpful. The plugin library by Sketch wasn't very helpful honestly. Soon after debugging and logging I isolated the issue to the 'resizeRoot' 

    resizeRoot: Available in Sketch 3.4 and below, 
    removed in Sketch 3.5 (see resizeToFitChildrenWithOption:). Resizes the group to fit around all of its sub-layers.

I then played around with it and go a single button working however for multiple text layers, it was adding the BG layer on top of the text. The old layer was somehow only working for the first layer in the loop. I simply switch the logic to insert the BF layer first and then insert my text later. That seemed to have worked. 

Tested it out manually, working well so far. 






