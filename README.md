# TimeBender

A Kontakt KSP script for real-time MIDI timing manipulation using pitch bend control.

![TimeBender Interface](path/to/screenshot.png)

## Overview

TimeBender allows you to dynamically shift MIDI note timing forward (decel) or backward (accel) during playback by using your pitch bend wheel. This creates expressive timing variations perfect for humanizing performances, creating ritardandos, or compensating for latency issues in orchestral libraries.

## Features

- **Real-time timing control**: Use pitch bend to rush or drag notes by up to ±250ms during playback from a DAW
- **Transport-aware**: Automatically bypasses delay when DAW transport is stopped for zero-latency live playing
- **Adjustable range**: Set predelay range from +/- 100ms to +/- 250ms
- **Visual feedback**: Animated knob shows current offset position, status indicator shows playback state
- **Info panel**: Built-in documentation accessible via info button

## How It Works

**Push the pitch bend forward or right** to hear notes later (decel or rit).  
**Pull the pitch bend back or left** to hear notes earlier (accel).

**Predelay** is the amount to set your track MIDI Delay in negative ms (not ticks).  
Range: +/- 100ms to +/- 250ms.

**Offset** displays the amount of rushing or dragging in ms.

## Installation

1. Download the latest release
2. Copy the `TimeBender` folder (containing images) to your ~Documents/Native Instruments/Kontakt/pictures directory
3. Copy the `.ksp` script into Kontakt's ~Documents/Native Instruments/Kontakt/presets/Multiscripts folder
4. Add Kontakt to a DAW track, click the KSP button, choose Preset > User > TimeBender

## Setup

1. **Set your DAW track delay**: Use **negative** ms (not ticks)
   - For 100ms Predelay: set track delay to **-100ms**
   - For 250ms Predelay: set track delay to **-250ms**

2. **Set KSP Predelay**: Match your track delay value
   - Track delay -100ms → Predelay 100ms
   - Track delay -250ms → Predelay 250ms

3. **Test pitch bend**: Move your pitch bend wheel to see timing offset changes in the UI

## Usage Tips

- **Center position** = notes play on time (with track delay compensation)
- **Max forward/right** = notes delayed by full predelay amount
- **Max back/left** = notes rushed by full predelay amount
- Use automation to create tempo rubato effects
- Works with both monophonic and polyphonic playing
- The script automatically disables when transport is stopped for zero-latency live performance

## Technical Details

- Version: 0.92
- Compatible with: Kontakt 5.6.8+
- All notes OFF on transport stop
- Pitch bend range: -8192 to +8191 (full 14-bit MIDI)

## Known Limitations

- Requires proper DAW track delay setup for full timing range

## Credits

Developed by [soundbed](https://github.com/nathancarlton)

## Version History

### v0.92
- Fixed note OFF timing at all predelay values
- Added transport-aware bypass for live playing
- Added status indicator

### v0.7-0.9
- Initial development and testing

## Links

- GitHub: https://github.com/nathancarlton/timebender
- Issues: https://github.com/nathancarlton/timebender/issues

## License

MIT License
