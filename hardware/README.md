## Hardware requirements (electronics)

1. The device shall provide WiFi connectivity
2. The device shall enable communication with MIFARE based NFC cards
  1. Reading UID at minimum
  2. Ideally allow for using secure authentication usign DESfire or similar cards
3. The device shall have an user friendly interface, this includes:
  1. A display well legible in sunlight
  2. A tactile input method operable without directly looking
  3. A sound feedback capability (speaker/buzzer)
4. The device shall run on a portable power source (battery)
5. The device shall provide configuration facilities for provisioning
6. The device shall be based around sufficiently powerful MCU to enable the use of HTTTPS


## Used components and protocols

- Main MCU - ESP32 based
  - WiFi enable by default (Requirement 1)
  - Powerful enough (Requirement 6)
  - Probably an WROOM-type module for ease of design
- NFC Frontend - PN512 (Requirement 2.*)
  - Cheap well documented solution
  - Already in KiCad (lazy me)
  - Antenna on PCB
  - SPI or I2C connected
- Input method
  - *EITHER* Generic matrix keypad module (Requirement 3.2)
    - Possibly with I2C I/O extender to save pins, preferably not
  - *OR* On PCB matrix keyboard with tactile buttons (Requirement 3.2)
    - Harder to design
    - Independent on what keyboard module can be sourced
- Output
  - Display
    - *EITHER* LCD display based on ST7920 or similar (Requirement 3.1)
      - Larger
      - Good legibility in sunlight
    - *OR* OLED based on SSH1106 (Requirement 3.1)
      - smol
      - Ok legibility in sunlight
      - Looks pretty
  - Passive onboard buzzer (Requirement 3.3)
- Power source 
  - *EITHER* Li-Ion battery 
    - Builtin charge circuit
  - *OR* External powerbank
  - *OR* 3xAA batteries, can be rechargable   
## References and links

### NFC Hardware

https://www.nxp.com/products/rfid-nfc/nfc-hf/nfc-readers/pn512-reader-board:PNEV512B - Scheamtics and PCB layout
