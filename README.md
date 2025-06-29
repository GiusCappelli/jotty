<p align="center">
  <img src="logo.png" alt="Jotty Logo" width="500"/>
</p>

<h1 align="center">Jotty</h1>

<p align="center">
  Minimalist command-line note-taking tool.
</p>

# Jotty

> "Oh that's a great idea... let me just jot that down..."
>
> -- <cite> Me, always </cite>

One way to truly become organized is to note down anything that comes to mind *as* it comes to mind: to jot down your thoughts. The obvious next step is to keep an agenda in which you note the day you're taking notes, and then jot away anything you're thinking. With Jotty you'll do the same from the comfort of the CLI.

Simply launch `jotty new` and jot down your thoughts with your favorite text editor (nvim by default). Your notes are saved as .txt files with the name of the day (YYYY-MM-DD.txt) in the `$HOME/notes` folder. You can easily change the editor and the notes' extension and folder (See Installation, Step 1).

Jotty offers a simple search functionality. You can search for a specific keyword (`jotty search <keyword>`), or for all the notes in a specific year (`jotty search-year <YYYY>`) or month (`jotty search-month <YYYY-MM>`).

Quickly open notes by typing `jotty view <YYYY-MM-DD>`. Keep using `jotty new` to open today's notes. List all notes in your folder with `jotty list`.

All jotty search commands as well as the jotty list command output the file names followed by the first line of the notes. Consider adding a "header" to all your notes in which you summarize the contents of that day's jotting session. This will allow you to recognize notes immediately: finding the notes you took for that one thing you were doing two months ago will be easier.

And that's it. For me, Jotty takes the sweetspot for a simple and usefult CLI tool to quickly take notes and keep them organized by their date. 

Jot away!

Caps


## Installation
1. Clone the repository
```
   git clone https://github.com/GiusCappelli/jotty.git
   cd jotty
```
(Optional) open jotty with your text editor and modify `EDITOR` if you use something else than neovim. Also modify `NOTES_DIR` to change the deafult directory for your notes, and the extension at line 8 from `.txt` to any other extension you might want to use instead (like .md).

2. Make the jotty script exectuable
```bash
   chmod +x jotty
```

3. Move it to a directory in your `$PATH` (for example `~/bin`):

```bash
   mv jotty ~/bin/
```
Or, if you want system-wide access (requires `sudo`):

```bash
   sudo mv jotty /usr/local/bin/
```

4. Verify it works:
```bash
   jotty help
```
You're set :).

## License
MIT - free for personal or professional use.

## Dependencies
- bash
- a text editor. I use neovim, but you can customize it (see Step 1 of Installation).
- grep, find, head, tr, and cut (common GNU utilities, you should have these).

## Usage

We already went over it, but just in case: 

### Create or Edit Today's Note

`jotty new`

Opens today's note in your editor (`nvim` by default). The note is saved as `~/jotty/YYYY-MM-DD.txt` by default.

### Search jotty by Keyword (with snippet preview)

`jotty search <keyword>`

Example:

`jotty search homelab`

Output:

```
2025-06-10.txt: Set up the homelab storage. Installed Tailscale on main node. AI node pending.
2025-06-14.txt: Planning network structure for homelab. Will test SSH tunnels between nodes.
```

### Search Notes by Month

`jotty search-month <YYYY-MM>`

For example:

`jotty search-month 2025-06`

Lists all notes from June 2025 with a snippet preview.


### Search Notes by Year

`jotty search-year <YYYY>`

For example:

`jotty search-year 2025`

Lists all notes from 2025 with snippet previews.

### View a Specific Note

`jotty view 2025-06-10`

Open that day's note in your editor

### List all notes

`jotty list`

Lists all note files in the notes directory. 
