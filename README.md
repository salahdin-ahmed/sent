# sent
Simple plaintext presentation tool.

![slide example from sent](sent-bullets-s.png)

sent does not need latex, libreoffice or any other fancy file format, it uses
plaintext files to describe the slides and can include images via farbfeld.
Every paragraph represents a slide in the presentation.

The presentation is displayed in a simple X11 window. The content of each slide
is automatically scaled to fit the window and centered so you also don't have to
worry about alignment. Instead you can really concentrate on the content.


# Dependencies

You need Xlib and Xft to build sent and the [farbfeld](http://tools.suckless.org/farbfeld/) tools installed to use
images in your presentations.
## Void Linux
	# xbps-install farbfeld libXft-devel fontconfig-devel libX11-devel

# (Non-)Features

- A presentation is just a simple text file.
- Each paragraph represents one slide.
- Content is automatically scaled to fit the screen.
- UTF-8 is supported.
- Images can be displayed (no text on the same slide).
- Just around 1000 lines of C
- No different font styles (bold, italic, underline)
- No fancy layout options (different font sizes, different colors, …)
- No animations
- No support for automatic layouting paragraphs
- No export function. If you really need one, just use a shell script with xdotool and your favorite screenshot application.
- Slides with exuberant amount of lines or characters produce rendering glitches intentionally to prevent you from holding bad presentations.

# Features of this fork

- Change colors on the fly from command line options
- Inverted colors array for inverting main colors on the fly with a comman line options
- Toggle mouse cursor on the fly inside the sent window with a hotkey
- Progress bar for slides

# Usage

	$ sent [-f FONT] [-c FG-COLOR] [-b BG-COLOR] [-v] [-i] [FILE]

If *FILE* is omitted or equals `-`, stdin will be read. Produce image slides by
prepending a `@` in front of the filename as a single paragraph. Lines starting
with `#` will be ignored. A `\` at the beginning of the line escapes `@` and
`#`. A presentation file could look like this:

	sent
	
	@nyan.png
	
	depends on
	- Xlib
	- Xft
	- farbfeld
	
	sent FILENAME
	one slide per paragraph
	# This is a comment and will not be part of the presentation
	\# This and the next line start with backslashes
	
	\@FILE.png
	
	thanks / questions?

# Demo

To get a little demo, just type

	$ git clone https://github.com/salahdin-ahmed/sent
	$ cd sent
	$ make && ./sent example

You can navigate with the arrow keys, reload with `r`, hide cursor with `x` and quit with `q`.

# Install

	$ git clone https://github.com/salahdin-ahmed/sent # do not do this if you already have cloned the repo (do not repeat this step if you have already done it while trying the demo)
	$ cd sent # as mentioned above, don't repeat this
	# make clean install

and thats it, now you have sent installed.
