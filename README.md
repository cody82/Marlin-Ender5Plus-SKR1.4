# Marlin-Ender5Plus-SKR1.4
Marlin 2.0.5.3 configuration for Ender 5 Plus and BigTreeTech SKR1.4 Turbo + TMC2208

# Notes
* Z_MIN_PROBE_USES_Z_MIN_ENDSTOP_PIN must be enabled, otherwise the BLTouch will not deploy and crash the nozzle during Z-homing.
* BLTouch sensor must be connected to the Z endstop pins instead of probe pins.
* Filament sensor is not used.

## BLTouch on probe pins:
https://github.com/bigtreetech/BIGTREETECH-SKR-V1.3/issues/207

Comment out the line in Configuration.H:

//#define Z_MIN_PROBE_USES_Z_MIN_ENDSTOP_PIN

and define:

#define Z_MIN_PROBE_PIN P0_10

Open Conditionals_LCD.h located in ..Marlin\src\inc.. and change these lines:

#define HAS_CUSTOM_PROBE_PIN DISABLED(Z_MIN_PROBE_USES_Z_MIN_ENDSTOP_PIN)

#define HOMING_Z_WITH_PROBE (Z_HOME_DIR < 0 &&!HAS_CUSTOM_PROBE_PIN)

to:

#define HAS_CUSTOM_PROBE_PIN true

#define HOMING_Z_WITH_PROBE (Z_HOME_DIR < 0)

Also the unused Z endstop pins must be shorted.
