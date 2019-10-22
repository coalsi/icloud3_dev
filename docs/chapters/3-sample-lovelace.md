# Lovelace Cards

The following examples show how Lovelace Cards can show iCloud3 information in various formats.

### Example 1 - Two People - 4x3 Format

![lovelace_gc_home_lc_away_4x3](../images/lovelace_gc_home_lc_away_4x3.jpg)

```yaml
  - title: Location (Gary)
    icon: mdi:cellphone-iphone
    cards:
      - type: vertical-stack
        cards:
          - type: glance
            title: Location Info - Gary
            column_width: 20%
            entities:
              - entity: device_tracker.gary_iphone
                name: Gary
              - entity: sensor.gary_iphone_interval
                name: Interval
                icon: mdi:clock-start
                tap_action: 
                  action: call-service
                  service: script.icloud_command_display_interval_formula
              - entity: sensor.gary_iphone_travel_time
                name: TravTime
                icon: mdi:clock-outline
              - entity: sensor.gary_iphone_zone_distance
                name: HomeDist
                icon: mdi:map-marker-distance 
              - entity: sensor.gary_iphone_next_update
                name: NextUpdt
                icon: mdi:update
         
          - type: glance
            column_width: 20%
            entities:
              - entity: sensor.gary_iphone_waze_distance
                name: WazeDist
                icon: mdi:map-marker-distance
              - entity: sensor.gary_iphone_calc_distance
                name: CalcDist
                icon: mdi:map-marker-distance
              - entity: sensor.gary_iphone_dir_of_travel
                name: Direction
                icon: mdi:compass-outline
              - entity: sensor.gary_iphone_last_located
                name: Located
                icon: mdi:map-clock
              - entity: sensor.gary_iphone_last_update
                name: LastUpdt
                icon: mdi:history
              
          - type: horizontal-stack
            cards:
            - type: entities
              entities:
                - entity: sensor.gary_iphone_info
                  name: Info
                  icon: mdi:information-outline 

          - type: entities
            entities:
              - script.icloud_update_location_gary
              - script.homeassistant_restart
              
      - type: vertical-stack
        cards:
          - type: glance
            title: Location Info - Lillian
            column_width: 20%
            entities:
              - entity: device_tracker.lillian_iphone
                name: Gary
              - entity: sensor.lillian_iphone_interval
                name: Interval
                icon: mdi:clock-start
                tap_action: 
                  action: call-service
                  service: script.icloud_command_display_interval_formula
              - entity: sensor.lillian_iphone_travel_time
                name: TravTime
                icon: mdi:clock-outline
              - entity: sensor.lillian_iphone_zone_distance
                name: HomeDist
                icon: mdi:map-marker-distance 
              - entity: sensor.lillian_iphone_next_update
                name: NextUpdt
                icon: mdi:update
         
          - type: glance
            column_width: 20%
            entities:
              - entity: sensor.lillian_iphone_waze_distance
                name: WazeDist
                icon: mdi:map-marker-distance
              - entity: sensor.lillian_iphone_calc_distance
                name: CalcDist
                icon: mdi:map-marker-distance
              - entity: sensor.lillian_iphone_dir_of_travel
                name: Direction
                icon: mdi:compass-outline
              - entity: sensor.lillian_iphone_last_located
                name: Located
                icon: mdi:map-clock
              - entity: sensor.lillian_iphone_last_update
                name: LastUpdt
                icon: mdi:history
          - type: entities
            entities:
              - entity: sensor.lillian_iphone_info
                name: Info
                icon: mdi:information-outline 

```
### Example 2 - Two People - 5x2 Format

![lovelace_gc_lc_5x2](../images/lovelace_gc_lc_5x2.jpg)

