# Google Nest / Smart Device GraphQL Schema

## Overview

This GraphQL schema models the Google Nest Smart Device Management (SDM) API, which provides access to Nest thermostats, cameras, doorbells, displays, and the structures and rooms they belong to. The API uses a trait-based model: each device exposes a set of traits (e.g., `ThermostatTemperatureSetpoint`, `CameraLiveStream`) that describe its capabilities and current state.

Source: https://developers.google.com/nest/device-access/reference/rest/v1/

## Schema Source

Conceptual schema derived from the Google Nest Device Access REST API reference, OAuth authorization model, and Smart Device Management trait documentation. Types cover devices, traits, structures, rooms, events, media streams, schedules, energy, and authentication.

## Type Summary

| Category | Types |
|---|---|
| Core Devices | Device, DeviceDetails, DeviceTraits, DeviceType |
| Thermostat | Thermostat, ThermostatHvac, ThermostatEco, ThermostatMode, Temperature, ThermostatSetpoint, Humidity, HvacStatus, EcoMode |
| Camera | Camera, CameraStream, CameraMotion, CameraSound, CameraClip, EventImage, VideoStream, AudioStream, CameraEvent |
| Display | Display, DisplayBrightness, DisplayRotation, DisplayMedia |
| Audio | Volume, AudioDevice, AudioRing |
| Doorbell | DoorBell, DoorbellChime, DoorbellPress |
| Lock | Lock, LockDetails, LockSecurity, LockKeypad, AccessCode, UnlockHistory |
| Structure | Structure, Room, RoomDetails, StructureMode |
| Presence | Away, Home, Sleep, Motion, MotionEvent, PresenceEvent |
| Media | ContinuousVideoRecording, SmartDisplay |
| Schedule | Schedule, DeviceSchedule, Time, SetpointSchedule |
| Energy | EnergyUsage |
| Auth | APIKey, OAuthToken, ProjectID, Webhook |

## Usage

Query devices within a project, read traits, and execute commands. All requests require OAuth 2.0 authorization with the `https://www.googleapis.com/auth/sdm.service` scope.

```graphql
query {
  devices(projectId: "my-project-id") {
    id
    type
    thermostat {
      mode {
        currentMode
      }
      temperature {
        ambientTemperatureCelsius
      }
      hvacStatus {
        status
      }
    }
    structure {
      displayName
    }
    room {
      displayName
    }
  }
}
```

## References

- REST API Reference: https://developers.google.com/nest/device-access/reference/rest/v1/
- Authorization: https://developers.google.com/nest/device-access/authorization
- Traits Reference: https://developers.google.com/nest/device-access/traits
- Getting Started: https://developers.google.com/nest/device-access/get-started
