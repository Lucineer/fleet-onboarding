# Fleet Map — Current Agents and Capabilities

> Last updated: 2026-04-27

## Active Vessels

### JC1 (JetsonClaw1)
- **Role:** Hardware, edge GPU, low-level systems, fleet infrastructure
- **Platform:** Jetson Orin Nano 8GB, ARM64, 1024 CUDA cores, 2TB NVMe
- **Lighthouse:** Oracle1
- **Repos:** JetsonClaw1-vessel, gpu-native-room-inference, cuda-*, flux-*, plato-jetson
- **Specialty:** Real hardware benchmarks, CUDA, TensorRT, edge deployment

### Oracle1
- **Role:** Cloud runtime, PLATO server, fleet lighthouse
- **Platform:** VPS
- **PLATO Shell:** `http://147.224.38.131:8848`
- **Matrix Bridge:** `http://147.224.38.131:6168`
- **Repos:** SuperInstance/oracle1-vessel, plato-mythos, plato-kernel, plato-dcs, plato-unified-belief, plato-edge

### Forgemaster (FM)
- **Role:** Constraint theory specialist, proof builder, code migration
- **Platform:** Gaming GPU (RTX 4050)
- **Repos:** SuperInstance/forgemaster
- **Specialty:** Takes float code and forges it into exact geometric steel

### Zeroclaws
- **Role:** Bridge pattern fleet agents
- **Platform:** Cloud
- **Repos:** zeroclaws
- **Specialty:** Multi-agent collaboration via PLATO rooms

## Fleet Repos (Shared Infrastructure)

| Repo | Purpose |
|---|---|
| fleet-onboarding | This repo — boarding protocol for all agents |
| cocapn-architecture | Brand, pricing, business entity |
| purplepincher.org | Nonprofit umbrella |
| plato | PLATO system core |
| plato-mud | PLATO MUD server |
| plato-os | MUD-first edge OS |
| jetson-bootstrap | Jetson replication — clone to board another Jetson |

## Communication

| Channel | Use Case |
|---|---|
| Plato rooms | Primary workspace, tiles, knowledge |
| Matrix | Real-time fleet coordination |
| Bottles | Async durable messages |
| GitHub Issues | Technical coordination |
| Telegram | Casey ↔ agent direct line |
