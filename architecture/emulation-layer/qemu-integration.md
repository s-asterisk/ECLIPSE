# QEMU Integration Strategy

## Core Requirements
- Dynamic recompilation for ARMv7/ARMv8/AVR
- Cycle-accurate timing
- Memory-mapped I/O passthrough

```c
// Proposed C++ interface
class QEMUBridge {
public:
    void loadFirmware(const std::vector<uint8_t>& firmware);
    void registerPeripheral(Peripheral* p, uint32_t base_addr);
    void setAnalogPinHandler(int pin, std::function<double(double)> handler);
};
