Project: AEGIS, a two-node ESP32 safety mesh where sensors must agree before the alarm fires.
Why Track 1 over Track 2
Hardware is guaranteed. ESP32 boards and sensors are provided for everyone. Track 2 depends on an NVIDIA GPU, and cloud GPUs are limited to 30 first-come spots.
Physical demos win rooms. A device that senses, decides and trips a siren in front of the judges is more memorable than a bounding box on a screen.
Fewer failure points. No training runs, no model export mismatches, no GPU queue.
What you build:-
Node	Hardware	Job
Wearable	ESP32 + IMU (MPU6050) + buzzer	Detects free-fall, then impact, then post-fall stillness, on-device
Room node	ESP32 + PIR + ultrasonic (+ gas/temp if available) + relay/LED	Watches for motion and presence, and drives the siren
The killer features: consensus alerts
One source triggers: WARNING (soft buzzer, logged).
Two independent sources agree within 2 seconds: CRITICAL. The siren fires and the relay trips.
Edge-only, offline. Nodes talk over ESP-NOW with no Wi-Fi or cloud, which doubles as a privacy argument.
Closed loop. It acts physically, not just on a dashboard.
Heartbeats. Nodes ping every 2 seconds, and a dead sensor raises a “node offline” alert.
Live benchmark panel. It shows sensor-to-siren latency and false-alarm rate with consensus on and off.
