# OmniFocus 2 Modifications Readme

Welcome to my little OmniFocus 2 mod repository. Feel free to screw around with the attached scripts and offer any feedback. You can tell me directly on Twitter ([@poritsky](https://twitter.com/poritsky)) or here on GitHub.

All I ask is that you keep this under your hat for a bit. By that I mean: no blogging about this, no repackaging it as your own.

I realize this is a public repository and all, but this is presently a work-in-progress. All feedback is welcome. Eventually I'll document the ideas behind these mods more fully on [the candler blog](http://candlerblog.com). Until then, let me know what you think and enjoy. And get back to work, dammit.

## Introduction

OmniFocus 2 for Mac introduced a few things I really like, but also took away many things I had grown used to in the original OmniFocus. These hacks are attempts to bring some of those features back. They are kludgy, but they help.

These are meant to be used *only* with OmniFocus 2 Pro. A few things I recommend before using these:

- Get the [Icons & Coffee Perspective Icons 2](http://iconsandcoffee.com/perspective-icons-2/) pack
- Use the hidden compact layout by putting the following URL in Safari and restarting OmniFocus 2 `omnifocus:///change-preference?ContentLayout=compact`
- Check out other hidden settings listed by Jason Verly here: http://braintags.com/blog/2014/05/omnifocus-2-configuration/

These are by no means required, but the scripts were all designed with the above setup.

Also, I've included an Alfred Workflow for running these scripts, but I've excluded general documentation on how to run the scripts. One thing to keep in mind is that whatever application you choose to run the script with (including AppleScript Editor) will need Accessibility access to your system. On first run, you will get prompted to give the application access. This is managed in System Preferences > Security & Privacy > Accessibility.

One more thing: the scripts will all act weird in fullscreen mode. I don't recommend using them there. Okay. On to the fun.

## Brain Dump.scpt

I don’t really adhere to GTD that closely, so I use the term “brain dump” loosely. For me, it’s just any time I feel like listing items in my Inbox without any clutter. I like to make OmniFocus look like almost completely blank when I do this. The Brain Dump script does three things:

- Turns off the Sidebar (left), Inspector (right) and Toolbar (top)
- Switches to your Inbox
- Shrinks and centers the main OmniFocus window

## Exit Brain Dump.scpt

Exit Brain Dump does the opposite of Brain Dump. Essentially it “normalizes” the window back to a reasonable size and adds the Sidebar, Inspector and Toolbar back.

## Inbox View.scpt

The idea behind Inbox View is to bring back one of the key features from OmniFocus 1 that didn’t make the cut in the redesign: the ability to file Inbox items into Projects.

Not to editorialize too much, but this is a *massive* failing of OmniFocus 2. Out of the box, all you can do to file Inbox items is to drag them to the Projects tab in the Sidebar, where, once dropped, each action will be turned into a new project. Or you can type the projects in to each task like a schmuck.

Inbox View fixes this filing problem with the following hack (recommended, if I recall, by Omni’s own ninjas):

- Changes the current window to the Projects view
- Creates a second window in Inbox view
- Moves the left edge of the Inbox window rightward 305px, which should line up exactly with the right edge of the project list in your Project window

Now you can drag Inbox items to Projects from one window to the next. To “exit” this view, just close the Inbox window.

## OmniFocus 2 Windows.alfredworkflow

Brings together the above 3 scripts in Alfred. I’ve been using the shortcut `ofw` (for OmniFocus Windows) to bring them up, but I’m not sure that that’s memorable enough.

## OFIFontRegistry.plist

Call me old fashioned, but I love Lucida Grande for my tasks because it looks great small. With OmniFocus 2’s compact layout turned on, I wanted Lucida Grande back at smaller sizes. And I really never liked Approxima Nova, the font used almost universally in OmniFocus 2. 

This .plist file will modify the look of OmniFocus. Think of it as light theming.

**Installation:**

- Move the modified `OFIFontRegistry.plist` provided here to `~/Library/Containers/com.omnigroup.OmniFocus2/Data/Library/Application Support/OmniFocus/`
	- A faster way to get to this location is to go to select `File > Show Backups…` in OmniFocus, then go up one folder in Finder
	- This method is more fully [documented on the OmniFocus forums](https://discourse.omnigroup.com/t/how-to-guide-create-your-own-custom-unsupported-themes-for-omnifocus-2/6774/8)
- Restart OmniFocus

Voila. I’ve used all system fonts (Avenir Next, Lucida Grande and Helvetica Neue) so you should see a dramatic change on restart. If you want to revert to the original, just delete or rename the modified `OFIFontRegistry.plist`. This file should stay intact even through app updates.