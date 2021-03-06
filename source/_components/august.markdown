---
layout: page
title: "August"
description: "Instructions on how to integrate your August devices into Home Assistant."
date: 2018-02-17 22:00
sidebar: true
comments: false
sharing: true
footer: true
logo: august.png
ha_category: Hub
ha_release: "0.64"
ha_iot_class: "Cloud Polling"
---

The `august` component allows you to integrate your [August](http://august.com) devices in Home Assistant. Currently this component supports August Lock and Doorbell.

## {% linkable_title Configuration %}

You will need your August login information (username (either phone# or email), and password) to use this module.

To set it up, add the following to your `configuration.yaml` file:

```yaml
# Example configuration.yaml entry
august:
  login_method: phone
  username: "+16041234567"
  password: YOUR_PASSWORD
```

{% configuration %}
login_method:
  description: Method to login to your August account, either "email" or "phone". A verification code will be sent to your email or phone during setup.
  required: true
  type: string
username:
  description: The username for accessing your August account. This depends on your login_method, if login_method is email, this will be your email of the account. Otherwise, this will be your phone number.
  required: true
  type: string
password:
  description: The password for accessing your August account.
  required: true
  type: string
timeout:
  description: Timeout to wait for connections.
  required: false
  type: int
  default: 10
{% endconfiguration %}

Once Home Assistant is started, a configurator will pop up asking you to enter verification code that is sent to your phone number or email.
