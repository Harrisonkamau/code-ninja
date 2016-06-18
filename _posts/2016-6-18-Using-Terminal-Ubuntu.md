---
layout: post
title: Using Linux Terminal
---

<h1>Introduction</h1>
<p>Whether you’re a new Linux user or you’ve been using Linux for a while, we’ll help you get started with the terminal. The terminal isn’t something you should be scared of – it’s a powerful tool with lots of uses.</p>

<h2>Basic Terminal Usage</h2>
<p>Launch a terminal from your desktop’s application menu and you will see the bash shell. There are other shells, but most Linux distributions use bash by default.</p>

<h2>Installing Software</h2>
<p>One of the most efficient things to do from the terminal is install software. Software management applications like the Ubuntu Software Center are fancy frontends to the few terminal commands they use in the background. Instead of clicking around and selecting applications one-by-one, you can install them with a terminal command. You even even install multiple applications with a single command.</p>
<p>On Ubuntu (other distributions have their own package management systems), the command to install a new software package is:</p>
~~~
sudo apt-get install packagename
~~~

<h2>Working With Directories and Files</h2>
<p>The shell looks in the current directory unless you specify another directory. For example, nano is an easy-to-use terminal text editor. The command nano document1 tells nano to launch and open the file named document1 from the current directory. If you wanted to open a document located in another directory, you’d need to specify the full path to the file – for example, nano /home/chris/Documents/document1 </p>
<p>If you specify a path to a file that does not exist, nano (and many other programs) will create a new, blank file at that location and open it.</p>
<p>To work with files and directories, you will need to know a few basic commands:</p>
<ul>
  <li><strong>cd -</strong>That ~ to the left of the prompt represents your home directory (that’s /home/you), which is the terminal’s default directory. To change to another directory, you can use the cd command. For example cd / would change to the root directory, cd Downloads would change to the Downloads directory inside the current directory (so this only opens your Downloads directory if the terminal is in your home directory), cd /home/you/Downloads would change to your Downloads directory from anywhere in the system, cd ~ would change to your home directory, and cd .. would go up a directory.
  </li>
  <li><strong>ls -</strong>The ls command lists the files in the current directory.</li>
  <li><strong>mkdir -</strong> The mkdir command makes a new directory. mkdir example would create a new directory named example in the current directory, while mkdir /home/you/Downloads/test would create a new directory named test in your Downloads directory.</li>
  <li><strong>rm -</strong> The rm command removes a file. For example, rm example removes the file named example in the current directory and rm /home/you/Downloads/example removes the file named example in the Downloads directory.</li>
  <li><strong>cp -</strong> The cp command copies a file from one location to another. For example, cp example /home/you/Downloads copies the file named example in the current directory to /home/you/Downloads.</li>
  <li><strong>mv -</strong>The mv command moves a file from one location to another. It works exactly like the cp command above, but moves the file instead of creating a copy. mv can also be used to rename files. For example, mv original renamed moves a file named original in the current directory to a file named renamed in the current directory, effectively renaming it.</li>
</ul>

<h2>Tab Completion</h2>
<p>Tab completion is a very useful trick. While typing something – a command, file name, or some other types of arguments – you can press Tab to autocomplete what you’re typing. For example, if you type <em>firef</em> at the terminal and press Tab, <em>firefox</em> automatically appears. This saves you from having to type things exactly – you can press Tab and the shell will finish typing for you. This also works with folders, file names, and package names. For example, you can type <strong>sudo apt-get install pidg</strong> and press <em>Tab</em> to automatically complete pidgin.</p>
<p>In many cases, the shell won’t know what you’re trying to type because there are multiple matches. Press the Tab key a second time and you’ll see a list of possible matches. Continue typing a few more letters to narrow things down and press Tab again to continue.</p>
