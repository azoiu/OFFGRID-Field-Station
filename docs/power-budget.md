# Power budget

These are planning estimates. I have not measured the finished device yet.

## Parts and estimated power

| Part | Planning power | Notes |
|---|---:|---|
| Raspberry Pi 5 8GB | 5–10 W | Depends on CPU load, USB devices and cooling |
| Waveshare 8DP-CAPLCD screen | about 4 W | Manufacturer specification |
| 512 GB NVMe SSD and HAT | 1–3 W | Depends on SSD activity |
| Heltec LoRa V3 | 0.3–1 W average allowance | Radio current changes between receive, transmit and sleep |
| GPS module | 0.1–0.3 W allowance | Exact breakout still needs checking |
| Fans and small losses | 0.5–1 W | Estimate only |

The rough total is about **11–19 W**. I use **15 W average** for the first battery calculation.

The Raspberry Pi 5 can need a 5.1 V / 5 A supply when peripherals are connected. This is the supply capacity, not constant power use.

## Selected battery direction

I choose a supplier-built **4S1P LiFePO4 pack using four 3.2 V 15 Ah Gotion 33140 cells**.

- Nominal voltage: 12.8 V
- Capacity: 15 Ah
- Nominal energy: 192 Wh
- Maximum charge voltage: 14.6 V only if confirmed by the final cell datasheet

Why I changed it: the previous 25 Ah pouch cells were very thin, but their large 239 × 155 mm face would take almost all the case floor. Four 33140 cells arranged next to each other should use a smaller footprint and leave more space for the other electronics.

The cell-only envelope is approximately 140 × 133 × 33.2 mm. The complete pack will be larger. The supplier must provide a dimensioned drawing before I order it.

## Runtime calculation

Using 80% usable battery energy and 90% converter efficiency:

- At 15 W average: 192 Wh × 0.8 × 0.9 ÷ 15 W = about **10.2 hours**
- At 19 W average: about **8.1 hours**
- At 12 W average: about **11.5 hours**

The first practical target should be around **8 hours**. Ten hours is possible if the average load stays closer to 15 W or lower. This must be measured on the finished build.

## Power outputs

- Pi 5: Geekworm Pi5-5V5APD terminal-block version. Check its output voltage at the Pi under full load.
- Screen: Pololu D24V50F5, 5 V output, mounted with airflow.
- GPS and LoRa: powered from Pi USB or a separately fused 5 V branch after checking exact board versions.

## Still to verify

- Final cell datasheet and supplier-built pack dimensions
- BMS current rating and connector
- Charger voltage and current compatibility
- Exact SSD and HAT power
- Exact GPS breakout voltage/current
- Heltec transmit/receive current
- Converter temperature and cable voltage drop
- Real runtime test

Sources:
- [Raspberry Pi power requirements](https://www.raspberrypi.com/documentation/computers/raspberry-pi.html)
- [Geekworm Pi5-5V5APD](https://wiki.geekworm.com/Pi5-5V5APD)
- [Pololu D24V50F5](https://www.pololu.com/product/2851/specs)
- [Gotion 33140 15 Ah cell listing](https://www.lifepo4cells.eu/en/cell/gotion-33140-15ah-lifepo4-cell/)

This is not a completed power test.
