# vscode-ipython-console README

Run Python code in an IPython console embedded in VSCode. Extension. Supports only Windows at the moment, and requires AutoHotKey installed. Tested to work on a Miniconda3 installation. But any configuration that allows you to use IPython should work.

## Requirements

- Windows 10 is the only OS currently supported.
- IPython.

## Installation

1. Clone this repo to the VS code extension folder (i.e. %userprofile%\.vscode\extensions)
2. Install AutoHotKey

## Recommendations

Disable console blocking due to opened Matplotlib figures: 

1. Navigate to %userprofile%\.ipython\profile_default\startup
2. Make a new file called "start.ipy" with the following content: %matplotlib qt5

## Usage

1. Open your Python project in VSCode.
2. Run the command "vscode-ipython-console: Initialize relevant consoles" by searching that command inside CTRL + SHIFT + P.
   1. (Tip: Make hotkey for this in Preferences > keyboard shortcuts).
   2. This will open two consoles: One for IPython, and another for AutoHotKey.
3. Get IPython console in focus (should be by default).
4. Open your IPython console by i.e. activate Python environment and opening IPython.
   1. This is a manual process since it's difficult to automate this to work for all Python setups.
5. Open a Python script and keep the script active (active cursor).
6. Run the command "vscode-ipython-console: Run the Python file".
   1. This should copy the filename together with a "run" command to IPython console and activate Enter command from AutoHotKey.

## Notes

AutoHotKey is required because passing a newline character to the IPython console results in IPython expecting more code. This is not the desired behavior as we would rather execute the code. The current, hacky, solution is to input an "Enter" keystroke by utilizing AutoHotKey. 

## Known Issues

## Release Notes

### 1.0.0

Initial release of vscode-ipython-console