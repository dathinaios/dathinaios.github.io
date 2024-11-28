---
author: "Dionysis Athinaios"
title: "Open any File in Terminal Vim by Default"
date: 2024-11-27
tags: ["mac", "neovim", "vim", "configuration"]
categories: ["Articles", "Code"]
draft: false
ShowToc: true
TocOpen: false
---

## The Problem

On a Mac, double clicking or otherwise opening a file (for instance through Alfred) often opens it in Xcode, TextEdit or other non-Vim based editor 😔. What if we use terminal Vim (ok, or any other editor, this should be useful anyway)? Two problems to solve:

1. Open a file in terminal Vim
2. Associate all relevant files with a certain app easily

## The Solution

### 1. Open a File in Terminal (Vim)

We can achieve this using an `Automator` workflow bundled as an app.

* Launch `Automator` and choose `Application` as type.
* Add a `Run AppleScript` action.
* Paste this script into the Run Applescript section:

```applescript
on run {input, parameters}
	-- Check if there is an argument passed (i.e., the input is not empty)
	if input is not {} then
		set myPath to POSIX path of input
		set cmd to "vim " & quote & myPath & quote
		tell application "iTerm"
			if it is running then
				-- This is in the case where iTerm is open and no window is open.
				if (count windows) is 0 then
					create window with profile "Default"
					tell current window
						tell current session
							write text (cmd)
						end tell
					end tell
					activate
				else
					tell current window
						-- We create a separate tab to the current window
						create tab with profile "Default"
						tell current session
							write text (cmd)
						end tell
					end tell
					activate
				end if
			else
				-- At startup of iTerm...
				tell application "iTerm"
					-- We do not create a tab since we know it's at startup
					tell current window
						tell current session
							write text (cmd)
						end tell
					end tell
					activate
				end tell
			end if
		end tell
	else
		-- If no input argument is passed, do nothing
		return
	end if
end run
```

--------

Finally, save the project as an application. You can put it in your Applications folder but I have found that it works fine from anywhere. I have named it `Vim` but you can choose any name as long as you modify the scripts for the following session.

### 2. Easily Associate any File with the Application

Now, we can of course right click on a file, got to "Get Info", choose an application to open it and choose to always open with that application. But that is a mission especially when we have to do it for so many files. Here is a better way:

Install the `duti` utility with `Homebrew` (or however else you like):

```bash
$ brew install duti
```

Then create a bash script to use it:

```bash
#!/bin/bash

# Reset all associations if necessary
# /System/Library/Frameworks/CoreServices.framework/Frameworks/LaunchServices.framework/Support/lsregister -kill -r -domain user

# Define the app's bundle ID
APP_BUNDLE_ID="com.apple.automator.Vim"

# Array of common text file extensions
TEXT_EXTENSIONS=(
    .txt
    .md
    .markdown
    .json
    .xml
    .yaml
    .yml
    .csv
    .log
    .ini
    .cfg
    .js
    .ts
    .jsx
    .tsx
    .css
    .scss
    .sass
    .php
    .py
    .rb
    .java
    .c
    .cpp
    .h
    .hpp
    .rs
    .go
    .sh
    .bash
    .zsh
    .pl
    .awk
    .sql
    .toml
)

# Loop through each extension and set the association
for EXT in "${TEXT_EXTENSIONS[@]}"; do
    duti -s "$APP_BUNDLE_ID" "$EXT" all
done

echo "Associations updated for all listed extensions with $APP_BUNDLE_ID."

```

----

The file extensions are just the ones I use. This script assumes the Automator app Vim (with ID `com.apple.automator.Vim`) we created above. If you have a different app name, or this is not working, run this to find the ID: `osascript -e 'id of app "Vim"'` changing `Vim` for the name of your app. If you are having trouble try to launch the application again or even manually "Open With.." for stubborn files. You can also try to use the commented line above to reset all associations (at your own risk!).

That's it. You should now be able to double click or launch any of the files with the above extensions in terminal Vim. Here is to never having a file opening in Xcode or TextEdit again! 🍻
