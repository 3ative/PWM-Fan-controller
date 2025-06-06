# ESPHome Automatic 4-Wire PWM (5-24v) Fan controller with Alarm.

Using a DALLAS temperature sensor and a threshold Slider, the speed of the Fan is automatically controlled from 0 to 100%. Making it ideal for ventilating / cooling your projects. I.E. Holiday Lights controller enclosure, Media Cabinet units and many more.


- With an on-board regulator to power the D1 Mini, this project is ready to control 5,12 or 24 Volt fans without modification
- (just make sure you power this project with the same voltage your fan uses).

## ESPHome 2024.6.0/1 Update notice:
If you are having problems with board resetting or DALLAS temperature after adding the ``one_wire:`` Breaking Change. [ssieb](https://github.com/ssieb) has got a fix for you.
Please add this External Component to your YAML:
```yaml
external_components:
  - source:
      type: git
      url: https://github.com/ssieb/esphome
      ref: onewire
    components: [ gpio ]
    refresh: 1min
```
 - I have also added it to the Yaml Files.
 - ### Note: This has now been "fixed" in ESPHome 2024.6.2 and therefore no longer required.

## Watch the tutorials here:
- [Part 1 - Building the Circuit Board](https://youtu.be/UQ6Gylbk8AI)
- [Part 2 - ESPHome Flash and Breakdown](https://youtu.be/72yCK_FiVSg)
- [Part 3 - Custom Dashboard Button](https://www.youtube.com/watch?v=oSUa1QDitAU)

---
### 🤝 Found this useful, want to say 'Thanks' and support my efforts. CHEERS🍺
| Buy me a Coffee | PATREON |
|-----------------|---------|
| [![Buy Me A Coffee](https://img.shields.io/badge/Buy%20Me%20A%20Coffee-donate-yellow.svg?style=flat-square&logo=buy-me-a-coffee)](https://www.buymeacoffee.com/3ative) | [![Patreon](https://img.shields.io/badge/Patreon-support-red.svg?style=flat-square&logo=patreon)](https://www.patreon.com/3ative) |
---

Problem 1: Temperature sensor cycles between On/NAN

Solution: Add a 4.7K Resistor

![image](https://user-images.githubusercontent.com/51385971/204195864-4291b25b-77ce-4076-a700-95b842102ca0.png)

____

Problem 2: Some Fans not turning off.
Andrew has a solution: [See Issue #2 Here](https://github.com/3ative/PWM-Fan-controller/issues/2)
