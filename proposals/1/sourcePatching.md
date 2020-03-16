# Source Patching

## Current situation

Patching the source is complicated because of the module system. Each module exposes public properties using global variables. If a mod developer wanted to inject into a method that relies on module-scoped variables, they are forced to either directly patch the source, clone the module into their mod and make the revisions they need, or think of a complicated way of manipulating the original behavior to get the desired effect wit. 