# Why

Original repo is great, but a bit out of date. To compile the code you need to do some troubleshouting. Figure out which version of platform use, select specific PR for external component. Also in my case even after all this changes - volume control was still broken. Volume was always on 100%.

# Main advantages

- Up-to-date (for now)
- Volume control works
- 2 settings for day and night brightness on LED strip (day/night hours are configurable)
- Still great project from **Tristam** and **jmiahman**

# Changes in comparison with the original repo:

- Schema changes
    - Max98357 connected to 5v instead of 3.3v (not necessary, only if you want to have louder sound)
- Script changes
    - Removed external_components
    - `speaker` and `media_player` replaced with standard ones
    - added `mixer` and `resampler` to allow `media_player` to utilize a single output `speaker`
    - The original LED effects were too bright for me, changed it
    - removed idle effect
    - removed onboard LED (it was used for debug only anyway)

# If Max98357 is too loud/quiet, you can adjust Gain
GAIN is, well, the gain setting. You can have a gain of 3dB, 6dB, 9dB, 12dB or 15dB.

- 15dB if a 100K resistor is connected between GAIN and GND
- 12dB if GAIN is connected directly to GND
- 9dB if GAIN is not connected to anything (this is the default)
- 6dB if GAIN is connected directly to Vin
- 3dB if a 100K resistor is connected between GAIN and Vin

# Problems

Only issue that I gound so far: after flashing firemware it extreamly quiet. But power cycle fixing it. So just unplag Type-C and plug it again.

# ORIGINAL READ ME
# Home Assistant Voice Assistant Smart Speaker

In the search for an "easy" Voice Assistant I ran across a lot of different implementations, many of which were confusing or left out key information needed. I decided to use an ESP32-S3-DevKitC-1-N8R2 Development Board. I finally found a Blog (https://tristam.ie/2024/1126/) that helped at least get a Voice Assistant up and running the only problem was, it wasn't a media_player. A lot of the work here is based on that work, except the Yaml file. I spent some time reviewing available working speakers including purchasing the ESP32-Box-S3 as an example of something that worked and finally came up with something that "works". It's still a work in progress, but I can play music on it, announcements, and it's working fairly well. Note: This is a Work in progress, not a finished project.  

# Files in the repo

- README.md - This readme
- schem (folder) - Contains a png wiring schematic for those who like a visual representation. This was taken from the aforementioned blog and edited.
- YAML (folder) - This contains the current working yaml for ESPHome in Home Assistant
- 3D Print - This contains the stl files to 3D print a box to place the components in. Currently, it is based on a remix (https://www.printables.com/model/982104-esp32-s3-esphome-voice-assistant-with-local-wake-w) of the original (https://www.printables.com/model/967157-esp32-s3-esphome-voice-assistant-with-local-wake-w) my plan is to not leave these unedited for long and make assembly more intuitive. 

# Parts list (Amazon - US)

- ESP32 Boards - [https://www.amazon.com/gp/product/B0C9H7Y66W](https://www.amazon.com/gp/product/B0C9H7Y66W?th=1)
- Omni directional Microphone (INMP441) - [https://www.amazon.com/gp/product/B09X3216DN](https://www.amazon.com/gp/product/B09X3216DN)
- Amplifier (MAX98357 3W) - [https://www.amazon.com/gp/product/B0CDWXZZCH](https://www.amazon.com/gp/product/B0CDWXZZCH)
- Speaker (Dayton Audio DMA45-4 1-1/2") - [https://www.amazon.com/gp/product/B07N1YW3SV](https://www.amazon.com/gp/product/B07N1YW3SV)
- Light Bar (Black WS2812B 5050 LED Light Stick) - [https://www.amazon.com/gp/product/B0D7CC469B](https://www.amazon.com/gp/product/B0D7CC469B)
- USB-C Connector - [https://www.amazon.com/gp/product/B0D7CN4BTV/](https://www.amazon.com/gp/product/B0D7CN4BTV/)
