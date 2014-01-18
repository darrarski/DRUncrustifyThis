DRUncrustifyThis
================

Helpful script for iOS and OS X developers writing code in Objective-C that allows to use uncrustify tool to apply standardized code formatting on all files in the project. It can be used directly from Xcode after configuring custom behaviour in Xcode preferences.

## Instalation

If you don't have uncrustify installed, you can do it using homebrew:

	brew install uncrustify

It's also required to create a symbolic link to uncrustify in /usr/bin so Xcode can find it:

	which uncrustify # this will return path to uncrustify installed by homebrew
	sudo ln -s /path/to/uncrustify /usr/bin/uncrustify

Put script in any directory, make it executable:

	chmod a+x uncrustify-objc

Create a symbolic link to the script in /usr/bin (required for running it from Xcode):

	sudo ln -s /path/to/uncrustify-objc /usr/bin/uncrustify-objc

## Usage

You can use the script from Terminal, just go to your project's directory and run:

	uncrustifythis --all

to apply formating on all files in current directory and all subdirectories. There are also options for applying formating only on changed or staged files (requires for the files to be managed by git repository) or specifying the files to uncrustify.

You can also configure an Xcode behaviour for applying formating on all files in your project:

- Go to Xcode preferences
- On Behaviours tab click on + button on the bottom of behaviours list
- Configure the behaviour for your needs, selecting Run script option and selecting uncrustify-obj
- You can also set keyboard shortcut for this behaviour if needed

To run the script from Xcode select Xcode -> Behaviours -> Your bahaviour (whatever you named it) form application menu. The script will then apply code formating to all files in your project (you can check changes made by script using git).

The script is using first found uncrustify configuration file in one of this locations:

- Current working directory (uncrustify.cfg - you can add it to your project files)
- User home directory (~/.uncrustify or ~/.uncrustify/uncrustify.cfg)
- Script dicrectory (uncrustify.cfg)

### Credits

The code is based on a script found in [The Apache Software Foundation](https://github.com/apache/) repostory on GitHub, unfortunately no longer availabe.
