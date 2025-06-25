# Analog Simulation  
*ECLIPSE hardware truthfulness pillar implementation*  

## Overview  
Models analog behaviors beyond digital GPIO:  
- **Purpose**: Simulate real-world circuit characteristics (voltage drift, impedance, noise)  
- **Scope**:  
  - Sensor physics (e.g., thermistor nonlinearity)  
  - Signal conditioning (filters, amplifiers)  
  - Mixed-signal interactions (ADC/DAC quantization)  
  - Peripheral analog constraints (e.g., PWM ripple)  

## Key Components  
| Component               | Responsibility |  
|-------------------------|----------------|  
| `AnalogPinModel`        | Voltage/impedance simulation per pin |  
| `CircuitSolver`         | Real-time nodal analysis engine |  
| `SensorPhysicsEngine`   | Temperature/light/force domain models |  
| `NoiseGenerator`        | Johnson-Nyquist/Burst noise injection |  

## Simulation Models  
**Behavioral Modeling** (Primary approach):  
```python  
class TemperatureSensor:  
    def read_voltage(self) -> float:  
        # Steinhart-Hart equation for thermistors  
        return A + B*math.log(self.resistance) + C*(math.log(self.resistance)**3  
