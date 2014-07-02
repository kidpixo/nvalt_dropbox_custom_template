## Readme

The idea behind this is to have a unique configuration for nvALT custom css shared between different machines.
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
      <link rel="stylesheet" href="file:///Users/damo_ma/Documents/Dropbox/ApplicationSupportDB/nvALT/styles/custom_BRETT.css">
     <!-- Import Stylesheet for code highlight -->
      <link rel="stylesheet" href="file:///Users/damo_ma/Documents/Dropbox/ApplicationSupportDB/nvALT/code_highlight/sunburst.css">

Change the first CSS with one of your choice in `/styles`, for the main document style, and the second with one from `/code_highlight`, for different highlight styles.


I included a couple of css found in Marked.app, thank thanks to [Brett Terpstra](http://brettterpstra.com) again.

### EDIT : Table Of Contents

After Brett's post [A GitHub README table of contents Service
](http://brettterpstra.com/2014/07/01/github-toc-service/) (thanks for the hints!)

I added a small javascript in the `template.html` to create a Table of Contents on the fly.

I suggest to use header 1 or 2 for the ToC (# or ##), if greater the added margins could mess up (it's a bug, but let's think it's a feature :-)

**Note** : The table is created **only** if the id='toc' is found in document. This way you can easily switch it on and off.

You can customize the id to attache the table to in the `template.html`, there some some indication in the `template.html` file.

I'm less than good at javascript, I just grab some code [here](http://codepen.io/chriscoyier/pen/EnLwb) (thanks [Chris Coyer](http://codepen.io/chriscoyier/)) and modified a bit for my purpose.

Now I scans all the header and add left margin to the `<li>` elements via

    <li style="margin-left: 10px;">
	 Some stuff
	 </li>

The loop does :

- fix the "base index" as first header element found.
- set indentation equal to `(actual_index-base_index)*margin_pixels`, 

`margin_pixels` is 10 pixel by default, adjust it here below to have less or more space  in the `template.html` file.

Some example :

	<h2> -> <h2>
	<h3> -> <h3 style="margin-left:10px;">
	<h4> -> <h4 style="margin-left:20px;">
	<h2> -> <h2>
	<h3> -> <h3 style="margin-left:10px;">
	<h2> -> <h2>

or something like :

		h2
		  h3
		   h4
		h2
		  h3
		h2


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
