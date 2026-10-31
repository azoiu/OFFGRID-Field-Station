# Power budget

I checked the main parts and made a first estimate. These are planning numbers, not measurements from my finished device.

## Parts and estimated power

| Part | Planning power | Notes |
|---|---:|---|
| Raspberry Pi 5 8GB | 5–10 W | Depends on CPU load, USB devices and cooling |
| Waveshare 8DP-CAPLCD screen | about 4 W | The shop page identifies the exact model as 8DP-CAPLCD |
| 512 GB NVMe SSD and HAT | 1–3 W | Depends on the SSD and how much it is used |
| Heltec LoRa V3 | 0.3–1 W average allowance | Radio current changes a lot between receive, transmit and sleep |
| GPS module | 0.1–0.3 W allowance | Depends on the exact breakout board and antenna |
| Fans and small losses | 0.5–1 W | Estimate only |

The rough total is about **11–19 W**. A useful first number for battery sizing is **15 W average**. Heavy CPU use or high screen brightness can use more.

The Raspberry Pi power supply requirement is not the same as its average power use. Raspberry Pi recommends a 5 V, 5 A supply for Pi 5. This gives enough room for the board and USB devices. It does not mean the Pi always uses 25 W.

## Battery calculation

For 10 hours at 15 W:

- Load energy: 15 W × 10 h = 150 Wh
- Allow 90% efficiency for the DC/DC converters: 150 Wh / 0.90 = 167 Wh
- Keep around 20% energy in reserve: 167 Wh / 0.80 = 209 Wh battery energy

A 12.8 V, 20 Ah LiFePO4 battery has about 256 Wh nominal energy. This looks like a reasonable first candidate on paper.

At 15 W average, the estimate is roughly 12 hours after the conversion loss and reserve above. This is not a runtime guarantee. Cold weather, battery age, screen brightness, AI use and SSD activity can change it.

## First power layout

I plan to use separate regulated outputs:

- 5.1 V for the Raspberry Pi 5, rated for at least 5 A continuous.
- 5 V for the screen, rated for at least 2 A.
- 3.3 V for the GPS only if the selected GPS board needs it and does not already have a regulator.

The Pi and screen should not share a small converter. The Pi can have short current peaks and should get a stable supply.

## What still needs checking

- Measure the real power use after the first build.
- Check the exact SSD model and its peak current.
- Check the Heltec board current in the firmware mode I will use.
- Check the GPS breakout board input voltage and current.
- Check the battery pack dimensions against the case.
- Check converter cooling and efficiency at the actual load.

Sources:
- [Raspberry Pi power supply requirements](https://www.raspberrypi.com/documentation/computers/getting-started.html)
- [Waveshare 8DP-CAPLCD product page](https://opencircuit.shop/product/8inch-capacitive-touch-display-optical-bonding)
- [Heltec WiFi LoRa 32 V3](https://heltec.org/project/wifi-lora-32-v3/)

This is an estimate for choosing parts. It is not a final electrical design.
