# Hector SLAM for Drones (ROS Noetic)

This setup runs Hector SLAM on drones without wheel odometry.

## Setup

- LiDAR: RP LIDAR A3
- IMU: From MAVROS (`/mavros/imu/data`)
- SLAM: `hector_mapping` (scan matching only)
- Odometry: Faked via scan alignment and IMU orientation

## Packages

- `hector_mapping`: SLAM
- `hector_imu_attitude_to_tf`: Publishes IMU-based transform
- `mavros`: Provides IMU data

## Launch Files

- `example.launch`: Loads IMU transform
- `hector_slam.launch`: Starts mapping
  - Supports custom LiDAR topic, map size, etc.

## Notes

- Edit `example.launch` to change IMU topic
- No real odometry required
- IMU used for roll/pitch only
