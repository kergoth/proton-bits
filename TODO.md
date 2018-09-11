# TODO

- Add support to the scripts in general for 32-bit prefixes, and determine how to enable that. Ceville needs dotnet35, which is incompatible with 64-bit prefixes, and the game isn't 64-bit anyway. Did a first attempt at this, but turned out to be rather more complex than I thought with that approach, so set it aside for now. My scripts end up calling wine/winetricks/etc before proton itself due to proton limitations (any non-existant exe ends up passed to start rather than wine, including winecfg, regedit, etc, and winetricks is a separate script entirely), so the prefix initialization from default_pfx doesn't happen unless I run proton without an exe, but lacking an exe, there's no way to determine whether to create a 32 or 64 bit prefix. I think either I should punt and not bother using proton to init the pfx, and init it with the correct WINEARCH myself, or we need a different way to pass the arch into proton.

## wine-steam-installscript

- Flesh out possible registry entry type values
- Fix handling of encoding. Registry entries are utf-16-le, but the .vdf fails to parse with utf-16. Could potentially use utf-8 with surrogates, but I'm not very familiar with how that works.

## Proton.app wrappers

- Handle the script python module dep on click
- Move the steam library into drive_c to avoid hardcoding host paths in drive_z in the registry

## run-proton

- Split run-proton into run-proton and run-proton-steam
- Determine if I should add unixodbc. Grey Goo is complaining about it
- Add argument to run the default exe for steam, by calling out to SteamCMD to app_print_info to get the windows exe name
- Add an included db of preparation commands to do further prefix setup for this game, i.e. winetricks, registry tweaks to be done prior to running the redists
- Make cmd optional

## get-steam-win-exe

- Handle 'osarch'
