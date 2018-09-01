# TODO

- Create a new script to wrap app_info_print from SteamCMD, to cache the info

## wine-steam-installscript

- Flesh out possible registry entry type values

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