# Gain Proxy

## Give a target gain control a dedicated, consistent fader.

Some Q-SYS components expose a gain control that is awkward to operate from a
custom panel, or use a different fader scale than the rest of a design. Gain
Proxy provides a control-only front end for one existing component control,
with its own dB range, fader taper, and optional ramp buttons.

## Setup

Enable **Script Access** on the target component. On the Setup page, select its
Code Name and the writable Float control to proxy. The plugin does not add
audio pins or embedded DSP.

Choose **dB Value** when the target's value is in dB. For a normalized `0–1`
target, choose **Position Value (0-1)** and set **Source Taper** to match the
target's curve. Set **Min Gain (dB)** and **Max Gain (dB)** to the target's
range. **Presented Taper** independently sets how this plugin's knob and fader
display that range.

## Controls and behavior

- The gain readout, knob, and fader stay synchronized with the target.
- External target changes are polled; the proxy does not replace the target's
  event handler.
- Binding or changing setup reads the target without writing a new value.
- Enable **Ramp Controls** to add Increase/Decrease buttons. A short press
  nudges the gain; holding starts a ramp after **Hold Off**. Choose continuous
  ramping or discrete steps.
- The logarithmic taper uses the mixer curve used by Log Gain; it is not
  automatically detected from the target.

This plugin controls a component value only. It provides no audio processing,
bypass, mute, polarity inversion, or audio metering.
