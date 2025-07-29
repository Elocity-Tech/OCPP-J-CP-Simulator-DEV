# OCPP ChargerPoint Simulator

A comprehensive, multi-instance OCPP 1.6 charge point simulator with advanced features for testing and development of OCPP-compliant charging station management systems.

## Features

### 🚀 Multi-Instance Support
- **4 simultaneous simulator instances** - Test multiple charge points concurrently
- **Tabbed interface** - Easy switching between different simulator configurations
- **Independent state management** - Each instance maintains its own connection and transaction state

### 🔌 OCPP 1.6 Compliance
- **Full OCPP 1.6 protocol support** - Implements all major OCPP operations
- **WebSocket communication** - Real-time bidirectional communication with OCPP servers
- **JSON message format** - Standard OCPP message structure

### ⚡ Core Operations
- **BootNotification** - Charge point registration and initialization
- **Authorize** - RFID tag authorization
- **StartTransaction/StopTransaction** - Complete charging session lifecycle
- **Heartbeat** - Connection keep-alive mechanism
- **StatusNotification** - Real-time status updates
- **MeterValues** - Detailed charging metrics and telemetry

### 📊 Advanced Meter Values
- **Configurable parameters**:
  - Energy consumption (kWh)
  - State of Charge (SoC) percentage
  - Power consumption (W)
  - Current (A)
  - Sample intervals and message counts
- **Realistic data generation** - Progressive values that simulate actual charging sessions
- **Resume capability** - Continue meter value transmission after disconnection

### 🔄 Remote Operations Support
- **RemoteStartTransaction** - Server-initiated charging sessions
- **RemoteStopTransaction** - Server-initiated session termination
- **Reset** - Soft and hard reset capabilities
- **ChangeAvailability** - Dynamic connector availability management

### 🛠️ Configuration Management
- **GetConfiguration/ChangeConfiguration** - Dynamic parameter updates
- **SetChargingProfile** - Charging rate control
- **GetCompositeSchedule** - Charging schedule management

### 📋 Additional OCPP Features
- **DataTransfer** - Custom vendor-specific data exchange
- **TriggerMessage** - On-demand message requests
- **GetDiagnostics** - Diagnostic information retrieval
- **UpdateFirmware** - Firmware update simulation
- **Reservations** - ReserveNow and CancelReservation support
- **Local Authorization List** - GetLocalListVersion and SendLocalList

### 💾 State Persistence
- **LocalStorage integration** - Automatic state preservation across browser sessions
- **Transaction recovery** - Resume interrupted charging sessions
- **Meter value continuity** - Maintain progress across disconnections

### 🔄 Connection Management
- **Automatic reconnection** - Exponential backoff retry mechanism
- **Connection status indicators** - Visual feedback for connection states
- **Graceful disconnection** - Proper cleanup and state preservation

## Getting Started

### Prerequisites
- Modern web browser with WebSocket support
- OCPP 1.6 compliant server endpoint

### Configuration
1. **Endpoint URL**: Set your OCPP server WebSocket endpoint
   - Default: `wss://ocpp-dev.evnet.xyz/ocpp/`
2. **Charge Point ID**: Unique identifier for your simulator instance
   - Default: `SIM_1`, `SIM_2`, etc.
3. **Connector ID**: Physical connector identifier
   - Default: `1`
4. **Authorization Tag**: RFID tag for authorization
   - Default: `TAG_1`, `TAG_2`, etc.

### Basic Usage
1. **Connect**: Click "Connect" to establish WebSocket connection
2. **Authorize**: Send authorization request with configured ID tag
3. **Start Transaction**: Begin a charging session
4. **Start Meter Values**: Begin sending charging telemetry
5. **Stop Transaction**: End the charging session

### Advanced Configuration

#### Meter Values Settings
- **Number of Messages**: Total meter value messages to send (default: 60)
- **Sample Interval**: Time between meter value transmissions in seconds (default: 10)
- **Energy Range**: Min/Max energy consumption in kWh (default: 1-25 kWh)
- **SoC Range**: Min/Max state of charge percentage (default: 10-95%)
- **Power/Current**: Average power and current values (default: 7200W, 32A)

#### Status Management
- **Status Notifications**: Configure charge point status (Available, Charging, Finishing, etc.)
- **Error Codes**: Set error conditions for testing
- **Connector Management**: Handle multiple connector scenarios

## Interface Overview

### Main Controls
- **Connect/Disconnect**: WebSocket connection management
- **Authorize**: Send authorization requests
- **Start/Stop Transaction**: Session lifecycle control
- **Heartbeat**: Manual heartbeat transmission
- **Status Notification**: Send status updates
- **Data Transfer**: Custom data exchange

### Meter Value Controls
- **Start Meter Values**: Begin new meter value transmission
- **Resume Meter Values**: Continue from last known position

### Status Indicators
- 🔴 **Red**: Disconnected
- 🟡 **Yellow**: Connected/Idle
- 🟢 **Green**: Charging
- 🔵 **Blue**: Connecting

### Tabbed Interface
- **Settings**: Configuration parameters
- **Log**: Real-time message log
- **Transactions**: Active transaction management

## Technical Details

### Message Format
Uses standard OCPP 1.6 JSON message format:
```json
[messageTypeId, messageId, action, payload]
```

### Supported OCPP Operations

#### Charge Point to Central System
- BootNotification
- Authorize
- StartTransaction
- StopTransaction
- Heartbeat
- StatusNotification
- MeterValues
- DataTransfer

#### Central System to Charge Point
- RemoteStartTransaction
- RemoteStopTransaction
- Reset
- ChangeAvailability
- SetChargingProfile
- GetConfiguration
- ChangeConfiguration
- ClearCache
- DataTransfer
- GetLocalListVersion
- SendLocalList
- CancelReservation
- ReserveNow
- ClearChargingProfile
- GetCompositeSchedule
- TriggerMessage
- GetDiagnostics
- UpdateFirmware
- UnlockConnector

### Browser Compatibility
- Chrome/Chromium (recommended)
- Firefox
- Safari
- Edge

## Development and Testing

### Use Cases
- **OCPP Server Testing**: Validate server implementations
- **Load Testing**: Multiple concurrent charge points
- **Protocol Compliance**: Verify OCPP 1.6 adherence
- **Integration Testing**: End-to-end charging workflows
- **Development**: Rapid prototyping and debugging

### Customization
The simulator is built with vanilla JavaScript and can be easily modified for:
- Custom meter value algorithms
- Additional OCPP operations
- Enhanced UI features
- Integration with test automation

## Licensing
Licensed under Apache License 2.0

## Contributing
This simulator provides a solid foundation for OCPP testing and can be extended with additional features as needed for specific use cases.
