# Awesome Support Addon Boilerplate

[![Scrutinizer Code Quality](https://scrutinizer-ci.com/g/Awesome-Support/Addon-Boilerplate/badges/quality-score.png?b=master)](https://scrutinizer-ci.com/g/Awesome-Support/Addon-Boilerplate/?branch=master)

This boilerplate is a starting point for creating addons for [Awesome Support](http://getawesomesupport.com). It contains all the things that are required in all addons, such as version checks and license activation.

The boilerplate should be used for all addons as it is uses a specific method to safely register itself with Awesome Support.

## Configuration

There is nothing much needed. Just rename the class and change the addon name. Here is the list of what needs to be changed:

- `AS_Boilerplate_Loader` (class name)
- `AS_Boilerplate_Loader::slug` (should be your addon name sanitized)
- `$plugin_name` in the `addon_license` method

## Usage

Your code should be placed in the `load` method. The easiest approach is to have all your code in a separate file and include this file from the `load` method.

**Be aware**, the addons are loaded by Awesome Support on the `plugins_loaded` hook with priority `20`. This means that when hooking within the `load` method, you **MUST** hook on `plugins_loaded` with priority `21` or later.