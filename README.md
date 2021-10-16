# bemenu_frecency
This shell script makes bemenu display applications sorted by frecency, which is a measure combining both frequency and recency. 

I wrote this script for using it with bemenu but it can also be used with any dmenu like applications. To use it dmenu,
``` sh
mv bemenu_run dmenu_run
sed -i 's/bemenu/dmenu/' dmenu_run
```

# Patches
Apply below patches using `patch` command, 
- **bemenu_atime.diff** - this allows sorting the unlaunched applications by thier file access time instead of thier alphabetical order. This minimizes keystrokes by providing recently launched commands first.
