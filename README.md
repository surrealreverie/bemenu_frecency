# bemenu_frecency
This shell script makes bemenu display applications sorted by frecency, which is a measure combining both frequency and recency. 

Normal __bemenu_run__ sorts the launched applications by frecency and the unlaunched applications by their alphabetical order. While the __bemenu_run_atime__ sorts the unlaunched applications by their file access time(atime), this reduces your keystrokes by showing recently launched applications first.

# Usage
- Make the script executable with `chmod +x bemenu_run` and bind a key from your window manager to use it.
- I wrote this script for using it with bemenu but it can also be used with any dmenu like applications. To use it dmenu,
```
mv bemenu_run dmenu_run
sed -i 's/bemenu/dmenu/' dmenu_run
```
