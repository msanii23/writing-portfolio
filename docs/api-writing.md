# Torc Autonomous Vehicle API Documentation
**Version:** 1.0  
**Last Updated:** 2026-02-11  
**Audience:** Developers, Engineers, System Integrators
## Overview
The Torc AV API provides developers with tools to **monitor, control, and interact** with autonomous vehicles. It enables **vehicle telemetry**, **navigation commands**, and **diagnostics**, supporting integration into **fleet management systems** and **simulation environments**.

---
## Authentication
- **Method:** API Key  
- **Header Format:** Authorization: Bearer <YOUR_API_KEY>
- **Notes:** API keys are issued via the Torc Developer Portal and must be kept confidential.

---

## Endpoints

### Get Vehicle Status: GET /vehicles/{vehicle_id}/status
**Description:** Returns the real-time operational status of a vehicle.

**Response Example:**

{
  "vehicle_id": "TAV-001",
  "status": "idle",
  "battery_level": 92,
  "location": {"lat": 37.7749, "lon": -122.4194},
  "speed": 0.0
}

### Send Navigation Command: POST /vehicles/{vehicle_id}/navigate

**Description:** Sends a command for the vehicle to navigate to a specific GPS coordinate.

**Request Body:** 
{
  "latitude": 37.7751,
  "longitude": -122.4185,
  "speed_limit": 5.0
}

**Response Example:**

{
  "vehicle_id": "TAV-001",
  "status": "navigating",
  "target_location": {"lat": 37.7751, "lon": -122.4185}
}

### Retrieve Diagnostic Data: GET /vehicles/{vehicle_id}/diagnostics

**Description:** Provides detailed diagnostics including sensor health, error codes, and system alerts.

**Response Example:**

{
  "vehicle_id": "TAV-001",
  "diagnostics": {
    "lidar_status": "operational",
    "camera_status": "operational",
    "gps_status": "operational",
    "errors": []
  }
}

**Error Codes**

| Code | Meaning               |
| ---- | --------------------- |
| 400  | Bad Request           |
| 401  | Unauthorized          |
| 404  | Vehicle Not Found     |
| 500  | Internal Server Error |

### Notes
GPS coordinates are in decimal degrees.
Vehicles execute navigation commands sequentially; new commands override previous queued commands.
Use the Torc Sandbox Environment for safe testing before production deployment.
