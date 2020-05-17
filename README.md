# Marlin-Ender5Plus-SKR1.4
Marlin 2.0.5.3 configuration for Ender 5 Plus and BigTreeTech SKR1.4 Turbo + TMC2208

# Notes
* Z_MIN_PROBE_USES_Z_MIN_ENDSTOP_PIN must be enabled, otherwise the BLTouch will not deploy and crash the nozzle during Z-homing.
* BLTouch sensor must be connected to the Z endstop pins instead of probe pins.
* Filament sensor is not used.
