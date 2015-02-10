# bash.d

A simple init-inspired personal bash script manager.

## To Install
1. clone/fork this repo (priviately if you have anything private...) to...
2. `~/.bash.d` or wherever you want it to live
3. `echo . ~/.bash.d/rc >> ~/.bashrc` as is typical to bootstrap into your bash session

That's basically all you will need in your `~/.bashrc` from here on out

## To use

* Place any scripts you wanted sourced into your bash session under `rc.d/*.sh`
* You can segregate scripts by host and use a single repo for all hosts; just place scripts in a subdir named after `hostname`, e.g. `rc.d/myhost/*.sh`
* Scripts will run in arbitrary order (well, an order defined by your filesystem).  If you to explicitly define some things before or after all other scripts, use the special script names `pre` and `post`.
* Top-level scripts (including `pre` and `post`) will run before host-level scripts.
* Place any executable scripts (not sourced into bash environment) into `bin`, which is now on your `$PATH`

## Output

Whenever you start a new bash session you'll see output indicating what set of scripts are being run in the environment.

```
Loading scripts from /home/user/.bash.d/rc.d
Loading scripts from /home/user/.bash.d/rc.d/thishost
[user@thishost ~]$ 
```

Ta Da

