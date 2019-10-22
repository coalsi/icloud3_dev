# Device Tracker Services

Four services are available for the iCloud3 device tracker component that are used in automations. 

| Service | Description |
|---------|-------------|
| icloud_update | Send commands to iCloud3 that change the way it is running (pause, resume, Waze commands, etc.) |
| icloud_set_interval | Override the dynamic interval calculated by iCloud3. |
| icloud_lost_phone | Play the Lost Phone sound. |
| icloud_reset | Reset the iCloud3 custom component. |


### icloud_update Service

This service allows you to change the way iCloud3 operates. The following parameters are used:

| Parameter | Description |
|-----------|-------------|
| device_name | Name of the device to be updated. All devices will be updated if this parameter is not specified.  All instances of the device_name are updated if it is in several groups. update *(Optional)* |
| command | The action to be performed (see below). *(Required)* |
| parameter | Additional parameters for the command. |

The following describe the commands that are available. 

| Command/Parameter |  Description |
|-----------------|-------------|
| pause |  Stop updating/locating a device (or all devices). Note: You may want to pause location updates for a device if you are a long way from home or out of the country and it doesn't make sense to continue locating your device. |
| resume |  Start updating/locating a device (or all devices) after it has been paused. |
| resume |  Reset the update interval if it was overridden the 'icloud_set_interval' service. |
| pause-resume |  Toggle pause and resume commands |
| zone zonename | service call) and immediately update the device interval and location data. Note: Using the device_tracker.see service call instead will update the device state but the new interval and location data will be delayed until the next 15-second polling iteration (rather than immediately). |
| waze on |  Turn on Waze. Use the 'waze' method to determine the update interval. |
| waze off |  Turn off Waze. Use the 'calc' method to determine the update interval. |
| waze toggle |  Toggle waze on or off |
| waze reset_range | Reset the Waze range to the default distances (min=1, max=99999). |
| info interval | Show how the interval is determined by iCloud3. This is displayed real time in the `info` attribute field. |
| info logging |  Toggle writing detailed debug information records to the HA log file. |
| restart |  Restart iCloud3. Detect any new devices, recheck the availability of the iCloud Location Service, relocate all devices, etc. |

#### Example Automations or Scripts

```yaml
# Commands to control how iCloud3 operates

icloud_command_pause_resume_polling:
  alias: 'Toggle Pause/Resume Polling'
  sequence:
    - service: device_tracker.icloud_update
      data:
        command: pause-resume

icloud_command_resume_polling:
  alias: 'Resume Polling'
  sequence:
    - service: device_tracker.icloud_update
      data:
        command: resume
        
icloud_command_pause_polling:
  alias: 'Pause Polling'
  sequence:
    - service: device_tracker.icloud_update
      data:
        command: pause

icloud_command_pause_polling_gary:
  alias: 'Pause (Gary)'
  sequence:
    - service: device_tracker.icloud_update
      data:
        device_name: gary_iphone
        command: pause

icloud_command_toggle_waze:
  alias: 'Toggle Waze On/Off'
  sequence:
    - service: device_tracker.icloud_update
      data:
        command: waze toggle

icloud_command_garyiphone_zone_home:
  alias: 'Gary - Zone Home'
  sequence:

    - service: device_tracker.icloud_update
      data:
        device_name: gary_iphone
        command: zone home
      

icloud_command_garyiphone_zone_not_home:
  alias: 'Gary - Zone not_home'
  sequence:
    - service: device_tracker.icloud_update
      data:
        device_name: gary_iphone
        command: zone not_home
```

```yaml
#Commands to Restart iCloud3

icloud_command_restart:
  alias: 'iCloud3 Restart'
  sequence:
    - service: device_tracker.icloud_update
      data:
        command: restart
```

```yaml
#Commands to Generate Detailed Information on iCloud3's Operations

icloud_command_info_interval_formula:
  alias: 'Display Interval Formula'
  sequence:
    - service: device_tracker.icloud_update
      data:
        command: info interval

icloud_command_info_logging_toggle:
  alias: 'Write Details to Log File (Toggle)'
  sequence:
    - service: device_tracker.icloud_update
      data:
        command: info logging
```

### icloud_set_interval Service

This service allows you to override the interval between location updates to a fixed time. It is reset when a zone is entered or when the icloud_update service call is processed with the 'resume' command. The following parameters are used:

| Parameter | Description |
|-----------|-------------|
| device_name | Name of the device to be updated. All devices will be updated if this parameter is not specified. All instances of the device_name are updated if it is in several groups.*(Optional)* |
| interval | The interval between location updates. This can be in seconds, minutes or hours. Examples are 30 sec, 45 min, 1 hr,  2 hrs, 30 (minutes are assumed if no time descriptor is specified). *(Required)* |

```yaml
#Commands to Change Intervals

icloud_set_interval_15_sec_gary:
  alias: 'Set Gary to 15 sec'
  sequence:
    - service: device_tracker.icloud_set_interval
      data:
        device_name: gary_iphone
        interval: '15 sec'
 
icloud_set_interval_1_min_gary:
  alias: 'Set Gary to 1 min'
  sequence:
    - service: device_tracker.icloud_set_interval
      data:
        device_name: gary_iphone
        interval: 1

icloud_set_interval_5_hrs_all:
  alias: 'Set interval to 5 hrs (all devices)'
  sequence:
    - service: device_tracker.icloud_set_interval
      data:
        interval: '5 hrs'
```

### icloud_lost_iphone  Service

This service will play the Lost iPhone sound on a specific device when you use the family-sharing tracking method. Due to an Apple limitation, this is not available for the Find-my-Friends tracking method.

| Parameter | Description |
|-----------|-------------|
| device_name | Name of the device *(Required)* |

### icloud_restart Service

This service will restart iCloud3 and refresh all of the devices being handled by iCloud3. It does the same action as the `icloud_command` with the `refresh` option described above. You will have to restart Home Assist if you have made changes to the configuration parameters (new device type, new device name, etc.) 

