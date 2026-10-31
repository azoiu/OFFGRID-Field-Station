# Power budget

I checked the main parts and made a first estimate. These are planning numbers, not measurements from the finished device.

## Parts and estimated power

| Part | Planning power | Notes |
|---|---:|---|
| Raspberry Pi 5 8GB | 5–10 W | Depends on CPU load, USB devices and cooling |
| Waveshare 8DP-CAPLCD screen | about 4 W | Product page identifies the exact model |
| 512 GB NVMe SSD and HAT | 1–3 W | Depends on SSD activity |
| Heltec LoRa V3 | 0.3–1 W average allowance | Radio current changes between receive, transmit and sleep |
| GPS module | 0.1–0.3 W allowance | Exact breakout board still needs checking |
| Fans and small losses | 0.5–1 W | Estimate only |

The rough total is about **11–19 W**. I use **15 W average** for the first battery calculation. Heavy CPU use or high screen brightness can use more.

The Raspberry Pi 5 needs a 5.1 V supply. The official 27 W supply can provide 5.1 V at 5 A. This is the available supply capacity, not the Pi's constant power use.

## Selected battery target

I choose a supplier-made 4S1P LiFePO4 pouch-cell pack:

- 12.8 V nominal
- 25 Ah
- 320 Wh nominal energy
- matched 4S LiFePO4 BMS

For 10 hours at 15 W:

- Load energy: 150 Wh
- With 90% converter efficiency: 167 Wh from the battery
- With 20% reserve: about 209 Wh nominal required

The selected 320 Wh target gives more margin.

Using 80% usable energy and 90% converter efficiency:

- At 15 W average: about 17.1 hours
- At 19 W average: about 13.5 hours

These are calculations, not a runtime promise. Cold weather, battery age, actual system load and converter temperature can change the result.

## Selected power outputs

- Raspberry Pi 5: Geekworm Pi5-5V5APD, 9–24 V input, USB-C 5 V/5 A PD output. It needs more than 30 W input for full output.
- Screen: Pololu D24V50F5, 5 V output, with cooling and airflow.
- GPS and LoRa: powered from the Pi USB or a separately fused 5 V branch after checking the exact board versions.

## What still needs checking

- Measure real power after the first build.
- Check exact SSD model and peak current.
- Check Heltec current in the firmware mode.
- Check GPS breakout voltage and current.
- Confirm battery size and BMS with the supplier.
- Check converter cooling and cable voltage drop.

Sources:
- [Raspberry Pi power requirements](https://www.raspberrypi.com/documentation/computers/raspberry-pi.html)
- [Geekworm Pi5-5V5APD](https://wiki.geekworm.com/Pi5-5V5APD)
- [Pololu D24V50F5](https://www.pololu.com/product/2851/specs)

This is still an estimate. It is not a completed power test.
