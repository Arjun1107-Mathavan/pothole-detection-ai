# Edge-AI Pothole & Road Quality Detector

Building AI course project

## Summary

This project aims to detect road hazards like potholes and surface cracks in real time using a smartphone or dashcam mounted on a vehicle. By running an on-device computer vision model, road anomalies are identified and geo-tagged automatically to aid municipal repairs and provide real-time road hazard alerts.

## Background

Road deterioration, particularly potholes and cracks, poses significant safety hazards:
* Accidents and Vehicle Damage: Potholes cause frequent tire punctures, rim bends, suspension damage, and fatal two-wheeler accidents.
* Delayed Municipal Audits: Local authorities often rely on slow, manual citizen complaints or expensive survey vehicles to inspect road health.
* Motivation: With widespread smartphone adoption, drivers can passively crowdsource road condition data during everyday commutes, turning regular commutes into real-time road maintenance audits.

## How is it used?

1. In-Vehicle Capture: A user mounts a smartphone or camera on a vehicle windshield/handlebar running the detection app.
2. On-Device Inference: The app continuously scans the road ahead using the camera feed.
3. Detection & Tagging: When a pothole or severe asphalt crack is recognized, its GPS coordinates, timestamp, and severity rating are recorded.
4. Aggregation: When connected to Wi-Fi, the app syncs logged hazard locations to a central map, which municipal bodies or navigation apps can use to schedule patch repairs or warn approaching drivers.

## Data sources and AI methods

* Data Sources: Public road inspection datasets (e.g., Road Damage Dataset - RDD2020 / RDD2022), dashcam and smartphone video feeds, and sensor telemetry (GPS and accelerometer/gyroscope readings).
* AI Methods: A lightweight Convolutional Neural Network (CNN) like MobileNetV2 optimized for real-time mobile inference, paired with sensor fusion to filter out visual false positives.

## Challenges

* Varying lighting, glare, heavy rain, and road shadows can confuse visual filters.
* Vehicle vibration and motion blur on rough roads.
* Privacy protection requires on-device processing so that license plates and faces are never stored or uploaded.
* Battery and thermal limits on mobile hardware requiring model quantization.

## What next?

* Integration with open community navigation apps to trigger real-time hazard audio warnings.
* Automated municipal road health heatmaps to streamline road repair dispatching.

## Acknowledgments

* Building AI course project by Reaktor and University of Helsinki.
* Reference datasets: Global Road Damage Detection Challenge (RDD2020/2022).
* 
