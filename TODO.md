# TODO

- Add support to the scripts in general for 32-bit prefixes, and determine how to enable that. Ceville needs dotnet35, which is incompatible with 64-bit prefixes, and the game isn't 64-bit anyway

## wine-steam-installscript

- Consider how to supply the cdkeys to the scripts to substitute %CDKEY%
- Flesh out possible registry entry type values
- Fix handling of encoding. Registry entries are utf-16-le, but the .vdf fails
  to parse with utf-16. Could potentially use utf-8 with surrogates, but I'm
  not very familiar with how that works.

## Proton.app wrappers

- Handle the script python module dep on click
- Move the steam library into drive_c to avoid hardcoding host paths in drive_z in the registry

## run-proton

- Split run-proton into run-proton and run-proton-steam
- Determine if I should add unixodbc. Grey Goo is complaining about it
- Improve redist exec to use the runkey registry entries
- Add argument to run the default exe for steam, by calling out to SteamCMD to app_print_info to get the windows exe name
- Add an included db of preparation commands to do further prefix setup for this game, i.e. winetricks, registry tweaks to be done prior to running the redists
- Make cmd optional

## get-steam-win-exe

- Handle 'osarch'
