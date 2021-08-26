---
title: Home Assistant PC Lock/Unlock Switch
date: 2021-08-27 00:06:05
tags: home-automation
---



# Instructions

In `configuration.yaml`, add these lines of YAML, replacing "My PC" / "my_pc" with your pc name, 
```
switch eros_lock_unlock:
  - platform: template
    switches:
      eros_lock_unlock:
        friendly_name: "Eros - Lock/Unlock"
        value_template: "{{ is_state('binary_sensor.eros_logonui', 'on') }}"
        turn_on:
          service: script.eros_lock
        turn_off:
          service: script.eros_unlock
        icon_template: >-
          {% if is_state('binary_sensor.eros_logonui', 'on') %}
            mdi:lock
          {% else %}
            mdi:lock-open
          {% endif %}
```