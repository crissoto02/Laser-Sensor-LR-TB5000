# LR-TB5000 Laser Sensor Basic Test

## Test Objective:
Verify basic detection and output behavior of the Keyence LR-TB5000 laser sensor by connecting it to a 24 VDC power supply and observing its outputs with an oscilloscope.

## Connection Setup:
- Brown wire (Pin 1) → +24 VDC (Power Supply Positive)
- Blue wire (Pin 3) → 0 VDC (Power Supply Ground)
- Black wire (Pin 4) → Connected to Oscilloscope Channel 1 (Out1)
- White wire (Pin 2) → Connected to Oscilloscope Channel 2 (Out2)

## Observations:
- Upon powering on, the sensor emitted a red laser beam.
- Default settings observed:
  - Spot diameter: Set to level 1 (smallest spot size)
  - Activation distance: Factory default 500 mm
- Adjusted settings applied:
  - Out1 (Black wire):
    - Set to N.C. (Normally Closed)
    - Activation distance adjusted to 100 mm
    - Behavior:
      - Distance > 100 mm → Output = 24 VDC (observed on oscilloscope)
      - Distance ≤ 100 mm → Output ≈ 6 VDC (observed on oscilloscope)
  - Out2 (White wire):
    - Set to N.O. (Normally Open)
    - Activation distance adjusted to 300 mm
    - Behavior:
      - Distance < 300 mm → Output = 24 VDC (observed on oscilloscope)
      - Distance ≥ 300 mm → Output ≈ 6 VDC (observed on oscilloscope)

## Indicator Lights:
- Green LED ON: Indicates Out1 (Black wire) is OFF.
- Orange LED ON: Indicates Out1 (Black wire) is ON.

## Notes:
- Power supply used: 24 VDC regulated, 2.2 A capacity.
- No PLC was connected during this test. Outputs were measured directly via oscilloscope.

## Next Step
Integrate the LR-TB5000 sensor into PLC programming using Siemens S7-1200:
- Connect Out1 and/or Out2 to the PLC’s digital input terminals.
- Configure input tags in TIA Portal to monitor sensor outputs.
- Program logical operations based on object detection using Ladder or FBD programming.
- Validate behavior through real-time monitoring in TIA Portal.
