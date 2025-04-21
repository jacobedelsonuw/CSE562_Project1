# Tilt Tracker iOS App

A CoreMotion-based iOS application for accurately measuring, analyzing, and visualizing device tilt using accelerometer and gyroscope sensors.

## Features

- **Sensor Calibration**: Measure bias and noise in accelerometer and gyroscope sensors
- **Multiple Tilt Measurement Methods**:
  - Accelerometer-only tilt tracking
  - Gyroscope-only tilt tracking
  - Complementary filter fusion (combines both sensors)
- **Real-time Visualization**: Visual tilt indicator and real-time charts
- **Statistical Analysis**: Mean, standard deviation, min/max values for each method
- **Drift Compensation**: Advanced algorithms to prevent gyroscope drift
- **Motion Detection**: Intelligent detection of device movement vs. rest

## How It Works

### Part 1: Calibration
Captures sensor data when the device is perfectly still to calculate:
- Bias offsets in all sensor axes
- Noise levels in all sensor axes
- Initial tilt position for zeroing

### Part 2: Method Comparison
Perform 1-minute tests for each tilt measurement method:
- **Accelerometer**: Provides absolute tilt measurements but is sensitive to vibrations
- **Gyroscope**: Provides smooth measurements but suffers from drift over time
- **Complementary Filter**: Combines both sensors for optimal performance

### Demo Mode
Real-time tilt visualization with:
- Visual tilt indicator
- Current tilt value display
- Motion state detection
- Optional chart view showing all three measurement methods simultaneously

## Technical Details

- **Complementary Filter**: Implements the algorithm described in [LaValle et al. (2014)](https://msl.cs.illinois.edu/~lavalle/papers/LavYerKatAnt14.pdf)
- **Drift Compensation**: Uses time-based adaptive correction and dynamic rate estimation
- **Zeroing**: All measurements are zeroed from the initial calibration position
- **Motion Detection**: Uses noise-adaptive thresholds for robust motion detection
- **Low-Pass Filtering**: Applies optional filtering to reduce sensor noise

## Requirements

- iOS 16.0 or later
- iPhone with accelerometer and gyroscope sensors

## Installation

1. Clone the repository
2. Open the project in Xcode 14 or later
3. Build and run on a physical iOS device (simulators do not provide sensor data)

## Usage

1. First run Part 1 to calibrate the sensors (keep the device perfectly still)
2. Use Part 2 to compare the different tilt measurement methods
3. Use Demo mode for real-time tilt visualization and testing

## License

MIT 
