# Load Set

## Current situation

-  The hardcoded path for mod installation or discovery is `assets/mods/`. The mod must exist there to be found. 
- Big mods that may conflict have to be individually disabled to minimize issues.
- It is harder to find source of problem with big mods potentially messing with smaller mods.

- Downgrading is impossible if one mod requires a version different from another.

## Solution

Allow users to create a set of mods referenceable by a name.

### Advantages

- One set can have a different version of the same mod for another set.

- Decreases complexity of debugging if used.

- No longer necessary to disable mods that might conflict with another mod.


### Disadvantages

- Increased implementation complexity.

- Increase storage usage.



## Solution 1


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

## Advantages

- Backwards compatibility

- Easier to manually install mods


## Disavantages

- Space efficient setups are harder to achieve with manual installation


Author: Emileyah

Discord id: 208763015657553921