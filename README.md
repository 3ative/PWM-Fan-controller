# ESPHome Automatic 4-Wire PWM (5-24v) Fan controller with Alarm.

Using a DALLAS temperature sensor and a threshold Slider, the speed of the Fan is automatically controlled from 0 to 100%. Making it ideal for ventilating / cooling your projects. I.E. Holiday Lights controller enclosure, Media Cabinet units and many more.


- With an on-board regulator to power the D1 Mini, this project is ready to control 5,12 or 24 Volt fans without modification
- (just make sure you power this project with the same voltage your fan uses).

### Parts List:
- **MOSFET: STP16NF06L** - discontinued. [Datasheet](https://4donline.ihs.com/images/VipMasterIC/IC/SGST/SGSTS38803/SGSTS38803-1.pdf?hkey=6D3A4C79FDBF58556ACFDE234799DDF0)

  Logic-level gate (VGS(th) 1-2.5V) - fully switches with 5V, so it drives straight off the D1 Mini's GPIO with no gate driver needed.

  **Equivalent: IRLZ44N** - same TO-220 pinout, logic-level, VDS 55V/ID 47A.
  
  
**Replacement part**- *no board changes*:
- "IRLZ44NPBF" Buy from [Mouser](https://eu.mouser.com/ProductDetail/Infineon-IR/IRLZ44N?qs=zO0nedAqnNIAphT7g5cSVQ%3D%3D) or [DigiKey](https://azcus.digikey.com/en/products/detail/infineon-technologies/IRLZ44NPBF/811808) - both ship worldwide, single units, no account needed.
  
 * Avoid eBay - mislabelled/off-spec stock reported for this part.

*Everything else can be found here:  Amazon UK * : https://amzn.to/3uRw8fi*
- ###### * As an Amazon Associate I earn from qualifying purchases. Using this link ⇈ provides small monetary support for my channel at no extra cost to you.💖

### ESPHome 2024.6.0/1 Update notice:
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

### Watch the tutorials here:
- [Part 1 - Building the Circuit Board](https://youtu.be/UQ6Gylbk8AI)
- [Part 2 - ESPHome Flash and Breakdown](https://youtu.be/72yCK_FiVSg)
- [Part 3 - Custom Dashboard Button](https://www.youtube.com/watch?v=oSUa1QDitAU)

---

<div align="center">

### 💖 Support This Project

Found this useful? Want to say thanks and fuel future creations?

**Your support keeps the creativity flowing!** 🍺✨

<table>
  <tr>
    <td align="center">
      <a href="https://www.buymeacoffee.com/3ative">
        <img src="https://img.shields.io/badge/Buy%20Me%20A%20Coffee-Support-yellow.svg?style=for-the-badge&logo=buy-me-a-coffee&logoColor=white" alt="Buy Me A Coffee"/>
        <br/>
        <b>☕ Buy me a Coffee</b>
      </a>
    </td>
    <td align="center">
      <a href="https://www.patreon.com/3ative">
        <img src="https://img.shields.io/badge/Patreon-Become%20a%20Patron-red.svg?style=for-the-badge&logo=patreon&logoColor=white" alt="Patreon"/>
        <br/>
        <b>💖 Join on Patreon</b>
      </a>
    </td>
  </tr>
</table>

**Every contribution helps bring more awesome projects to life!** 🚀

</div>

---

Problem 1: Temperature sensor cycles between On/NAN

Solution: Add a 4.7K Resistor

![image](https://user-images.githubusercontent.com/51385971/204195864-4291b25b-77ce-4076-a700-95b842102ca0.png)

____

Problem 2: Some Fans not turning off.
Andrew has a solution: [See Issue #2 Here](https://github.com/3ative/PWM-Fan-controller/issues/2)
