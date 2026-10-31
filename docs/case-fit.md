# Case fit notes

I want to keep the SINOCASE SC001. The listed inside size is 255 × 190 × 85 mm. I measured about 58 mm usable depth in the bottom part.

## Screen

The main screen is the Waveshare 8DP-CAPLCD. Its panel size is about 194 × 119 mm. It should fit the general case footprint, but I still need a physical template to check the lid, hinge and bezel.

## Battery choice

I am no longer using the 32700 cylindrical-cell idea. It was not a good layout for the shallow case because the cells are about 70 mm long.

The new choice is a supplier-made 4S1P pouch-cell LiFePO4 pack. A 25 Ah pouch cell listed by Topwell is about 239 × 155 × 6.6 mm. Four cells in series have about 26.4 mm cell thickness before compression plates, insulation, BMS and wiring.

Reference: https://www.topwellpower.com/products/5c-32v-20ah-lithium-iron-phosphate-pouch-cell

The complete pack must be made to a maximum target size of **245 × 175 × 45 mm**. The supplier must provide a dimensioned drawing. The real flat area inside the case must be measured before ordering.

## Layout plan

- Battery flat on the bottom of the case.
- Raspberry Pi and SSD above or beside the battery only if cooling and service access remain possible.
- Keep the DC/DC modules away from the pouch cell and give them airflow.
- Put the screen in the lid.
- Secure the battery so it cannot slide or be crushed when the case is carried.

## Measurements still needed

- Clear flat bottom area between ribs.
- Actual depth at battery location.
- Hinge and screw mount positions.
- Height available with the lid closed.
- Space for cable bends, fuse and switch.

The battery cell size looks promising, but the finished pack fit is not confirmed until the supplier sends its drawing and I check the case with a template.
