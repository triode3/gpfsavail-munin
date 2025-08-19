# README 
for the gpfsavail-munin script and templates for adding GPFS (available space) graphing to [Munin](https://munin-monitoring.org/)

This readme is broken into a few small sections: What,  Why, How to install, How to change, License. 

# What is this thing?

This readme assumes you know what [Munin](https://munin-monitoring.org/) is all about, and that you know, or are using IBM GPFS (now called Storage Scale). 

This plugin is for trending available space in gpfs with munin. 

An example output with three gpfs filesystems is given below.

![screenshot of gpfsavail-munin for three gpfs filesystems](https://github.com/triode3/gpfsavail-munin/blob/main/images/gpfs-avail.png)


# Why did I make this?

You are probably asking:

- Doesn't gpfs give warnings when available space is low? (Why yes, it can)
- Couldn't I gleam this information from teh other plugin? (Why yes, you could)
- Could I not just type df at a prompt? (Of course you can)

And I would say, well, it was really simple to graph the available space in munin, and it gives a nice trending picture (gee, available space on gpfs2 is going _up?_) Honestly, it is nice to have a graph, and also cool in that it turns yellow when the available space drops below the warning levels (set in the plugin). 

# How to install it.

There is only the plugin file that is mandatory for this plugin:

- **gpfsavail**                       # the script to make it go

Put the gpfsavail in /usr/share/munin/plugins/. If your distributtion (or your own build) of munin puts the actual plugins in another location, place the plugin there.

Link it in the /etc/munin/plugins directory (e.g. ln -s /usr/share/munin/plugins/gpfsavail /etc/munin/plugins/gpfsavail). Again, if you installed the "etc"/munin/plugins somewhere else, reflect that change here. 

# How to change it, etc. 

There are docs in the **gpfsavail** plugin on changing it, basically you will **need** to change the filesystem names if your are not "gpfs1", "gpfs2", "gpfs3". A simple search/replace on the gpfsavail plugin for those three names will get you there. 


# LICENSE

GNU GENERAL PUBLIC LICENSE (see LICENSE.md)

A copy of the GPL3 is included with this software. (see gpl-3.0.txt)




