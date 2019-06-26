# bwalarm (akasma74 edition)

## Disclaimer
This fork was created to maintain the original [bwalarm](https://github.com/gazoscalvertos/Hass-Custom-Alarm) custom component until its author is back.
Feel free to create a new issue or pull request here **if you downloaded code from my repo**.
The corresponding HA thread [here](https://community.home-assistant.io/t/bwalarm-akasma74-edition/113666)

## How to - installation

Copy the following files/complete folders into your home assistant configuration directory:
```
  alarm.yaml                  This file stores your alarm configuration
  custom_components/bwalarm/  The brains of the operation. This is the logic of the custom alarm system
```

To get things working with Home Assistant (HA) you need to add the following to your configuration.yaml:
```
alarm_control_panel: !include alarm.yaml
```

**NOTE:** If you experience issues with the page not displaying then add the following:
```
#configuration.yaml
frontend:
  javascript_version: latest
```
You may need to restart HA if the component doesn't load first time as HA will need to install a dependency (ruamel.yaml).

It's advisable to start with a new alarm.yaml file with the minimum configuration set (alarm.yaml from this repo):
```
platform: bwalarm
name: House
```
You can always configure your alarm using web interface or by modifying your alarm.yaml directly.

The default password to access the settings page is: **HG28!!&dn**

For more details please refer to the [configuration description](https://github.com/akasma74/Hass-Custom-Alarm/blob/master/guidance/configuration.md).

## How to - update
Currently the update process is pretty much similar to installation - you copy a new release archive/clone the repository from here and save the files into custom_components/bwalarm/ folder.

Soon the component will be supported by [HASC](https://github.com/custom-components/hacs) and there will be no need to update it manually.

However, you need to keep in ming that the component's code is loaded on Home Assistant startup and the panels' code is cached by browser.
Therefore, evety time you update no matter how, you HAVE to clear chache of ALL of your browsers and then restart Home Assistant. 

Please test and provide feedback/suggestions.


## Custom resources.

You can override any resource under the /resource directory, to do that create a directory called `bwalarm` in the root of your configuration directory.

**Example:**

```
<config_dir>/bwalarm/images/ha.png
will override:
<config_dir>/custom_components/bwalarm/images/ha.png
and it will stay there during updates.
```