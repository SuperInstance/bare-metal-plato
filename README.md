# bare-metal-plato

A C library and protocol for giving IoT devices (ESP32, RP2040) an AI-powered upgrade path. Devices start as raw sensors and progressively gain autonomy through a 5-level "turbo-shell" system where agents discover devices, assess capabilities, and flash new intelligence.

The vision: a teacher says "I want 30 temperature sensors that water plants when the soil is dry" and the agent system discovers all devices, writes firmware, flashes them, and creates a real-time dashboard — no C or embedded experience required.

## What's Here

| File | Description |
|------|-------------|
| `plato_client.h` / `plato_client.c` | C client library for connecting to PLATO servers over TCP |
| `plato_mcp.h` / `plato_mcp.c` | MCP (Model Context Protocol) integration for agent-device communication |
| `EMBODIMENT-PROTOCOL.md` | The 5-step handshake protocol (Discover → Assess → Bridge → Confirm → Upgrade) |
| `EDUCATIONAL-VISION.md` | Design philosophy and use cases for educators and makers |
| `examples/` | Reference implementations |

### Example Firmware

- `examples/esp32_sensor_node.c` — ESP32 sensor using the PLATO client
- `examples/rp2040_led_node.c` — RP2040 LED controller
- `examples/agent_embodiment.py` — Python agent that discovers and upgrades devices

## Turbo-Shell Levels

| Level | Name | Behavior |
|-------|------|----------|
| 0 | Raw | Publishes raw sensor readings |
| 1 | Conditioned | Threshold filtering, noise reduction |
| 2 | Smart | Context-aware decisions, local state machine |
| 3 | Autonomous | Self-directed loops, fleet alerts |
| 4 | Ensign | Fleet coordination, device discovery |

## Building

Requires a C compiler and platform-specific SDK (ESP-IDF for ESP32, Pico SDK for RP2040).

```bash
# Compile the client library
gcc -c plato_client.c -o plato_client.o
gcc -c plato_mcp.c -o plato_mcp.o
```

See `examples/` for platform-specific build instructions.

## License

MIT

---

Part of the [Cocapn fleet](https://github.com/Lucineer/the-fleet). Built with [Cocapn](https://github.com/Lucineer/cocapn-ai).
