# Design Goals
- A tiny single-addressable strip controller
    - 12v or 5v variants, with either a single or dual data lines such as APA102, or WS2815
- Wireless Control
- Be powered from the same power rail as the LED controller

# Design Reasonings
- Using a switching regulator instead of an LDO
    - At 5v, there would be a 0.3-0.5W power drop across the regulator. A bit wasteful, no?
        - also needs a large heatsink
    - With the potential for a 12v, input, the power drop goes up to 1.7-2.6W. Toasty!
- ESP32 for MCU
    - cheap
    - common
    - wifi and ble built-in
    - WLED supports it already
    - need I say more?
- Barrel Jack and wire input
    - for convinience, so small LED runs can be powered with a single barrel jack without wiring that to the LED seperatly.
    - on the PCB, the width already exist due to the antenna and LED connector
- No mounting holes
    - Reduction in size: an M3 screw looks HUGE on the board
- lack of a 1000uF LED supply capacitor
    - size
    - a tht capacitor will consume both top and bottom space
