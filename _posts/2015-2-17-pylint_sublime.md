---
layout: post
title: "Installing Sublime Pylint from Scratch"
date: 2015-2-17
---

#### Summary 

I'm an avid Python programmer and I love using Sublime, but I've always missed a nice linter for it. A [linter][] is a tool that checks your code in real time for "suspicious and non-portable constructs" that are most likely indicative of a bug. In practice, this means errors like bad indents or typos can be caught before you run the program preventing silly errors and speeding up a programmer's workflow. 

Part of what makes this tutorial necessary is that we are going to need four programs besides Sublime to get our Python linter working. These are as follows: 

* [Package Control][]: This is a Sublime application that allows you to install packages into the editor. 
* [SublimeLinter][]: This is a Sublime application that creates the framework for a variety of linters to be displayed. 
* [Pylint][]: This is a python program that actually takes care of the linting task. 
* [SublimeLinter-pylint][]: This is the plug-in that connects the display ability of SublimeLinter with the Pylint engine. 

To set all of these up required five or so different tutorials operating in parallel with some extra Googling thrown in for good measure. I am unifying these into one more simple tutorial, which I am presenting here to hopefully save readers some time. 

I'm going to doing this tutorial on a Mac that uses Python 2.7. These steps should all apply to a *nix system, although Python pathing might be different on Windows. 

#### Installation Steps

## Step 0: Prerequisites

I'm assuming for the sake of tutorial that you already have the following installed: 

* [Sublime][] Text 3
* Python 
* Pip 

#### Step 1: Install Sublime package control

The Sublime package control system allows us to install a variety of packages (think Plugins) including SublimeLinter.

Open the Sublime console with: ``` ctrl + ` ``` (control and `)

You should see a console appear at the bottom of Sublime: 

<figure>
		<img class="displayed" src="/pictures/sublime/1.png" alt="Package Control" align="middle" width="50%" height="100%">
		<figcaption>Installing the package manager</figcaption>
</figure>

Copy and paste the following into the console and press enter: 

```import urllib.request,os,hashlib; h = 'eb2297e1a458f27d836c04bb0cbaf282' + 'd0e7a3098092775ccb37ca9d6b2e4b7d'; pf = 'Package Control.sublime-package'; ipp = sublime.installed_packages_path(); urllib.request.install_opener( urllib.request.build_opener( urllib.request.ProxyHandler()) ); by = urllib.request.urlopen( 'http://packagecontrol.io/' + pf.replace(' ', '%20')).read(); dh = hashlib.sha256(by).hexdigest(); print('Error validating download (got %s instead of %s), please try manual install' % (dh, h)) if dh != h else open(os.path.join( ipp, pf), 'wb' ).write(by)```

Restart Sublime and confirm that it works by checking the preference menu: 

<figure>
		<img class="displayed" src="/pictures/sublime/2.png" alt="Original FCQ" align="middle" width="75%" height="75%">
</figure>

See [Official package control tutorial][] if you are having problems. 

## Step 2: Install the Sublime linter via package control

Open the preferences menu and click "Package Control" : 

<figure>
		<img class="displayed" src="/pictures/sublime/3.png" alt="Opening package control" align="middle" width="75%" height="75%">
</figure>

You should see a menu pop up like the one below, type in ```install``` and select 'Package Control: Install Package'.

<figure>
		<img class="displayed" src="/pictures/sublime/4.png" alt="Install Menu" align="middle" width="75%" height="75%">
		<figcaption>The install menu</figcaption>
</figure>

Press enter and you should see another menu listing packages to install: 

<figure>
		<img class="displayed" src="/pictures/sublime/5.png" alt="Insalling packages" align="middle" width="75%" height="75%">
		<figcaption>Install Packages</figcaption>
</figure>

Install the following: “SublimeLinter”

Restart.

Repeat the process and then install:  “SublimeLinter-pylint”

Confirm that they are both installed by checking the preference menu. You should see entries for both SublimeLinter and SublimeLinter-pylint. 

<figure>
		<img class="displayed" src="/pictures/sublime/6.png" alt="Package confirm" align="middle" width="75%" height="75%">
		<figcaption>Successfully installed packages</figcaption>
</figure>


## Step 3: Install pylint 

Pylint is a python application that will actually do the linting work displayed by Sublime. 

Open your terminal and install pylint with the following command: 

``` $ pip install pylint ```

Confirm that it works by going to the terminal and running pylint:

``` $ pylint ```

My output looked like this: 

<figure>
		<img class="displayed" src="/pictures/sublime/7.png" alt="Pylint" align="middle" width="75%" height="75%">
		<figcaption>Pylint working </figcaption>
</figure>

Official [Pylint install instructions][]

##Step 4: Get your Python path

To access Pylint, the SublimeLinter needs to know the path of where Python is installed. You can find this out by starting the python interpreter from your console: 

``` $ python ```

When you are in the interpreter run the following commands: 

``` >> import sys ```

``` >> print sys.path ```

You should have output that looks like the following: 

<figure>
		<img class="displayed" src="/pictures/sublime/8.png" alt="Python path" align="middle" width="75%" height="75%">
		<figcaption>Getting your Python path</figcaption>
</figure>

Copy all of the output of this print statement. 

## Step 5: Modify SublimeLinter-pylint settings

Access the SublimeLinter-pylint Default-settings document (Preferences > Package Settings > Pylinter > Settings -Default) 

<figure>
		<img class="displayed" src="/pictures/sublime/9.png" alt="Pylinter Settings" align="middle" width="75%" height="75%">
		<figcaption>Accessing Pylinter settings</figcaption>
</figure>


Replace the "python_path", which should be blank, with your correct path. Remember to include the square brackets! 

<figure>
		<img class="displayed" src="/pictures/sublime/10.png" alt="Adding the path" align="middle" width="75%" height="75%">
		<figcaption>Adding in the path</figcaption>
</figure>

Save the document and restart your Sublime. 

## Step 6: Confirm that everything works

To test that it works, open a new python file, and check the margins of a line containing an error. You should see some coloring: 

<figure>
		<img class="displayed" src="/pictures/sublime/11.png" alt="Success" align="middle" width="75%" height="75%">
		<figcaption>Pylint is working!</figcaption>
</figure>


[linter]: http://en.wikipedia.org/wiki/Lint_(software)
[Package Control]: https://packagecontrol.io/
[SublimeLinter]: http://sublimelinter.readthedocs.org/en/latest/about.html
[Pylint]: http://www.pylint.org/#install
[Sublime]: http://www.sublimetext.com/3

[Official package control tutorial]: https://packagecontrol.io/installation
[SublimeLinter]: http://sublimelinter.readthedocs.org/en/latest/installation.html
[Pylint install instructions]: http://www.pylint.org/#install
