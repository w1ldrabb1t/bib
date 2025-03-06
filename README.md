# bib (a CLI Bible reference tool)

bib is a CLI program that quickly prints Bible verses to the Terminal, using markdown files for the Bible generated by my [BibleGateway-to-Obsidian script](https://github.com/prestonharberts/biblegateway-to-obsidian).

Soon I will include the NET translation as its copyright allows for redistribution.

## Features

- Verse-by-verse format
- Specified verse is shown in red
- Editorial headings are kept intact
- New paragraphs are shown with an arrow
- Ability to view multiple verses or a verse section
- Certain translation show words in italic, and I put them in brackets here
- Hyphenated text to give the appearance of justified text alignment
- Works on a variety of terminal sizes

## Usage

I recommend putting this script in your PATH so that it can be called from anywhere. I made a Bin folder in my user directory, moved bib to it, and added this line to my `.bashrc`:

```bash
export PATH=/home/$USER/Bin/:$PATH
```

Next, give execution privileges to bib:

```bash
chmod u+x ~/Bin/bib
```

Here are some example usecases. By default, the previous and next 2 verses are also printed to show context. The specific verse you request is printed in red to stand out from the context verses.

```bash
# this prints the entire Genesis 1 chapter
bib gen1

# this prints just Genesis 1:1 (and context verses Genesis 1:2-3)
bib gen1 1

# this prints the verses Genesis 1:1-2 (no context verses are printed)
bib gen1 1 2

# this prints John 3:16 (without any context verses)
bib -c john3 16
```

### Example (NKJV)

Until I get the NET translation working, here is an example of the program running with the [New King James Version](https://www.biblegateway.com/versions/New-King-James-Version-NKJV-Bible/):

<p align=center><img src="https://github.com/user-attachments/assets/878d0824-dbb9-492f-9b13-525107623619" width="512"></p>

Scripture taken from the New King James Version®. Copyright © 1982 by Thomas Nelson. Used by permission. All rights reserved.

### Copying text

Included in this repo is a program `bibcopy` that copies entire chapters at a time, reformats them, and lets me paste them into [Monkeytype](https://monkeytype.com/). It's formatted to be very minimal and looks like this in the NKJV:

<p align=center><img src="https://github.com/user-attachments/assets/d8b225cb-54fc-4652-94e6-20fda4cb3e00" width="512"></p>

Support to automatically copy what you see with Bib isn't fully supported, but it would be done like this if you can remove the color codes that get introduced with my code. Just make sure to install `xclip`.

```bash
bib john3 16|xclip -sel clipboard
```

I recommend just running bib multiple times in a row similar to this, and then just copying the output from the terminal:

<p align=center><img src="https://github.com/user-attachments/assets/0c2a8efe-93db-4146-947b-ea3d8b9f24a7" width="512"></p>
