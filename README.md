This is a simple change to the original StashVideohasherNode script, which allows for the generation of sprites and previews on MacOS using the VideoToolbox hardware acceleration.

The original script is available at: https://github.com/stashapp/StashVideohasherNode

StashVideohasherNode script

This is a very simple script that can be run on multiple systems to process a large Stash import of scenes.  Instead of running cover, scrubber sprite, preview and phash generation tasks on the Stash server itself, this script will allow you to do the same thing on as many computers as you would like, with all of the nodes contributing back to the Stash server.

It requires Peolic's videohashes binaries (https://github.com/peolic/videohashes) that you just need to put into the same directory as this script, then update the script to reflect the filename that you saved the binaries with.

The script is pretty well commented, but if you have any questions you can message me on Discord.  If you know about this script, you know how to get me on there.  

It will process the queue in batches of 25 scenes per node, and tag that batch as "In Process" to keep other nodes from working on the same scenes.  As it finishes the scenes, it will keep going until there are less than 25 scenes left to be done.  Pretty simple actually.

Also please note, the script will pull scenes to process based on the lack of a phash.  So if you have a phash attached to a scene, the script won't load it for processing the other items.  Likewise the phash is the first thing generated, so if there is a failure on the cover image (for example) then the phash will be written to the scene and it won't be picked up for processing on a subsequent run.
