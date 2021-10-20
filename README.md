# bemenu_frecency
This shell script displays commands sorted by their frecency, which is a measure combining both frequency and recency. 

I wrote this script for using it with bemenu but it can also be used with any dmenu like programs. To use it with dmenu, apply the required patches first and then,
``` sh
cp bemenu_run dmenu_run
sed -i 's/bemenu/dmenu/' dmenu_run
```

## Patches
The below patches improve the functionality of `bemenu_run`, apply them using `patch` command,
``` sh
patch < patches/patch_name.diff
```
- **bemenu_atime.diff**  - this allows sorting the unlaunched commands by their access time instead of their alphabetical order. This minimizes keystrokes by providing recently launched commands first.
- **bemenu_zsh_af.diff** - this allows launching zsh aliases and functions through `bemenu_run`.

## History file
Each launched command occupies a single line in the history file, and that line will be structured like this,
``` 
# n = maximum no. of timestamps allowed [default: 10]
command | launch count | timestamp(n) [latest timestamp] | timestamp(n - 1) | ... | timestamp(1) 
```
If you had removed a command from your system, then remove the line associated with that command so that it doesn't display unnecessarily. You can also modify the timestamp and launch count values if you want. 

## About the algorithm
The Frecency algorithm is first known to be implemented in Mozilla Firefox. My implementation is based on this [article](https://slack.engineering/a-faster-smarter-quick-switcher).
