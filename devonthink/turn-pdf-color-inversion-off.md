# Turn PDF Color Inversion Off in DEVONthink

To stop DEVONthink from inverting PDF colors in Dark Mode, you need to disable the app’s forced PDF dark mode using its hidden preferences:

1. Quit DEVONthink completely
2. Open your Mac's Terminal application
3. Paste the following command and press Return: `defaults write com.devon-technologies.think3 DisablePDFDarkMode -bool TRUE` 

[DEVONthink | Hidden Preferences](https://download.devontechnologies.com/download/devonthink/3.8.2/DEVONthink.help/Contents/Resources/pgs/appendix-hiddenpreferences.html) 