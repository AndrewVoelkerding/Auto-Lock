# Retrofit IoT Smart Lock

A collaborative electromechanical engineering project to retrofit a standard deadbolt into a smart lock. The system integrates a custom 3D-printed gear train with a high-torque worm gear motor, triggered by an external piezo knock sensor and wireless (WiFi/Bluetooth) proximity connection. 

This repository houses the mechanical CAD, assembly documentation, and system architecture details. The logic and sensor integration were handled in collaboration with a Computer Engineering partner.

## Mechanical Architecture

The primary mechanical challenge was automating a deadbolt without eliminating the ability to lock and unlock the door manually from the outside. Because the system utilizes a high-torque DC worm gear motor (which cannot be easily backdriven), coupling the motor directly to the lock would render manual key operation impossible.

*   **Gear Train:** A custom 1:1 ratio gear train featuring two 21-tooth spur gears designed to standard involute profiles using *Machinery's Handbook*.
*   **Lost-Motion Mechanism:** The driven gear features a custom internal "butterfly" cutout. This acts as a 90-degree mechanical deadband. When the motor is stationary, the deadbolt tailpiece can still freely rotate 90 degrees inside the gear, allowing for unrestricted manual operation via a physical key.
*   **Actuation:** To automate the lock, the motor engages the gear train, rotating exactly 90 degrees in 2.5 seconds at 36°/sec to flip the deadbolt, before resetting.

## Hardware & Power Specifications

Component selection was highly integrated to balance motor torque requirements with the power budget of the external sensor suite.

*   **Motor:** JGY-370 DC Worm Gear Motor
    *   **Voltage/Current:** 12V, 0.5A (3W)
    *   **Speed:** 6 RPM
    *   **Stall Torque:** ~25 kg-cm
*   **Battery:** 2000 mAh 7.4V Li-ion (100g)
    *   **Endurance:** Capable of ~2,880 lock/unlock cycles (90° forward, 90° back) per charge, exclusive of the microcontroller's idle draw.

## CAD & Fabrication
All mechanical bracketry and gears were designed for additive manufacturing. 
*   **Software:** Siemens NX / Fusion 360
*   **Fabrication:** FDM 3D printed (Bambu Lab ecosystem) using structural thermoplastics to withstand the 25 kg-cm stall torque scenario.

## Future Development
*   Finalizing the external protective packaging and enclosure for the battery and PCB.
*   PCB routing for the piezo knock-sensor array and wireless transceiver.
