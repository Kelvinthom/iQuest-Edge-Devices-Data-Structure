# iQuest-Vib-Daq Data Specification

## Overview

The iQuest-Vib-Daq system provides vibration and condition monitoring data for predictive analytics and fault detection.  
This document defines the structure, parameters, and data types available for cloud ingestion and analytics processing.

---

## Data Streams

The Data Acquisition (DAQ) system generates the following primary data types.

---

### DAQ_Info

Metadata describing the acquisition setup, monitored asset, and sensor configuration.

#### Fields

- **Location**: Physical or operational site of the asset (e.g., plant section or machine area).
- **assetID**: Unique identifier of the monitored machine or equipment.
- **sensorLabels**: Human-readable names describing sensor positions and measurement orientation.
- **sensorID**: Internal identifiers mapped to each sensor channel or acquisition point.
- **Units**: Measurement units used across the system (e.g., g, mm/s, °C, ms, Hz).

#### Example Structure

```json
{
  "DAQ_Info": {
    "Location": "BM-Primary-Milling",
    "assetID": "Ball-mill-3",
    "sensorLabels": [
      "MTR-NDE-H",
      "G/OU-DE-V",
      "MTR-DE-H",
      "G/IN-DE-H",
      "G/IN-NDE-H",
      "G/OU-NDE-H",
      "PN-DE-H",
      "PN-NDE-H"
    ],
    "sensorID": [
      "POINT1",
      "POINT2",
      "POINT3",
      "POINT4",
      "POINT5",
      "POINT6",
      "POINT7",
      "POINT8"
    ],
    "Units": [
      "g",
      "mm/s",
      "degrees C",
      "ms",
      "Hz"
    ]
  }
}
````


### S_aRMS_t

Time-domain Root Mean Square (RMS) of acceleration signals. Represents overall vibration energy or intensity over time.

---

### S_vRMS_t

Time-domain Root Mean Square (RMS) of velocity signals. Commonly used to assess machine vibration severity and long-term condition trends.

---

### S_aTW

Acceleration Time Waveform data. Raw or processed acceleration signal sampled over time, used for transient detection and waveform analysis.

---

### S_vTW

Velocity Time Waveform data. Time-based velocity signal derived from sensors or integrated from acceleration, used in condition monitoring and diagnostics.

---

### S_aFFT

Frequency-domain representation (FFT) of acceleration signals. Used to identify vibration frequencies, harmonics, and mechanical fault signatures.

---

### S_vFFT

Frequency-domain representation (FFT) of velocity signals. Commonly used in rotating machinery diagnostics for clearer fault frequency interpretation.

---

### S_temp

Temperature measurements captured by the DAQ system. Used for thermal monitoring and detection of abnormal operating conditions.

---

### speedRMS

RMS value of rotational speed or speed variation. Indicates operational stability and mechanical performance consistency.


