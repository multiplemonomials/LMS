# Legendary Moonlight Sculptor Re-Edit and Re-Publish Project
This repository is an effort to re-edit and republish all of the Legendary Moonlight Sculptor (LMS) e-books via an open-source, collaboration-friendly setup. 

The [Re:VIEW](https://reviewml.org/) ebook generator is used to compile ebooks from plain text markup. This tool is not super well known (in the English speaking world at least), but is incredibly powerful and meets the requirements of:

- Generating an ebook in EPUB format
- Operating on plain-text source files which can be easily version controlled
- Having reasonable defaults (I didn't have to go too crazy configuring the styles and settings)
- Being able to run via GitHub Actions to generate all epub files

## Setting Up Re:VIEW

### Install Ruby
#### For Windows:
Install Ruby via [RubyInstaller](https://rubyinstaller.org/downloads/).  You will need the DevKit version.  Or, if you use MSYS2, you can also use MSYS2's pacman to install ruby.

### Install Re:VIEW
In any terminal:
```
$ gem install review
```

### Install Pandoc
#### On Windows: 
Install pandoc from [here](https://github.com/jgm/pandoc/releases/latest). It should auto add to your PATH.

#### On Ubuntu:
```
$ apt install pandoc
```

### Install Pandoc2review
```
$ gem install pandoc2review
```
## Compiling the EPUB for any volume:
Open a terminal in that volume's folder.  Then run:
```
$ rake epub
```

## Converting an ebook chapter to Re:VIEW format:
First, extract the .xhtml chapter from the ebook.  Then do:
```
pandoc2review --strip-emptydev /path/to/chapter.xhtml > chapter.re
```
NOTE: on Windows, use cmd, not PowerShell! Somehow using powershell screws up all the unicode text in the output file.