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

## Format Proposal


## `load-sets.json`
At the root of the CrossCode installation, there will be a file named `load-sets.json`. This will contain information about where all Load Sets are located relative to the root directory.

### Example File

```js
{
    "mods": {
        "simplify-1.0.0": "/assets/mod-archive/simplify-1.0.0.ccmod",
        "mod1-1.0.1": "/assets/mod-archive/mod1-1.0.1/",
    },
    "sets": {
        "default": "/assets/mods/",
        "name": "/path/to/mods/"
    }

}
```
Note: To keep backwards compatibility, `default` should always point to `/assets/mods/` 

Note: Mod paths beginning with `/assets/mod-archive/` are only examples. They are not a requirement.

## `mods.json`

Each named load set path will have a file name `mods.json` at the root. For example, the file `/assets/mods/mod.json` will be linked to `default` load set.

The contents will be a list of JSON object with the key being the mod name and the value being the version.


```js
[
    "simplify-1.0.0",
    "mod1-1.0.1"
]
```


Author: Emileyah

Discord id: 208763015657553921