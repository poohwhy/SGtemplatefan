# SGtemplatefan
Home Assistant fan template scripts for Singapore market fans

The Home Assistant template fan integration is extremely useful but it does not have the best write up to understand how it works. A guide by Chris Lim on HA forums was a great benefit in understanding how it works: https://community.home-assistant.io/t/guide-template-fan-and-broadlink/323488

However, the guide is not targeted at fans most commonly available in the Singapore market (IR/RF controlled, controlled with off - 1 - 2 - 3 - 4 - 5 or similar settings). I'm sharing my configuration in the hope that this will help someone integrate their fans into HA.

The config is meant for a fan with memory function connected to a smart switch, with speed controls via IR/RF remote.

The behaviour of the fan is as follows:
  - The fan is turned on and off via the smart switch. This maintains ease of use with the physical smart switch.
  - When the fan is on:
    - Setting the fan speed percentage will send the appropriate speed command to the fan via the remote.
    - Setting the fan speed percentage to 0% will turn the fan off via the smart switch (not the remote).
    - Turning the fan off will be done via turning off the smart switch, but not set the fan speed percentage to 0% in HA.
  - When the fan is off:
    - Turning on the fan will first turn on the smart switch, then send the current fan speed percentage in HA via the remote to the fan. 
    - Turning on the fan when the fan speed percentage is 0% will turn on the smart switch, and send speed 2 via the remote to the fan.
 
 Comments are welcome, especially if the scripts can be optimised. I am quite new to HA and Github.
