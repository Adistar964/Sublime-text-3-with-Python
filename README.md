# Python Setup for Sublime Text

This repository contains configuration files to set up Python development in Sublime Text using a custom build system and Jedi for autocompletion.

## Prerequisites
- Download and install [Sublime Text](https://www.sublimetext.com/)
- Install Python from [Python's official website](https://www.python.org/downloads/) and note the installation path

## Installation Steps

### 1. Configure the Python Build System
1. Open Sublime Text.
2. Navigate to `Tools` > `Build System` > `New Build System`.
3. Replace the content with the following, updating `python-path` with your actual Python installation path:

   ```json
   {
       "cmd": ["python-path", "-u", "$file"],
       "file_regex": "^[ ]*File \"(...*?)\", line ([0-9]*)",
       "selector": "source.python"
   }
   ```
4. Save the file as `Python_Build_System.sublime-build`.
5. Select the new build system via `Tools` > `Build System` > `Python_Build_System`.

### 2. Configure Jedi for Autocompletion
Jedi is a powerful autocompletion library for Python in Sublime Text.

1. Install [Jedi](https://packagecontrol.io/packages/Jedi) via Package Control.
2. Navigate to `Preferences` > `Package Settings` > `Jedi` > `Settings - User`.
3. Replace the content with:

   ```json
   {
       "settings": {
           "python_virtualenv": "Your_python_path", // Replace with your Python Path
           "python_interpreter": "Your_python_path", // Replace with your Python Path
           "python_package_paths": [
               "$home/.buildout/eggs",
               "$project_path/addons"
           ]
       },
       "auto_complete_triggers": [{"selector": "source.python", "characters": "."}]
   }
   ```
4. Save the file and restart Sublime Text.

## Running Python Code
To execute a Python script:
1. Open your Python file in Sublime Text.
2. Press `Ctrl + B` (or `Cmd + B` on macOS) to run the script.

## Troubleshooting
- If the build system does not work, ensure that the Python path is correctly set.
- If autocompletion does not function as expected, restart Sublime Text or verify Jedi's settings.

## Contact
Author: [Mohammed Abdullah Amaan](mailto:abdullah@abdullahamaan.com)

