# Google Nest Smart Device Management API

The Smart Device Management (SDM) API is a REST API that allows developers to manage Google Nest devices including thermostats, cameras, doorbells, and displays. It provides access to device traits and commands using a trait-based model, enabling applications to read device state, execute commands to control devices, and manage structures and rooms within a home.

## Artifacts

- **APIs.yml** - Machine-readable API metadata following the APIs.json specification.
- **OpenAPI** (`openapi/openapi.yml`) - OpenAPI 3.1.0 specification describing the SDM API endpoints, parameters, and response schemas.
- **JSON Schema** (`json-schema/google-nest.json`) - JSON Schema (draft 2020-12) defining device, structure, room, and command objects.
- **JSON-LD** (`json-ld/google-nest.jsonld`) - JSON-LD context mapping SDM API terms to schema.org and API-specific vocabularies.

## Key Endpoints

| Method | Path | Description |
|--------|------|-------------|
| GET | `/enterprises/{id}/devices` | List all authorized devices |
| GET | `/enterprises/{id}/devices/{deviceId}` | Get device details and traits |
| POST | `/enterprises/{id}/devices/{deviceId}:executeCommand` | Execute a device command |
| GET | `/enterprises/{id}/structures` | List structures (homes) |
| GET | `/enterprises/{id}/structures/{structureId}/rooms` | List rooms in a structure |

## Resources

- [Device Access Documentation](https://developers.google.com/nest/device-access)
- [Getting Started](https://developers.google.com/nest/device-access/get-started)
- [API Reference](https://developers.google.com/nest/device-access/api)

## Maintainer

Kin Lane - kin@apievangelist.com
