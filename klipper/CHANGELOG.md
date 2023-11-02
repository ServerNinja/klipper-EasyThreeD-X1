# Changelog
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [0.0.1] - 2023-10-31 - Initial config
### Added
- Initial configuration of printer.cfg installed on stock EasyThreeD X1 printer

## [0.0.2] - 2023-11-2 - Improvements
### Added
- A macros.cfg file that can be included with the print.cfg
  - Includes a START_PRINT and END_PRINT macro that can be used along with Cura and Prusia slicers (see comments for details)
  - START_PRINT: includes homing all axis and performing a purge line just before printing
- Adjustments in print.cfg for closer accuracy (although some improvements are still needed)
- TODO:
  - Need to re-visit the "XYZ" and "Thin Wall" Calibration Cubes for further adjustments in printer.cfg
- Known Issues:
  - Layer separation and z-axis wobble when using z-hop. I tried lowering the z-hop distance and speed and it didn't seem to improve anything.
  - Z_ENDSTOP_CALIBRATE command seems to push the z axis position_endstop in the negative out of bounds requiring me to adjust the position_min to be a lower negative value. This step is still needed in order to get a perfect first layer.
  - Dealing with some y-axis wobbling, which can be seen at the top of an XYZ Cube test where the "Z" boarder is separating from the infill lines.
  - Using cubic infill causes major layer shifting and destroys your print after just a few layers in. Only tested "cubic", "grid", and "lines" infill patterns.
