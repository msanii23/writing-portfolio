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

```json
{
  "vehicle_id": "TAV-001",
  "status": "idle",
  "battery_level": 92,
  "location": {"lat": 37.7749, "lon": -122.4194},
  "speed": 0.0
}

<br>