```yaml
  - title: Location (Gary)
    icon: mdi:cellphone-iphone
    cards:
      - type: vertical-stack
        cards:
          - type: glance
            title: Location Info - Gary
            column_width: 20%
            entities:
              - entity: device_tracker.gary_iphone
                name: Gary
              - entity: sensor.gary_iphone_interval
                name: Interval
                icon: mdi:clock-start
                tap_action: 
                  action: call-service
                  service: script.icloud_command_display_interval_formula
              - entity: sensor.gary_iphone_travel_time
                name: TravTime
                icon: mdi:clock-outline
              - entity: sensor.gary_iphone_zone_distance
                name: HomeDist
                icon: mdi:map-marker-distance 
              - entity: sensor.gary_iphone_next_update
                name: NextUpdt
                icon: mdi:update
         
          - type: glance
            column_width: 20%
            entities:
              - entity: sensor.gary_iphone_waze_distance
                name: WazeDist
                icon: mdi:map-marker-distance
              - entity: sensor.gary_iphone_calc_distance
                name: CalcDist
                icon: mdi:map-marker-distance
              - entity: sensor.gary_iphone_dir_of_travel
                name: Direction
                icon: mdi:compass-outline
              - entity: sensor.gary_iphone_last_located
                name: Located
                icon: mdi:map-clock
              - entity: sensor.gary_iphone_last_update
                name: LastUpdt
                icon: mdi:history
              
          - type: horizontal-stack
            cards:
            - type: entities
              entities:
                - entity: sensor.gary_iphone_info
                  name: Info
                  icon: mdi:information-outline 

          - type: entities
            entities:
              - script.icloud_update_location_gary
              - script.homeassistant_restart
#-------------------------------------------------------------------------              
      - type: vertical-stack
        cards:
          - type: glance
            title: Location Info - Lillian
            column_width: 20%
            entities:
              - entity: device_tracker.lillian_iphone
                name: Gary
              - entity: sensor.lillian_iphone_interval
                name: Interval
                icon: mdi:clock-start
                tap_action: 
                  action: call-service
                  service: script.icloud_command_display_interval_formula
              - entity: sensor.lillian_iphone_travel_time
                name: TravTime
                icon: mdi:clock-outline
              - entity: sensor.lillian_iphone_zone_distance
                name: HomeDist
                icon: mdi:map-marker-distance 
              - entity: sensor.lillian_iphone_next_update
                name: NextUpdt
                icon: mdi:update
         
          - type: glance
            column_width: 20%
            entities:
              - entity: sensor.lillian_iphone_waze_distance
                name: WazeDist
                icon: mdi:map-marker-distance
              - entity: sensor.lillian_iphone_calc_distance
                name: CalcDist
                icon: mdi:map-marker-distance
              - entity: sensor.lillian_iphone_dir_of_travel
                name: Direction
                icon: mdi:compass-outline
              - entity: sensor.lillian_iphone_last_located
                name: Located
                icon: mdi:map-clock
              - entity: sensor.lillian_iphone_last_update
                name: LastUpdt
                icon: mdi:history
          - type: entities
            entities:
              - entity: sensor.lillian_iphone_info
                name: Info
                icon: mdi:information-outline 

```
### Example 3 - Tracking from 2 Zones - Home and Whse
![lovelace_gc_away_2_zones_5x2](../images/lovelace_gc_away_2_zones_5x2.jpg)

```yaml
  - title: Location (Gary)
    icon: mdi:cellphone-iphone
    cards:
      - type: vertical-stack
        cards:
          - type: glance
            title: Location Info - Gary
            column_width: 20%
            entities:
              - entity: device_tracker.gary_iphone
                name: Gary
              - entity: sensor.gary_iphone_interval
                name: Interval
                icon: mdi:clock-start
                tap_action: 
                  action: call-service
                  service: script.icloud_command_display_interval_formula
              - entity: sensor.gary_iphone_travel_time
                name: TravTime
                icon: mdi:clock-outline
              - entity: sensor.gary_iphone_zone_distance
                name: HomeDist
                icon: mdi:map-marker-distance 
              - entity: sensor.gary_iphone_next_update
                name: NextUpdt
                icon: mdi:update
         
          - type: glance
            column_width: 20%
            entities:
              - entity: sensor.gary_iphone_waze_distance
                name: WazeDist
                icon: mdi:map-marker-distance
              - entity: sensor.gary_iphone_calc_distance
                name: CalcDist
                icon: mdi:map-marker-distance
              - entity: sensor.gary_iphone_dir_of_travel
                name: Direction
                icon: mdi:compass-outline
              - entity: sensor.gary_iphone_last_located
                name: Located
                icon: mdi:map-clock
              - entity: sensor.gary_iphone_last_update
                name: LastUpdt
                icon: mdi:history
              
          - type: horizontal-stack
            cards:
            - type: entities
              entities:
                - entity: sensor.gary_iphone_info
                  name: Info
                  icon: mdi:information-outline 

          - type: entities
            entities:
              - script.icloud_update_location_gary
              - script.homeassistant_restart

#-------------------------------------------------------------------------              
      - type: vertical-stack
        cards:
          - type: glance
            title: Location Info - Gary (Warehouse)
            column_width: 25%
            entities:
              - entity: device_tracker.gary_iphone
                name: Gary
              - entity: sensor.whse_gary_iphone_interval
                name: Interval
                icon: mdi:clock-start
                tap_action: 
                  action: call-service
                  service: script.icloud_command_display_interval_formula
              - entity: sensor.whse_gary_iphone_travel_time
                name: TravTime
                icon: mdi:clock-outline
              - entity: sensor.whse_gary_iphone_zone_distance
                name: WhseDist
                icon: mdi:map-marker-distance 
              - entity: sensor.whse_gary_iphone_next_update
                name: NextUpdt
                icon: mdi:update
         
          - type: glance
            column_width: 25%
            entities:
              - entity: sensor.whse_gary_iphone_waze_distance
                name: WazeDist
                icon: mdi:map-marker-distance
              - entity: sensor.whse_gary_iphone_calc_distance
                name: CalcDist
                icon: mdi:map-marker-distance
              - entity: sensor.whse_gary_iphone_dir_of_travel
                name: Direction
                icon: mdi:compass-outline
              - entity: sensor.whse_gary_iphone_last_located
                name: Located
                icon: mdi:map-clock
              - entity: sensor.whse_gary_iphone_last_update
                name: LastUpdt
                icon: mdi:history
 
          - type: entities
            entities:
              - entity: sensor.whse_gary_iphone_info
                name: Info
                icon: mdi:information-outline 
```

