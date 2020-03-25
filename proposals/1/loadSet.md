# Load Set

## Current situation

Mod discovery and installation is currently limited to a single directory. The only way to control whether a mod loads after restarting the game is enabling or disabling it. This is tedious when managing multiple conflicting mods.


## Solution

Allow users to create a set of mods referenceable by a name.

### Advantages

- One set can have a different version of the same mod for another set.

- Decreases complexity of debugging if used.

- No longer necessary to disable mods that might conflict with another mod.


### Disadvantages

- Increased implementation complexity.

- Increase storage usage.



## Option 1


Folder structure
```
/assets
    /load-set
        /foo-mods
            /test
            bar.ccmod
        /bar-mods
            foo.ccmod
    /mods
        a.ccmod
```

`/assets/mods/` is the default load set.

`/assets/load-set/{name}-mods/` is the `{name}` load set.

### Advantages

- Backwards compatibility

- Easy to manually install mods


### Disadvantages

- Space efficient setups are harder to achieve with manual installation

- Requires managing two separate folders


## Solution 2

Folder structure
```
/assets

    /mods
        /foo-mods
            /test
            bar.ccmod
        /bar-mods
            foo.ccmod
        a.ccmod
```


### Advantages

- Easy to manually install mods

- All mods are in a single folder

### Disadvantages

- Space efficient setups are harder to achieve with manual installation

- Harder to differentiate between mod folders and load-set folders


## Solution 3

```
/assets

    /installed-mods
        /test-1.0.0
        a-1.0.0.ccmod
        bar-1.0.0.ccmod
        foo-1.0.0.ccmod
    /mods
        /foo-mods
            mod-list.json
        /bar-mods
            mod-list.json
        mod-list.json
```

### Advantages

- A single mod version is stored at most once

- Can easily see all versions of a mod installed

- 
### Disadvantages

- Tedious for manual installation/uninstallation. Near impossible for large amount of load sets.

- Requires managing two folders.


Author: Emileyah

Discord id: 208763015657553921