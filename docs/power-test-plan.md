# Power test plan

I need to test the real device before saying it can run for 10 hours.

## Before testing

- Check every converter output with a multimeter before connecting the Pi or screen.
- Check polarity on every connector.
- Check that the battery BMS and charger match the battery.
- Check that the fuse is fitted close to the battery.
- Check that wires and connectors do not get hot.
- Make sure the Pi has a safe shutdown method.

## Test setup

I will test the main station with:

- Raspberry Pi 5 and SSD
- 8-inch screen at normal brightness
- GPS running
- LoRa connected and receiving
- Fans running
- The normal OFFGRID software

I should use a watt meter or a DC power meter between the battery and the power board. I can also measure the 5 V outputs separately.

## What to write down

| Test | Result |
|---|---|
| Battery model and capacity | Not tested |
| Starting battery voltage | Not tested |
| Average power | Not tested |
| Highest power seen | Not tested |
| Screen brightness | Not tested |
| Test start and end time | Not tested |
| Runtime | Not tested |
| Converter temperature | Not tested |
| Any shutdown or low-voltage warning | Not tested |

## Test steps

1. Charge the battery using its correct charger.
2. Start the system with the normal settings.
3. Use the screen, maps, GPS and LoRa as they would be used outside.
4. Record battery voltage and power every 30 minutes.
5. Keep the test in a safe place and do not leave the first test unattended.
6. Stop the test before the BMS cuts power. Shut down the Pi properly.
7. Repeat the test once the setup is stable.

The first test should be done with a current-limited bench supply if possible, before connecting the battery pack.

## Pass condition

The goal is at least 10 hours with the normal setup. I will only write that it passed after a real test.

A short test on the desk does not prove that it will last 10 hours in cold weather outside.
