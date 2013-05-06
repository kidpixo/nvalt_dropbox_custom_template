## Readme

The idea behind this is to have a unique configuration for nvALT custom css and shared between different machines.
I used Dropx to achive this, but you can use any location reachable from your machine.

### Use the shared template

1. Copy the whole `nvalt_dropbox_custom_template` folder to your Dropbox folder
2. Copy `template.html` to your `~/Library/Application\ Support/nvALT/`
3. Customize the `template.html` searching for the string : </br>
    `[CUSTOMIZE WITH YOUR DROPBOX PATH]` </br>
  ans substitute it with your Dropbox path to `nvalt_dropbox_custom_template` (amazing, uh?)
4. Now you can erase everything from your `~/Library/Application\ Support/nvALT/`, all the ncessary files are on Dropbox

### Customize it!

In `template.html` search for the lines :

     <!-- Import Stylesheet -->
      <style type="text/css">
         @import url("[CUSTOMIZE WITH YOUR DROPBOX PATH]/nvalt_dropbox_custom_template/custom.css");    
      </style>
     <!-- Import Stylesheet for code highlight -->
      <link rel="stylesheet" href="file://[CUSTOMIZE WITH YOUR DROPBOX PATH]/nvalt_dropbox_custom_template//code_highlight/github.css">

Change the first CSS with one of your choice in `/styles`, for the main document style, and the second with one from `/code_highlight`, for different highlight styles.


I included a couple of css found in Marked.app, thank thanks to [Brett Terpstra](http://brettterpstra.com) again.

### NOTE: Where is the javascript?

You may notice I referred to the  [highlight](http://softwaremaniacs.org/soft/highlight/en/download/) and [jquery](http://jquery.com/) version from Dropbox and not using the one in the Brett's original Lopash pacakge.

    <script src="file://[CUSTOMIZE WITH YOUR DROPBOX PATH]/nvalt_dropbox_custom_template/jquery.min.js"></script>
    [...]
    <script src="file://[CUSTOMIZE WITH YOUR DROPBOX PATH]/nvalt_dropbox_custom_template/nvALT/highlight.pack.js"></script>

The reason is to leave open the possibility to adapt the two scripts to your needs.

I am for example considering to extend the highlighted languages consisently on all my machine, or to include the whole jquery package.

### Common Error

The javascript inclusion needs the whole path on your machine, for example Mac Os :

    <script src="file:///Users/kidpixo/Documents/Dropbox/nvalt_dropbox_custom_template/....

notice that your final path should start with the / like this `file:///Users` ! 

On the othe side the CSS inclusion need only the full path to your file, something like

         @import url("/Users/kidpixo/Documents/Dropbox/nvalt_dropbox_custom_template/custom.css");    


I did the mistakes myself :-P and they are hard to find!


---

## Original Readme for Lopash by Brett Terpstra

---

### Lopash for nvALT

The Lopash theme was originally created by [Erik Sagen](http://www.kartooner.com) for [Marked](http://markedapp.com), and modified by [Brett Terpstra](http://brettterpstra.com) for use with [nvALT](http://brettterpstra.com/projects/nvalt/).

This version is copyright Brett Terpstra, 2013. It is free for unlimited use with nvALT, but may not be re-purposed or published without permission.

### What you'll get

* The Lopash theme from the upcoming version of [Marked](http://markedapp.com), complete with custom web fonts.
* Automatic highlighting of code blocks with [highlight.js](http://softwaremaniacs.org/soft/highlight/en/)
* A basic implementation of [Widon't](http://shauninman.com/archive/2006/08/22/widont_wordpress_plugin) for headlines.
* Smooth scrolling when clicking footnotes and anchors.
* A "back to top" link that appears when scrolling down a note.

### Installation

First, back up any custom files you've created previously. You can always restore the default just by deleting the `custom.css` and `template.html` files from `[User Home]/Library/Application Support/nvALT/`.

Copy the files in the zip folder to `[User Home]/Library/Application Support/nvALT/`. If the "nvALT" folder doesn't exist, create it or simply drag the folder you unzipped into **[User Home]→Library→Application Support**.

You should have the following files in your Support folder:

    custom.css
    highlight.pack.js
    jquery.min.js
    solarized_dark.css
    solarized_light.css
    template.html

Solarized Light is included in case you prefer it with the theme, and can be switched in with a quick edit in template.html (near the top).

nvALT will automatically pick up this new theme even if it's already running. After switching notes you should see the change.
