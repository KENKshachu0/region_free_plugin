# Region Free Plugin

This plugin allows you to launch an title of an other region and / or force a language of an title.

## Installation

Load the plugin with the [Wii U Plugin System Backend](https://github.com/wiiu-env/WiiUPluginLoaderBackend) by placing it on the SD Card into the 
directory `sd:/wiiu/plugin/`

At the first launch with the plugin open the config menu (press ZL, DPAD Down and Minus on the gamepad) and set your default language for each region.

## Usage

The plugin has a built in auto detection, so in most cases it just works out of the box.

Via the plugin config menu (press ZL, DPAD Down and Minus on the gamepad) you can configurate the plugin. The avaible options are the following:

- **Auto Detection**: Enabled/Disabled the auto detection of the region/language. When you disable it, you need/can set the region and language for a title on each title start. Enabled by default.
- **Prefer System Settings For Own Region**: Forces the region and language of your console when starting an title or your region (Ignoring "Default Language for Region"). Enabled by default.
- **Default Language for EUR**: Sets the default language for EUR titles. Set to English by default.
- **Default Language for USA**: Sets the default language for USA titles. Set to English by default.

If the auto detection fails, the user needs to enter a region/language on the title boot.

The plugin keeps tracks the region/language the user has selected for an title.

Scenario:  
 - The User has disabled the auto detection and booted a EUR version of Mario Kart 8 in German on their US console.
 - The User then enables the auto detection and set the default language for EUR titles to English.
 - The EUR version of Mario Kart 8 will still boot in German. To change the language the user has to disable the auto detection and reboot the title.

## Building using the Dockerfile

It's possible to use a docker image for building. This way you don't need anything installed on your host system.

```
# Build docker image (only needed once)
docker build . -t regionfree_plugin-builder

# make 
docker run -it --rm -v ${PWD}:/project regionfree_plugin-builder make

# make clean
docker run -it --rm -v ${PWD}:/project regionfree_plugin-builder make clean
```
