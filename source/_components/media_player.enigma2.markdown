---
layout: page
title: "Enigma2 (OpenWebif)"
description: "Instructions on how to integrate an Enigma2 based box running OpenWebif into Home Assistant."
date: 2019-02-21 12:02
sidebar: true
comments: false
sharing: true
footer: true
logo: openwebif.png
ha_category: Media Player
featured: false
ha_release: "0.90"
ha_iot_class: "Local Polling"
---

The `enigma2` platform allows you to control a Linux based set-top box which is running [Enigma2](https://github.com/oe-alliance/oe-alliance-enigma2) with the OpenWebif plugin installed.

[OpenWebif](https://github.com/E2OpenPlugins/e2openplugin-OpenWebif) is an open source web interface for Enigma2 based set-top boxes.

Enigma2 devices should be discovered automatically by using the [the discovery component](/components/discovery/).

To manually add a set-top box to your installation, add the following to your `configuration.yaml` file:

```yaml
# Example configuration.yaml entry
media_player:
  - platform: enigma2
    host: IP_ADDRESS
```

{% configuration %}
  host:
    description: The IP/hostname of the Enigma2 set-top box on your home network.
    required: true
    type: string
  use_channel_icon:
    description: By default, a screen grab of the current channel is shown. If you prefer the channel icon to be shown instead, set this to true.
    required: false
    type: boolean
    default: false
  port:
    description: Port which Openwebif is listening on.
    required: false
    type: integer
    default: 80
  name:
    description: A name for easy identification of the device.
    required: false
    type: string
    default: Enigma2 Media Player
{% endconfiguration %}
