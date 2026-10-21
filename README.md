# Sea2Sky (Sea2Air Repository)

Sea2Sky is an open, cross-domain GNSS and multisensor dataset designed for fair positioning comparisons across **road**, **water**, and **air**.  
This repository is intended to host dataset metadata, calibration, baseline code, and benchmark splits for reproducible evaluation.

## Why this dataset exists

Positioning errors in automated systems can directly contribute to safety-critical incidents. Existing GNSS benchmark datasets are valuable but are typically domain-specific (mostly road) and collected with different sensor stacks and reference pipelines, which makes cross-domain conclusions difficult.

Sea2Sky addresses that gap by keeping the following fixed across domains:
- Sensor hardware
- Time synchronization strategy
- Reference trajectory approach
- Baseline algorithm evaluation workflow

With this setup, performance differences can be attributed to environment/domain effects rather than changes in instrumentation.

## Core contributions

1. **Cross-domain dataset with one fixed low-cost rig**  
   A common sensor suite is used on:
   - A car (urban roads, freeway, hills, racetrack)
   - A buoy/boat platform (Lake Washington and Lake Sammamish)
   - A UAV platform (60 Acres Park, Redmond, WA)

2. **Unified multimodal raw data release**  
   The dataset includes synchronized GNSS and complementary sensing modalities suitable for GNSS-only and multisensor fusion research.

3. **Open benchmark protocol**  
   Fixed train/test splits and baseline code are provided so new methods can be compared on identical data partitions.

## Sensor and reference stack

- **GNSS observables:** 5× u-blox ZED-F9P multiband receivers
- **IMU:** 2 inertial measurement units
- **RF IQ capture:** 5-channel KrakenSDR recording GPS L1 IQ samples
- **IQ metadata format:** ION GNSS SDR Metadata Standard
- **Vision:** DJI Osmo 360 camera
- **LiDAR:** Slamtec RPLIDAR A2 (2D)
- **Time base:** common PPS synchronization
- **Reference trajectory:** SparkFun RTK Postcard with NTRIP corrections from WSRN

## Initial release summary

- 8 sequences
- 5.0 hours total data
- 44 km total coverage
- Data segments across road, water, and air domains

Additional collection is ongoing, and future releases will expand coverage.

## What is included

Planned/available repository assets:
- Raw GNSS observables
- GPS L1 IQ recordings + ION SDR metadata
- IMU, camera, and LiDAR streams
- Calibration files
- RTK reference trajectories
- Baseline positioning scripts
- Fixed train/test split definitions

## Baseline evaluation scope

Baselines are intended to include:
- Standard GNSS positioning methods
- GNSS/INS fusion methods
- Camera-aided and LiDAR-aided positioning variants

Each method is run consistently across all domains to support controlled performance comparisons.

## Intended use

Sea2Sky supports research on:
- GNSS multipath and NLOS mitigation
- Cross-domain localization robustness
- Sensor fusion for low-cost navigation stacks
- Generalization of positioning algorithms across environment types

## Citation

If you use Sea2Sky in research, please cite the corresponding dataset/paper release when citation metadata is published in this repository.
# Sea2Air

## Citation

If you use this dataset, please cite: https://doi.org/10.5281/zenodo.23374107
