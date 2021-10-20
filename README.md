# bemenu_frecency
This shell script makes bemenu display applications sorted by frecency, which is a measure combining both frequency and recency. 

I wrote this script for using it with bemenu but it can also be used with any dmenu like applications. To use it dmenu,
``` sh
mv bemenu_run dmenu_run
sed -i 's/bemenu/dmenu/' dmenu_run
```

## Patches
Apply below patches using `patch` command,
``` sh
patch < patches/patch_name.diff
```
- **bemenu_atime.diff** - this allows sorting the unlaunched applications by their access time instead of their alphabetical order. This minimizes keystrokes by providing recently launched commands first.

## History Cleanup
Each launched command occupies a single line in the history file. If you don't want a command to be displayed using frecency because you had removed it or accidentally launched it, then delete the line associated with that command.

## About the algorithm
The Frecency algorithm is first known to be implemented in Mozilla Firefox. My implementation is based around this [article](https://slack.engineering/a-faster-smarter-quick-switcher).
