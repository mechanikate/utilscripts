<h1 align="center">utilscripts</h1>
<a href="https://github.com/mechanikate/utilscripts">utilscripts</a> is my personal compendium of useful scripts for my Linux installations, all of which should just work on regular <code>bash</code> and plain ol' Linux.
<h3>Features:</h3>
<ul>
    <li>
        <a href="https://github.com/mechanikate/utilscripts/blob/main/cata-src/cata"><code>cata</code></a>, a script to <code>cat</code> all the files in a directory specified or <code>.</code> if unspecified
    </li>
    <li>
        <a href="https://github.com/mechanikate/utilscripts/blob/main/mvln-src/mvln"><code>mvln</code></a>, a script to <code>mv</code> a file/directory and <code>ln -s</code> (symlink/symbolic link) it back to where it started. Sourced almost entirely from <a href="https://unix.stackexchange.com/a/228166">this StackOverflow answer</a>
    </li>
    <li>
        <a href="https://github.com/mechanikate/utilscripts/blob/main/wtfetch-src/wtfetch"><code>wtfetch</code></a>, a script to print out your hardware & shell specs, and optionally export them to a folder, similar to <a href="https://github.com/dylanaraps/neofetch"><code>neofetch</code></a> but more barebones
</ul>

<h2>Using the scripts</h2>
This is some brief documentation on how to use each of the scripts.
<h3>cata</h3>
<code>cata</code> can be used in the following format:

```
cata [folder]
```
where `folder` is the folder to `cat` all the files of. If this argument is unspecified, it defaults to the current directory (`./*`).

<h3>mvln</h3>
<code>mvln</code> can be used as follows:

```
mvln <file/folder> <folder>
```

where the first parameter, `<file/folder>`, is the source/where the file/folder to be moved is, and the second parameter, `<folder>`, is the folder to move the first parameter to. Both of these parameters are required.

<h3>wtfetch</h3>
<code>wtfetch</code> can be used as follows:

```
wtfetch [export [folder]]
```

where `export` is a parameter where you can optionally specify the folder name to export the specs to, defaulting to `./specs/`. By default, this prints out the specs without exporting it to any files.

For example, on an Acer Chromebook R11, this is the input and output:
```bash
$ wtfetch export specsfolder
Software:
---------
OS:     |-> Arch (Linux)
        |-> Username: -> kate
        |-> Hostname: -> katepc
        |-> Shell: -> zsh
        \-> Kernel version: -> 6.14.5-arch1-1

Hardware:
---------
CPU:    |-> Intel Celeron CPU N3060
        |-> Architecture: -> x86_64
        \-> Frequency: -> 2.480 GHz (2480000 Hz)

RAM:    |-> 2.7G/3.8G (2895736832/4041543680 B)
Exporting to folder specsfolder...
```
Then, printing out `specsfolder/`'s contents:
```bash
$ cata specsfolder
specsfolder/cpu:
Intel Celeron CPU N3060
x86_64
2480000
2.480 GHz

specsfolder/mem:
4041543680
3.8G

specsfolder/os:
Arch
kate
katepc
zsh
6.14.5-arch1-1
```
