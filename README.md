# dashcam-for-road-obstacle-avoidance-in-low-visibility-conditions

Problem statement:
Road safety and infrastructure maintenance are critical challenges that affect millions of drivers worldwide. Potholes and road irregularities not only cause significant damage to vehicles but also contribute to a high number of accidents, particularly in low visibility conditions such as fog, rain, or nighttime driving. Existing technologies for pothole detection and road monitoring, such as manual inspections, fixed sensors, and user-reported apps, are often limited by high costs, insufficient coverage, and a lack of real-time data. These limitations hinder the ability to proactively address road hazards, leading to delayed maintenance, increased vehicle damage, and elevated risks of accidents.
Existing methodologies and their drawbacks
1. Manual Inspection
Methodology: Manual inspection involves road personnel visually surveying roadways to identify and document potholes.
Drawbacks: Manual inspection is time-consuming, requiring significant human resources and extended periods to cover large road networks.
2. Fixed Sensors
Sensors Used: Fixed sensors in road surfaces include strain gauges, accelerometers, and piezoelectric sensors. Strain gauges detect surface deformation, accelerometers measure vibrations and changes in acceleration, and piezoelectric sensors assess pressure and strain.
Methodology: These sensors are embedded directly into the road surface to continuously track its condition. As traffic and environmental factors affect the road, the sensors capture data .
Drawbacks: The high cost of installing and maintaining these sensors is a major drawback. The fixed nature of the sensors means their coverage is limited to specific locations.
3. Mobile Apps
Methodology: Users report potholes through mobile applications, allowing them to input details and location of road issues directly from their smartphones.
Drawbacks: The system relies on active user participation, which can lead to inconsistent and delayed data
4. Vehicle-Mounted Systems
A) Image Processing-Based Detection
Sensors Used: Cameras are used to capture images or video of the road surface.
Methodology: The captured images are processed using computer vision techniques to detect potholes based on their texture, shape, and shadow patterns.
Drawbacks: Performance can be significantly affected by lighting conditions, shadows, rain, or fog, which may obscure the road surface and it can also lead to false positives or negatives.
B) Vibration-Based Detection
Sensors Used: Accelerometers and gyroscopes are used to monitor vehicle vibrations and orientation changes.
Methodology: These sensors detect sudden changes in vibrations and orientation caused by potholes, indicating their presence as the vehicle moves over affected areas.
Drawbacks: The system may produce false positives, such as rough roads or speed bumps, which can create similar vibrations and it is not real time detection.
C) Laser Scanning
Sensors Used: LIDAR (Light Detection and Ranging) systems
Methodology: LIDAR uses laser beams to scan the road surface and detect deviations that indicate potholes or other irregularities.
Drawbacks: LIDAR equipment is costly, making it impractical for widespread deployment. Its performance can be affected by environmental conditions such as rain or fog, which may obscure the laser's path.
D) Ultrasonic Detection
Sensors Used: Ultrasonic sensors
Methodology: These sensors emit ultrasonic waves and measure the time it takes for the waves to bounce back from the road surface. This information helps identify dips or depressions that may indicate the presence of potholes.
Drawbacks: Ultrasonic sensors have a limited range, making them effective only for small-scale detection. They can also be affected by road noise and other environmental factors.
E) Infrared Thermography
Sensors Used: Infrared cameras
Methodology: Infrared cameras capture thermal images of the road surface, identifying potholes based on their different thermal properties compared to the surrounding area.
Drawbacks: Infrared thermography is highly dependent on ambient temperature and weather conditions, which can affect the accuracy of the thermal readings.
5. GIS-Based Mapping
Methodology: GIS-Based Mapping utilizes Geographic Information Systems (GIS) to create detailed maps of road conditions.
Drawbacks: A major drawback is the lack of real-time data, which limits the effectiveness of these maps for up-to-date navigation and immediate decision-making.
Proposed system:
This project introduces a new system for detecting and mapping potholes using an ESP32 microcontroller and other modern tools. The system uses a Yolo V8 model to analyze live video from a moving vehicle and find potholes. When a pothole is detected, its location is recorded and sent to a central database.The NEO GPS Module tracks the exact location of each pothole, while the MPU6050 sensor measures the impact of the potholes on the vehicle. This helps to understand how bad each pothole is.
Pothole detection model processes video to spot potholes. At the same time, the GPS and MPU6050 sensors collect data about the vehicle’s position and how much it is affected by the potholes. This information is combined to create a detailed record of each pothole, including where it is, how severe it is, and when it was found. The system checks and updates the status of reported potholes on a digital map.
The system updates the map in real-time and allows users to report potholes. If a pothole has been fixed, it is removed from the map. If it is still there, it stays highlighted. This helps keep the map accurate and current.The system also handles poor visibility conditions, like rain or fog, by updating pothole information based on GPS data. This ensures potholes are still tracked even when visibility is low.
How the Proposed System Overcomes Existing Research Gaps
1.
Integration of Multiple Data Sources:
The system combines video data, gyroscope readings, and GPS information, offering a accurate assessment of pothole conditions. This multi-sensor approach reduces false positives and negatives.
2.
Real-Time Detection :
With machine learning algorithms, the system detects and classifies potholes as critical or non-critical in real time overcoming traditional gyro sensor based systems that detect after coming into contact with the pothole.
3.
Crowdsourced Data :
By aggregating reports from multiple users, the system creates a dynamic and detailed map of pothole hotspots. This crowdsourced approach improves detection accuracy, identifies patterns, and provides a broader coverage than single-vehicle systems.
4.
Adaptability in Low Visibility Conditions:
The system uses GPS data to update pothole information in low visibility conditions like rain or fog, overcoming the challenges faced by camera-based systems that struggle in poor visibility. This ensures continuous operation and accurate updates even when visual data is limited.
5.
Cost-Effectiveness:
Utilizing the ESP32 microcontroller and standard sensors makes the system more affordable and scalable compared to expensive technologies like LIDAR.
6.
Continuous Learning :
The machine learning component allows the system to adapt and improve as more data is collected, leading to more accurate pothole detection over time. This feature addresses the static nature of traditional detection methods.
7.
Dynamic Status Updates:
The system dynamically checks and updates the status of reported potholes. If a pothole is repaired, it is removed from the map, while unresolved issues are highlighted, improving maintenance prioritization and responsiveness compared to static maps.
8.
Efficient Resource Utilization:
The system’s use of low-cost, readily available components ensures efficient use of resources, reducing the need for extensive infrastructure and enabling more effective management of road maintenance budgets.

Components and Technologies Used:
Image processing module (Tentative) :
•
Yolo V8 Model ( does not tell the status of the pothole like critical , normal etc):
The Yolo (You Only Look Once) V8 model is a deep learning algorithm used for real-time object detection. It is known for its speed and accuracy in identifying objects within images or video streams.
•
Monocular Depth Estimation (using Single Camera is harder to achieve and accuracy is lower compared to other image detection models)
Monocular depth estimation is a method where a deep learning model (such as a Convolutional Neural Network) is trained to estimate depth from a single image. The model learns to recognize depth cues such as texture, shading, and object size from the image.
IoT Sensors connected via Arduino Uno:
IoT sensors are used to collect environmental data through the ArduIno IDE. In this context, they play a critical role in verifying and marking detected potholes.
The specific sensors used
•
NEO GPS Module: This module provides accurate geospatial data, allowing the system to track the exact location of potholes.
•
MPU6050: This sensor is used for collecting accelerometer and gyroscope information, which helps in understanding the severity and impact of road irregularities.
•
ESP32 Camera module.
