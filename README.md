Edge-AI Pothole & Road Quality Detector

Building AI course project

Summary

This project aims to detect road hazards like potholes and surface cracks in real time using a smartphone or dashcam mounted on a vehicle. By running an on-device computer vision model, road anomalies are identified and geo-tagged automatically to aid municipal repairs and provide real-time road hazard alerts.

Background

Road deterioration, particularly potholes and cracks, poses significant safety hazards:
Accidents and Vehicle Damage: Potholes cause frequent tire punctures, rim bends, suspension damage, and fatal two-wheeler accidents.
Delayed Municipal Audits: Local authorities often rely on slow, manual citizen complaints or expensive survey vehicles to inspect road health.
Motivation: With widespread smartphone adoption, drivers can passively crowdsource road condition data during everyday commutes, turning regular commutes into real-time road maintenance audits.

How is it used?

1. In-Vehicle Capture: A user mounts a smartphone or camera on a vehicle windshield/handlebar running the detection app.
2. On-Device Inference: The app continuously scans the road ahead using the camera feed.
3. Detection & Tagging: When a pothole or severe asphalt crack is recognized, its GPS coordinates, timestamp, and severity rating are recorded.
4. Aggregation: When connected to Wi-Fi, the app syncs logged hazard locations to a central map, which municipal bodies or navigation apps can use to schedule patch repairs or warn approaching drivers.

Data sources and AI methods

Data Sources
Public road inspection datasets (e.g., Road Damage Dataset - RDD2020 / RDD2022).
Open-access dashcam and smartphone video feeds captured under diverse lighting and weather conditions.
Sensor telemetry (GPS data and accelerometer/gyroscope readings for bump validation).

AI Methods
Convolutional Neural Networks (CNNs): A lightweight vision model (such as MobileNetV2, YOLO-Nano, or a fine-tuned CNN) optimized for real-time object detection on edge hardware.
Sensor Fusion: Combining visual bounding box detections with sharp vertical acceleration spikes measured by phone IMU sensors to minimize false positives (e.g., shadows vs. actual holes).

Challenges

Varying Lighting & Weather: Low lighting, heavy rain, water-filled potholes, or tree shadows can confuse purely visual filters.
Camera Shake & Blur: Vehicle vibrations, particularly on two-wheelers, can cause motion blur.
Privacy: Capturing camera footage on public roads requires on-device processing so that license plates and pedestrian faces are never uploaded or stored.
Hardware Constraints: Processing video streams at 15–30 FPS on budget mobile devices requires aggressive model quantization (e.g., INT8) to prevent phone overheating and battery drain.

What next?

Integrate the detection pipeline into community navigation systems (e.g., OpenStreetMap or crowd-navigation apps) for live audio alerts ("Caution: severe pothole 50m ahead").
Partner with municipal town planning bodies to provide an automated road deterioration heatmap and priority repair scheduling dashboard.

#Acknowledgments

* Based on concepts from the [Building AI course](https://buildingai.elementsofai.com/) by Reaktor and the University of Helsinki.
* Reference datasets: Global Road Damage Detection Challenge (RDD2020/2022).
