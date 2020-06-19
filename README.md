fabric-forge
===

fabric-forge is an experimental effort to allowing running mods written
for Fabric on Minecraft Forge, comprised of 2 efforts:

- Allowing mods written for fabric-loader to run under FML
- Porting the Fabric APIs to use either Forge's API (if available), or
  ensure the Mixins apply against Forge correctly.
  
fabric-forge was inspired by comments I had made some time ago
questioning Patchwork's approach to implement the larger work ontop the
smaller work, experimental work I was doing to work out roughly how
Forge support would work for the Sponge Project going forward, and
recent comments by cpw.

---

**fabric-forge is an experimental toy project**. I do not normally
release my toy projects, but this one had some interest - so here you
are. As with my typical toy projects, this WILL NOT BE MAINTAINED -
any commits will be sporadic, if at all.

---

## Features

- Remaps mods at runtime from Intermediary to SRG
  - Includes Mixins and Mixin refmaps
- Loads mods from the standard FML mods path
  - Will load jar-in-jar mods
- Loads mods using Fabric Loader's language adapters
  - *I did not implement scanning for language adapters though, so currently
    only old-style custom adapters will work*.
    
## License

All original code is licensed under the MIT License, available under
[LICENSE.txt](./LICENSE.txt). Some files have been derived from either Minecraft
Forge or the Fabric Project, these files have retained their original license
headers - and are available under their respective licenses.

## FAQs

### How can I run fabric-forge?

You will need to add the patched fabric-loader to the classpath of the game.
One fairly easy way to do this is to use [MultiMC](https://multimc.org/) with
a "custom package", I've provided the package file I used for testing.

### Can I run the Fabric API as a mod?

No, many of the mixins don't apply - that's why a separate effort to port the
Fabric APIs is necessary.

### Does fabric-forge run in a development environment?

No, I only implemented runtime deobf for Fabric mods to SRG, not MCP mappings -
though it should be possible to hook into Forge's MCP naming service.
