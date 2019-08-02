# Industrial Robots extension for VSCode

The Industrial Robots extension for VSCode/VSCodium is an open source extension that aims to provide syntax highlighting for programs. This extension aims to support most of the industrial robots currently in use.

![VSCode in RoboDK](/screenshots/VSCode-in-RoboDK.png)

## Features

This extension currently supports the following robots and their corresponding robot controllers and programing languages.
> - ABB (MOD,PRG files)
> - KUKA (SRC/DAT files)
> - Comau (PDL)
> - Motoman (JBI)
> - Fanuc (LS files)
> - Universal Robots (script)
> - Staubli (VAL3/XML)
> - Kawasaki (PRG)

## Requirements

Installing the extension has no requirements, simply install Industrial Robots from within visual studio like any other add-on.
If you installed RoboDK v3.8.5 or later you should have VSCodium with this extension available. VSCodium is a simplified version of VSCode with almost the same functionality.

## Building and making changes

The Industrial robots VSCode extension is automatically generated from Python files. Therefore, it is better to understand and modify the Python scripts to automatically update the plugin.

The files in the Python directory of the plugin are used to add keywords and regular expressions to the add-on. Python scripts work with Python 2 and Python 3. 

Each Python file generates a theme for one programming language. You can add or edit the theme_* files which use a common library to apply the changes to the plugin.

Most of the functions contained within the python files are self descriptive and can be understood by taking a look at the Python/update_themes.py file.

repo_match() can either take a list of keywords to add to that category or a regular expression. If there is a "\\" at the start of the string it will be interpreted as a regular expression and passed as is to the json in field specified in the function.

If there isn't a "\\" at the start of the string it will generate a regular expression that highlights all the space separated words in the string. As such you must not have any trailing spaces in these strings or the regular expression generated will break that files syntax.

To add a new language you would create a new python file based on the currently existing ones and modify the keywords as necessary. After modifying and running the script you also need to manually edit the plugins package.json file and the files that where generated.

## Known Issues

No known issues.

-----------------------------------------------------------------------------------------------------------

## Screenshots

ABB (MOD,PRG files)
![ABB](/screenshots/ABB.png)

KUKA (SRC/DAT files)
![KUKA](/screenshots/KUKA.png)

Motoman (JBI)
![Motoman](/screenshots/Motoman.png)

Fanuc (LS files)
![Fanuc](/screenshots/Fanuc.png)

Universal Robots (script)
![Universal Robots](/screenshots/UR.png)

